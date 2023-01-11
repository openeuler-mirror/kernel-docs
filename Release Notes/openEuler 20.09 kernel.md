```
很高兴 openEuler 20.09 kernel 如期而至，该版本包含众多特性，欢迎通过 openEuler
版本来体验。

openEuler-20.09 kernel tree 位于:
	git@gitee.com:openeuler/kernel.git openEuler-20.09

openEuler kernel 项目位于:
	https://gitee.com/openeuler/kernel

openEuler 20.09 kernel 依然基于社区的 Linux 4.19 LTS 内核，在 openEuler 1.0 LTS
基础上往前演进(跟踪到 4.19.140)，在这大概6个月的时间内，合入并使能了多个特性,
下面从架构支持，驱动支持，以及内核特性支持等几个方面来进行介绍。

1 架构支持

1.1 支持海光CPU-Hygon Dhyana

  海光的Peng Wu向openEuler贡献了Hygon CPU的支持补丁集，通过这个补丁集，新增了
  Hygon CPU 的ACPI, cpufreq，perf，KVM，NTB以及Hygon CPU的识别等支持，通过这
  个补丁集，openEuler完整支持海光x86 CPU。

1.2 支持昇腾芯片

  包括CPU和AI CPU共享虚拟地址的SVM（shared virtual memory）特性，以及芯片的硬件
  支持。

1.3 支持鲲鹏PC平台

  鲲鹏PC CPU基于鲲鹏920,8核。20.09 版本内核加入了对PC的休眠支持（架构特性），
  以及I2C控制器等支持。

1.4 支持 ARM v8.x 特性

  - ARMv8.0 CRC32 instructions
  - ARMv8.0-SB Control of speculation
  - Armv8.2 Cache clean to Point of Deep Persistence
  - ARMv8.2-TTCNP, Translation table Common not private translations
  - ARMv8.4-TLBI, TLB maintenance and TLB range instructions
  - Armv8.5-RNG, Random number generator
  - Armv8.5-BTI, Branch target identification
  - Armv8.5-E0PD, Preventing EL0 access to halves of address map
  - ARMv8.6 Data gathering hint
  - ARMv8.6 Matrix multiply extension

1.5 支持 risc-v

  支持 risc-v kvm. (openEuler 20.09 通过 kernel 5.5 来支持 risc-v)

  kernel tree 位于：
  git@gitee.com:openeuler/kernel.git kernel-5.5

2. 新介质以及新驱动支持

2.1 ARM64支持 persistence memory

  ARMv8.2引入新的指令支持 persistent memory，鲲鹏920处理器完整支持该特性，通过
  打开内核的 ACPI NFIT以及libnvdimm的配置文件，就能在鲲鹏上完美支持NVDIMM介质
  内存。

2.2 1822 网卡驱动增强

  - 1822网卡支持x86架构
  - 1822网卡支持128队列

2.3 3408/3416 RAID卡规避

  3408iMR/3416iMRraid卡在ARM64平台上（ARM64生态问题）使用存在问题，开启SMMU后，
  会存在不兼容，通过SMMU 设备bypass特性，规避不兼容问题。

2.4 Huawei iBMA 驱动

  iBMA 驱动是一组 BMC 与带内系统通信的驱动，系统宕机时，能辅助保存宕机时的运行
  状态信息，帮助定位故障原因。

2.5 hns3: update hns3 version to 1.9.38.8
2.6 TIPC: enable TIPC module by default

3. 存储/IO特性支持

3.1 bcache稳定性提升

 bcache Maintainer Coly回合了大量bcache的bugfix以及特性，大幅提升bcache稳定性
 和可用性

4. 性能优化特性

4.1 sched Task Steal

  回合社区的Task Steal特性，通过提升CPU利用率，替身MySQL数据库mix场景的性能10%+；

4.2 REFCOUNT_FULL以及CMPXCHG_LOOP()优化

  通过atomic_fetch_*操作来降低cmpxchg()带来的性能开销，从而提升refcount机制性能，
  带来文件读写等场景的性能提升，在ARM64服务器上尤其明显，空文件读写的benchmark 20+提升。

4.3 Linux's vmalloc Seeing "Large Performance Benefits"

  优化 vmalloc 性能，内核针对vmalloc区的查找做了优化，从O(N)到~O(log(N) 。
  See: https://www.phoronix.com/scan.php?page=news_item&px=Linux-5.2-vmalloc-Performance

4.4 MPAM特性增强

  支持通过ACPI获取系统MPAM资源；

4.5 percpu refcount for pagecache

  pagecache的生命周期管理是通过refcount来管理的，在多核并发压力下，读取文件cache
  的atomic操作成为瓶颈，因此引入percpu refcount mechanism来提升性能，针对nginx
  http测试，性能有1倍+的提升

4.6 ARM64 clear_page()性能优化

  通过‘stnp’代替'dc zva'指令，提升clear_page()的性能，在鲲鹏920上，针对hugetlb
  测试，有53%的性能提升。

4.7 调度，优化关键进程的抢占时延，提升响应速度

  对 SCHED_IDLE 策略的优化，之前选核的时候只选择 idle 的CPU，现在是如果那个CPU
  上运行的是 SCHED_IDLE 的进程，也可以选择到，由于运行SCHED_IDLE进程的CPU并不是
  idle，没有唤醒时延，能提升响应速度。

5. 安全特性

5.1 支持AppArmor

  AppArmor相比Selinux使用起来简单，但之前版本未开启AppArmor支持。20.09版本支持
  AppArmor，但默认的安全策略依然是Selinux，需要在启动参数传入security=apparmor使能

5.2 IMA摘要列表增强

  相比内核社区原生 IMA 机制，IMA 摘要列表扩展从安全性、性能、易用性三个方面进行
  了改良，助力完整性保护机制在生产场景下落地，并具有三大优势：

  极致安全

  原生 IMA 机制要求在现网环境下预先生成并标记文件扩展属性，访问文件时将文件扩展属
  性作为参考值，信任链不完整。摘要列表扩展将文件参考摘要值保存在内核空间中，构建阶
  段通过摘要列表的形式携带在发布的 rpm 包中，安装 rpm 包的同时导入摘要列表并执行
  验签，确保了参考值来自于软件发行商，实现了完整的信任链。

  惊艳的性能表现

  IMA 度量场景下，摘要列表扩展在确保安全性的前提下，减少了不必要的 PCR 扩展操作，
  开启度量时性能损失小于 5%，相比原生 IMA 度量性能提升高达 50%。IMA 评估场景下，
  摘要列表扩展将签名验证统一移动到启动阶段进行，避免每次访问文件时都执行验签，
  相比原生 IMA 评估场景提升运行阶段文件访问的性能约 20%。

  快速部署，平滑升级

  原生 IMA 机制在初次部署或每次更新软件包时，需要切换到 ﬁx 模式手动标记文件扩展
  属性后再重启进入 enforce 模式，才能正常访问安装的程序。 摘要列表扩展可实现安
  装完成后开箱即用，且允许直接在enforce 模式下安装或升级 rpm 包，无需重启和手动
  标记即可使用，实现了用户感知最小化，适合现网环境下快速批量部署。

6. 功耗特性

6.1 支持 CPU idle TEO governor

  TEO 是新引入的CPU调频算法，更适合 tickless 系统，可以为CPU选择更合适的节能状态。

7 调测特性

7.1 support livepatch without ftrace

8. 虚拟化特性

8.1 支持双层调度

  双层调度就是让Hypervisor的调度器感知到VM的VCPU上跑什么应用。让VM的调度器感知到
  Hypervisor 层物理CPU压力。两层调度感知，整机达到最好的业务性能。

8.2 支持 PMU nmi watchdog

8.3 支持 SmartPolling （guest idle poll)

  ARM 平台上 cpu idle 支持 smart polling，用来提升性能。

8.4 支持 vmtop, 用于虚拟机性能指标监测
8.5 支持ARM架构PV qspinlock功能，提升vcpu的自旋锁等锁性能

---
openEuler Kernel SIG
```