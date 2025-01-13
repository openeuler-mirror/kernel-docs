
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2022/12/30 Kernel SIG 双周例会】
会议时间：2022年12月30日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/83523573625?pwd=Z0QvZU5la2I5emh5NzRlemkwT1krZz09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（10min）  --- 郑增凯
明年kernel发布计划：在release sig中将会详细叙述

议题二：openEuler 23.03 创新版本拟选择 6.1 内核讨论 ---谢秀奇
openEuler 23.03 创新版本拟选择 6.1 内核
 
创新版本承担了新技术验证，以及为稳定版本做技术准备的使命。openEuler 22.03 LTS 系列
使用 5.10 内核，SP1 版本发布在即，5.10 内核在创新版本上的使命已基本完成，是时候
在 23.03 创新升级新的内核版本了。
 
6.1 内核是上游社区的最新版本，因此拟选择 6.1 内核，作为 23.03 创新版本的内核。
 
6.1 内核在 23.03 的基本目标：
 
 - 至少支持 ARM64 与 x86 架构
 - 验证&适配新内核与基础包的兼容性
 - 消除阻塞版本正常运行的阻塞性问题
 
社区开发协作上的改进目标：
 - 联合 QA SIG 和基础设施 SIG，支持内核的 PR 级测试
 - 联合基础设施 SIG 支持 PR 通知到具体 Committer，支持 PR Review 提醒
 - PR 构建 & 版本构建时长优化
 - 探索 Committer & Maintainer 高效协作的机制

三、本期遗留问题
1、

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2022/12/16 Kernel SIG 双周例会】
会议时间：2022年12月16日 14:00-15:30
轮值主持：郑增凯
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/83523573625?pwd=Z0QvZU5la2I5emh5NzRlemkwT1krZz09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（10min）  --- 郑增凯
近两周(2022.12.5 ~ 12.16)内进展同步：
    总体上
    OLK-5.10主干更新tag 至5.10.0-138.0.0 
    openEuler-22.03-LTS维护分支更新tag至5.10.0-60.72.0， 对应rpm包下载地址：https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支已从OLK-5.10 的tag 5.10.0-136.0.0拉取，目前RC4已发，获取链接： http://121.36.84.172/dailybuild/EBS-openEuler-22.03-LTS-SP1/rc4_openeuler-2022-12-15-16-22-57/ ，最新tag： 5.10.0-136.4.0

        以OLK-5.10主为例：
    从5.10.0-132.0.0 更新至5.10.0-138.0.0，回合补丁数304个
    git log 5.10.0-127.0.0..5.10.0-132.0.0 --oneline | wc -l
    304

        其中：
    CVE: 3个
        CVE-2022-4129
        CVE-2022-4139
        CVE-2022-45934
        
        同步linux 5.10.y 社区LTS补丁集 2 个：5.10.139， 5.10.140
        
        OLK-5.10合入PR: 
        Intel SPR:
        intel: backport Sapphire Rapids PMT errata fix https://gitee.com/openeuler/kernel/pulls/311
        intel: backport fix for SPR c1 and c1e independent support for intel_idle https://gitee.com/openeuler/kernel/pulls/312
        SPR: support Intel In Field Scan(IFS) https://gitee.com/openeuler/kernel/pulls/316
        
        AMD:
        AMD: Fix allmodconfig build issue in amd perf uncore module. https://gitee.com/openeuler/kernel/pulls/317
        
        sw64:
        update patches for sw64 architecture https://gitee.com/openeuler/kernel/pulls/304
        
        net-swift:
        txgbe : fix arm32 compiler error warning in txgbe_main.c https://gitee.com/openeuler/kernel/pulls/301
        [5.10] [Feature] :add netswift WX1860 series NIC ngbe module support https://gitee.com/openeuler/kernel/pulls/281
        txgbe : merge net-swift txgbe out_of_tree module v1.2.3 to openEuler/txgbe for some known bugs https://gitee.com/openeuler/kernel/pulls/232
        
        Hisilicon:
        config: support hns3 pmu https://gitee.com/openeuler/kernel/pulls/310
        arch: mach: add support for 16dv300 series soc. https://gitee.com/openeuler/kernel/pulls/307
        net: hns3: Some bugfix about rx packet,rx copybreak and phy link ksettings for the HNS3. https://gitee.com/openeuler/kernel/pulls/318
        net: hns3: fix the HCLGE_OPC_WOL_CFG opcode id for wol and fix the incorrect way to obtain parameters. https://gitee.com/openeuler/kernel/pulls/321
    clk： 16dv300： add GPL license info for 16dv300 module.  https://gitee.com/openeuler/kernel/pulls/324
        
        Virtualization:
        vdpa: Add the vdpa device management mechanism and optimize the iotlb https://gitee.com/openeuler/kernel/pulls/309
        
        Misc:
        tc-testing: fix a bug in gitignore of tc-testing https://gitee.com/openeuler/kernel/pulls/306
        defconfig: add helper script for update openeuler_defconfig https://gitee.com/openeuler/kernel/pulls/286
        openEuler: add openEuler/MAINTAINERS for Maintainers & Committers https://gitee.com/openeuler/kernel/pulls/293
        config: disable CONFIG_QOS_SCHED_SMT_EXPELLER https://gitee.com/openeuler/kernel/pulls/314


议题二：

三、本期遗留问题
1、

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2022/12/02 Kernel SIG 双周例会】
会议时间：2022年12月02日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/88119872664?pwd=V1V3eFBJeVBPZ25RbExvWGthZXJWUT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（10min）  --- 郑增凯


议题二：zswap不开启时的占用内存优化  --- 刘世鑫
4.19->5.10，内核占用内存底噪增加
问题点：zswap特性会在内核启动时进行初始化，并申请一部分内存，尽管zswap未开启或未使用，仍会空占内存
解决办法：把zswap的初始化流程延后；在通过接口第一次打开zswap时，再将其初始化，可在zsawp未启动时，节省18M内存
基于5.10开发，并已经往linux kernel社区提交；

议题三： kernel sig committer 推选
麒麟软件 郭东太
统信 苟浩
会议选举通过郭工和苟工担任openEuler kernel sig committer

议题四：openEuler Summit议题收集
https://mp.weixin.qq.com/s/4AOJcKeRu0nTrG73QFXNgg

三、本期遗留问题
1、

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2022/11/18 Kernel SIG 双周例会】
会议时间：2022年11月18日 14:00-15:30
轮值主持：郑增凯
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/87237435945?pwd=OGJBQS9OYnNuNEpHRmZLZ2ptcENZUT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
1、NVME盘符漂移 --- 段廷银  15：00
新版的没这个问题，麒麟那边反馈从4.19.90-25.13.v2101 开始 nvme_core.multipath 默认禁用了。
禁用nvme_core.multipath 或者用 主线5.4 那个patch都没有问题，具体原因还在分析。

二、议题列表

议题一：ksmbd：introduce new SMB3 kernel server ---严爱杰
smbd->ksmbd：把用户态的smbd服务挪到内核态，以提升性能
介绍了ksmbd的基本架构
与现有samba的架构对比：samba是基于SMB1用户态的SMB服务端，而ksmbd是基于SMB3内核态SMB服务端
展示了相应的性能数据：单线程和多线程读写均有30%左右的性能提升，文件操作在某些情况下可达到90%和100%的提升，并在Windows客户端上进行了测试

议题二：进展update（10min）  --- 郑增凯
近两周(2022.11.7 ~ 11.18)内进展同步：
    总体上
    OLK-5.10主干更新tag 至5.10.0-127.0.0 
    openEuler-22.03-LTS维护分支更新tag至5.10.0-60.67.0， 对应rpm包下载地址：https://repo.openeuler.org/openEuler-22.03-LTS/update/
    src-openeuler构建仓openEuler-22.03-LTS-SP1已拉分支

    以OLK-5.10主干为例：
    从5.10.0-125.0.0 更新至5.10.0-127.0.0，回合补丁数986个
    git log 5.10.0-125.0.0..5.10.0-127.0.0 --oneline | wc -l
    986
        其中：
    CVE: 13个
        CVE-2022-2978
        CVE-2022-3523
        CVE-2022-3535
        CVE-2022-3536
        CVE-2022-3542
        CVE-2022-3546
        CVE-2022-3621
        CVE-2022-3623
        CVE-2022-3628
        CVE-2022-3629
        CVE-2022-40768
        CVE-2022-42432
        CVE-2022-43750

    同步linux 5.10.y 社区LTS补丁集 5 个：5.10.133 - 5.10.137
    
        OLK-5.10合入PR: 21个
        https://gitee.com/openeuler/kernel/pulls/207 [5.10] [bugfix] : merge net-swift txgbe out_of_tree module v1.2.3 to openEuler/txgbe for some known bugs
        https://gitee.com/openeuler/kernel/pulls/165 ascend agent smmu: an implementation of ARM SMMUv3 ATOS feature
        https://gitee.com/openeuler/kernel/pulls/224 ROH: Support hns roh device init and adapt roh mac type
        https://gitee.com/openeuler/kernel/pulls/219 【OLK-5.10】RDMA/hns: Support for bonding
        https://gitee.com/openeuler/kernel/pulls/190 sharepool: Update patches from hulk
        https://gitee.com/openeuler/kernel/pulls/128 [OLK-5.10] Add Zhaoxin rng driver
        https://gitee.com/openeuler/kernel/pulls/168 SPR: Add vfio_group_iommu_domain interface to support DLB
        https://gitee.com/openeuler/kernel/pulls/176 bugfix: Limit "Dummy wait" workaround to old Intel systems in acpi idle driver
        https://gitee.com/openeuler/kernel/pulls/175 AMD: Add minimum support for AMD EPYC Genoa platform
        https://gitee.com/openeuler/kernel/pulls/195 kernel: add OPENEULER_VERSION_CODE to version.h
        https://gitee.com/openeuler/kernel/pulls/196 openEuler-22.03-LTS: kernel: add OPENEULER_VERSION_CODE to version.h
        https://gitee.com/openeuler/kernel/pulls/199 bugfix: Limit "Dummy wait" workaround to old Intel systems in acpi idle driver
        https://gitee.com/openeuler/kernel/pulls/230 Intel SPR: Add Sapphire Rapids server intel-uncore-freq support for OLK-5.10
        https://gitee.com/openeuler/kernel/pulls/226 Intel SPR: Adding core PMU support for OLK-5.10
        https://gitee.com/openeuler/kernel/pulls/217 AMD: Support HSMP feature for AMD EPYC platforms
        https://gitee.com/openeuler/kernel/pulls/231 ROH: Support ROH basic functions and adapt ROH mode for RDMA/hns driver
        https://gitee.com/openeuler/kernel/pulls/200 x86: support MWAIT C1 as the default idle state
        https://gitee.com/openeuler/kernel/pulls/235 Introduce memory reliable
        https://gitee.com/openeuler/kernel/pulls/228 Intel SPR: Fix watchdog blocking reboot issue on ACPI WDAT watchdog enabled system for OLK-5.10
        https://gitee.com/openeuler/kernel/pulls/253 [5.10] [bugfix] : fix arm32 compiler error ERROR and warning
        https://gitee.com/openeuler/kernel/pulls/233 dma-mapping: provide a benchmark for streaming DMA mapping

议题三：可编程调度框架的方案和开发指南（20min） ---陈辉
可编程调度是openEuler可编程内核的一部分，openEuler可编程内核主要包含了可编程调度、可编程网络、安全、可观测性等内容
背景：不同场景下，所需要的调度策略不同，比如在ICT场景下需要低时延，而在终端场景需要性能和功耗均衡，在云场景下需要高资源利用率和隔离，在IOT场景下需要低底噪等
如果在内核态写一系列的调度策略，会导致一系列问题，导致人力成本增加，内核态架构腐化
本质问题：用户态和内核态是隔离的
解决办法：打通用户态和内核态的调度的语义鸿沟，把用户态的业务模型和业务目标传递至内核态，使可根据用户态的需求给出精准的调度资源共享，并打通内核态中不同模块的信息传递渠道
具体做法：基于Roman's基础调度框架做了一系列拓展，主要包括：关键资源标签化管理机制、可拓展点和辅助方法、lib库
并以具体场景进行了举例

议题四：推举Intel 施爱春 为openEuler kernel SIG committer
结论： 同意施爱春担任openEuler kernel sig committer

三、本期遗留问题
1、

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2022/11/04 Kernel SIG 双周例会】
会议时间：2022年11月04日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/87646118604?pwd=Q3doR3VOQW4zRm51QjZHZzBJcldYUT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
1、无
https://gitee.com/openeuler/kernel/commit/1e83e42b007c725259d1442b86996727fde2d87f
https://gitee.com/openeuler/kernel/commit/7d574b4c65c79a2243673262b7485831fd72bf90

二、议题列表
议题一：进展update（10min）  --- 郑增凯
近两周内进展同步：
     总体上
    OLK-5.10主干更新tag 至5.10.0-125.0.0 
    openEuler-22.03-LTS维护分支更新tag至5.10.0-60.65.0， 对应rpm包下载地址：https://repo.openeuler.org/openEuler-22.03-LTS/update/
    openEuler-22.03-LTS-SP1分支暂未拉出， 计划11月15日拉取，当前仍基于OLK-5.10主干开发

    以OLK-5.10主干为例：
    从5.10.0-119.0.0 更新至5.10.0-125.0.0，回合补丁数850个
    
    git log 5.10.0-119.0.0..5.10.0-125.0.0 --oneline | wc -l

        850

    CVE: 12 + 28 = 40个

        CVE-2022-42719/CVE-2022-41674/CVE-2022-42720/CVE-2022-42703/CVE-2022-3435/CVE-2022-20422/

        CVE-2022-20421/CVE-2022-41850/CVE-2022-41849/CVE-2022-3303/CVE-2022-2663/CVE-2022-1184

        CVE-2022-3577/CVE-2022-3649/CVE-2022-3633/CVE-2022-3594/CVE-2022-2602/CVE-2022-3586/CVE-2022-3566/

        CVE-2022-3567/CVE-2022-3565/CVE-2022-3564/CVE-2022-3545/CVE-2022-3534/CVE-2022-3521/CVE-2022-3524/CVE-2022-42722CVE-2022-20409


    同步linux 5.10.y 社区LTS补丁集 11个：5.10.122 - 5.10.133
    其余bugfix: 25个

议题二：Support Cluster scheduling on kunpeng platform（20min）---杨一聪
https://gitee.com/openeuler/kernel/pulls/169
任务唤醒PR已经提交
支持鲲鹏平台，降低延迟、提升吞吐量
欧拉测试组正在组织进行验证测试

议题三：增加cgroupv1 writeback功能特性 -- 卢佳琳
https://gitee.com/openeuler/kernel/pulls/215
cgroup writeback使能意义：1）开启回写条件；2）回写速率限制
cgroup writeback使能前提：1）struct bdi_writeback的归属问题：bdi->cgroup；2）对于脏页的阈值判断问题：struct wb_domain；3）sturct inode对应的memcg的归属问题：Boyer-Moore算法
目前只能在v2使能，在v1无法使能；解决思路：遵循v2中实现的逻辑，以memcg为准，用户态给memcg绑定对应的blkcg

议题四：
1.txgbe 网卡驱动 Committer 更新     ---网讯 温端强
https://gitee.com/openeuler/kernel/issues/I5Z1W2

2.新增kernel SIG 飞腾平台Committer  ---飞腾 毛泓博 帅家坤
飞腾平台已完成工作：已经将飞腾服务器内核补丁提交到openEuler社区
具体内容：1）支持飞腾S2500双路特性；2）支持飞腾服务器SMMU特性；3）支持飞腾服务器Kdump功能；4）支持飞腾S2500中断均衡功能
现阶段工作：维护社区已经提交的飞腾内核补丁代码
后续工作：1）创建飞腾SIG小组；2）完善飞腾服务器内核补丁，将最新代码同步到社区；3）推送飞腾X100内核补丁代码；4）推送飞腾桌面内核补丁代码（待定）
结论： 同意毛泓博担任openEuler kernel sig committer

3.TCP-option-address Committer更新 ---孙苏皖
   新增 统信Committer  openEuler ID：yugart
   新增 网络LVS专家      openEuler ID：far_beyond

三、本期遗留问题
1、NVME盘符漂移

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


2022-10-21 14：00
会议主题：openEuler Kernel SIG例会
当前议题：
1.openEuler-22.03-LTS-SP1 支持generic VDPA device介绍；
  结论：会后提PR回合openEuler 5.10开发主干： 
2.openEuler-22.03-LTS-SP1信息同步；
  SP1开发窗口中欢迎贡献者踊跃提PR
3.kernel SIG committer推举;
新增如下committer:
Intel 曾昭荣
AMD 谢昊成
龙芯 张洪臣
申威 顾子滔
超聚变 陈玮
天翼云 王夕波
 结论：各位候选人依次完成竞选陈述，与会者无反对意见，会上同意新增如上6位kernel sig committer

会议链接：https://us06web.zoom.us/j/85064426665?pwd=cDkyZ25DVDNwZXdJWUx0emVxQWR2QT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings
 
温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID


2022-09-30 14：00
会议主题：openEuler Kernel SIG例会
会议内容：

1.openEuler-22.09内核版本总结；
   https://gitee.com/openeuler/kernel/issues/I5TZB2?from=project-issue
   
2.openEuler-22.03-LTS-SP1开始内核需求收集；
  相关需求可以通过提gitee issue方式反馈
3.openEuler开源之夏特性 -- Add sysfs file for OverlayFS;

4.openEuler开源之夏特性 -- 增加rust-for-linux driver支持;
  review后合入
会议链接：https://us06web.zoom.us/j/83050040350?pwd=eXdPa28zb1orVmRvS0J4c2lPUnhpUT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings
 
温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID

2022-09-16 14：00
会议主题：openEuler Kernel SIG例会

会议内容：
1.openEuler-22.09龙芯支持特性简介
 Review后合入
2.openEuler开源之夏特性 -- 轻量级死锁检测实现
 Review后合入
3.调度系列技术分享第三期 -- Linux调度器框架

会议链接：https://us06web.zoom.us/j/87690719217?pwd=cDN6V3Bhc05DU3lqTmhHYzA2L0RBQT09

会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID

2022-09-02 14:00 

会议主题：openEuler Kernel SIG例会
会议链接：https://us06web.zoom.us/j/85985675927?pwd=ZXl4K3hzZWRpTUIvUWR6RkJJalpPdz09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings
会议内容：
1.AMD EPYC Gen4 Genoa平台openEuler-22.09支持简介
   https://gitee.com/openeuler/kernel/pulls/98
   Review后合入
2.申威openEuler-22.09内核特性介绍
   https://gitee.com/openeuler/kernel/pulls/31
   已合入
 

2022-08-19
 会议主题：openEuler Kernel SIG例会
 
会议链接：https://us06web.zoom.us/j/88345524477?pwd=WHAvcmcza0JnY1JhekNVdUJzUE04UT09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

议题列表：
1.arm64: add machine check safe support特性回合评审；
https://gitee.com/openeuler/kernel/pulls/78 
 Review后合入
2.Add memory reliable feature特性回合评审；
https://gitee.com/openeuler/kernel/pulls/79
 Review后合入
3. 同步Intel SPR 22.09支持的状态
4. 新增kernel sig committer 
 新增裘来彬为committer， 会上同意通过

2022-08-12
会议链接：https://us06web.zoom.us/j/89836175849?pwd=ODlUNVhldkdndnN0b21VRUIxNkg0dz09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

议题列表： 
1.英特尔Sapphire Rapids平台PMU新特性介绍
   https://gitee.com/openeuler/kernel/pulls/62
2.基于BPF内核缓存的Redis加速特性评审
   https://gitee.com/openeuler/kernel/pulls/69
   Review后合入
3.BPF CO-RE(Compile Once-Run Everywhere)特性评审
   https://gitee.com/openeuler/kernel/pulls/70
   是否同意回合或相关意见请在PR中评论
温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.co
会议链接：https://us06web.zoom.us/j/89651338599?pwd=RUMzN1B6WStiMXVwcEdZZVYxTWRmdz09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

议题列表
1. arm64: support SME(Scalable Matrix Extension)特性回合评审 ---汪少博  
   https://gitee.com/openeuler/kernel/pulls/50
   armv8.x特性回合， 增强矩阵运算功能，review后合入
2. rust for openEuler特性回合评审 ---  陈为珑
   https://gitee.com/openeuler/kernel/pulls/44
   rust 驱动框架支持， review后合入
3. 可编程调度框架抢占、选核、选任务部分实现及示例  --- 任智杰/唐辉
   https://gitee.com/openeuler/kernel/pulls/60
   openEuler-22.09内核可编程调度特性持续开发中，欢迎社区一起参与开发，已经有相关感兴趣同学加入，PR补丁review
4.add exec hugetlb support特性回合评审 --- 刘紫贤
   https://gitee.com/openeuler/kernel/pulls/59
   Review后合入


2022-07-22
会议链接：https://us06web.zoom.us/j/81074273618?pwd=dTV6UmRETzR6Umd3amU0OFRXVlhndz09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

议题列表
1、introduce scheduler BPF特性回合评审  - renzhijie
        https://gitee.com/openeuler/kernel/pulls/38
2、支持在离线混部任务优先级负载均衡特性回合评审    -   zhangsong
      - https://gitee.com/openeuler/kernel/pulls/37
3、kernel仓支持PR回合补丁介绍   - zhengzengkai
4、kernel仓库瘦身讨论  - 谢秀奇
 
纪要：
1.可编程调度进展同步 -- 陈辉
2.introduce scheduler BPF特性回合评审  - renzhijie
   PR Review后合入openEuler-22.09分支
3.支持在离线混部任务优先级负载均衡特性回合评审 -zhangsong
   PR Review后先合入openEuler-22.09分支
4.kernel仓支持PR回合补丁介绍   - zhengzengkai
   kernel仓逐步完善PR机制，欢迎社区踊跃提PR
   操作指南：

       gitee通用PR操作：https://gitee.com/help/articles/4304#article-header0

               openEuler kernel仓 PR 操作步骤(README更新中)：https://gitee.com/openeuler/community/blob/master/sig/Kernel/README.md
5.kernel仓库瘦身讨论
按如下issue计划操作：
  https://gitee.com/openeuler/kernel/issues/I5F32E?from=project-issue， 


2022-07-08
会议链接：https://us06web.zoom.us/j/89123664797?pwd=S1BKR3BHTTBOZUd0TTg2VE9FRUVMQT09

议题列表：
14:10 - 15:00：美团贡献富容器隔离及内部自研混部特性到openEuler kernel的讨论
1.富容器隔离：

    补丁相关链接：

    https://gitee.com/anolis/cloud-kernel/commit/6cec9ebab206b9dccdb525a5d18ac96a5351af35 

    https://gitee.com/anolis/cloud-kernel/commit/2f5c25e0dad0f81ef2b781ccd09940f6b9f8977d

    https://gitee.com/anolis/cloud-kernel/commit/78e9e41b5040f6b345cc2401f5d6aa83d2e41858

    美团，华为，麒麟参与了讨论，支持相关补丁回合 ,  补丁适配后，后续通过PR合入


2.内部自研混部特性：
特性简介：
美团内部针对容器级别的在离线混部实现了一整套方案，包括cfs抢占、HT隔离和bfq优先级三个部分。
方案可以通过标记容器为在线/普通/离线容器，实现在cfs调度级别不同优先级容器之间的抢占，同一
个物理核下不同逻辑核（HT）不同优先级容器进程的隔离，bfq调度下不同优先级容器IO下发 的抢占。
方案实现通过proc接口控制，默认不开启时对现有内核影响程度很小。方案的缺点是对cfs调度和bfq
有一定的侵入改动，但是受proc接口控制。

美团先把PR提上来，进行补丁Review。

OLK-5.10 已合入的混部补丁：
https://gitee.com/openeuler/kernel/commit/4e57e412b84a70355140222399481db2557674e3
https://gitee.com/openeuler/kernel/commit/fd5207be48fa9ec41a21562137eb18c92fadb132
https://gitee.com/openeuler/kernel/commit/42f42feeaae6ba1017954f8fcb63b9feed56aa7e
https://gitee.com/openeuler/kernel/commit/8090ab77223b8311bf0214a7930e2ba75551f1b6
https://gitee.com/openeuler/kernel/commit/d933b9f1aea75c2862beac8b3249f549ed615c44
对应的 issue:
    https://gitee.com/openeuler/kernel/issues/I52611
     https://gitee.com/openeuler/kernel/issues/I4K96G

openEuler社区加入方式：
openEuler kernel SIG 微信技术交流群
请添加小助手微信（微信号：openeuler-kernel）
备注“交流群”或“技术交流”
加入 openEuler kernel SIG 技术交流群


2022-06-24
会议主题：openEuler kernel SIG例会&技术分享

会议内容：
openEuler kernel 技术分享：执行实体创建与切换
会议链接：https://us06web.zoom.us/j/82875828076?pwd=cWVmcGtITlJlM0RxcXYzcDlXZjVJUT09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings



2022-5-20
会议链接：https://us06web.zoom.us/j/81837728501?pwd=THk0TnBjc0ZFbXJ0ZnlJTzBxVCtWUT09

议题列表（更新中）：
1. 14:10 - 15:00：openEuler kernel 技术分享：内核调度器简史




2022-3-17 
主持人：唐嘉远
下次会议主持人：
与会人：liuchao

会议链接：https://us06web.zoom.us/j/82640076508?pwd=MktwWWxWR3ZqNFF4SlgwdGhwNlNDZz09

议题列表（更新中）：
1. 14:10 - 14:25：[openEuler-22.03-LTS]建议在spec中对内核模块压缩减少磁盘消耗   - liuchao
https://gitee.com/src-openeuler10/kernel/pulls/551

在kernel.spec中对内核模块进行压缩，压缩为.xz格式，可以减少内核模块约72%的磁盘消耗。
对于openEuler操作系统，可以减少约175 MB磁盘消耗。

目前openEuler中modprobe等工具都支持.xz格式的内核模块，该更改对正常使用无影响。

此功能在centos、opensuse均已默认打开。

压缩命令：
find $RPM_BUILD_ROOT/lib/modules/ -type f -name '*.ko' | xargs -n1 -P`nproc --all` xz

会议结论：节省磁盘，副作用小，其他社区已经在用，比较成熟的，同意合入 22.03.
同时在 22.03 NEXT 也同步过去。

2. 14:25 - 14:40： 修改内核spec，从内核中直接生成libbpf软件包 -  liuxin
https://gitee.com/src-openeuler/kernel/pulls/560

会议结论：分歧比较大，需要收集更多的意见才能决策。先遗留，带收集信息之后，下次会议决策。

主要讨论的焦点：
 - kernel 功能 libbpf 兼容性如何保证，如何维护；

3. openEuler kernel技术分享第18期 - 内核中断子系统介绍





2022-2-18
主持人：唐嘉远
下次会议主持人：
与会人：Geliang Tang

议题列表（更新中）：

14:10 - 14:30：intel SGX特性介绍及合入
https://gitee.com/openeuler/kernel/issues/I4SIGI

会议结论：当前已经 Review 一轮，修改修改OK后，同意合入 openEuler 22.03 LTS 版本。

14:30 - 14:45 ： 申请适配toa开源插件 
https://gitee.com/openeuler/kernel/issues/I4QHWR

会议结论：同意 toa 模块引入 kernel sig，已单独仓库和模块的形式。待提交 PR。

14:45 - 15:00：实现ima namespace 的 digest list
https://gitee.com/openeuler/kernel/issues/I4TPUM

会议结论：暂不合入openEuler 22.03 LTS，可以合入 22.09 创新版本。

15:00 - 15:30: openEuler 22.03 KABI 白名单基线（初稿）评审
https://gitee.com/openeuler/kernel/issues/I4U6NZ

会议结论：会后发出列表初稿，共大家评审。

-------- 历史分割线 ----------

2021-12-31议题
14:10 - 14:25 议题：希望在内核态支持RDMA通信
14:25 - 14:40 议题：openEuler 22.03支持mptcp介绍
14:40 - 15:30 openEuler kernel技术分享第17期 - cgroup介绍

2021-12-17议题
14:10 - 15:00 openEuler kernel技术分享第16期 - openEuler内核热补丁介绍

Welcome to Etherpad!

This pad text is synchronizedas you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents!

Get involved with Etherpad at https://etherpad.org