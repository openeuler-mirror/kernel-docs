#### 引言

linux io子系统主要包括了文件系统层、调度器层、通用块层、驱动层和设备层，数据从用户空间到最终到达磁盘经过了非常复杂的流程。本文主要介绍通过两个用户态工具：iostat和blktrace来分析io的性能，并且在遇到io性能相关的问题时在不熟悉相关内核实现的基础上能做到快速定界。

#### iostat

##### 简介

iostat 命令是 I/O statistics(输入/输出统计)的缩写，主要用于监控系统设备的 IO 负载情况。通过内核提供的sysfs接口读取磁盘io相关的信息，然后计算出相关的io性能指标给用户。

##### 内核打点

结构体stat_group和disk_stats，在io路径上内核会将相关信息存储到数据结构中：

```c
enum stat_group {
        STAT_READ,		-> 读
        STAT_WRITE,		-> 写
        STAT_DISCARD,	-> discard
        STAT_FLUSH,		-> flush

        NR_STAT_GROUPS
};
 
struct disk_stats {
         u64 nsecs[NR_STAT_GROUPS];					-> io延时
         unsigned long sectors[NR_STAT_GROUPS];		-> io大小
         unsigned long ios[NR_STAT_GROUPS];			-> io数量
         unsigned long merges[NR_STAT_GROUPS];		-> io合并数量
         unsigned long io_ticks;					-> 磁盘在处理io的时间
         local_t in_flight[2];						-> 未完成的io数量
 };
```

##### 内核sysfs接口，打印存储的信息

```c
ssize_t part_stat_show(struct device *dev,
                ┊      struct device_attribute *attr, char *buf)
{
        struct hd_struct *p = dev_to_part(dev);
        struct request_queue *q = part_to_disk(p)->queue;
        struct disk_stats stat;
        unsigned int inflight;

        part_stat_read_all(p, &stat);
        if (queue_is_mq(q))
                inflight = blk_mq_in_flight(q, p);
        else
                inflight = part_in_flight(p);

        return sprintf(buf,
                "%8lu %8lu %8llu %8u "
                "%8lu %8lu %8llu %8u "
                "%8u %8u %8u "
                "%8lu %8lu %8llu %8u "
                "%8lu %8u"
                "\n",
                stat.ios[STAT_READ],
                stat.merges[STAT_READ],
                (unsigned long long)stat.sectors[STAT_READ],
                (unsigned int)div_u64(stat.nsecs[STAT_READ], NSEC_PER_MSEC),
                stat.ios[STAT_WRITE],
                stat.merges[STAT_WRITE],
                (unsigned long long)stat.sectors[STAT_WRITE],
                (unsigned int)div_u64(stat.nsecs[STAT_WRITE], NSEC_PER_MSEC),
                inflight,
                jiffies_to_msecs(stat.io_ticks),
                (unsigned int)div_u64(stat.nsecs[STAT_READ] +
                                ┊     stat.nsecs[STAT_WRITE] +
                                ┊     stat.nsecs[STAT_DISCARD] +
                                ┊     stat.nsecs[STAT_FLUSH],
                                                NSEC_PER_MSEC),
                stat.ios[STAT_DISCARD],
                stat.merges[STAT_DISCARD],
                (unsigned long long)stat.sectors[STAT_DISCARD],
                (unsigned int)div_u64(stat.nsecs[STAT_DISCARD], NSEC_PER_MSEC),
                stat.ios[STAT_FLUSH],
                (unsigned int)div_u64(stat.nsecs[STAT_FLUSH], NSEC_PER_MSEC));
}
```

##### 每个设备(或者分区)一共打印17个字端

含义依次为

| 字段 | 含义                   | 内核统计接口                                        | iostat输出字段 | 含义                            |
| ---- | ---------------------- | --------------------------------------------------- | -------------- | ------------------------------- |
| 1    | 读io数量               | part_stat_inc(part, ios[STAT_READ])                 | r/s            | 每秒完成读请求数量              |
| 2    | 读io合并数量           | part_stat_inc(part, merges[STAT_READ])              | rrqm/s         | 读请求每秒合并次数              |
| 3    | 读io扇区数量           | part_stat_add(part, sectors[STAT_READ], sectors)    | rkB/s          | 每秒读的带宽                    |
| 4    | 读io花费时间总和       | part_stat_add(part, nsecs[STAT_READ], duration)     | r_await        | 读请求平均等待时间              |
| 5    | 写io数量               | part_stat_inc(part, ios[STAT_WRITE])                | w/s            | 每秒完成写请求数量              |
| 6    | 写io合并数量           | part_stat_inc(part, merges[STAT_WRITE])             | wrqm/s         | 写请求每秒合并次数              |
| 7    | 写io扇区数量           | part_stat_add(part, sectors[STAT_WRITE], sectors)   | wkB/s          | 每秒写的带宽                    |
| 8    | 写io花费时间总和       | part_stat_add(part, nsecs[STAT_WRITE], duration)    | w_await        | 写请求平均等待时间              |
| 9    | 当前的inflight io数量  | blk_mq_in_flight                                    |                |                                 |
| 10   | 设备在处理io的时间     | update_io_ticks                                     | %util          | 磁盘利用率                      |
| 11   | 所有io花费的时间总和   | 4, 8, 15, 17总和                                    | aqu-sz         | 平均队列长度                    |
| 12   | discard io数量         | part_stat_inc(part, ios[STAT_DISCARD])              | d/s            | 每秒完成discard请求数量         |
| 13   | discard io合并数量     | part_stat_inc(part, merges[STAT_DISCARD])           | drqm/s         | discard请求每秒合并次数         |
| 14   | discard io扇区数量     | part_stat_add(part, sectors[STAT_DISCARD], sectors) | dkB/s          | 每秒discard的带宽               |
| 15   | discard io花费时间总和 | part_stat_add(part, nsecs[STAT_DISCARD], duration)  | d_await        | discard请求平均等待时间         |
| 16   | flush io数量           | part_stat_inc(part, ios[STAT_FLUSH])                | f/s            | 每秒完成flush请求数量           |
| 17   | flush io花费时间总和   | part_stat_add(part, nsecs[STAT_FLUSH], duration)    | f_await        | flush请求平均等待时间段，-x参数 |

#### blktrace

##### 简介

当发生io性能问题时，iostat因为只能提供整体的信息(io从开始到结束)，用于问题的定位是远远不够的。而blktrace则可以跟踪每个io在路径中每一个阶段的具体信息，可以很方便的分析出问题出在io子系统中的哪一层。

blktrace的实现依赖于内核的tracepoint机制，在io路径的关键位置上插入了钩子函数用于打印出关键的信息。

##### 流程

1. fd = open(“/dev/xxx”,O_RDONLY|O_NONBLOCK)

   打开块设备

2. ioctl(fd, BLKTRACESETUP, …)

   在内核调用blk_trace_setup()去注册tracepoint

3. ioctl(fd, BLKTRACESTART)

   标记开始

4. ioctl(fd, BLKTRACESTOP)

   标记结束，同一个设备无法并发

5. 利用ftrace的debugfs接口获取信息

   /sys/kernel/debug/block/xxx/tracexx (每个cpu都有一个文件)

6. ioctl(fd, BLKTRACETEARDOWN)

   在内核调用blk_trace_remove()去删除注册的tracepoint

##### 记录信息接口

blk_add_trace_bio：通过内核tracepoint, 将相关数据存储在buffer中

- 参数：request_queue, bio, action, error

- 数据的获取：

  -> 根据参数action获取在io路径中的位置
  -> 根据bio->bi_opf获取io的类型
  -> 根据rq->\_\_sector获取io的偏移量
  -> 根据rq->\_\_data_len获取io的大小
  -> 根据q->bt->dev 获取主次设备号
  -> 从current获取进程号和cpu

##### 通过debugfs获取记录的信息

注册trace_event后，用户可以通过debugfs接口获取信息(内核通过kernel/trace/blktrace.c 中的 print_one_line()接口将buffer中存储的信息打印给用户）

##### io 路径

| action | 含义          | tracepoint              |
| ------ | ------------- | ----------------------- |
| Q      | 开始新的io    | trace_block_bio_queue   |
| G      | io生成request | trace_block_getrq       |
| I      | io到达调度器  | trace_block_rq_insert   |
| D      | io下发到驱动  | trace_block_rq_issue    |
| C      | io完成        | trace_block_rq_complete |
| P      | io plug       | trace_block_plug        |
| U      | io unplup     | trace_block_unplug      |
| F      | io前向合并    | block_bio_backmerge     |
| M      | io后向合并    | block_bio_frontmerge    |
| X      | io拆分        | trace_block_split       |
| R      | io requeue    | trace_block_rq_requeue  |

一般io都会经过Q->G->I->D->C 这几个关键的阶段

##### io类型

- R 读
- W 写
- S 同步io
- D discard
- M 元数据
- F flush, 刷磁盘缓存
- U force unit access(fua), 数据要跳过缓存裸盘

##### blkprase

blktrace输出的数据不利于用户的阅读，因此需要blkprase对blktrace输出的数据进行解析

默认输出格式是 %D %2c %8s %5T.%9t %5p %2a %3d

- %D 主次设备号
- %2c CPU
- %8s 序列号
- %5T.%9t 时间戳
- %5p 进程号
- %2a actions，代表在io路径中的位置
- %3d io类型
- io 开始位置 + io大小 + 进程名

#### 实例1 大内存页同步下io

内核版本：主线内核，v5.15

测试环境：64k page size

文件系统：xfs

测试参数：dd if=/dev/zero of=/mnt/test bs=4k count=1024 oflag=sync

存在问题：性能远小于4k page size场景  

##### 测试结果

- dd打印： 4194304 bytes (4.2 MB, 4.0 MiB) copied, 15.991 s, 262 kB/s

- iostat数据

  | w/s    | wMB/s | wrqm/s | %wrqm | w_await | aqu-sz | wareq-sz | %util  |
  | ------ | ----- | ------ | ----- | ------- | ------ | -------- | ------ |
  | 180.00 | 2.0   | 51.00  | 22.08 | 5.57    | 1.50   | 10.97    | 100.00 |

  - w/s 较高是因为sync操作会有元数据写/日志写
  - 写带宽达到了2MB/s，远高于dd的数据262kB/s

- blktrace数据

  根据action C过滤后的结果，截取一段：

  ```shell
   8,48  18      125     0.273247960  1150 C WS 2105616 + 8 [0]
   8,48  18      132     0.290411700  1150 C WS 2105616 + 16 [0] 
   8,48  18      139     0.307578160  1150 C WS 2105616 + 24 [0] 
   8,48  18      146     0.324731900  1150 C WS 2105616 + 32 [0] 
   8,48  18      153     0.341879060  1150 C WS 2105616 + 40 [0] 
   8,48  18      160     0.359044200  1150 C WS 2105616 + 48 [0] 
   8,48  18      167     0.376196200  1150 C WS 2105616 + 56 [0] 
   8,48  18      174     0.393358220  1150 C WS 2105616 + 64 [0] 
   8,48  18      181     0.410508000  1150 C WS 2105616 + 72 [0] 
   8,48  18      188     0.427665960  1150 C WS 2105616 + 80 [0] 
   8,48  18      195     0.444819860  1150 C WS 2105616 + 88 [0] 
   8,48  18      202     0.461983320  1150 C WS 2105616 + 96 [0] 
   8,48  18      209     0.479134400  1150 C WS 2105616 + 104 [0] 
   8,48  18      216     0.496282220  1150 C WS 2105616 + 112 [0] 
   8,48  18      223     0.513446780  1150 C WS 2105616 + 120 [0]
   8,48  18      230     0.530594240  1150 C WS 2105616 + 128 [0]
  ```

  - io大小依次为 4k, 8k, ..., 64k
  - 异常点：用户下4k大小io，但是内核处理的io大小要大于4k
  - 定界到文件系统层：用户态->文件系统->通用块层(有问题)

- 问题的跟因是xfs文件系统不支持subpage，在buffer io时即使只改了一个字节，也会将整个page置脏，导致写脏页的时候会把整个page落盘(64k)

#### 实例2 bfq并发同步io

内核版本：主线内核，v5.15

测试环境：任意支持bfq调度器的环境(CONFIG_IOSCHED_BFQ)，并且开启基于bfq的io管控(CONFIG_BFQ_GROUP_IOSCHED)

调度器：bfq

测试方式：绑定进程到不同的 cgroup下，并发下同步io

存在问题：性能很差，与单进程性能持平

fio测试参数：每个进程

```shell
[global]
filename=/dev/sdd
ioengine=psync
bs=4k
direct=1
numjobs=1
size=1g

[test]
rw=randwrite
```

##### 测试结果

- fio结果

  | 进程数量 | iops 每个进程 | iops 总共 |
  | -------- | ------------- | --------- |
  | 1        | 14k           | 14k       |
  | 2        | 7k            | 14k       |
  | 4        | 3.5k          | 14k       |

  - 随着进程数量提高，总体iops维持不变

- iostat数据

  | 进程数量 | w/s      | wMB/s | wrqm/s | %wrqm | w_await | aqu-sz | wareq-sz | %util  |
  | -------- | -------- | ----- | ------ | ----- | ------- | ------ | -------- | ------ |
  | 1        | 15544.00 | 60.72 | 0.00   | 0.00  | 0.05    | 1.50   | 8.00     | 100.00 |
  | 2        | 14976.00 | 58.50 | 0.00   | 0.00  | 0.12    | 1.81   | 8.00     | 100.00 |
  | 4        | 15611.00 | 60.98 | 0.00   | 0.00  | 0.24    | 3.79   | 8.00     | 100.00 |

  - 随着进程数量提高，io平均等待时间和平均队列长度提高

- blktrace数据：io无法并发

  ```shell
   8,0    5       99     0.001550075  1605 Q WS 992656 + 8 [fio]
   8,0    5      100     0.001551290  1605 G WS 992656 + 8 [fio] 
   8,0    5      101     0.001551425  1605 P  N [fio] 
   8,0    5      102     0.001551627  1605 UT N [fio] 1 
   8,0    5      103     0.001552049  1605 I WS 992656 + 8 [fio] 
   8,0    5      104     0.001559766   427 D WS 992656 + 8 [kworker/5:1H] 
   8,0    5      105     0.001601695     0 C WS 992656 + 8 [0] 
   8,0    5      106     0.001612254  1605 Q WS 992664 + 8 [fio] 
   8,0    5      107     0.001613409  1605 G WS 992664 + 8 [fio] 
   8,0    5      108     0.001613545  1605 P  N [fio] 
   8,0    5      109     0.001613747  1605 UT N [fio] 1 
   8,0    5      110     0.001614143  1605 I WS 992664 + 8 [fio] 
   8,0    5      111     0.001622087   427 D WS 992664 + 8 [kworker/5:1H] 
   8,0    5      112     0.001662681     0 C WS 992664 + 8 [0] 
   8,0    5      113     0.001673206  1605 Q WS 992672 + 8 [fio] 
   8,0    5      114     0.001674380  1605 G WS 992672 + 8 [fio] 
   8,0    5      115     0.001674517  1605 P  N [fio] 
   8,0    5      116     0.001674733  1605 UT N [fio] 1 
   8,0    5      117     0.001675175  1605 I WS 992672 + 8 [fio] 
   8,0    5      118     0.001682875   427 D WS 992672 + 8 [kworker/5:1H] 
   8,0    5      119     0.001725369     0 C WS 992672 + 8 [0] 
  ```

  - 每个io的D->C依次完成，不存在有多个io在D2C阶段，也就是说同一时间只有一个io落盘

- blktrace数据：D2C延时

  ```shell
  Write latency
  cnt 80406 sum 3718.9ms mean 0.0ms min 0.0ms max 6.2ms
  >=(ms) .. <(ms)   : count    ratio    |distribution                            |
       0 .. 1       : 80405    100.0%   |########################################|
       1 .. 2       : 0        0.0%     |                                        |
       2 .. 4       : 0        0.0%     |                                        |
       4 .. 8       : 1        0.0%     |#                                       | 
  ```

  - 平均延时0.046ms

- blktrace数据：I2C延时

  ```shell
  Write latency
  cnt 80403 sum 20624.8ms mean 0.3ms min 0.0ms max 500.1ms
  >=(ms) .. <(ms)   : count     ratio |distribution                            |
       0 .. 1       : 80358     99.9% |########################################|
       1 .. 2       : 0          0.0% |                                        |
       2 .. 4       : 0          0.0% |                                        |
       4 .. 8       : 1          0.0% |#                                       |
       8 .. 16      : 0          0.0% |                                        |
      16 .. 32      : 0          0.0% |                                        |
      32 .. 64      : 0          0.0% |                                        |
      64 .. 128     : 0          0.0% |                                        |
     128 .. 256     : 3          0.0% |#                                       |
     256 .. 512     : 41         0.1% |#                                       | 
  ```

  - 平均延时0.3ms，远高于D2C的延时，因此io主要卡在调度器里
  - 因此问题可以定界到调度器层

- 问题的跟因是bfq调度器为了保证io相对管控的效果，不支持并发的同步io

#### 关注点总结

- io大小：buffer io时关注是否一致 (实例1)
- io延时: Q->G->I->D->C 各个阶段的延时情况 (实例2)
- io并发程度：同时处在D2C阶段的io数量，实例(2)
- io偏移量：机械盘需要关注
- io是否有合并：性能劣化可能是由于合并少导致的
- io是否拆分：io拆分后应该是顺序的io，关注完成顺序是否一致
- io类型：数据/元数据/日志，同步/异步，flush