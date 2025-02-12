---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/12/29 Kernel SIG 双周例会】
轮值主持：廖涛 【轮值主持顺序：郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：郑增凯
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/986451425
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&郑增凯）
近两周(2023.12.11 ~ 12.29)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-182.0.0
        openEuler-22.03-LTS-SP3更新到tag 5.10.0-182.0.0（rc6）
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.37.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.58.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.120.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-176.0.0 更新至 5.10.0-182.0.0, 回合补丁数136个
        git log 5.10.0-176.0.0..5.10.0-182.0.0 --oneline | wc -l
        136

        performance:
        https://gitee.com/openeuler/kernel/pulls/3463  Support node_reclaim_distance adjust
        https://gitee.com/openeuler/kernel/pulls/3427  tcp: Disable header prediction for MD5 flow.
        https://gitee.com/openeuler/kernel/pulls/3421  backport some network patches
        https://gitee.com/openeuler/kernel/pulls/3461  Revert "mm/mempolicy: don't handle MPOL_LOCA
        https://gitee.com/openeuler/kernel/pulls/3375  locking/osq_lock: Avoid false sharing in optimistic_spin_node

        Intel:
        https://gitee.com/openeuler/kernel/pulls/3093 backport adding GNR support for Intel PCIe gen5 NTB
        https://gitee.com/openeuler/kernel/pulls/3221 Backport x86 patches from upstream 5.10.189

        Phytium:
        https://gitee.com/openeuler/kernel/pulls/3084 [OLK-5.10] add Phytium DRM drivers CONFIG

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/3535 Bugfixes for RDMA/hns
        https://gitee.com/openeuler/kernel/pulls/3504 net: hns3: fix kernel crash when 1588 is received on HIP08 devices
        https://gitee.com/openeuler/kernel/pulls/3508  roh/hns3: Fix the processing flow of ROH CMDq during the reset process.
        https://gitee.com/openeuler/kernel/pulls/3415 Some bugfix for hns3
        https://gitee.com/openeuler/kernel/pulls/3404 Add the verification operation after the  bus recovery operation obtains resources through the ACPI
        https://gitee.com/openeuler/kernel/pulls/3413 Backport bugfixes for hns
        https://gitee.com/openeuler/kernel/pulls/3274  Fixed some memory leak issues of the Perf tool
        https://gitee.com/openeuler/kernel/pulls/3303 net: hns3: Add support for some CMIS transceiver modules and synchronize some CMIS transceiver
        https://gitee.com/openeuler/kernel/pulls/3304 roh/core: Synchronously update the mac address of the vlan device when configuring the vlan device ip
        https://gitee.com/openeuler/kernel/pulls/3301 unic: Change the max frame size sent to firmware
        https://gitee.com/openeuler/kernel/pulls/3222  md/raid5: fix miscalculation of 'end_sector' in raid5_read_one_chunk()
        https://gitee.com/openeuler/kernel/pulls/3269  iommu/arm-smmu-v3: disable stall for quiet_cd
        https://gitee.com/openeuler/kernel/pulls/3219 crypto: hisiilicon some bugfixs and cleanup
        https://gitee.com/openeuler/kernel/pulls/3256 RDMA/hns: Cleanups of some optimize code
        https://gitee.com/openeuler/kernel/pulls/3257 net: hns3: add input parameters checking and arp cleancode

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/3553  kernel: update SP3 OPENEULER_MINOR and introduced OPENEULER_LTS
        https://gitee.com/openeuler/kernel/pulls/3519  tick/broadcast-hrtimer: Prevent the timer device on broadcast duty CPU from being disabled
        https://gitee.com/openeuler/kernel/pulls/3422  sch_netem: fix issues in netem_change() vs get_dist_table()
        https://gitee.com/openeuler/kernel/pulls/3424 mbigen: vtimer: disable vtimer mbigen probe when vtimer_irqbypass disabled
        https://gitee.com/openeuler/kernel/pulls/3390  mm/userswap: modify the USWAP registration flag
        https://gitee.com/openeuler/kernel/pulls/3376  mm/mempolicy: check preferred_node rather than nodes for MPOL_PREFERRED
        https://gitee.com/openeuler/kernel/pulls/3346  smart_grid: cpufreq: clear offline and isolated CPU in warm CPUs
        https://gitee.com/openeuler/kernel/pulls/3374  cpumask: cleanup nr_cpu_ids vs nr_cpumask_bits mess
        https://gitee.com/openeuler/kernel/pulls/3360  arm64: cpufeature: Add missing .field_width for system registers
        https://gitee.com/openeuler/kernel/pulls/3329  iommu/arm-smmu-v3: Add a SYNC command to avoid broken page table prefetch
        https://gitee.com/openeuler/kernel/pulls/3320  Make the rcache depot scale better
        https://gitee.com/openeuler/kernel/pulls/3254  icmp: Fix a data-race around sysctl_icmp_errors_use_inbound_ifaddr.


        openEuler-22.03-LTS-SP3 all features:
        https://gitee.com/openeuler/kernel/issues/I8SB67
近三周(2023.12.11 ~ 12.29)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2312.6.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/

        openEuler-1.0-LTS从 4.19.90-2312.1.0 更新至 4.19.90-2312.6.0, 回合补丁数45个
        git log --no-merges 4.19.90-2312.1.0..4.19.90-2312.6.0 --oneline | wc -l
        45

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/3239  net: hns: fix fake link up
        https://gitee.com/openeuler/kernel/pulls/3531  Fix kernel panic occurs during ISO installation on the 20.03 SP3/SP4
        https://gitee.com/openeuler/kernel/pulls/3417  SCSI: hisi_raid: support SPxxx serial RAID/HBA controllers
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/3607  Fix CVE-2023-6546
        https://gitee.com/openeuler/kernel/pulls/3606  perf/core: Fix CVE-2023-6931
        https://gitee.com/openeuler/kernel/pulls/3483  net: Remove acked SYN flag from packet in the transmit queue correctly
        https://gitee.com/openeuler/kernel/pulls/3426  Revert "hrtimers: Push pending hrtimers away from outgoing CPU earlier"
        https://gitee.com/openeuler/kernel/pulls/3347  tun: avoid double free in tun_free_netdev
        https://gitee.com/openeuler/kernel/pulls/3113  KVM: arm64: limit PMU version to PMUv3 for ARMv8.1
        https://gitee.com/openeuler/kernel/pulls/3281  LTS patch backport
        https://gitee.com/openeuler/kernel/pulls/3122  nvme: retain split access workaround for capability reads
        https://gitee.com/openeuler/kernel/pulls/3262  icmp: Fix a data-race around sysctl_icmp_errors_use_inbound_ifaddr.
        https://gitee.com/openeuler/kernel/pulls/3276  linux-4.19.y inclusion
        https://gitee.com/openeuler/kernel/pulls/3263  workqueue: Override implicit ordered attribute in workqueue_apply_unbound_cpumask()
        https://gitee.com/openeuler/kernel/pulls/3267  x86/cpu: Fix AMD erratum #1485 on Zen4-based CPUs
        https://gitee.com/openeuler/kernel/pulls/3021  fix CFS bandwidth vs. hrtimer self deadlock
        https://gitee.com/openeuler/kernel/pulls/3202  regmap: fix NULL deref on lookup
20231229：
OLK-6.6进展同步：
特性回合事项：
         截至12月29日，新分支已合入PR 69个，补丁 1787个
KABI专项：
         1.KABI预留字段前置补丁https://gitee.com/openeuler/kernel/pulls/3331已合入OLK-6.6 ;
         2.KABI白名单初稿正在输出；
         3.部分KABI预留PR已经发出;
处理器支持专项：
         1.处理器厂商PR: 兆芯 27个，龙芯3个，飞腾1个，海光1个；
         2.目前2个已合入，其他正在review中；
内核编译专项：
         1. Arm64&X86已基于5.10 openeuler_defconfig生成OLK-6.6内核初始配置上库，扫描出5.10至6.6新增Kconfig待评审开关
         https://gitee.com/openeuler/kernel/pulls/2900
         2. kernel rpm包构建， 合入PR https://gitee.com/src-openeuler/kernel/pulls/1341

议题二：新增树莓派dev分包（张子杨）
树莓派内核未提供devel软件包，想要编译树莓派环境下使用的内核模块ko文件时，需要下载所有树莓派源码进行编译，这样对于开发很不方便。此PR提供一个raspberrypi-kernel-devel子包。
https://gitee.com/src-openeuler/kernel/pulls/1384

https://gitee.com/openeuler/community/tree/master/sig/Kernel#%E5%88%86%E6%94%AF%E7%AE%A1%E7%90%86
openEuler/kernel仓库的OLK-5.10分支对应src-openEuler/kernel仓库的openEuler-22.03-LTS-Next分支

议题三：内核态vDPA支持热迁移特性回合SP1/SP2影响评审（姜冬旭）
内核态vDPA已合入至openEuler OLK-5.10分支及SP3分支，当前鲲鹏计算考虑到SP1/SP2已经支持内核态vDPA特性，但不支持热迁移。当前存量用户需要使用该特性，提出诉求，需要合入SP1/SP2。
release sig评审提出意见，内核sig先评估是否存在兼容性等风险。
https://gitee.com/openeuler/kernel/pulls/3343
https://gitee.com/openeuler/kernel/pulls/3369

评审意见：补充SP1/SP2上的验证，并需要相关committer review PR

议题四：glibc huge page patch backport（议题非kernel相关，不在kernel sig例会讨论）
https://gitee.com/src-openeuler/glibc/pulls/396

The Two hugepage patches have been merged to glibc master: https://sourceware.org/git/glibc.git
https://patches.linaro.org/project/libc-alpha/patch/20231123172915.893408-2-adhemerval.zanella@linaro.org/
https://patches.linaro.org/project/libc-alpha/patch/20231123172915.893408-3-adhemerval.zanella@linaro.org/
具体原因：
From adhemerval.zanella@linaro.org
I found out what is happening. For large sizes glibc malloc will always try
to allocate memory through mmap (the malloc with MAX_POOL_LENTH * sizeof(struct uadk_bd))
and the current heuristics I added is to use MAP_HUGETLB iff the requested size is larger
than hugepage size as way to avoid much waste by using large mmaps sizes.
Since the size is smaller than the default page size (2MB on aarch64), it will
fallback to mmap. You can disable it by setting the mmap threshold similar to
large page size with the tunable glibc.malloc.mmap_threshold=2097152,
which will make sizes up to 2097152 to be services by the hep extension way
with MAP_HUGETLB).
I think I will send a patch to set the mmap threshold to the default page size,
to always use large size.

三、本期遗留问题

(which without mmap is brk(), but with hugetlb=2 it will fallback to mmap

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/12/22 Kernel SIG 双周例会】
轮值主持：廖涛（张伽琳代）【轮值主持顺序：郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：桑力鹏
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/966610402
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 章昌仲
近两周(2023.12.11 ~ 12.22)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-180.0.0
        openEuler-22.03-LTS-SP3更新到tag 5.10.0-180.0.0
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.36.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.57.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.119.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        
        以OLK-5.10为例:
        从 5.10.0-176.0.0 更新至 5.10.0-180.0.0, 回合补丁数127个
        git log 5.10.0-176.0.0..5.10.0-180.0.0 --oneline | wc -l
        127

        performance:
        https://gitee.com/openeuler/kernel/pulls/3463  Support node_reclaim_distance adjust
        https://gitee.com/openeuler/kernel/pulls/3427  tcp: Disable header prediction for MD5 flow.
        https://gitee.com/openeuler/kernel/pulls/3421  backport some network patches
        https://gitee.com/openeuler/kernel/pulls/3461  Revert "mm/mempolicy: don't handle MPOL_LOCA
        https://gitee.com/openeuler/kernel/pulls/3375  locking/osq_lock: Avoid false sharing in optimistic_spin_node

        Intel:
        https://gitee.com/openeuler/kernel/pulls/3093 backport adding GNR support for Intel PCIe gen5 NTB
        https://gitee.com/openeuler/kernel/pulls/3221 Backport x86 patches from upstream 5.10.189

        Phytium:
        https://gitee.com/openeuler/kernel/pulls/3084 [OLK-5.10] add Phytium DRM drivers CONFIG

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/3504 net: hns3: fix kernel crash when 1588 is received on HIP08 devices
        https://gitee.com/openeuler/kernel/pulls/3508  roh/hns3: Fix the processing flow of ROH CMDq during the reset process.
        https://gitee.com/openeuler/kernel/pulls/3415 Some bugfix for hns3
        https://gitee.com/openeuler/kernel/pulls/3404 Add the verification operation after the  bus recovery operation obtains resources through the ACPI
        https://gitee.com/openeuler/kernel/pulls/3413 Backport bugfixes for hns
        https://gitee.com/openeuler/kernel/pulls/3274  Fixed some memory leak issues of the Perf tool
        https://gitee.com/openeuler/kernel/pulls/3303 net: hns3: Add support for some CMIS transceiver modules and synchronize some CMIS transceiver
        https://gitee.com/openeuler/kernel/pulls/3304 roh/core: Synchronously update the mac address of the vlan device when configuring the vlan device ip
        https://gitee.com/openeuler/kernel/pulls/3301 unic: Change the max frame size sent to firmware
        https://gitee.com/openeuler/kernel/pulls/3222  md/raid5: fix miscalculation of 'end_sector' in raid5_read_one_chunk()
        https://gitee.com/openeuler/kernel/pulls/3269  iommu/arm-smmu-v3: disable stall for quiet_cd
        https://gitee.com/openeuler/kernel/pulls/3219 crypto: hisiilicon some bugfixs and cleanup
        https://gitee.com/openeuler/kernel/pulls/3256 RDMA/hns: Cleanups of some optimize code
        https://gitee.com/openeuler/kernel/pulls/3257 net: hns3: add input parameters checking and arp cleancode
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/3422  sch_netem: fix issues in netem_change() vs get_dist_table()
        https://gitee.com/openeuler/kernel/pulls/3424 mbigen: vtimer: disable vtimer mbigen probe when vtimer_irqbypass disabled
        https://gitee.com/openeuler/kernel/pulls/3390  mm/userswap: modify the USWAP registration flag
        https://gitee.com/openeuler/kernel/pulls/3376  mm/mempolicy: check preferred_node rather than nodes for MPOL_PREFERRED
        https://gitee.com/openeuler/kernel/pulls/3346  smart_grid: cpufreq: clear offline and isolated CPU in warm CPUs
        https://gitee.com/openeuler/kernel/pulls/3374  cpumask: cleanup nr_cpu_ids vs nr_cpumask_bits mess
        https://gitee.com/openeuler/kernel/pulls/3360  arm64: cpufeature: Add missing .field_width for system registers
        https://gitee.com/openeuler/kernel/pulls/3329  iommu/arm-smmu-v3: Add a SYNC command to avoid broken page table prefetch
        https://gitee.com/openeuler/kernel/pulls/3320  Make the rcache depot scale better
        https://gitee.com/openeuler/kernel/pulls/3254  icmp: Fix a data-race around sysctl_icmp_errors_use_inbound_ifaddr.

近两周(2023.12.11 ~ 12.22)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2312.4.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/

        openEuler-1.0-LTS从 4.19.90-2312.1.0 更新至 4.19.90-2312.4.0, 回合补丁数36个
        git log --no-merges 4.19.90-2312.1.0..4.19.90-2312.4.0 --oneline | wc -l
        36

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/3239  net: hns: fix fake link up
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/3426  Revert "hrtimers: Push pending hrtimers away from outgoing CPU earlier"
        https://gitee.com/openeuler/kernel/pulls/3347  tun: avoid double free in tun_free_netdev
        https://gitee.com/openeuler/kernel/pulls/3113  KVM: arm64: limit PMU version to PMUv3 for ARMv8.1
        https://gitee.com/openeuler/kernel/pulls/3281  LTS patch backport
        https://gitee.com/openeuler/kernel/pulls/3122  nvme: retain split access workaround for capability reads
        https://gitee.com/openeuler/kernel/pulls/3262  icmp: Fix a data-race around sysctl_icmp_errors_use_inbound_ifaddr.
        https://gitee.com/openeuler/kernel/pulls/3276  linux-4.19.y inclusion
        https://gitee.com/openeuler/kernel/pulls/3263  workqueue: Override implicit ordered attribute in workqueue_apply_unbound_cpumask()
        https://gitee.com/openeuler/kernel/pulls/3267  x86/cpu: Fix AMD erratum #1485 on Zen4-based CPUs
        https://gitee.com/openeuler/kernel/pulls/3021  fix CFS bandwidth vs. hrtimer self deadlock
        https://gitee.com/openeuler/kernel/pulls/3202  regmap: fix NULL deref on lookup

议题二：议题征集中

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/12/8 Kernel SIG 双周例会】
轮值主持：郑增凯
下次轮值主持：廖涛
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/981980862
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

summit2023:
https://www.openeuler.org/zh/interaction/summit-list/summit2023/

议题一：进展update --- 张伽琳 & 章昌仲

近两周(2023.11.27 ~ 12.8)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2312.1.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/

        openEuler-1.0-LTS从 4.19.90-2311.4.0 更新至 4.19.90-2312.1.0, 回合补丁数19个
        git log --no-merges 4.19.90-2311.4.0..4.19.90-2312.1.0 --oneline | wc -l
        19

        飞腾：
        https://gitee.com/openeuler/kernel/pulls/3000  [openEuler-1.0-LTS] add Phytium drivers CONFIG

        openeuler_defconfig：
        https://gitee.com/openeuler/kernel/pulls/2960  Add script to check & update openeuler_defconfig

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/2804  signal: Properly set TRACE_SIGNAL_LOSE_INFO in __send_signal
        https://gitee.com/openeuler/kernel/pulls/2805  sched/fair: Refill bandwidth before scaling
        https://gitee.com/openeuler/kernel/pulls/2869  mm, memory_hotplug: update pcp lists everytime onlining a memory block
        https://gitee.com/openeuler/kernel/pulls/2908  mm/migrate.c: fix potential indeterminate pte entry in migrate_vma_insert_page()
        https://gitee.com/openeuler/kernel/pulls/3030  x86/mce/inject: Fix a wrong assignment of i_mce.status
        https://gitee.com/openeuler/kernel/pulls/3031  x86/mce/amd: Publish the bank pointer only after setup has succeeded
        https://gitee.com/openeuler/kernel/pulls/3038  ipv4: igmp: fix refcnt uaf issue when receiving igmp query packet
        https://gitee.com/openeuler/kernel/pulls/3071  perf/core: Fix perf_mmap fail when CONFIG_PERF_USE_VMALLOC enabled
        https://gitee.com/openeuler/kernel/pulls/2977  Backport crypto bugfix
        https://gitee.com/openeuler/kernel/pulls/3118  sched: smart grid: check is active in affinity timer
        https://gitee.com/openeuler/kernel/pulls/2781  cpufreq: Abort show()/store() for half-initialized policies
        https://gitee.com/openeuler/kernel/pulls/3158  mm: don't let userspace spam allocations warnings

近两周(2023.11.27 ~ 12.8)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-176.0.0
        openEuler-22.03-LTS-SP3更新到tag 5.10.0-176.0.0
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.35.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.57.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.119.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-172.0.0 更新至 5.10.0-176.0.0, 回合补丁数1394个
        git log 5.10.0-172.0.0..5.10.0-176.0.0 --oneline | wc -l
        1394

        其中
        同步linux 5.10.y社区LTS补丁集7个: 5.10.183 - 5.10.189
        https://gitee.com/openeuler/kernel/pulls/3150 Backport 5.10.189 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/3117 Backport 5.10.188 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/3085 Backport 5.10.185 -  5.10.187 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/2938 Backport 5.10.183 - 5.10.184 LTS patches from upstream

        内存动态隔离和释放:
        https://gitee.com/openeuler/kernel/pulls/3214  bring mc support to page eject
        https://gitee.com/openeuler/kernel/pulls/3065  support page eject

        支持功耗感知调度:
        https://gitee.com/openeuler/kernel/pulls/3037  introduce smart_grid zone

        CPU巡检:
        https://gitee.com/openeuler/kernel/pulls/2915 Introduce CPU inspect feature

        RCU stall维测增强:
        https://gitee.com/openeuler/kernel/pulls/3066  rcu: Add RCU stall diagnosis information

        PSI支持对资源竞争度量及处理器性能监控单元指标低负载采集:
        https://gitee.com/openeuler/kernel/pulls/3087  psi irq in cgroupv1 and psi fine grained

        SME特性:
        https://gitee.com/openeuler/kernel/pulls/3062 backport SME from mainline

        KVM性能优化:
        https://gitee.com/openeuler/kernel/pulls/3259 mbigen: vtimer: isolate mbigen vtimer funcs with macro
        https://gitee.com/openeuler/kernel/pulls/3220 KVM: arm64: vtimer/virt_dev irq bypass support
        https://gitee.com/openeuler/kernel/pulls/3092 [OLK-5.10]KVM: arm64: Add host/guest KVM-PTP support

        支持vDPA设备虚拟机热迁移框架:
        https://gitee.com/openeuler/kernel/pulls/3148  vdpa: add vmstate header file
        https://gitee.com/openeuler/kernel/pulls/3145  vhost-vdpa: add reset state params to indicate reset level
        https://gitee.com/openeuler/kernel/pulls/3009  vhost-vdpa: allow set feature VHOST_F_LOG_ALL when been negotiated.

        Intel TDP MMU:
        https://gitee.com/openeuler/kernel/pulls/2831 [22.03-LTS-SP3]  TDP MMU Support

        sangfor smc:
        https://gitee.com/openeuler/kernel/pulls/845 [OLK-5.10] net/smc: Introduce generic netlink interface for diagnostic purposes
        https://gitee.com/openeuler/kernel/pulls/811 [OLK-5.10]  net/smc:  patches to optimize  rmbs and sndbuff
        https://gitee.com/openeuler/kernel/pulls/865 [OLK-5.10] net/smc: backport the bugfixes of crash and other key problems in SMC

        Mucse Network Adapter:
        https://gitee.com/openeuler/kernel/pulls/2788  [OLK-5.10] Add support for Mucse Network Adapter(N10)

        yusilicon eth/rdma driver:
        https://gitee.com/openeuler/kernel/pulls/2747 [OLK-5.10] drivers: initial support for xsc drivers from Yunsilicon Technology

        Wangxun：
        https://gitee.com/openeuler/kernel/pulls/2617 [SYNC patch to OLK-5.10]Add ACS quirk for Wangxun NICs

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/3226  hinic: ethtool: Allow userspace to set more aggregation params
        https://gitee.com/openeuler/kernel/pulls/3215 net: hns: fix fake link up on xge port and fix wrong head when modify the tx feature when sending packets
        https://gitee.com/openeuler/kernel/pulls/3212  drivers/perf: hisi: UC PMU support statistics in power saving mode
        https://gitee.com/openeuler/kernel/pulls/3198 udma: add dfx ability of dca for hns3
        https://gitee.com/openeuler/kernel/pulls/3205 RDMA/hns: Fix the incomplete netdev speed, unspecific interrupt name, and resource value verification
        https://gitee.com/openeuler/kernel/pulls/3203 Some fixes and optimizations for hisi_sas
        https://gitee.com/openeuler/kernel/pulls/3154 crypto: hisilicon - fix the process to obtain capability register value
        https://gitee.com/openeuler/kernel/pulls/3196  drivers/perf: hisi: Fix some event id for HiSilicon UC pmu
        https://gitee.com/openeuler/kernel/pulls/3130  config: enable COBFIG_ARM64_BRBE for arm64
        https://gitee.com/openeuler/kernel/pulls/3061  drivers: perf: Add feature flag check in armpmu_add/del
        https://gitee.com/openeuler/kernel/pulls/2925 [OLK 5.10]Fix the call trace when hibmc loaded failed
        https://gitee.com/openeuler/kernel/pulls/3100 Default select PAGE_POOL_STATS, add command queue trace for hns3
        https://gitee.com/openeuler/kernel/pulls/3069  drivers: perf: Not enabled ARM64_BRBE by default
        https://gitee.com/openeuler/kernel/pulls/3045 crypto: hisilicon/zip - add zip comp high perf mode configuration
        https://gitee.com/openeuler/kernel/pulls/2953 Revert vf fault patch and fix some page pool bug
        https://gitee.com/openeuler/kernel/pulls/3051 [OLK-5.10] ub: add device parameter to ubcore_user_control
        https://gitee.com/openeuler/kernel/pulls/3019 RDMA/hns: Some cleanups for openEuler
        https://gitee.com/openeuler/kernel/pulls/3008 [OLK-5.10] ub: Fix bugs in urma kernel and user lib
        https://gitee.com/openeuler/kernel/pulls/2879  SCSI: hisi_raid: support SPxxx series RAID/HBA controllers
        https://gitee.com/openeuler/kernel/pulls/2774 [OLK-5.10] sched/fair: Scan cluster before scanning LLC in wake-up path

        LoongArch:
        https://gitee.com/openeuler/kernel/pulls/2946  LoongArch: disable 40bit user space by default
        https://gitee.com/openeuler/kernel/pulls/3005 [sync] PR-1617: LoonArch: KVM: fix vcpu timer

        zhaoxin:
        https://gitee.com/openeuler/kernel/pulls/2594 [OLK-5.10] x86/perf: Update PMU support for more Zhaoxin CPU

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/2987  fix CFS bandwidth vs. hrtimer self deadlock
        https://gitee.com/openeuler/kernel/pulls/3161  fs: Fix error checking for d_hash_and_lookup()
        https://gitee.com/openeuler/kernel/pulls/3206  Two bugfix patch about memcg swap qos
        https://gitee.com/openeuler/kernel/pulls/3128  fix ksmbd to release the ones allocated for async work
        https://gitee.com/openeuler/kernel/pulls/3152  scsi: scsi_device_gets returns failure
        https://gitee.com/openeuler/kernel/pulls/3110  spdxcheck.py: Fix a type error
        https://gitee.com/openeuler/kernel/pulls/3109  arm64/mpam: Fix static analysis warning
        https://gitee.com/openeuler/kernel/pulls/3083  fs/dirty_pages: introduce a new config option 'CONFIG_DIRTY_PAGES'
        https://gitee.com/openeuler/kernel/pulls/3082  fs/dirty_pages: add last read check in seq_read_dirty()
        https://gitee.com/openeuler/kernel/pulls/2988 [sync] PR-1203:  Revert "locking/rwsem: Prevent potential lock starvation"
        https://gitee.com/openeuler/kernel/pulls/3072  printk: ringbuffer: Fix truncating buffer size min_t cast
        https://gitee.com/openeuler/kernel/pulls/3020  fs/dirty_pages: fix inode reference count leakage error in dump_dirtypages_sb()
        https://gitee.com/openeuler/kernel/pulls/3022  fs/dirty_pages: fix some errors in seq_read_dirty()
        https://gitee.com/openeuler/kernel/pulls/3048  posix-cpu-timers: Implement timer_wait_running callback
        https://gitee.com/openeuler/kernel/pulls/3057  livepatch/powerpc: Fix issue that miss one layer on stack checking
        https://gitee.com/openeuler/kernel/pulls/3049  Revert "arm64/mpam: Fix mpam corrupt when cpu online"
        https://gitee.com/openeuler/kernel/pulls/3052  mpam: Fix uninitialized value
        https://gitee.com/openeuler/kernel/pulls/3033  ipmi_si: fix a memleak in try_smi_init()
        https://gitee.com/openeuler/kernel/pulls/3006  open: make RESOLVE_CACHED correctly test for O_TMPFILE
        https://gitee.com/openeuler/kernel/pulls/3039  ipv4: igmp: fix refcnt uaf issue when receiving igmp query packet
        https://gitee.com/openeuler/kernel/pulls/2964  Backport crypto bugfix
        https://gitee.com/openeuler/kernel/pulls/3011  config: update openeuler_defconfig for x86 with gcc 10.3.1
        https://gitee.com/openeuler/kernel/pulls/553 fix vmx_ldtr_test failed
        https://gitee.com/openeuler/kernel/pulls/2989 [sync] PR-1095: irqchip: gic-v3: Collection table support muti pages
        https://gitee.com/openeuler/kernel/pulls/2973 Add script to check & update openeuler_defconfig
        https://gitee.com/openeuler/kernel/pulls/2961  can: raw: fix memory leak
        https://gitee.com/openeuler/kernel/pulls/2949  Cmdline for ARMv8 Pointer Authentication

议题二：scsi下部分驱动commiter申报 -- 胡勇
drivers/scsi/lpfc
drivers/scsi/qla2xxx
drivers/scsi/mpt3sas
结论：通过，已经在openEuler社区提交并合入相关的bugfix，之前这部分驱动缺少committer

议题三：hisilicon gpu驱动commiter申报 -- 施永邦
kernel/drivers/gpu/drm/hisilicon/hibmc
结论：门禁和committer信息的文件可以先更新，先进行一定的工作，正式的committer可以工作一段时间之后再上会评审

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/11/24 Kernel SIG 双周例会】
轮值主持：桑力鹏
下次轮值主持：张伽琳
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/963265866
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 章昌仲
近两周(2023.11.13 ~ 11.24)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2311.4.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/

        openEuler-1.0-LTS从 4.19.90-2311.2.0 更新至 4.19.90-2311.4.0, 回合补丁数39个
        git log --no-merges 4.19.90-2311.2.0..4.19.90-2311.4.0 --oneline | wc -l
        39

        修复CVE 3个:
        CVE-2023-39197
        CVE-2023-39198
        CVE-2022-45884

        云芯智联：
        https://gitee.com/openeuler/kernel/pulls/2785  [openEuler-1.0-LTS] SCSI: SSSRAID: Support 3SNIC 3S5XX serial RAID/HBA controllers

        飞腾：
        https://gitee.com/openeuler/kernel/pulls/1935  [openEuler-1.0-LTS] Add Phytium optee driver support
        https://gitee.com/openeuler/kernel/pulls/2508  [openEuler-1.0-LTS] jpeg: Add a Phytium JPEG Engine driver
        https://gitee.com/openeuler/kernel/pulls/2522  [openEuler-1.0-LTS] Add support for Phytium SoC RNG
        https://gitee.com/openeuler/kernel/pulls/2693  [openEuler-1.0-LTS] Add support for Phytium QSPI
        https://gitee.com/openeuler/kernel/pulls/2402  [openEuler-1.0-LTS] Add Phytium w1 driver support
        https://gitee.com/openeuler/kernel/pulls/2403  [openEuler-1.0-LTS] Add Phytium adc driver support
        https://gitee.com/openeuler/kernel/pulls/1874  [openEuler-1.0-LTS] Add Phytium mailbox driver support
        https://gitee.com/openeuler/kernel/pulls/2024  [openEuler-1.0-LTS] Add Phytium RTC driver support
        https://gitee.com/openeuler/kernel/pulls/2682  [openEuler-1.0-LTS] Add support for Phytium MMC
        https://gitee.com/openeuler/kernel/pulls/2671  [openEuler-1.0-LTS] phytium dwmac net driver
        https://gitee.com/openeuler/kernel/pulls/2676  [openEuler-1.0-LTS] Add Phytium gpio driver support
        https://gitee.com/openeuler/kernel/pulls/2604  [openEuler-1.0-LTS] Add support for Phytium SPI
        https://gitee.com/openeuler/kernel/pulls/2540  [openEuler-1.0-LTS] Driver for the Phytium keypad port.

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/2895  netfilter: conntrack: dccp: copy entire header to stack buffer, not just basic one
        https://gitee.com/openeuler/kernel/pulls/2873  Fix SAS start error with maxcpus=1
        https://gitee.com/openeuler/kernel/pulls/2877  Revert "tcp: fix delayed ACKs for MSS boundary condition"
        https://gitee.com/openeuler/kernel/pulls/2818  Fix memleak in disassociate_ctty()
        https://gitee.com/openeuler/kernel/pulls/2810  drivers/gmjstcm: import CVE-2011-1160 CVE-2011-1162 fixes to tcm.c
        https://gitee.com/openeuler/kernel/pulls/2803  drivers/gmjstcm: fix a dev_err() call in spi tcm device probe
        https://gitee.com/openeuler/kernel/pulls/2841  drm/qxl: fix UAF on handle creation
        https://gitee.com/openeuler/kernel/pulls/2809  bugfix for CVE-2022-45884

近两周(2023.11.9 ~ 11.24)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-172.0.0
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.33.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.55.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.117.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-167.0.0 更新至 5.10.0-172.0.0, 回合补丁数826个
        git log 5.10.0-167.0.0..5.10.0-172.0.0 --oneline | wc -l
        826
        
        其中
        同步linux 5.10.y社区LTS补丁集3个: 5.10.180 - 5.10.182
        https://gitee.com/openeuler/kernel/pulls/2865 Backport 5.10.181 - 5.10.182 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/2775 Backport 5.10.180 LTS patches from upstream.

        修复CVE 4个:
        CVE-2023-6176
        https://gitee.com/openeuler/kernel/pulls/2902  net/tls: do not free tls_rec on async operation in bpf_exec_tx_verdict()
        CVE-2023-39197
        https://gitee.com/openeuler/kernel/pulls/2867  netfilter: conntrack: dccp: copy entire header to stack buffer, not just basic one
        CVE-2022-45884
        https://gitee.com/openeuler/kernel/pulls/2851  bugfix for CVE-2022-45884
        CVE-2023-39198
        https://gitee.com/openeuler/kernel/pulls/2840  drm/qxl: fix UAF on handle creation

        核隔离特性增强:
        https://gitee.com/openeuler/kernel/pulls/2776  blk-mq: avoid housekeeping CPUs scheduling a worker on a non-housekeeping CPU

        HBM混合内存管理：
        https://gitee.com/openeuler/kernel/pulls/2821  arm64: config: Disable CONFIG_ARM64_PBHA by default

        performance:
        https://gitee.com/openeuler/kernel/pulls/2943  ext4: mitigate cacheline false sharing in struct ext4_inode_info

        jingdong:
        https://gitee.com/openeuler/kernel/pulls/2829 Modify idle cpu judgment in dynamic affinity

        Intel:
        https://gitee.com/openeuler/kernel/pulls/2888 OLK-5.10: GNR-SRF new KVM ISA support
        https://gitee.com/openeuler/kernel/pulls/2762 Intel: backport SPR/EMR vt-d pcie upstream bug fix for 5.10

        LoongArch:
        https://gitee.com/openeuler/kernel/pulls/2884  LoongArch: fix two cpu hotplug problem

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/2929 RDMA/hns:  A set of bugfixes for openEuler
        https://gitee.com/openeuler/kernel/pulls/2932 Revert "net: hns3: add command queue trace for hns3"
        https://gitee.com/openeuler/kernel/pulls/2928 ub: add new feature for urma
        https://gitee.com/openeuler/kernel/pulls/2845 crypto: hisilicon - revert some patch
        https://gitee.com/openeuler/kernel/pulls/2926 Fixed some issues of ultrasoc-smb
        https://gitee.com/openeuler/kernel/pulls/2864 unic: add ub support to hns3
        https://gitee.com/openeuler/kernel/pulls/2890 net: ipv6: addrconf: Add the IPv6 link local address of the UB port.
        https://gitee.com/openeuler/kernel/pulls/2872 net: hns3: Backport some mainline feature and some hns3 bugfix
        https://gitee.com/openeuler/kernel/pulls/2881 soc: hisilicon: kunpeng_hccs: Support the platform with PCC type3 and interrupt ack
        https://gitee.com/openeuler/kernel/pulls/2875 Support SRQ Context tracing by debugfs
        https://gitee.com/openeuler/kernel/pulls/2868 backport the patch moving ACPI PCC macro definition to common header file
        https://gitee.com/openeuler/kernel/pulls/2852  MAINTAINERS: update openEuler/MAINTAINERS for vdpa driver
        https://gitee.com/openeuler/kernel/pulls/2756  Introduce some vdpa ops to support vdpa device live migrate
        https://gitee.com/openeuler/kernel/pulls/2863 Support some dfx for hns3
        https://gitee.com/openeuler/kernel/pulls/2862 UBL: Change the name of ub netdev to ubl.
        https://gitee.com/openeuler/kernel/pulls/2855 Support SW stats with debugfs
        https://gitee.com/openeuler/kernel/pulls/2837 udma: solve two compile problem of hns3-udma driver
        https://gitee.com/openeuler/kernel/pulls/2794  arm64/perf: Enable branch stack sampling
        https://gitee.com/openeuler/kernel/pulls/2777 RDMA/hns: Revert the private patch on the openEuler and Re-upload the patch from Linux mainline.

        sangfor:
        https://gitee.com/openeuler/kernel/pulls/828 [OLK-5.10] net/smc:  Optimization for connect performance
        https://gitee.com/openeuler/kernel/pulls/827 [OLK-5.10]  net/smc:  aligning the connect behaviour with TCP
        https://gitee.com/openeuler/kernel/pulls/825 [OLK-5.10] net/smc: optimization related to data transmission
        https://gitee.com/openeuler/kernel/pulls/847  [OLK-5.10]  net/smc:  support cork option
        https://gitee.com/openeuler/kernel/pulls/826 [OLK-5.10]  net/smc:  mutex lock optimize
        https://gitee.com/openeuler/kernel/pulls/813 [OLK-5.10] net/smc: backport dma sync ops optimize
        https://gitee.com/openeuler/kernel/pulls/810 configs: enable CONFIG_SMC and CONFIG_SMC_DIAG by default

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/2731  PCI/IOV: Add pci_sriov_numvfs_lock to support enable pci sriov concurrently
        https://gitee.com/openeuler/kernel/pulls/1967  cpu/hotplug: Prevent self deadlock on CPU hot-unplug
        https://gitee.com/openeuler/kernel/pulls/2687  integrity: Fix possible multiple allocation in integrity_inode_get()
        https://gitee.com/openeuler/kernel/pulls/2911  Fix syntax issues in comments and print
        https://gitee.com/openeuler/kernel/pulls/2348  net: ipv4: fix one memleak in __inet_del_ifa()
        https://gitee.com/openeuler/kernel/pulls/2798  handle uninitialized numa nodes gracefully.
        https://gitee.com/openeuler/kernel/pulls/2791 [sync] PR-1122:  ext4: delete redundant uptodate check for buffer
        https://gitee.com/openeuler/kernel/pulls/2820  Fix memleak in disassociate_ctty()
        https://gitee.com/openeuler/kernel/pulls/2843  Add error handle for sd
        https://gitee.com/openeuler/kernel/pulls/2825  Add error handle for driver

        5.10各分支PR清理情况统计:
        11.14 5.10各分支待合入PR：373，11.14-11.24 kernel仓库新增PR：101，当前kernel仓库待合入PR：243
        PR清理数量约为231

        网卡驱动Kconfig默认值讨论：
        https://gitee.com/openeuler/kernel/pulls/2747

议题二：openEuler Summit 2023 内核相关模块介绍 --- 谢秀奇 & 郑增凯 & 桑力鹏 & 廖涛
（1）Linux内核分论坛
（2）openEuler kernel SIG组工作会议

openEuler官网介绍：https://www.openeuler.org/zh/interaction/summit-list/summit2023/

议题三：tdpmmu integration for 22.03 SP3 - Zhang Yu (Intel)
https://gitee.com/openeuler/kernel/pulls/2831  [22.03-LTS-SP3] TDP MMU Support

议题四：OLK-6.6分支进展同步

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/11/10 Kernel SIG 双周例会】
轮值主持：廖涛
下次轮值主持：桑力鹏
会议链接：https://us06web.zoom.us/j/87016190729?pwd=QXivFoXObEngRNR23faQCqS1XGbrs3.1
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
热补丁移植到riscv架构——2536

二、议题列表

议题一：进展update --- 张伽琳 & 章昌仲
近两周(2023.10.30 ~ 11.9)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-167.0.0
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.32.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.54.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.116.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-164.0.0 更新至 5.10.0-167.0.0, 回合补丁数340个
        git log 5.10.0-164.0.0..5.10.0-167.0.0 --oneline | wc -l
        340

        其中
        同步linux 5.10.y社区LTS补丁集2个: 5.10.177 - 5.10.178
        https://gitee.com/openeuler/kernel/pulls/2686 Backport 5.10.179 LTS patches from upstream.
        https://gitee.com/openeuler/kernel/pulls/2631 Backport 5.10.178 LTS patches from upstream.

        修复CVE 9个:
        CVE-2023-37453
        https://gitee.com/openeuler/kernel/pulls/2443  CVE-2023-37453
        VE-2023-46862
        https://gitee.com/openeuler/kernel/pulls/2678  io_uring/fdinfo: lock SQ thread while retrieving thread cpu/pid
        CVE-2023-5178
        https://gitee.com/openeuler/kernel/pulls/2688  nvmet-tcp: Fix a possible UAF in queue intialization setup
        CVE-2023-46813
        https://gitee.com/openeuler/kernel/pulls/2672  fix CVE-2023-46813
        CVE-2023-39194
        https://gitee.com/openeuler/kernel/pulls/2666  net: xfrm: Fix xfrm_address_filter OOB read
        CVE-2023-5717
        https://gitee.com/openeuler/kernel/pulls/2641  Fix CVE-2023-5717
        CVE-2023-31085
        https://gitee.com/openeuler/kernel/pulls/2628  ubi: Refuse attaching if mtd's erasesize is 0
        CVE-2023-31083
        https://gitee.com/openeuler/kernel/pulls/2608 [sync] PR-2557:  Bluetooth: hci_ldisc: check HCI_UART_PROTO_READY flag in HCIUARTGETPROTO
        CVE-2022-44033
        https://gitee.com/openeuler/kernel/pulls/2624 [sync] PR-2613:  CVE-2022-44033

        jingdong:
        https://gitee.com/openeuler/kernel/pulls/2765 Remove invalid cpu selection logic in dynamic affinity
        https://gitee.com/openeuler/kernel/pulls/2546 memcg swap qos:  add ability to disable memcg swap
        https://gitee.com/openeuler/kernel/pulls/2319  add a mutex lock for qos_level

        Phytium:
        https://gitee.com/openeuler/kernel/pulls/2381 Add Phytium Display Engine support to the OLK-5.10.

        LoongArch:
        https://gitee.com/openeuler/kernel/pulls/2694  LoongArch: add 32/64 pc relative relocation type support
        https://gitee.com/openeuler/kernel/pulls/2579  LoongArch: default IPMI related defconfig to m

        Intel:
        https://gitee.com/openeuler/kernel/pulls/2541 Intel: Backport some SPR and EMR PMU related upstream bugfixes to OLK-5.10

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/2757  soc: hisilicon: hisi_hbmdev: Add hbm acls repair and query methods
        https://gitee.com/openeuler/kernel/pulls/2737  perf auxtrace ptt: Record whether an auxtrace mmap is needed
        https://gitee.com/openeuler/kernel/pulls/2670 page_pool: Add support query allocation stats and recycle stats
        https://gitee.com/openeuler/kernel/pulls/2714 crypto: hisilicon/zip - support deflate algorithm
        https://gitee.com/openeuler/kernel/pulls/2675 RDMA/hns: Support STARS over RDMA
        https://gitee.com/openeuler/kernel/pulls/2704 crypto: hisilicon - round some bugfixes
        https://gitee.com/openeuler/kernel/pulls/2695 BTC for openeuler
        https://gitee.com/openeuler/kernel/pulls/2495 [OLK 5.10]drm driver bug revise for hisilicon
        https://gitee.com/openeuler/kernel/pulls/2621 RDMA/hns: Append SCC context to the raw dump of QP Resource
        https://gitee.com/openeuler/kernel/pulls/2656  coresight: trbe: Enable ACPI based devices
        https://gitee.com/openeuler/kernel/pulls/2657  Synchronize mainline hisilicon uncore pmu driver bugfix to openEuler-OLK-5.10
        https://gitee.com/openeuler/kernel/pulls/2642  Synchronize coresight driver bugfix patches to openEuler
        https://gitee.com/openeuler/kernel/pulls/2620  coresight: etm4x: Migrate ACPI AMBA devices to platform drive
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/2716  ext4: recheck buffer valid after page unlock
        https://gitee.com/openeuler/kernel/pulls/2783  Add error handle for add_disk
        https://gitee.com/openeuler/kernel/pulls/2782  cpufreq: Abort show()/store() for half-initialized policies
        https://gitee.com/openeuler/kernel/pulls/2683  fix memcgv1 oom meminfo bug
        https://gitee.com/openeuler/kernel/pulls/2721  net: sched: sch_qfq: Use non-work-conserving warning handler
        https://gitee.com/openeuler/kernel/pulls/2699  add sample sockmap code for redis
        https://gitee.com/openeuler/kernel/pulls/2632  arm64: fix a concurrency issue in emulation_proc_handler()
        https://gitee.com/openeuler/kernel/pulls/2377  tracing: Backport bugfixes
        https://gitee.com/openeuler/kernel/pulls/2543  psi: fix "no previous prototype" warnings when CONFIG_CGROUPS=n
        https://gitee.com/openeuler/kernel/pulls/2615  preempt/dynamic: Fix setup_preempt_mode() return value
        https://gitee.com/openeuler/kernel/pulls/2452  audit: fix possible soft lockup in __audit_inode_child()

近两周(2023.10.30 ~ 11.9)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2311.2.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/

        openEuler-1.0-LTS从 4.19.90-2310.4.0 更新至 4.19.90-2311.2.0, 回合补丁数71个
        git log --no-merges 4.19.90-2310.4.0..4.19.90-2311.2.0 --oneline | wc -l
        71

        修复CVE 6个:
        CVE-2023-31085
        CVE-2022-44033
        CVE-2023-5717
        CVE-2022-45919
        CVE-2023-31083
        CVE-2023-34324

        网讯：
        https://gitee.com/openeuler/kernel/pulls/2605  add CONFIG_NGBE for Wangxun 1G NIC for aarch64

        云芯智联：
        https://gitee.com/openeuler/kernel/pulls/2164  Net: ethernet: Support 3snic 3s9xx network card

        飞腾：
         https://gitee.com/openeuler/kernel/pulls/1873  [openEuler-1.0-LTS] Add Phytium hda driver support
         https://gitee.com/openeuler/kernel/pulls/2564  [openEuler-1.0-LTS] Add Phytium i2c driver support
         https://gitee.com/openeuler/kernel/pulls/2588  [openEuler-1.0-LTS] Add Phytium Display Engine support.
         https://gitee.com/openeuler/kernel/pulls/1974  CAN driver for phytium CPUs

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/2758  crypto: hisilicon - qm obtain the mailbox config at one time
        https://gitee.com/openeuler/kernel/pulls/1860  irqchip/gicv3-its: Add workaround for hip09 ITS erratum 162100801

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/2760  fs: lockd: avoid possible wrong NULL parameter
        https://gitee.com/openeuler/kernel/pulls/2636  kernel/trace: Fix do not unregister tracepoints when register sched_migrate_task fail
        https://gitee.com/openeuler/kernel/pulls/2754  Sync LTS patches for openEuler-1.0-LTS
        https://gitee.com/openeuler/kernel/pulls/2730  PCI/IOV: Add pci_sriov_numvfs_lock to support enable pci sriov concurrently
        https://gitee.com/openeuler/kernel/pulls/2722  net: sched: sch_qfq: Use non-work-conserving warning handler
        https://gitee.com/openeuler/kernel/pulls/2650  sched/cpuacct: Fix charge cpuacct.usage_sys
        https://gitee.com/openeuler/kernel/pulls/2609  Fix CVE-2023-5717
        https://gitee.com/openeuler/kernel/pulls/2627  ubi: Refuse attaching if mtd's erasesize is 0
        https://gitee.com/openeuler/kernel/pulls/2473  Revert irq reentrant warm log
        https://gitee.com/openeuler/kernel/pulls/2551  Avoid spin or livelock during panic
        https://gitee.com/openeuler/kernel/pulls/2314  can: raw: add missing refcount for memory leak fix
        https://gitee.com/openeuler/kernel/pulls/2396  efi: use 32-bit alignment for efi_guid_t literals
        https://gitee.com/openeuler/kernel/pulls/2446  audit: fix possible soft lockup in __audit_inode_child()
        https://gitee.com/openeuler/kernel/pulls/2614  CVE-2022-44033
        https://gitee.com/openeuler/kernel/pulls/2577  media: dvb-core: Fix use-after-free due to race condition at dvb_ca_en50221
        https://gitee.com/openeuler/kernel/pulls/2550  xen/events: replace evtchn_rwlock with RCU
        https://gitee.com/openeuler/kernel/pulls/2557  Bluetooth: hci_ldisc: check HCI_UART_PROTO_READY flag in HCIUARTGETPROTO

议题二：TDP MMU合并进22.03 SP3的讨论 -- 张宇 (Intel)
相关负责人跟踪PR合入，由于改动较大，建议社区多方共同检视&维护，保障PR合入质量，有问题及时反馈。

议题三：openEuler kernel 6.6新内核启动开发   --- 郑增凯
Kernel SIG已完成社区开工会宣讲， 11月10日openEuler-24.03-LTS(6.6新内核)启动开发，任务已分配到各领域。

议题四： 龙芯高巨鑫(giteeid: @gaojuxin09)申请成为committer

    欧拉社区贡献：

    review by:

    https://gitee.com/openeuler/kernel/pulls/2579

    https://gitee.com/openeuler/kernel/pulls/2664

    https://gitee.com/openeuler/kernel/pulls/2694

    欧拉社区commit:

    81e76248eaf5 2023-06-21  Revert "LoongArch: Add ARCH_HAS_SETUP_DMA_OPS and DMA_OPS" [Juxin Gao]

    51a58dd0d66f 2023-06-21  Revert "LoongArch: Add swiotlb backups buffer" [Juxin Gao]

    dec8be1d451c 2023-06-06  LoongArch: defconfig: Enable a large number of configurations [Yingkun Meng]

    753912bceb7a 2023-06-06  LoongArch: Add swiotlb backups buffer [Juxin Gao]

    0c86a5542a47 2023-06-06  LoongArch: Add ARCH_HAS_SETUP_DMA_OPS and DMA_OPS [Juxin Gao]

    ba6684fc0351 2023-06-06  pci: irq: Add early_param pci_irq_limit to limit pci irq numbers [Juxin Gao]

意见：通过


议题五：Pull Request讨论：VFIO支持SR-IOV直通 -- 曾昭荣（Intel）

    https://gitee.com/openeuler/kernel/pulls/2833



三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/10/27 Kernel SIG 双周例会】
轮值主持：张伽琳
下次轮值主持：廖涛
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/965660880
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
openEuler-22.03-LTS-SP3需求收集 
       需求收集截止: 10月27日（下次kernel sig例会）
       需求合入截止: 12月1日

二、议题列表

议题一：进展update --- 张伽琳 & 章昌仲
近两周(2023.10.16 ~ 10.27)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-164.0.0
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.30.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.52.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.114.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-162.0.0 更新至 5.10.0-164.0.0, 回合补丁数516个
        git log 5.10.0-162.0.0..5.10.0-164.0.0 --oneline | wc -l
        516

        其中
        同步linux 5.10.y社区LTS补丁集2个: 5.10.176 - 5.10.177
        https://gitee.com/openeuler/kernel/pulls/2465 Backport 5.10.177 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/2442 Backport 5.10.176 LTS patches from upstream.

        修复CVE 14个:
        CVE-2022-45919
        https://gitee.com/openeuler/kernel/pulls/2573  media: dvb-core: Fix use-after-free due to race condition at dvb_ca_en50221
        CVE-2023-34324
        https://gitee.com/openeuler/kernel/pulls/2571  xen/events: replace evtchn_rwlock with RCU
        CVE-2023-45871
        https://gitee.com/openeuler/kernel/pulls/2454  igb: set max size RX buffer when store bad packet is enabled
        CVE-2023-42754
        https://gitee.com/openeuler/kernel/pulls/2370  ipv4: fix null-deref in ipv4_link_failure
        CVE-2023-39193
        https://gitee.com/openeuler/kernel/pulls/2411  netfilter: xt_sctp: validate the flag_info count
        CVE-2023-32254
        CVE-2023-32246
        CVE-2023-32256
        CVE-2023-32258
        CVE-2023-2593
        https://gitee.com/openeuler/kernel/pulls/2476  Fixed five CVEs vulnerabilities of ksmbd
        CVE-2023-2898
        https://gitee.com/openeuler/kernel/pulls/2499  f2fs: fix to avoid NULL pointer dereference f2fs_write_end_io()
        CVE-2023-39192
        https://gitee.com/openeuler/kernel/pulls/2440  netfilter: xt_u32: validate user space input
        CVE-2023-39189
        https://gitee.com/openeuler/kernel/pulls/2410  netfilter: nfnetlink_osf: avoid OOB read
        CVE-2023-20569
        https://gitee.com/openeuler/kernel/pulls/2326 fix CVE-2023-20569

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/1613  arm64/mpam: implement CPU_PM notifier
        https://gitee.com/openeuler/kernel/pulls/2492  Avoid spin or livelock during panic
        https://gitee.com/openeuler/kernel/pulls/2437  crypto: drbg - Only fail when jent is unavailable in FIPS mode
        https://gitee.com/openeuler/kernel/pulls/2468  fix cgroup poll UAF
        https://gitee.com/openeuler/kernel/pulls/2340  xfs: recent patches to fix xfs issues

        performance:
        https://gitee.com/openeuler/kernel/pulls/2481  Introduce PBHA and PBHA bit0 to control the usage of HBM Cache precisely

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/2592 Add support for RDMA VF over UBL
        https://gitee.com/openeuler/kernel/pulls/2496 uacce: some bugfix and cleanup
        https://gitee.com/openeuler/kernel/pulls/2537 Support SRQ record doorbell
        https://gitee.com/openeuler/kernel/pulls/2456 Added the UB network management driver.
        https://gitee.com/openeuler/kernel/pulls/2517 RDMA/hns: Support flexible wqe buffer page size
        https://gitee.com/openeuler/kernel/pulls/2159 Enable HiSilicon Erratum 162001900 quirk for HIP08/09
        https://gitee.com/openeuler/kernel/pulls/2491 udma: add udma support to hns3
        https://gitee.com/openeuler/kernel/pulls/2480  coresight: Fix loss of connection info when a module is unloaded
        https://gitee.com/openeuler/kernel/pulls/2488  coresight: etm4x: Match all ETM4 instances based on DEVARCH and DEVTYPE
        https://gitee.com/openeuler/kernel/pulls/2483 Fix bug for init roh client instance
        https://gitee.com/openeuler/kernel/pulls/2459 Bugfixes for RDMA/hns
        https://gitee.com/openeuler/kernel/pulls/2500 Modify a format problem of gpio
        https://gitee.com/openeuler/kernel/pulls/2489 Some optimizations for PTT driver
        https://gitee.com/openeuler/kernel/pulls/2407 Revert "uacce: use filep->f_mapping to replace inode->i_mapping"
        https://gitee.com/openeuler/kernel/pulls/2462 ub: change name in kconfig, and kconfig content of ub
        https://gitee.com/openeuler/kernel/pulls/2447  xhci: print warning when HCE was set
        https://gitee.com/openeuler/kernel/pulls/2449 [OLK-5.10] arch_topology: Limit span of cpu_clustergroup_mask()
        https://gitee.com/openeuler/kernel/pulls/2308 unic: add ub support to hns3
        https://gitee.com/openeuler/kernel/pulls/2423 Revert "perf: pmu: fix set wrong filter mode for running events issue" and "perf: hns3: default use hardware event 0 as group leader event."
        https://gitee.com/openeuler/kernel/pulls/2428 Add Hisilicon hibmc drm driver maintainers to openEuler/MAINTAINERS
        https://gitee.com/openeuler/kernel/pulls/1282  Stop attempts to auxtrace mmap when not an auxtrace event
        https://gitee.com/openeuler/kernel/pulls/2406 ub: change default Kconfig of urma to n, and depends on arm64
        https://gitee.com/openeuler/kernel/pulls/2395 Uacce round main line two cleanup patches

        jingdong:
        https://gitee.com/openeuler/kernel/pulls/1553 remove useless spinlock section
        https://gitee.com/openeuler/kernel/pulls/1804 count time in drain_all_pages during direct reclaim as memory pressure
        https://gitee.com/openeuler/kernel/pulls/2363 skip smt expel when cpu down

        windriver:
        https://gitee.com/openeuler/kernel/pulls/2501  scsi: mpt3sas: Perform additional retries if doorbell read returns 0
        
        Intel:
        https://gitee.com/openeuler/kernel/pulls/1293 Enable reliable memory for x86 platform
        https://gitee.com/openeuler/kernel/pulls/2431 Backport microcode patches from upstream 5.10.173

2023.10.13 ~ 10.27进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2310.4.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/


        openEuler-1.0-LTS从 4.19.90-2310.2.0 更新至 4.19.90-2310.4.0, 回合补丁数13个
        git log --no-merges 4.19.90-2310.2.0..4.19.90-2310.4.0 --oneline | wc -l
        13

        修复4个CVE:
        CVE-2023-39192                
        CVE-2023-45862                
        CVE-2023-39193                
        CVE-2023-39189                
                
        openEuler-1.0-LTS合入PR：
                
                北航：
                                https://gitee.com/openeuler/kernel/pulls/2334 ktask: add memory leak handling for ktask_works in ktask_init()
                                https://gitee.com/openeuler/kernel/pulls/2333 ktask: add null-pointer checks for ktask_works in ktask_init()
                                https://gitee.com/openeuler/kernel/pulls/2330 Add a check of uvhub_mask in init_per_cpu()
                                
                hisilicon：
                                 https://gitee.com/openeuler/kernel/pulls/2360 scsi: hisi_sas: Handle the NCQ error returned by D2H frame
                                 
                社区问题修复以及上游社区bugfix补丁回合：
                                https://gitee.com/openeuler/kernel/pulls/2453 igb: set max size RX buffer when store bad packet is enabled
                                https://gitee.com/openeuler/kernel/pulls/2441 netfilter: xt_u32: validate user space input
                                https://gitee.com/openeuler/kernel/pulls/2435 USB: ene_usb6250: Allocate enough memory for full object
                                https://gitee.com/openeuler/kernel/pulls/2466 x86/microcode/AMD: Make stub function static inline
                                https://gitee.com/openeuler/kernel/pulls/2461 perf/core: Fix reentry problem in perf_output_read_group()
                                https://gitee.com/openeuler/kernel/pulls/2409 netfilter: nfnetlink_osf: avoid OOB read
                                https://gitee.com/openeuler/kernel/pulls/2412 netfilter: xt_sctp: validate the flag

议题二：云脉芯联（Yusilicon）申请xsc以太驱动和rdma驱动开源到kernel sig OLK-5.10分支 - 何页 hey@yunsilicon.com
net rdma 驱动
结论：通过，驱动模块相对独立，影响可控，先将PR提上来，以兼容性sig review结论为准，
gitee_id:weihonggang-git <weihg@yunsilicon.com>

议题三：kernel committer 申报 -- 罗盛炜
结论：通过，承担20.03-LTS-SP4版本的维护，是openEuler其他sig的committer，对openEuler比较熟悉
gitee_id:Lostwayzxc <luoshengwei@huawei.com>

议题四：smc-r特性合入以及申请成为smc模块committer----- 深信服焦利涛
https://gitee.com/openeuler/kernel/pulls/833
https://gitee.com/openeuler/kernel/pulls/825
https://gitee.com/openeuler/kernel/pulls/804
https://gitee.com/openeuler/kernel/pulls/810
https://gitee.com/openeuler/kernel/pulls/865
https://gitee.com/openeuler/kernel/pulls/845
https://gitee.com/openeuler/kernel/pulls/813
https://gitee.com/openeuler/kernel/pulls/811
https://gitee.com/openeuler/kernel/pulls/826
https://gitee.com/openeuler/kernel/pulls/827
https://gitee.com/openeuler/kernel/pulls/828
https://gitee.com/openeuler/kernel/pulls/847
结论：通过，目前缺少smc的committer，成为模块committer，后续补充测试结果，进行质量保障。
可以把smc-r的特性介绍和使用补充到openEuler kernel doc仓：
https://gitee.com/openeuler/kernel-docs/tree/master/Kernel%20Features
gitee_id:giree2 <jiaolitao@sangfor.com.cn>

议题五：新增张建华（华为）为kernel sig committer —— 章昌仲
1、主要负责维护内核体系结构(arm32/arm64/ppc)和中断子系统
2、在Linux内核社区合入9个patch，review openEuler补丁100+
3、之后在社区主要投入体系结构领域的开发与维护
结论：通过，背景是很多模块缺少committer，导致PR积压，后续其他缺少看护的模块也需要committer
gitee_id:chris_zjh <chris.zjh@huawei.com>

议题六：enfs特性合入以及申请成为enfs模块的committer  ——  张明谦（华为）
结论：对应模块的committer审核（张翼），其他committer也参与审核，合入之后，新增模块的作者成为该模块committer，维护的文件目录需要沟通，提供测试报告，进行质量保障。
gitee_id:mingqian218472 <zhangmingqian.zhang@huawei.com>

议题七：openEuler-22.03-LTS-SP3需求评审 —— 张伽琳
https://gitee.com/openeuler/kernel/issues/I7SVH7 [openEuler 22.03 SP3]eNFS特性合入，提升NFS客户端的性能与可靠性
结论：对应模块的committer审核（张翼），其他committer也参与审核，新增模块的作者可以成为committer，维护的文件目录需要沟通，提供测试报告，进行质量保障。
https://gitee.com/openeuler/kernel/issues/I88YFC [OpenEuler22.03-LTS-SP3]Backporting of KVM TDP MMU for X86
结论：以相关领域committer意见为准（朱科潜）
https://gitee.com/openeuler/kernel/issues/I89D3P [openEuler-22.03-SP3]SPxx系列RAID卡驱动需求合入
结论：通过，驱动模块相对独立，影响可控，先将PR提上来，以兼容性sig review结论为准
https://gitee.com/openeuler/kernel/issues/I89GNZ [openEuler-22.03-SP3]yusilicon合入eth driver以及rdma driver
结论：通过，驱动模块相对独立，影响可控，先将PR提上来，以兼容性sig review结论为准
https://gitee.com/openeuler/kernel/issues/I8AJCF [openEuler-22.03-SP3] 从上游kernel stable tree kernel-5.10.y 回合AMD GPU驱动重要的bug fix
结论：通过，后续沟通committer事宜
https://gitee.com/openeuler/kernel/issues/I7ZBQB [openEuler-22.03-SP3]【可靠性】支持CPU巡检功能
结论：通过，先跟踪，能否合入SP3看开发情况
https://gitee.com/openeuler/kernel/issues/I7ZBSR [openEuler-22.03-SP3]【功耗】支持功耗感知调度
结论：通过，先跟踪，能否合入SP3看开发情况
https://gitee.com/openeuler/kernel/issues/I7ZBTV [openEuler-22.03-SP3]【性能】核隔离特性增强
结论：通过，先跟踪，能否合入SP3看开发情况
https://gitee.com/openeuler/kernel/issues/I8BCH4 [openEuler-22.03-LTS-SP3] ext4多次挂载循环日志记录特性
结论：通过，ext4维测，风险不大
https://gitee.com/openeuler/kernel/issues/I8BCJU [openEuler-22.03-LTS-SP3] ext4写入量监控特性
结论：通过，ext4维测，风险不大
https://gitee.com/openeuler/kernel/issues/I8BCV4 [openEuler-22.03-LTS-SP3] 支持对资源竞争度量及处理器性能监控单元指标低负载采集
结论：通过
https://gitee.com/openeuler/kernel/issues/I7CGGT [openEuler-22.03-SP3]Per-memcg swap control
结论：通过

（议题征集中）

三、本期遗留问题
下次议题：热补丁移植到riscv架构——2536

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/10/13 Kernel SIG 双周例会】
轮值主持：桑力鹏
下次轮值主持：张伽琳
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/985668321
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings
一、上期遗留问题跟踪
        1. 建议：固定议题介绍pending PR --- 对应责任人
        2. 清理PR的同时，整理下无人看护的模块
            门禁的回复过多，评审意见淹没在其中，找基础设施讨论
        3. 疑似对comment的reply的修改会触发门禁，找基础设施确认：https://gitee.com/openeuler/kernel/pulls/1293

二、议题列表

议题一：进展update --- 张伽琳 & 章昌仲
近两周(2023.9.25 ~ 10.13)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-162.0.0
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.29.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.51.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.113.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-161.0.0 更新至 5.10.0-162.0.0, 回合补丁数763个
        git log 5.10.0-161.0.0..5.10.0-162.0.0 --oneline | wc -l
        763

        其中
        同步linux 5.10.y社区LTS补丁集3个: 5.10.173 - 5.10.175

        修复CVE 4个:
        CVE-2023-5197
        https://gitee.com/openeuler/kernel/pulls/2384  netfilter: nf_tables: disallow rule removal from chain binding
        https://gitee.com/openeuler/kernel/pulls/2383  nf_table LTS
        CVE-2023-42753
        https://gitee.com/openeuler/kernel/pulls/2359  netfilter: ipset: add the missing IP_SET_HASH_WITH_NET0 macro for ip_set_hash_netportnet.c
        CVE-2023-42755
        https://gitee.com/openeuler/kernel/pulls/2323  net/sched: Retire rsvp classifier
        CVE-2023-25775
        https://gitee.com/openeuler/kernel/pulls/2347  RDMA/irdma: Prevent zero-length STAG registration

        performance:
        https://gitee.com/openeuler/kernel/pulls/2258  ext4: do not mark inode dirty every time when appending using delalloc

        jingdong:
        https://gitee.com/openeuler/kernel/pulls/2390 Backport 5.10.174 -  5.10.175 LTS patches from upstream.
        https://gitee.com/openeuler/kernel/pulls/1931 Backport 5.10.173 LTS patches from upstream.
        https://gitee.com/openeuler/kernel/pulls/2313 fixed the repeated setting logic of memcg_swap_qos_enable
        https://gitee.com/openeuler/kernel/pulls/1972 sched/fair: fix qos_idle_h_nr_running in enqueue/dequeue

        LoongArch:
        https://gitee.com/openeuler/kernel/pulls/2305  drm/inspur: fix compile warning

        windriver:
        https://gitee.com/openeuler/kernel/pulls/2287  scsi: lpfc: Fix ioremap issues in lpfc_sli4_pci_mem_setup()
        https://gitee.com/openeuler/kernel/pulls/2286  scsi: lpfc: Prevent lpfc_debugfs_lockstat_write() buffer overflow

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/2350 UB driver: add implementation of urma ubcore and uburma module
        https://gitee.com/openeuler/kernel/pulls/2307 Add UB driver，Initialize the UBCORE and UBURMA modules in the URMA subsystem, and add the data and API definition on which the hardware driver depends.
        https://gitee.com/openeuler/kernel/pulls/2255 Sync the commit "irqchip/gicv3-its: Add workaround for hip09 ITS erratum 162100801" from 22.03-SP2 to OLK-5.10
        https://gitee.com/openeuler/kernel/pulls/2309 hns3 : Add support to query scc version
        https://gitee.com/openeuler/kernel/pulls/2261 backport kunpeng hccs driver and enable compiling config
        https://gitee.com/openeuler/kernel/pulls/2280 add myself as kunpeng hccs maintainer
        https://gitee.com/openeuler/kernel/pulls/2306 [RoCE] Fix the  WC cannot be polled occasionally after reseting
        https://gitee.com/openeuler/kernel/pulls/2197 [RoCE] Support getting xrcd num from firmware；Fix incorrect post-send with direct wqe of wr-list
        https://gitee.com/openeuler/kernel/pulls/2292 Backport some patch for HNS3 and revert some patch

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/1688  mm/ksm: Remove the ksm_merge_any status
        https://gitee.com/openeuler/kernel/pulls/1448  Tracing fixes
        https://gitee.com/openeuler/kernel/pulls/2302  xfrm6: fix inet6_dev refcount underflow problem
        https://gitee.com/openeuler/kernel/pulls/2282  sdei_watchdog: Avoid exception during sdei handler
        https://gitee.com/openeuler/kernel/pulls/1243  config: enable set the max iova mag size to 128

2023.9.25 ~ 10.13进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2310.2.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/


        openEuler-1.0-LTS从 4.19.90-2309.4.0 更新至 4.19.90-2310.2.0, 回合补丁数33个
        git log --no-merges 4.19.90-2309.4.0..4.19.90-2310.2.0 --oneline | wc -l
        33

        修复5个CVE:
        CVE-2023-25775              
        CVE-2023-42753               
        CVE-2023-42754                
        CVE-2023-42755                
        CVE-2020-36766                  
                
        openEuler-1.0-LTS合入PR：
                
                hisilicon：
                                https://gitee.com/openeuler/kernel/pulls/2360 scsi: hisi_sas: Handle the NCQ error returned by D2H frame
                                https://gitee.com/openeuler/kernel/pulls/2262 crypto: hisilicon - reset before init the device
                

                社区问题修复以及上游社区bugfix补丁回合：
                                https://gitee.com/openeuler/kernel/pulls/2322 net/sched: Retire rsvp classifier
                                https://gitee.com/openeuler/kernel/pulls/2346 RDMA/irdma: Prevent zero-length STAG registration
                                https://gitee.com/openeuler/kernel/pulls/2349 net: ipv4: fix one memleak in __inet_del_ifa()
                                https://gitee.com/openeuler/kernel/pulls/2329 ipv4: fix null-deref in ipv4_link_failure
                                https://gitee.com/openeuler/kernel/pulls/2342 linux-4.19.y inclusion
                                https://gitee.com/openeuler/kernel/pulls/2345 Backport lts bugfix patch for macvlan
                                https://gitee.com/openeuler/kernel/pulls/2344 PCI: acpiphp: linux-4.19.y bugfixes backport
                                https://gitee.com/openeuler/kernel/pulls/2341 quota: fix warning in dqgrab()
                                https://gitee.com/openeuler/kernel/pulls/1706 cgroup: fix missing cpus_read_{lock,unlock}() in cgroup_transfer_tasks()
                                https://gitee.com/openeuler/kernel/pulls/2337 mm: memory-failure: use rcu lock instead of tasklist_lock when collect_procs()
                                https://gitee.com/openeuler/kernel/pulls/2335 x86/topology: Fix erroneous smp_num_siblings on Intel Hybrid platforms
                                https://gitee.com/openeuler/kernel/pulls/2301 xfrm6: fix inet6_dev refcount underflow problem
                                https://gitee.com/openeuler/kernel/pulls/2303 cifs: Release folio lock on fscache read hit.
                                https://gitee.com/openeuler/kernel/pulls/2294 netfilter: ipset: add the missing IP_SET_HASH_WITH_NET0 macro for ip_set_hash_netportnet.c
                                https://gitee.com/openeuler/kernel/pulls/2276 cpuidle: Fix kobject memory leaks in error paths
                                https://gitee.com/openeuler/kernel/pulls/2274 cec-api: prevent leaking memory through hole in structure
                                https://gitee.com/openeuler/kernel/pulls/2281 sdei_watchdog: Avoid exception during sdei handler
                                https://gitee.com/openeuler/kernel/pulls/2212 [sync] PR-2210:  jbd2: Fix potential data lost in recovering journal raced with synchronizing fs bdev

议题二：进展pending PR清理 --- 张伽琳 & 章昌仲
openeuler/kernel仓库pending PR：310，新增：63，历史清理：79
pending PR review: 对应提交人主动上报；或提前一周整理历史PR，发邮件给提交者

议题二：openEuler bpftool发布件上游源修改 --- 刘忻

议题三：openEuler-22.03-LTS-SP3需求收集
openEuler-22.03-LTS-SP3需求收集里程碑: https://e.gitee.com/open_euler/milestones/185400/issues/table
openEuler-22.03-LTS-SP3 Release Plan: https://gitee.com/openeuler/release-management/blob/master/openEuler-22.03-LTS-SP3/release-plan.md#release-plan
需求收集截止: 10月27日（下次kernel sig例会）
需求合入截止: 12月1日

目前是需求收集阶段，如果您有合入 openEuler-22.03-LTS-SP3 kernel 的需求，请您尽快向 openEuler 社区 kernel sig 提交需求 issue
需求 issue 提交链接： https://gitee.com/openeuler/kernel/issues， issue 类型选择需求， issue 标题以 [openEuler-22.03-LTS-SP3] 开头
我们将在 2023 年 10 月 27 日 kernel sig 双周例会上集中讨论，采纳的需求将纳入里程碑规划

议题四：征集中

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/9/22 Kernel SIG 双周例会】
轮值主持：廖涛
下次轮值主持：桑力鹏
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/984839769
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings
一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 章昌仲
近两周(2023.9.11 ~ 9.22)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-161.0.0
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.28.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.50.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.112.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-160.0.0 更新至 5.10.0-161.0.0, 回合补丁数96个
        git log 5.10.0-160.0.0..5.10.0-161.0.0 --oneline | wc -l
        96

        回合CVE补丁13个:
        CVE-2022-45887
        CVE-2023-4921
        CVE-2023-4881
        CVE-2023-20588
        CVE-2023-4015
        CVE-2023-32247
        CVE-2023-32251
        CVE-2023-32253
        CVE-2023-32249
        CVE-2023-21400
        CVE-2023-3777
        CVE-2023-4623
        CVE-2023-4622

        OLK-5.10合入PR:

        zram二次压缩特性:
        https://gitee.com/openeuler/kernel/pulls/2190  zram: correctly handle all next_arg() cases
        https://gitee.com/openeuler/kernel/pulls/2162  zram: do not waste zram_table_entry flags bits

        LoongArch:
        https://gitee.com/openeuler/kernel/pulls/2156  drm: add inspur drm driver support
        https://gitee.com/openeuler/kernel/pulls/2163  Fix the two problems when using binutil 2.41.

        windriver:
        https://gitee.com/openeuler/kernel/pulls/1778  nvme-pci: fix DMA direction of unmapping integrity data

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/2256 MAINTAINERS: update openEuler/MAINTAINERS for UB and PMU
        https://gitee.com/openeuler/kernel/pulls/2199  Not clear ATA_PFLAG_EH_PENDING and not thaw the port twice in ata_eh_reset()
        https://gitee.com/openeuler/kernel/pulls/2173  ata: libahci: clear pending interrupt status
        https://gitee.com/openeuler/kernel/pulls/1517 [OLK-5.10] Rework CPU capacity asymmetry detection
        https://gitee.com/openeuler/kernel/pulls/2218 uacce: modify the configuration mode of device isolation stragety
        https://gitee.com/openeuler/kernel/pulls/2123 Backport some patch for HNS3 and revert some unnecessary patch
        https://gitee.com/openeuler/kernel/pulls/2099 xhci:fix USB xhci controller issue
        https://gitee.com/openeuler/kernel/pulls/2009 Fix errors related to bond for RDMA/hns

        CVE:
        https://gitee.com/openeuler/kernel/pulls/2230  media: ttusb-dec: fix memory leak in ttusb_dec_exit_dvb()
        https://gitee.com/openeuler/kernel/pulls/2169  net: sched: sch_qfq: Fix UAF in qfq_dequeue()
        https://gitee.com/openeuler/kernel/pulls/2153  netfilter: nftables: exthdr: fix 4-byte stack OOB write
        https://gitee.com/openeuler/kernel/pulls/2086  fix CVE-2023-20588
        https://gitee.com/openeuler/kernel/pulls/2095  io_uring: ensure IOPOLL locks around deferred work
        https://gitee.com/openeuler/kernel/pulls/2126  netfilter: nf_tables: skip immediate deactivate in _PREPARE_ERROR
        https://gitee.com/openeuler/kernel/pulls/2085  af_unix: Fix null-ptr-deref in unix_stream_sendpage().
        https://gitee.com/openeuler/kernel/pulls/2097  Fixed 4 CVEs of the ksmbd
        https://gitee.com/openeuler/kernel/pulls/2092  netfilter: nf_tables: skip bound chain on rule flush
        https://gitee.com/openeuler/kernel/pulls/2090  net/sched: sch_hfsc: Ensure inner classes have fsc curve

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/2269  etmem: Fixed an issue where the module reference counting is incorrect
        https://gitee.com/openeuler/kernel/pulls/2220  sched/qos: Fix warning in CPU hotplug scenarios
        https://gitee.com/openeuler/kernel/pulls/2224  ext4: fix rec_len verify error
        https://gitee.com/openeuler/kernel/pulls/2222  Add new config 'CONFIG_EXT4_ERROR_REPORT' to control ext3/4 error reporting
        https://gitee.com/openeuler/kernel/pulls/2183  livepatch/core: Fix possible issue that old function is not checked
        https://gitee.com/openeuler/kernel/pulls/2210  jbd2: Fix potential data lost in recovering journal raced with synchronizing fs bdev
        https://gitee.com/openeuler/kernel/pulls/1806  SUNRPC: Add cond_resched() at the appropriate point in __rpc_execute()
        https://gitee.com/openeuler/kernel/pulls/1977  fix race between setxattr and write back

近两周(2023.9.11 ~ 9.22)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2309.4.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-20.03-LTS-SP3分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP3/update/


        openEuler-1.0-LTS从 4.19.90-2309.1.0 更新至 4.19.90-2309.4.0, 回合补丁数126个
        git log 4.19.90-2309.1.0..4.19.90-2309.4.0 --oneline | wc -l
        126

        修复8个CVE:
        CVE-2022-45887        
        CVE-2023-20588        
        CVE-2023-21400        
        CVE-2023-4881        
        CVE-2023-4921        
        CVE-2022-40982        
        CVE-2023-4622        
        CVE-2023-4623        
                
        openEuler-1.0-LTS合入PR：
                
                hisilicon：
                https://gitee.com/openeuler/kernel/pulls/2226 crypto: hisilicon/qm - prevent soft lockup in qm_poll_qp()'s loop
                https://gitee.com/openeuler/kernel/pulls/2207 crypto:hisilicon/qm - cache write back before flr and poweroff
                https://gitee.com/openeuler/kernel/pulls/2205 crypto:hisilicon/sec - modify hw endian config
                https://gitee.com/openeuler/kernel/pulls/2056 i2c: hisi: Add gpio bus recovery support
                
                GCC value profile特性:
                https://gitee.com/openeuler/kernel/pulls/2118 Compiler: Backport value profile support to openEuler 20.03 LTS SP3.
                
                社区问题修复以及上游社区bugfix补丁回合：
                https://gitee.com/openeuler/kernel/pulls/2168 net: sched: sch_qfq: Fix UAF in qfq_dequeue()
                https://gitee.com/openeuler/kernel/pulls/2225 media: ttusb-dec: fix memory leak in ttusb_dec_exit_dvb()
                https://gitee.com/openeuler/kernel/pulls/2177 sched/qos: Fix warning in CPU hotplug scenarios
                https://gitee.com/openeuler/kernel/pulls/2206 Fix booting failure on arm64
                https://gitee.com/openeuler/kernel/pulls/2154 netfilter: nftables: exthdr: fix 4-byte stack OOB write
                https://gitee.com/openeuler/kernel/pulls/2140 io_uring: ensure IOPOLL locks around deferred work
                https://gitee.com/openeuler/kernel/pulls/2082 fix CVE-2023-20588
                https://gitee.com/openeuler/kernel/pulls/2084 af_unix: Fix null-ptr-deref in unix_stream_sendpage().
                https://gitee.com/openeuler/kernel/pulls/2071 【openEuler-1.0-LTS】net: openvswitch: don't send internal clone attribute to the userspace
                https://gitee.com/openeuler/kernel/pulls/2089 net/sched: sch_hfsc: Ensure inner classes have fsc curve
                https://gitee.com/openeuler/kernel/pulls/335 efi: fix crash due to EFI runtime service page faults
                https://gitee.com/openeuler/kernel/pulls/2088 [openEuler-1.0-LTS] bugfixes of scsi
                https://gitee.com/openeuler/kernel/pulls/2069 x86/speculation: Add Gather Data Sampling mitigation
                https://gitee.com/openeuler/kernel/pulls/1692 Mainline bugfix patches backport 4.19
                https://gitee.com/openeuler/kernel/pulls/2075 x86/cpu/amd: Enable Zenbleed fix for AMD Custom APU 0405
                https://gitee.com/openeuler/kernel/pulls/2079 [openEuler-1.0-LTS] stable inclusion from linux-4.19.y
                https://gitee.com/openeuler/kernel/pulls/2070 net bugfixes inclusion from linux-4.19.y
                https://gitee.com/openeuler/kernel/pulls/1987 tracing: Fix race issue between cpu buffer write and swap
                https://gitee.com/openeuler/kernel/pulls/2067 memcg: add refcnt for pcpu stock to avoid UAF problem in drain_all_stock()
                https://gitee.com/openeuler/kernel/pulls/2063 cpu/hotplug: Prevent self deadlock on CPU hot-unplug
                https://gitee.com/openeuler/kernel/pulls/2046 use precise io accounting apis
                https://gitee.com/openeuler/kernel/pulls/2050 memcg: fix a UAF problem in drain_all_stock()
                https://gitee.com/openeuler/kernel/pulls/1976 fix race between setxattr and write back

议题二：目前pending PR整理 --- 张伽琳
现状：
数据统计情况：
openeuler/kernel仓库未合入PR：326，OLK-5.10：166，22.03-LTS：39，22.03-LTS-SP1：42，22.03-LTS-SP2：39
OLK-5.10为例：需要跟踪：28，其中100天以内：11
计划：
1、清理历史PR，下个双周例会过清理进展以及疑难PR评审
2、优化筛选机制

4.19PR合入请求：
https://gitee.com/openeuler/kernel/pulls/2038

议题三：mpt3sas raid卡驱动升级评审---张浩
遗漏，相关人员讨论 --- huyong、zhanghao
邮件列表转PR需要先订阅邮件列表：https://mailweb.openeuler.org/postorius/lists/kernel.openeuler.org/

议题四：推出 arm64  64kb 大页内核包 - -- 京东 赵小强
https://gitee.com/openeuler/kernel/issues/I829LP

议题五：新增openEuler内核社区committer Lin Yunsheng ——穆丰演
gitee_id:yunshenglin <linyunsheng@huawei.com>
1、主要负责维护网卡模块（HNS3）、网络page_pool子模块
2、从2017年6月至今在Linux内核社区合入230个patch，review该模块的patch350+
3、之后在社区主要负责网络模块的开发和维护

结论：通过

三、本期遗留问题
1、建议：固定议题介绍pending PR --- 对应责任人
2、清理PR的同时，整理下无人看护的模块
      门禁的回复过多，评审意见淹没在其中，找基础设施讨论

      疑似对comment的reply的修改会触发门禁，找基础设施确认：
      https://gitee.com/openeuler/kernel/pulls/1293

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/9/8 Kernel SIG 双周例会】
轮值主持：张伽琳
下次轮值主持：廖涛
会议链接：https://us06web.zoom.us/j/82146435494?pwd=ek56cW1UYmljbXZXRTlhWVNnRVpLUT09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings
一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.8.28 ~ 9.8)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-160.0.0
        openEuler-22.03-LTS-SP2分支，更新到5.10.0-153.26.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.48.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.110.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-159.0.0 更新至 5.10.0-160.0.0, 回合补丁数101个
        git log 5.10.0-159.0.0..5.10.0-160.0.0 --oneline | wc -l
        101

        回合CVE补丁3个:
        CVE-2023-3866
        CVE-2022-40982
        CVE-2023-3865

        OLK-5.10合入PR:

        zram二次压缩特性
        https://gitee.com/openeuler/kernel/pulls/1954 zs_malloc: return ERR_PTR on failure

        IMA摘要列表特性代码添加宏控进行隔离
        https://gitee.com/openeuler/kernel/pulls/2080 ima: fix the undefined value during the build
        https://gitee.com/openeuler/kernel/pulls/2042 ima: Add macros to isolate the IMA digest list

        jingdong
        https://gitee.com/openeuler/kernel/pulls/1718 ignore the rt /dl task in tg_change_scheduler
        
        Hygon
        https://gitee.com/openeuler/kernel/pulls/1531 [OLK-5.10] Add support for Hygon model 4h~6h processors

        LoongArch:
        https://gitee.com/openeuler/kernel/pulls/1786 LoongArch: export lsx/lasx related struct to user space

        iBMA driver:
        https://gitee.com/openeuler/kernel/pulls/1327 Huawei BMA: To fix the bug in the iBMA driver code

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/2040 iommu/arm-smmu-v3: Fix ECMDQ initialization error and add arm_smmu_v3.disable_ecmdq
        https://gitee.com/openeuler/kernel/pulls/2068 i2c: hisi: Only handle the interrupt of the driver's  transfer
        https://gitee.com/openeuler/kernel/pulls/2055 Only enable unicast promisc when mac table full to fix the hns3 bug
        https://gitee.com/openeuler/kernel/pulls/1928 RDMA/hns Bugfix from mainline linux
        https://gitee.com/openeuler/kernel/pulls/1919 net: hns3: revert some patch and backport some hns3 mainline
        https://gitee.com/openeuler/kernel/pulls/1920 net/hinic3: Add DPU PF device type support.
        https://gitee.com/openeuler/kernel/pulls/1872 Synchronizing mainline HiSilicon uncore PMU patches
        https://gitee.com/openeuler/kernel/pulls/1834 cleanup for RDMA/hns from mainline linux

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/1986 tracing: Fix race issue between cpu buffer write and swap
        https://gitee.com/openeuler/kernel/pulls/1905 tracing: Fix memleak due to race between current_tracer and trace
        https://gitee.com/openeuler/kernel/pulls/1900 tracing: Fix cpu buffers unavailable due to 'record_disabled' missed
        https://gitee.com/openeuler/kernel/pulls/2065 dm: switch to precise io accounting
        https://gitee.com/openeuler/kernel/pulls/1991 sched/smt: fix unbalance sched_smt_present dec/inc
        https://gitee.com/openeuler/kernel/pulls/1966 cpu/hotplug: Prevent self deadlock on CPU hot-unplug
        https://gitee.com/openeuler/kernel/pulls/1965 crypto:padata: Fix return err for PADATA_RESET
        https://gitee.com/openeuler/kernel/pulls/1963 block: don't get gendisk if queue has not been registered
        https://gitee.com/openeuler/kernel/pulls/1883 SUNRPC: don't pause on incomplete allocation
        https://gitee.com/openeuler/kernel/pulls/1446 Fix the default return value of dm_pool_dec_data_range()

遗留：1、目前pending PR整理；2、4.19 进展update

议题二：Intel曾昭荣申请成为maintainer

通过maintainer申请，后续工作需要进一步沟通

征集中，新增议题可直接填入此处

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/8/25 Kernel SIG 双周例会】
轮值主持：桑力鹏
下次轮值主持：张伽琳
会议链接：https://us06web.zoom.us/j/88618764013?pwd=aGc4UU9WL2FpNUxnUFphM24xZDBOZz09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings
一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.8.14 ~ 8.25)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-159.0.0
        openEuler-22.03-LTS-SP2分支，更新到5.10.0-153.24.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.46.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.108.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-158.0.0 更新至 5.10.0-159.0.0, 回合补丁数1352个
        git log 5.10.0-158.0.0..5.10.0-159.0.0 --oneline | wc -l
        1352

        其中
        同步linux 5.10.y社区LTS补丁集10个: 5.10.163 - 5.10.172

        回合CVE补丁11个:
        CVE-2023-1206
        CVE-2023-40283
        CVE-2023-4194
        CVE-2023-20593
        cve-2023-38432
        CVE-2023-4273
        CVE-2023-4128
        CVE-2023-4134
        CVE-2023-4133
        CVE-2023-3867
        CVE-2023-4147

        OLK-5.10合入PR:

        arm64架构使能tlb批量刷新
        https://gitee.com/openeuler/kernel/pulls/1852  arm64: support batched/deferred tlb shootdown during page reclamation/migration

        zram支持二次压缩
        https://gitee.com/openeuler/kernel/pulls/1802  zram: Support multiple compression streams

        arm64架构使能THP SWAP优化
        https://gitee.com/openeuler/kernel/pulls/1796  arm64: enable THP_SWAP for arm64

        支持bonding下xdp功能，增强bonding模式下网络处理能力:
        https://gitee.com/openeuler/kernel/pulls/1520  enable bonding XDP

        新增timer_shutdown[_sync]()接口:
        https://gitee.com/openeuler/kernel/pulls/1727  add support for timer_shutdown() api

        jd:容器级超线程驱逐:
        https://gitee.com/openeuler/kernel/pulls/1623 introduce cgroup level smt expell

        3snic 3s9xx network driver:
        https://gitee.com/openeuler/kernel/pulls/1724 Net: ethernet: Support management channel of the host tool in 3snic 3s9xx network driver
        https://gitee.com/openeuler/kernel/pulls/1597 Fix the bugs of 3SNIC driver compilation failure while using clang

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/1721 [sync] PR-1651: Fix missing dealloc_dfx_cnt() during device unregister
        https://gitee.com/openeuler/kernel/pulls/1671 Backport bugfixes for RDMA/hns from mainline linux
        https://gitee.com/openeuler/kernel/pulls/1719 net: hns3: revert "net: hns3: disbable pfc en before the reset" and backport the mainline
        https://gitee.com/openeuler/kernel/pulls/1201 [sync] PR-1144: crypto: hisilicon/qm: modify loop exit condition

        loongarch:
        https://gitee.com/openeuler/kernel/pulls/1646 Fixed extioi hardware emulation bugs on loongarch

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/1821  nbd: pass nbd_sock to nbd_read_reply() instead of index
        https://gitee.com/openeuler/kernel/pulls/1843  net: bridge: multicast: notify switchdev driver whenever MC processing gets disabled
        https://gitee.com/openeuler/kernel/pulls/1833  xsk: Initialise xskb free_list_node
        https://gitee.com/openeuler/kernel/pulls/1650  mm: disable kernelcore=mirror when no mirror memory
        https://gitee.com/openeuler/kernel/pulls/1768  bonding: Fix incorrect deletion of ETH_P_8021AD protocol vid from slaves
        https://gitee.com/openeuler/kernel/pulls/1766  xen/netback: Fix buffer overrun triggered by unusual packet
        https://gitee.com/openeuler/kernel/pulls/1649 Enable TPM TIS customization
        https://gitee.com/openeuler/kernel/pulls/1734  arm64/mpam: mark partid non-exclusive if self-owned
        https://gitee.com/openeuler/kernel/pulls/1680  nvme-pci: fix doorbell buffer value endianness
        https://gitee.com/openeuler/kernel/pulls/1693  nvme-pci: fix mempool alloc size
        https://gitee.com/openeuler/kernel/pulls/1666  nvme-pci: fix timeout request state check
        https://gitee.com/openeuler/kernel/pulls/1709  Backport cgroup: fix missing cpus_read_{lock,unlock}() in cgroup_transfer_tasks()

议题二：两个Pull Request讨论 --- 曾昭荣

    1，https://gitee.com/openeuler/kernel/pulls/1293

    2，https://gitee.com/openeuler/kernel/pulls/1871


议题三：赵小强申请成为committer 
结论：先成为分支维护的committer，如果想成为某个模块的committer，可以在相应模块做贡献，然后成为相应模块的committer，先提PR更新sig-info.yaml文件和committers.md成为维护分支committer，更新committers.md的configs模块

议题四：龙芯毛碧波申请成为committer
结论：先参与一段时间的社区贡献，再加入commiter，先提PR更新sig-info.yaml和committers.md成为contributors

committer相关信息:
https://gitee.com/openeuler/community/blob/master/sig/Kernel/sig-info.yaml
https://gitee.com/openeuler/community/blob/master/sig/Kernel/committers.md

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/8/11 Kernel SIG 双周例会】
会议时间：2023年8月11日 14:00-15:45
轮值主持：廖涛
下次轮值主持：桑力鹏

会议链接：https://us06web.zoom.us/j/85789825222?pwd=bVcrNXVhVW9ObzVQWjVKdTlBNm14Zz09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
讨论新增陈为珑为kernel sig committer 

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.7.31 ~ 8.11)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-158.0.0
        openEuler-22.03-LTS-SP2分支，更新到5.10.0-153.22.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.44.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.106.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-157.0.0 更新至 5.10.0-158.0.0, 回合补丁数157个
        git log 5.10.0-157.0.0..5.10.0-158.0.0 --oneline | wc -l
        157

        其中
        同步linux 5.10.y社区LTS补丁集3个: 5.10.160 - 5.10.162

        回合CVE补丁15个:
        CVE-2023-3772
        CVE-2023-4004
        CVE-2023-4132
        CVE-2023-32250
        CVE-2023-32252
        CVE-2023-32257
        CVE-2023-38430
        CVE-2023-3863
        CVE-2023-38427
        CVE-2023-3609
        CVE-2023-38426
        CVE-2023-3776
        CVE-2023-38429
        CVE-2023-21255
        CVE-2023-38428

        dynamic affinity for scheduler设置负载统计的方式：
        https://gitee.com/openeuler/kernel/pulls/1630 sched: Add feature 'UTIL_TASKGROUP' for dynamic affinity
        
        sock_ops和sk_msg类型BPF程序支持调用bpf_get_netns_cookie辅助函数：
        https://gitee.com/openeuler/kernel/pulls/1522 Allow bpf_get_netns_cookie in BPF_PROG_TYPE_SK_MSG and BPF_PROG_TYPE_SOCK_OPS

        sharepool代码白盒检视类问题整改：
        https://gitee.com/openeuler/kernel/pulls/1550 Sync patches for sharepool

        LoongArch:
        https://gitee.com/openeuler/kernel/pulls/1618 LoongArch: fix some config not defined

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/1683 net: hns3: revert some bugfix and backport some patch
        https://gitee.com/openeuler/kernel/pulls/1690 uacce: delete the pointer address printing
        https://gitee.com/openeuler/kernel/pulls/1268 [sync] PR-1070: crypto: hisilicon - fix some reset problem
        https://gitee.com/openeuler/kernel/pulls/1659 vfio-pci: Match specific devices with vendor id and device id
        https://gitee.com/openeuler/kernel/pulls/1555 net: hns3: fix setting wrong tx_timeout value issue and synchronizes the differences between the kernel and openeuler

        JD:
        https://gitee.com/openeuler/kernel/pulls/1660 remove cpu.qos_leve from root cpu cgroup
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/1707 Mainline bugfix patches backport 5.10
        https://gitee.com/openeuler/kernel/pulls/1672 tty: fix pid memleak in disassociate_ctty()
        https://gitee.com/openeuler/kernel/pulls/1580 tracing: Fix warning in trace_buffered_event_disable()
        https://gitee.com/openeuler/kernel/pulls/1611 sched: Fix build error for dynamic_affinity_enable()
        https://gitee.com/openeuler/kernel/pulls/1581 psi: fix compile error for psi cgroupv1 when CONFIG_CGROUP=n

        KABI问题:
        https://gitee.com/openeuler/kernel/pulls/1636 blk-mq: Improve performance of non-mq IO schedulers with multiple HW queues


议题二：讨论新增邢明政为arch/riscv目录committer
https://gitee.com/openeuler/community/pulls/4954
参与维护openEuler RISC-V kernel，申请担任邢明政为arch/riscv目录committer
结论：通过

议题三：申请成为committer
    1. 李雪峰 龙芯 giteeid: lixuefeng-loongson
    review补丁:
    https://gitee.com/openeuler/kernel/pulls/1148
    https://gitee.com/openeuler/kernel/pulls/1202
    https://gitee.com/openeuler/kernel/pulls/1618
    提交贡献：
    https://gitee.com/openeuler/kernel/pulls/1157
    https://gitee.com/openeuler/kernel/pulls/1175
    https://gitee.com/openeuler/kernel/pulls/1179
    2.毛碧波 龙芯 giteeid: maobibo
结论：通过

议题四：新增陈为珑为kernel sig committer 
所在部门：华为OS内核实验室
多年Linux开发经验，专长异构内存、内核设备管理、网络、调度系统子系统等领域
目前担任子仓committer ，申请主仓committer 
结论：通过

openEuler社区邮件列表：
https://mailweb.openeuler.org/hyperkitty/list/kernel@openeuler.org/
订阅链接：https://mailweb.openeuler.org/postorius/lists/kernel.openeuler.org/
发送时需要git format-patch --subject-prefix="PATCH branch-name"， 多个补丁的补丁集的话需要加--cover-letter
如：git format-patch --cover-letter --subject-prefix="PATCH OLK-5.10"发到指定的分支才能同步提PR到指定分支。

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/7/28 Kernel SIG 双周例会】
会议时间：2023年7月28日 14:00-15:45
轮值主持：张伽琳
下次轮值主持：桑力鹏

会议链接：https://us06web.zoom.us/j/85789825222?pwd=bVcrNXVhVW9ObzVQWjVKdTlBNm14Zz09
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.7.17 ~ 7.28)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-157.0.0
        openEuler-22.03-LTS-SP2分支，更新到5.10.0-153.20.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.42.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.104.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-156.0.0 更新至 5.10.0-157.0.0, 回合补丁数723个
        git log 5.10.0-156.0.0..5.10.0-157.0.0 --oneline | wc -l
        723

        其中
        同步linux 5.10.y社区LTS补丁集6个: 5.10.154 - 5.10.159

        回合CVE补丁7个:
        CVE-2023-3611
        CVE-2023-3567
        CVE-2023-35001
        CVE-2022-45886
        CVE-2023-3117
        CVE-2023-3338
        CVE-2023-31248

        ARMv8.x 新增特性 lrcpc 回合:
        https://gitee.com/openeuler/kernel/pulls/1437 arm64: enable lrcpc feature of ARMv8.x from mainline

        bonding模块支持双发网卡的ARP:
        https://gitee.com/openeuler/kernel/pulls/1434 anolis: bond: broadcast ARP or ND messages to all slaves

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/1527 arm64/mpam: fix missing kfree domain's ctrl_val arrray
        https://gitee.com/openeuler/kernel/pulls/1548 mm: memcontrol: fix cannot alloc the maximum memcg ID
        https://gitee.com/openeuler/kernel/pulls/1441 workqueue: fix sanity check warning when invoke destroy_workqueue()
        https://gitee.com/openeuler/kernel/pulls/1476 ipv6/addrconf: fix a potential refcount underflow for idev
        https://gitee.com/openeuler/kernel/pulls/1428 scsi: iscsi_tcp: Check that sock is valid before iscsi_set_param()
        https://gitee.com/openeuler/kernel/pulls/1425 loop: loop_set_status_from_info() check before assignment
        https://gitee.com/openeuler/kernel/pulls/1427 nbd: Fix debugfs_create_dir error checking
        https://gitee.com/openeuler/kernel/pulls/1415 Fix generic/299 fail
        Intel:
        https://gitee.com/openeuler/kernel/pulls/1315 Intel: Backport mainline UPI uncore discovery warning fixes for SPR MCC to OLK-5.10
        Zhaoxin
        https://gitee.com/openeuler/kernel/pulls/1475 pmu: remove uncore code for Zhaoxin Platform
        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/1488 RDMA/hns: Remove unnecessary QP type checks
        https://gitee.com/openeuler/kernel/pulls/1184 Fix CQ and QP cache affinity

议题二：容器级 core_pattern 隔离  -- 赵小强 京东
原实现有KABI变更，会后讨论修复方案

议题三：外部驱动引入内核流程说明 --- 刘彦泽

议题四：申请使能 riscv64 架构 -- 邢明政 (ISCAS)

议题五：新增陈为珑为kernel sig committer  
遗留，下次例会讨论


三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/7/14 Kernel SIG 双周例会】
会议时间：2023年7月14日 14:00-15:30
轮值主持：廖涛
下次轮值主持：张伽琳

会议链接：https://us06web.zoom.us/j/84401590636?pwd=MitsdU9RcFYyYnJHWDRSdmRWQzd3UT09

会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.7.3 ~ 7.15)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-156.0.0
        openEuler-22.03-LTS-SP2分支，更新到5.10.0-153.18.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.40.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.102.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以openEuler-22.03-LTS-SP2为例:
        从 5.10.0-153.16.0 更新至 5.10.0-153.18.0, 回合补丁数43个
        git log 5.10.0-153.16.0..5.10.0-153.18.0 --oneline | wc -l
        43
        其中
        openEuler-22.03-LTS-SP2分支回合CVE补丁9个:
        CVE-2023-3268
        CVE-2023-35828
        CVE-2023-31084
        CVE-2023-35824
        CVE-2023-35823
        CVE-2023-3327
        CVE-2023-3358
        CVE-2023-3090
        CVE-2023-3389
        测试发现的问题修复以及上游社区补丁回合：
        https://gitee.com/openeuler/kernel/pulls/1211 [sync] PR-1185:  nbd: validate the block size in nbd_set_size
        https://gitee.com/openeuler/kernel/pulls/1234 [sync] PR-1220:  mm/memory_hotplug: extend offline_and_remove_memory() to handle more than one memory block
        https://gitee.com/openeuler/kernel/pulls/1249 [sync] PR-1245:  hugetlb: Fix some incorrect behavior
        https://gitee.com/openeuler/kernel/pulls/1236 [sync] PR-1194:  fix memleak with efi_fake_mem
        https://gitee.com/openeuler/kernel/pulls/1231 [sync] PR-1191:  fix memory reliable related issues
        https://gitee.com/openeuler/kernel/pulls/1306 [sync] PR-1297:  iommu/iova: move IOVA_MAX_GLOBAL_MAGS outside of IOMMU_SUPPORT
        https://gitee.com/openeuler/kernel/pulls/1344 [sync] PR-1272:  xfs: fix some problems recently

议题二： TDPMMU enabling in OLK
                  eg. about parallel MMU operations with TDP MMU -- Zhang Yu - Intel 
                  Note: please also invite virt-sig maintainer
                  待进一步讨论
议题三：23.09版本策略交流 -- 李炜

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/6/30 Kernel SIG 双周例会】
会议时间：2023年6月30日 14:00-15:30
轮值主持：桑力鹏
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/81270448575?pwd=WElDeFQ1azluejNHcXR0a3Y4R1VHUT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
KABI新增接口：有兼容性SIG分析结论再同步到kernel sig

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.6.19 ~ 6.30)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-155.0.0
        openEuler-22.03-LTS-SP2更新到5.10.0-153.16.0，RC6 5.10.0-153.12.0
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.100.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.38.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以openEuler-22.03-LTS-SP2为例:
        从 5.10.0-153.9.0 更新至 5.10.0-153.16.0, 回合补丁数52个
        git log 5.10.0-153.9.0..5.10.0-153.16.0 --oneline | wc -l
        52

openEuler-22.03-LTS-SP2版本内核总结: https://gitee.com/openeuler/kernel/issues/I7HCHQ

上周遗留： KABI新增接口：兼容性SIG分析结论：https://gitee.com/openeuler/kernel/issues/I7GJJY
议题二：openEuler 2203 sp2 版本 sysmonitor开源内核适配补丁评审 --- 谢堂鑫 & 齐森

议题三：增强mirror memory中hugetlb适配虚拟化场景，并为x86平台使能reliable memory -- 曾昭荣

23.09需求收集里程碑: https://e.gitee.com/open_euler/milestones/185397/issues/table
三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/6/16 Kernel SIG 双周例会】
会议时间：2023年6月16日 14:00-15:30
轮值主持：张伽琳
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/88482572951?pwd=dXV5bFh4Nyt2Z1VpN0NOL3hGSWVHUT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.6.5 ~ 6.16)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-154.0.0
        openEuler-22.03-LTS-SP2更新到5.10.0-153.9.0，RC4转测 5.10.0-153.8.0
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.98.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.36.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以openEuler-22.03-LTS-SP2为例:
        从 5.10.0-153.0.0 更新至 5.10.0-153.9.0, 回合补丁数303个
        git log 5.10.0-153.0.0..5.10.0-153.9.0 --oneline | wc -l
        303

        其中
        openEuler-22.03-LTS-SP2分支回合CVE补丁4个:
        CVE-2022-48502
        CVE-2023-33288
        CVE-2023-2985
        CVE-2023-22998

        openEuler-22.03-LTS-SP2合入PR:
        https://gitee.com/openeuler/kernel/pulls/1140  tools: add sample sockmap code for redis
        https://gitee.com/openeuler/kernel/pulls/1126 [sync] PR-1115:  userswap bugfix
        https://gitee.com/openeuler/kernel/pulls/1125  add one bpf helper function for redissockmap
        https://gitee.com/openeuler/kernel/pulls/1105 [sync] PR-1089:  power: supply: bq24190: Fix use after free bug in bq24190_remove due to race condition
        https://gitee.com/openeuler/kernel/pulls/1110 [sync] PR-1090:  fs/ntfs3: Check fields while reading
        https://gitee.com/openeuler/kernel/pulls/1119 [openEuler-22.03-LTS-SP2] net: hns3: refactor hclge_mac_link_status_wait and add wait until mac link down
        https://gitee.com/openeuler/kernel/pulls/1093 vfio-pci: Match specific devices with vendor id and device id
        https://gitee.com/openeuler/kernel/pulls/1085 irqchip/gicv3-its: Add workaround for hip09 ITS erratum 162100801
        https://gitee.com/openeuler/kernel/pulls/1095 irqchip: gic-v3: Collection table support muti pages
        https://gitee.com/openeuler/kernel/pulls/1081  some backport bugfix for sockmap
        https://gitee.com/openeuler/kernel/pulls/1077  drm/qxl: Fix missing free_irq
        https://gitee.com/openeuler/kernel/pulls/1087 genirq: Increase the number of IRQ descriptors
        https://gitee.com/openeuler/kernel/pulls/1063 i2c: hisi: Only handle the interrupt of the driver's transfer
        https://gitee.com/openeuler/kernel/pulls/1059 [sync] PR-1028:  fs: hfsplus: fix UAF issue in hfsplus_put_super
        https://gitee.com/openeuler/kernel/pulls/1042  xfrm: Reinject transport-mode packets through workqueue
        https://gitee.com/openeuler/kernel/pulls/1069  support ACPI for MPAM 2.0
        https://gitee.com/openeuler/kernel/pulls/1070 crypto: hisilicon - fix some reset problem
        https://gitee.com/openeuler/kernel/pulls/1026 [sync] PR-947:  locking/rwsem: Prevent potential lock starvation
        https://gitee.com/openeuler/kernel/pulls/1022 [sync] PR-978:  io_uring: fix the problem of running
        https://gitee.com/openeuler/kernel/pulls/1045 perf: hisi: delete global enable pmu from xxx_write_counter()
        https://gitee.com/openeuler/kernel/pulls/1037  xfs: fixes patchs and backport patchs
        https://gitee.com/openeuler/kernel/pulls/1048 spi: dw: Add support for 32-bits max xfer size
        https://gitee.com/openeuler/kernel/pulls/1055 Complementing PTT functions to the openEuler-22.03-LTS-SP2
        https://gitee.com/openeuler/kernel/pulls/1005 scsi: hisi_sas: A group of SAS-related bugfixes
        https://gitee.com/openeuler/kernel/pulls/1052 [sync] PR-1027: scripts: Fix issue of module signing with openssl 3.x
        https://gitee.com/openeuler/kernel/pulls/1039 [sync] PR-1032: bugfix the lost interruption problem after live migration
        https://gitee.com/openeuler/kernel/pulls/996 [sync] PR-990:  ubi: Fix deadlock caused by recursively holding work_sem
        https://gitee.com/openeuler/kernel/pulls/1001 [sync] PR-928:  hikey9xx: Fixed incorrect use of kfree to free sreg
        https://gitee.com/openeuler/kernel/pulls/1018 [sync] PR-944:  nbd: get config_lock before sock_shutdown
        https://gitee.com/openeuler/kernel/pulls/1033 perf: hns3: add event suppport for ROH and default use hardware event 0 as group leader event
        https://gitee.com/openeuler/kernel/pulls/1012 [sync] PR-924:  dm: add disk before alloc dax
        https://gitee.com/openeuler/kernel/pulls/1015 [sync] PR-920:  dm thin: Fix ABBA deadlock by resetting dm_bufio_client
        https://gitee.com/openeuler/kernel/pulls/1020 [sync] PR-1003: roh: Fix ROH multi-BD cmdq issue
        https://gitee.com/openeuler/kernel/pulls/1009 [sync] PR-980: crypto: hisilicon - fix mailbox operation process
        https://gitee.com/openeuler/kernel/pulls/952 [sync] PR-929:  xfs: rework feature flags
        https://gitee.com/openeuler/kernel/pulls/982 [sync] PR-356: x86/boot/compressed: Register dummy NMI handler in EFI boot loader, to avoid kdump crashes
        https://gitee.com/openeuler/kernel/pulls/973 [sync] PR-969:  kobject: Fix slab-out-of-bounds in fill_kobj_path()
        https://gitee.com/openeuler/kernel/pulls/988 [sync] PR-954:  block: iocost bugfix
        https://gitee.com/openeuler/kernel/pulls/985 [sync] PR-946:  icost bugfix
        https://gitee.com/openeuler/kernel/pulls/1006 drivers/perf: hisi: Don't migrate perf to the CPU going to teardown
        https://gitee.com/openeuler/kernel/pulls/993 Clean up for RDMA/HNS
        https://gitee.com/openeuler/kernel/pulls/979 [sync] PR-943: Fixed the accelerator capability register issue.
        https://gitee.com/openeuler/kernel/pulls/981 [sync] PR-967:  Support dynamic_hugetlb on arm64 and fix some bug
        https://gitee.com/openeuler/kernel/pulls/989 [sync] PR-940: net: hns3: related bugfixes, refactoring, and cleanup
        https://gitee.com/openeuler/kernel/pulls/992 [sync] PR-949:  mm: page_counter: remove unneeded atomic ops for low/min
        https://gitee.com/openeuler/kernel/pulls/977 [sync] PR-968:  Fix ORC unwinder on paravirt {save,restore}_fl
        https://gitee.com/openeuler/kernel/pulls/964 [sync] PR-937:  tcp: restrict net.ipv4.tcp_app_win
        https://gitee.com/openeuler/kernel/pulls/961 [sync] PR-925:  tcp: prohibit TCP_REPAIR_OPTIONS if data was already sent
        https://gitee.com/openeuler/kernel/pulls/957 [sync] PR-938:  config: Disable CONFIG_EULER_FS by default
        https://gitee.com/openeuler/kernel/pulls/933 [sync] PR-922:  jbd2: fix checkpoint inconsistent
        https://gitee.com/openeuler/kernel/pulls/923 [sync] PR-918: Misc fixes for Kunpeng accelerator drivers!
        https://gitee.com/openeuler/kernel/pulls/914 [sync] PR-906:  ipv6: Add lwtunnel encap size of all siblings in nexthop calculation
        https://gitee.com/openeuler/kernel/pulls/921 [sync] PR-919:  Revert "ext4: dio take shared inode lock when overwriting preallocated blocks"
        https://gitee.com/openeuler/kernel/pulls/898 [sync] PR-894: Fixed two accelerator bugfixes
        https://gitee.com/openeuler/kernel/pulls/908 [sync] PR-874: nic: hns3: fix pointer cast for wol and fix getting GE port lanes error and set cpu affinity
        https://gitee.com/openeuler/kernel/pulls/909 [sync] PR-907:  tcp/dccp: Add another way to allocate local ports in connect()
        https://gitee.com/openeuler/kernel/pulls/893 mitigatin cacheline false sharing
        https://gitee.com/openeuler/kernel/pulls/903 backport block bugfix
        https://gitee.com/openeuler/kernel/pulls/899 [sync] PR-895:  config: enable CONFIG_BPF_STREAM_PARSER=y on arm64
        https://gitee.com/openeuler/kernel/pulls/888 [sync] PR-881: arm64: Keep HWCAP2_WFXT uapi consistent with upstream
        https://gitee.com/openeuler/kernel/pulls/885 [sync] PR-860: [OLK-5.10] Add support for Emerald Rapids to powercap/intel_rapl driver.
        https://gitee.com/openeuler/kernel/pulls/878 Bugfixes for RDMA/hns
        https://gitee.com/openeuler/kernel/pulls/879 [sync] PR-877: sched: fix performance degradation on lmbench
        https://gitee.com/openeuler/kernel/pulls/871 [sync] PR-866:  arm64: kdump: Avoid reserving low memory repeatedly
        https://gitee.com/openeuler/kernel/pulls/872 [sync] PR-863:  Backport CVEs and bugfixes

议题二：
KABI新增接口 --- 张伽琳
https://gitee.com/openeuler/kernel/issues/I7CBAP
https://gitee.com/src-openeuler/kernel/commit/f4b3bcd976db08077e6ccd3741244c785d0bce0c

议题三：smc-r功能以及开源社区对其性能优化方面的介绍
smc-r功能以及其性能优化方面的介绍

议题四：龙芯申请添加两个commiter
@lixuefeng-loongson 李雪峰
@maobibo 毛碧波
结论：先参与一段时间的社区贡献，再加入commiter，先提PR更新openEuler/MAINTAINERS

三、本期遗留问题
KABI新增接口：有兼容性SIG分析结论再同步到kernel sig

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/6/2 Kernel SIG 双周例会】
会议时间：2023年6月2日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/89684516659?pwd=QWwyVURRUlhpVjY1RmhTVFFqeit3Zz09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.5.22 ~ 6.2)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-153.0.0 -> openEuler-22.03-LTS-SP2
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.96.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.34.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以OLK-5.10为例:
        从 5.10.0-149.0.0 更新至 5.10.0-153.0.0, 回合补丁数349个
        git log 5.10.0-149.0.0..5.10.0-153.0.0 --oneline | wc -l
        349

        其中
        OLK-5.10分支回合CVE补丁2个:
        CVE-2023-32233
        CVE-2023-2124

        同步linux 5.10.y社区LTS补丁集2个：5.10.152...5.10.153

        OLK-5.10合入PR:

        混部CPU多优先级特性:
        sched/fair: Introduce multiple qos level https://gitee.com/openeuler/kernel/pulls/795

        uswap特性:
        Support userswap feature https://gitee.com/openeuler/kernel/pulls/786

        进程、容器级别KSM使能:
        mm: enable ksm per process and cgroup https://gitee.com/openeuler/kernel/pulls/790

        GCC value profile特性:
        Compiler: Add value profile support for kernel. https://gitee.com/openeuler/kernel/pulls/773

        华为智能网卡hinic3驱动:
        Add Huawei Intelligent Network Card Driver: hinic3 https://gitee.com/openeuler/kernel/pulls/835
        
        云芯智联3snic网卡驱动:
        Net: ethernet: Support 3snic 3s9xx network card https://gitee.com/openeuler/kernel/pulls/608

        查询BPF程序是否附加到sockmap:
        bpf: support BPF_PROG_QUERY for progs attached to sockmap https://gitee.com/openeuler/kernel/pulls/798
        
        x86开启CONFIG_BCACHE内核配置:
        openEuler supports bcache by default on x86 platforms https://gitee.com/openeuler/kernel/pulls/782
        
        performance:
        A patchset of sched to improve benchmark performance https://gitee.com/openeuler/kernel/pulls/844

        kvm:
        fix  test_vmxon failed https://gitee.com/openeuler/kernel/pulls/601
        Fix kvm-unit-tests  vmx_cr4_osxsave_test  case failed https://gitee.com/openeuler/kernel/pulls/739

        hisilicon:
        net: hns3: add support for Hisilicon ptp sync device https://gitee.com/openeuler/kernel/pulls/842
        Backport bugfixes for RDMA/hns https://gitee.com/openeuler/kernel/pulls/837
        ACC support no-sva feature https://gitee.com/openeuler/kernel/pulls/803
        perf/smmuv3: Enable HiSilicon Erratum quirk https://gitee.com/openeuler/kernel/pulls/851
        Support T6 ETM and Workaround CPU hung bug on hip09 https://gitee.com/openeuler/kernel/pulls/848
        Add support for HiSilicon UC/H60PA/PAv3 PMU driver https://gitee.com/openeuler/kernel/pulls/805
        crypto: hisilicon/qm - support dumping stop queue status https://gitee.com/openeuler/kernel/pulls/791
        scsi: hisi_sas: The IO timeout mechanism and error handling related bugfix https://gitee.com/openeuler/kernel/pulls/794

        Intel EMR Support:
        intel: backport  uncore-freq current  frequency sysfs related patches https://gitee.com/openeuler/kernel/pulls/840
        intel: backport intel-pstate patches for Server platforms https://gitee.com/openeuler/kernel/pulls/839
        x86 FPU/AMX bug fix since kernel v5.18 https://gitee.com/openeuler/kernel/pulls/789
        Intel: Support In Field Scan(IFS) Array BIST https://gitee.com/openeuler/kernel/pulls/787
        Intel: backport split lock EMR  CPU support for OLK 5.10 https://gitee.com/openeuler/kernel/pulls/781

        LoongArch:
        LoongArch: kvm: add pv ipi support https://gitee.com/openeuler/kernel/pulls/793
        LoongArch: defconfig: enable memory and pci hotplug related configs for LoongArch https://gitee.com/openeuler/kernel/pulls/809
        net: stmmac: fix potential double free of dma descriptor resources https://gitee.com/openeuler/kernel/pulls/761
        LoongArch: kvm: fix bug of kvm's hugepage https://gitee.com/openeuler/kernel/pulls/760
        LoongArch: fix some stability issues https://gitee.com/openeuler/kernel/pulls/765

        Zhaoxin:
        [OLK-5.10] cpufreq: ACPI: Add Zhaoxin/Centaur turbo boost control interface support https://gitee.com/openeuler/kernel/pulls/547
        [OLK-5.10] ACPI, x86: Improve Zhaoxin processors support for NONSTOP TSC https://gitee.com/openeuler/kernel/pulls/544
        [OLK-5.10] x86/acpi/cstate: Optimize ARB_DISABLE on Centaur CPUs https://gitee.com/openeuler/kernel/pulls/545

        sw64:
        update patches for sw64 architecture https://gitee.com/openeuler/kernel/pulls/777

        3snic:
        Net: ethernet: 3snic 3s9xx network driver add "select NET_DEVLINK" https://gitee.com/openeuler/kernel/pulls/824

        m1600:
        Net: m1600: Fix build err https://gitee.com/openeuler/kernel/pulls/820

议题二：
混部CPU多优先级特性   -- 赵文晖
loongarch kdump 支持情况介绍  -- 唐友灵

议题三：
京东-桑力鹏申请成为Maintainer   -- 桑力鹏
总结京东在openEuler上的贡献，探讨进一步合作，期待深入参与到openEuler社区工作
个人处理了900+issue，参与评审PR
结论：通过

议题四：
openEuler kernel Maintainer 职责说明、申请机制讨论

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/5/19 Kernel SIG 双周例会】
会议时间：2023年5月19日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/87319358677?pwd=dVFTTkYxNTR0TStZUEVsWFZaVmtOUT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
需求PR审视、简单汇报

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.5.8 ~ 5.19)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-149.0.0
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.94.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.32.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以OLK-5.10为例:
        从 5.10.0-148.0.0 更新至 5.10.0-149.0.0, 回合补丁数365个
        git log 5.10.0-148.0.0..5.10.0-149.0.0 --oneline | wc -l
        365

        其中
        OLK-5.10分支回合CVE补丁13个:
        CVE-2023-32269
        CVE-2023-2002
        CVE-2023-26544
        CVE-2023-0459
        CVE-2022-4382
        CVE-2023-0458
        CVE-2023-2269
        CVE-2023-2483
        CVE-2023-31436
        CVE-2023-2194
        CVE-2023-2166
        CVE-2023-2176
        CVE-2023-2007

        同步linux 5.10.y社区LTS补丁集1个：5.10.151

        OLK-5.10合入PR:

        DAMON:
        DAMON features: Support for process-level hot and cold data recognition and adjustment. https://gitee.com/openeuler/kernel/pulls/763

        QOS_SMT_EXPELL priority reversion mechanism:
        sched/fair: Introduce QOS_SMT_EXPELL priority reversion mechanism https://gitee.com/openeuler/kernel/pulls/640

        m1600:
        Net: m1600: Support nebula-matrix m1600-series network card https://gitee.com/openeuler/kernel/pulls/570

        kvm:
        arm64: Add initial support for FEAT_WFxT https://gitee.com/openeuler/kernel/pulls/629

        timekeeping:
        timekeeping: Make  CLOCKSOURCE_VALIDATE_LAST_CYCLE configurable https://gitee.com/openeuler/kernel/pulls/772

        Intel EMR Support:
        intel: backport intel-idle support for EMR https://gitee.com/openeuler/kernel/pulls/749
        intel: backport intel-uncore-freq support for EMR https://gitee.com/openeuler/kernel/pulls/748
        SPR: EDAC driver enhance for driver decode and 2LM https://gitee.com/openeuler/kernel/pulls/742
        Intel: Add PMU support for Intel Emerald Rapids https://gitee.com/openeuler/kernel/pulls/622
        Intel: Add RAPL support for Emerald Rapids(EMR) https://gitee.com/openeuler/kernel/pulls/615
        Intel SPR fast rep string operations support https://gitee.com/openeuler/kernel/pulls/624
        Intel: SGX incremental backporting patches until upstream 6.3 https://gitee.com/openeuler/kernel/pulls/594
        Intel: Recover two microcode interfaces when support In Field Scan(IFS) multi-blob images https://gitee.com/openeuler/kernel/pulls/580
        OLK-5.10: x86/cpu: Add several Intel server CPU model numbers https://gitee.com/openeuler/kernel/pulls/469

        LoongArch:
        LoongArch: add kexec&kdump support https://gitee.com/openeuler/kernel/pulls/766
        net: hns3: Backport wol feature and some hns3 bugfix https://gitee.com/openeuler/kernel/pulls/758
        usb: disable soft retry for EJ188 controller https://gitee.com/openeuler/kernel/pulls/564

        hisilicon:
        Accelerator Linux Mainline Patch Round https://gitee.com/openeuler/kernel/pulls/634
        sched/fair: Scan cluster before scanning LLC in wake-up path https://gitee.com/openeuler/kernel/pulls/169
        backport some bug fix for page pool https://gitee.com/openeuler/kernel/pulls/678
        drivers/coresight: Add UltraSoc System Memory Buffer driver https://gitee.com/openeuler/kernel/pulls/596
        backport some PCC driver patches https://gitee.com/openeuler/kernel/pulls/636

        arm64/mpam
        arm64/mpam: modify mpam irq register error log https://gitee.com/openeuler/kernel/pulls/753
        
        driver/hifc&hinic:
        driver/hifc&hinic: Fix compile error in allyesconfigs https://gitee.com/openeuler/kernel/pulls/675

        zhaoxin:
        [HUST CSE] fix a use-after-free bug in uncore_pci_remove() https://gitee.com/openeuler/kernel/pulls/665


议题二：SP2特性串讲
        DAMON特性: https://gitee.com/openeuler/kernel/issues/I6MRUG
        DAMON features: Support for process-level hot and cold data recognition and adjustment. https://gitee.com/openeuler/kernel/pulls/763

        混部SMT驱离防止优先级反转特性: https://gitee.com/openeuler/kernel/issues/I6SIY2
        sched/fair: Introduce QOS_SMT_EXPELL priority reversion mechanism https://gitee.com/openeuler/kernel/pulls/640

        Introduce dynamic affinity for scheduler: https://gitee.com/openeuler/kernel/issues/I526XC
        sched: Supprot dynamic affinity in scheduler https://gitee.com/openeuler/kernel/pulls/256

三、本期遗留问题


温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/5/5 Kernel SIG 双周例会】
会议时间：2023年5月5日 14:00-15:30
轮值主持：郑增凯
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/84858762199?pwd=WVE1eGJXcEp1K1FYcDM1U0k3L2Z3QT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯
近两周(2023.4.17 ~ 5.5)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-148.0.0
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.92.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.30.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以OLK-5.10为例:
        从 5.10.0-147.0.0 更新至 5.10.0-148.0.0, 回合补丁数533个
        git log 5.10.0-147.0.0..5.10.0-148.0.0 --oneline | wc -l
        533

        其中
        OLK-5.10分支回合CVE补丁14个:
        CVE-2023-1855
        CVE-2023-2006
        CVE-2023-30772
        CVE-2023-1872
        CVE-2023-1829
        CVE-2022-36280
        CVE-2022-1015
        CVE-2023-1989
        CVE-2023-30456
        CVE-2023-1990
        CVE-2023-1998
        CVE-2023-1859
        CVE-2023-1670
        CVE-2023-1611

        同步linux 5.10.y社区LTS补丁集1个：5.10.150

        OLK-5.10合入PR:

        hisi_sas:
        The driver modifies the configuration of SAS link establishment and link stability. https://gitee.com/openeuler/kernel/pulls/644
        Bugfixes related to SAS error handling, DIF, and low power consumption https://gitee.com/openeuler/kernel/pulls/618
        SAS-related bugfix：rolls back these policies without disabling the hard disk PHY. https://gitee.com/openeuler/kernel/pulls/503
        
        RDMA/hns:
        Fix errors related to bond and rq inline https://gitee.com/openeuler/kernel/pulls/639
        Support geting xrcd num from firmware https://gitee.com/openeuler/kernel/pulls/617
        Add SVE DIRECT WQE flag to support libhns https://gitee.com/openeuler/kernel/pulls/581

        net/hns3:
        net: hns3: add support handling tx dhcp packets for  ROH https://gitee.com/openeuler/kernel/pulls/381
        net: hns3: supports customization requirements https://gitee.com/openeuler/kernel/pulls/616
        net: hns3: add supports customization requirements and fix vf fault detect err https://gitee.com/openeuler/kernel/pulls/611
        
        AMD:
        AMD: Fix build warning. https://gitee.com/openeuler/kernel/pulls/625
        
        pci:
        vfio/pci: Fix mistakenly deleted "vdev->num_regions" https://gitee.com/openeuler/kernel/pulls/630
        PCI: Support BAR sizes up to 8TB https://gitee.com/openeuler/kernel/pulls/600
        
        SP2 PR 最晚6月3日之前合入

议题二：内核热升级社区进展与讨论  --- 曾昭荣
介绍业界内核热升级发展动态：开源操作系统技术年度会议 字节跳动基础架构部内核团队 -- 面向云服务的内核热升级探索

议题三：openEuler-1.0-LTS maintainer由原来的裘来彬更新成章昌仲
擅长领域：网络
主要负责：版本发布、CVE闭环
结论：通过

      

三、本期遗留问题
需求PR审视、简单汇报

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/4/7 Kernel SIG 双周例会】
会议时间：2023年4月7日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/88353599877?pwd=aFZtMjJwUHl1UmNTZFV4eUJQM2xVdz09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update --- 张伽琳 & 郑增凯

近两周(2023.3.27 ~ 4.7)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-147.0.0
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.89.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.27.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以OLK-5.10为例：
        从 5.10.0-145.0.0 更新至 5.10.0-147.0.0, 回合补丁数91个
        git log 5.10.0-145.0.0..5.10.0-147.0.0 --oneline | wc -l
        91

        其中
        OLK-5.10分支回合CVE补丁12个：
        CVE-2023-1513
        CVE-2022-4269
        CVE-2023-0266
        CVE-2023-1281
        CVE-2022-48423
        CVE-2023-1249
        CVE-2022-48425
        CVE-2022-48424
        CVE-2023-28327
        CVE-2023-28466
        CVE-2023-1380
        CVE-2023-23004

        OLK-5.10合入PR:

        LoongArch:
        LoongArch: fix compile warnning of drm/loongson driver https://gitee.com/openeuler/kernel/pulls/539
        LoongArch: fix dual-bridge machine can not work https://gitee.com/openeuler/kernel/pulls/510
        Loongson: fix 7a2000 gpu driver can not work https://gitee.com/openeuler/kernel/pulls/509

        Hisilicon:
        net: hns3: modify reset delay time to avoid configuration timeout https://gitee.com/openeuler/kernel/pulls/556
        Disable local invalidate operation, fix memory leak and error code of CMD https://gitee.com/openeuler/kernel/pulls/538
        i2c: hisi: Only use the completion interrupt to finish the transfer and i2c: hisi: Avoid redundant interrupts https://gitee.com/openeuler/kernel/pulls/527
        net: hns3: add supports storage product scustomization requirements https://gitee.com/openeuler/kernel/pulls/525
        Add new command to support query vf caps https://gitee.com/openeuler/kernel/pulls/519

        KVM:
        KVM: arm64: Add minimal handling for the ARMv8.7 PMU https://gitee.com/openeuler/kernel/pulls/507

        sssraid:
        SCSI: SSSRAID: Fix the bug that system automatically reboot when issue a 'pcie-linkdown' command https://gitee.com/openeuler/kernel/pulls/508
        
        PR先合主干，后续拉SP2分支

议题二：openEuler-22.03-LTS-SP2需求评审 
Intel EMR Support  -- 曾昭荣（Intel 新CPU前期支持，小新特性提交）
Introduce dynamic affinity for scheduler    -- 唐辉（解决服务器多核场景下的业务干扰问题，PR已提）
混部SMT驱离防止优先级反转特性  -- 关景
Damon 特性  -- 左泽（内存访问框架，新特性合入）
Kernel新增星云智联板卡N1045XS网卡驱动  -- 刘彦泽
建议开启x86架构 的CONFIG_BCACHE内核配置 -- 朱超

议题三：新增兼容性组committer ---刘彦泽
https://gitee.com/openeuler/community/pulls/4604
新增：杜开田（@jimmy_hero）、刘彦泽（@ygn-ndwd-official）为Kernel SIG组的committer
代表Compatibility-Infra SIG组，负责第三方驱动支持

结论：通过

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/3/24 Kernel SIG 双周例会】
会议时间：2023年3月24日 14:00-15:30
轮值主持：郑增凯
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/85131900036?pwd=RFZVYlZFK3B1RVhpTHROOW82OTdLQT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（10min）  --- 张伽琳 & 郑增凯
近两周(2023.3.13 ~ 3.24)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-145.0.0
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.86.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.24.0，
                release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以OLK-5.10为例：
        从 5.10.0-144.0.0 更新至 5.10.0-145.0.0, 回合补丁数188个
        git log 5.10.0-144.0.0..5.10.0-145.0.0 --oneline | wc -l
        188

        其中
        OLK-5.10分支回合CVE补丁5个：
        CVE-2023-28328
        CVE-2023-1382
        CVE-2023-1079
        CVE-2023-1074
        CVE-2023-23000

        OLK-5.10合入PR:

        LoongArch:
        LoongArch: fix failed to boot https://gitee.com/openeuler/kernel/pulls/476
        LoongArch: update network related default config https://gitee.com/openeuler/kernel/pulls/479
        LoongArch: fix some pci problems https://gitee.com/openeuler/kernel/pulls/448
        tools: fix compile error introduced by LoongArch commit https://gitee.com/openeuler/kernel/pulls/477
        add perf loongarch support https://gitee.com/openeuler/kernel/pulls/447
        LoongArch: add kvm support https://gitee.com/openeuler/kernel/pulls/449
        LoongArch: fix compile error when using make allmodconfig https://gitee.com/openeuler/kernel/pulls/466
        LoongArch: some LS7a device drivers support and LoongArch bug fix https://gitee.com/openeuler/kernel/pulls/444

        Hisilicon hns:
        Support congestion control algorithm parameter configuration https://gitee.com/openeuler/kernel/pulls/475
        Support the feature of querying stats https://gitee.com/openeuler/kernel/pulls/427

        Intel In Field Scan (IFS):
        Intel: Support In Field Scan(IFS) multi-blob images https://gitee.com/openeuler/kernel/pulls/471

        security landlock:
        Add landlock support https://gitee.com/openeuler/kernel/pulls/388

        sw64 architecture:
        update patches for sw64 architecture https://gitee.com/openeuler/kernel/pulls/425
        
        openEuler-22.03-LTS-SP2 需求收集，
        需求收集截止时间20230407
     

议题二： Intel In Field Scan multi-test images的支持 --- 施爱春

议题三：新增鲲鹏committer
https://gitee.com/openeuler/community/pulls/4501/
https://gitee.com/openeuler/kernel/pulls/424/
结论：通过

三、本期遗留问题

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/3/10 Kernel SIG 双周例会】
会议时间：2023年3月10日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/87191608489?pwd=eG96T0p2Y0NDRUdHOW9SYys5SElTQT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪
1、openEuler缺陷issue处理流程介绍
2、内核热升级下一步规划，需求讨论

二、议题列表

议题一：进展update（10min）  --- 张伽琳 & 郑增凯
近两周(2023.2.27 ~ 3.10)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-144.0.0
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.84.0，
                对应rpm包下载地址: https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.22.0，
                release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        
        以OLK-5.10为例：
        从 5.10.0-143.0.0 更新至 5.10.0-144.0.0, 回合补丁数157个
        git log 5.10.0-143.0.0..5.10.0-144.0.0 --oneline | wc -l
        157

        其中：
        OLK-5.10分支回合CVE补丁14个：
        CVE-2023-23000
        CVE-2023-1118
        CVE-2023-1073
        CVE-2022-27672
        CVE-2023-0461
        CVE-2023-1075
        CVE-2023-22995
        CVE-2023-26607
        CVE-2023-1078
        CVE-2023-1076
        CVE-2023-26545
        CVE-2023-0045
        CVE-2023-20938
        CVE-2023-0240

        OLK-5.10合入PR:
        scsi:
        scsi:sssraid: Introduce map_queue in sssraid module & code quality reinforcement content https://gitee.com/openeuler/kernel/pulls/426
        sharepool:
        OLK-5.10 backport sharepool and config isolation patches https://gitee.com/openeuler/kernel/pulls/443
        hbm:
        add drivers to support hbm memory and hbm cache https://gitee.com/openeuler/kernel/pulls/451
        ACPI:
        ACPI: Add Platform Runtime Mechanism(PRM) feature support https://gitee.com/openeuler/kernel/pulls/413
        RDMA/hns:
        Fixed the following errors: The reset with stream fails, the query of AH attr is invalid and the RoCE Bonding https://gitee.com/openeuler/kernel/pulls/402
        netswift:
        [5.10]Make Multiple functions On Netswift PCIE NIC belong to different IOMMU group https://gitee.com/openeuler/kernel/pulls/332

议题二：内核热升级使用及技术探讨和规划  ---桑琰
内核热升级技术原理介绍；应用场景、升级时间、下一步工作规划等讨论
与超聚变、intel、云核等加强后续交流探讨，看能否进一步合作

议题三：kernel sig committer新增：

    桑力鹏( 京东科技)：在离线混部（调度、内存、I/O、虚拟化、容器）、自研特性、几十人团队支撑

    结论：通过，具体子系统征求其他模块committer意见，逐步深入

     李炜(华为)：ARM体系结构

    结论：通过


三、本期遗留问题


温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/2/24 Kernel SIG 双周例会】
会议时间：2023年2月24日 14:00-15:30
轮值主持：郑增凯
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/82111503728?pwd=TWRGa2REc0V2ZmlGZ2ZreUF1OXA3dz09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（10min）  --- 张伽琳 & 郑增凯
近两周(2023.2.10 ~ 2.24)内进展同步：
        总体上
        OLK-5.10主干更新tag 至5.10.0-142.0.0
        openEuler-22.03-LTS维护分支更新tag至5.10.0-60.82.0，
                对应rpm包下载地址：https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.20.0，
                release ISO获取链接： https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址：
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
        以openEuler-22.03-LTS-SP1为例：
        从5.10.0-136.18.0 更新至5.10.0-136.20.0，回合补丁数395个
        git log 5.10.0-136.18.0..5.10.0-136.20.0 --oneline | wc -l
        395
        主要是CVE，内存、网络、文件系统相关bugfix，同步linux 5.10.y 社区LTS补丁集
        
        openEuler-22.03-LTS-SP1分支回合CVE补丁2个:
        CVE-2023-0597
        CVE-2023-0615

        同步linux 5.10.y 社区LTS补丁集7个：5.10.143 - 5.10.149

        openEuler-22.03-LTS-SP1合入PR: 2 个:
        net:
        anolis: bond: broadcast ARP or ND messages to all slaves https://gitee.com/openeuler/kernel/pulls/346
        kvm:
        kvm: arm64: fix some pvsched bugs https://gitee.com/openeuler/kernel/pulls/404

议题二：openeuler 实时内核（PREEMPT_RT）规划讨论  --丁翔

议题三：Industrial-Control SIG ROADMAP 完成情况介绍  --郭浩（麒麟软件）

三、本期遗留问题
1、openEuler缺陷issue处理流程介绍
2、内核热升级下一步规划，需求讨论

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/2/10 Kernel SIG 双周例会】
会议时间：2023年2月10日 14:00-15:30
轮值主持：廖涛
下次轮值主持：郑增凯

会议链接：https://us06web.zoom.us/j/82433422280?pwd=S2FtQmg2cTVJdUpZeExoOGNyRzlUQT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（10min）  --- 张伽琳 & 郑增凯
近两周(2023.1.30 ~ 2.10)内进展同步：
        总体上
        OLK-5.10主干更新tag 至5.10.0-142.0.0
        openEuler-22.03-LTS维护分支更新tag至5.10.0-60.80.0，
                对应rpm包下载地址：https://repo.openeuler.org/openEuler-22.03-LTS/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.18.0，
                release ISO获取链接： https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址：
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/aarch64/Packages/
                
        以openEuler-22.03-LTS-SP1为例：
        从5.10.0-136.16.0 更新至5.10.0-136.18.0，回合补丁数142个
        git log 5.10.0-136.16.0..5.10.0-136.18.0 --oneline | wc -l
        142
        主要是内存、文件系统相关bugfix和CVE
        
        openEuler-22.03-LTS-SP1分支回合CVE补丁8个:
        CVE-2022-3707
        CVE-2023-0394
        CVE-2023-0590
        CVE-2022-47929
        CVE-2023-0179
        CVE-2023-23454
        CVE-2023-23455
        CVE-2023-23559

        同步linux 5.10.y 社区LTS补丁集2个：5.10.141 - 5.10.142

        OLK-5.10合入PR: 4 个:
        Hisilicon:
        net: hns3: Some bugfix about L3E check, promisc mode update, FD counter rules and rss config for HNS3 https://gitee.com/openeuler/kernel/pulls/365
        Virtualization:
        AMD: Support svm guest when host CR4.LA57 is set. https://gitee.com/openeuler/kernel/pulls/362
        Fix virtio-gpu free issues https://gitee.com/openeuler/kernel/pulls/360
        mm:
        machine check safe review issue modification https://gitee.com/openeuler/kernel/pulls/354

        社区运维：
                        新增了一份openEuler kernel贡献通用流程：
                        Generic steps to contribute to openEuler kernel
                        https://gitee.com/openeuler/kernel/wikis/Generic%20steps%20to%20contribute%20to%20openEuler%20kernel?sort_id=7738111
                        
                        openEuler/kernel PR门禁变更：
                        新增了checkpatch/checkformat/checkdepend检查项
                        
                        openeuler-ci-bot Get Maintainers 回显功能准备上线
                        
                        需求管理：
                        使用gitee自带的milestones里程碑跟踪openEuler-22.03-LTS-SP2需求，各开发者可以提前录入跟踪：
                        https://e.gitee.com/open_euler/milestones/181999/issues/table
                        
                        希望创建一个openEuler kernel特性支持看板

议题二：英特尔平台几个复杂特性的代码情况说明和讨论 --- 曾昭荣
主要介绍了两个变动较大的复杂特性：TDX和IOMMUFD/VTD-Nested/SIOV
结论：变动较大的复杂特性，建议结合应用场景进一步描述，需要统筹多方共同商讨

三、本期遗留问题
1、

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2023/1/13 Kernel SIG 双周例会】
会议时间：2023年1月13日 14:00-15:30
轮值主持：郑增凯
下次轮值主持：廖涛

会议链接：https://us06web.zoom.us/j/82433422280?pwd=S2FtQmg2cTVJdUpZeExoOGNyRzlUQT09
 
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（10min）  --- 郑增凯

议题二：新增张伽琳为kernel sig committer
通过

三、本期遗留问题
1、

温馨提醒：请在接入会议后修改参会人的姓名，也可以使用您在gitee.com的ID
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------