-------------------------------------------------------------------------------------------------------------------------------------
【2024/12/20 Kernel SIG 双周例会】
轮值主持：廖涛 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：曾昭荣
会议链接：https://meeting.huaweicloud.com:36443/#/j/961056722
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（李楠&仉鹏）
OLK-5.10进展同步
近两周(2024.12.6 ~ 12.20)内进展同步:
                OLK-5.10主干更新到tag 5.10.0-242.0.0
                openEuler-22.03-LTS-SP3、SP4分支，更新到tag 5.10.0-242.0.0
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
                openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.104.0，
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
                从 5.10.0-239.0.0 更新至 5.10.0-242.0.0, 回合补丁数197个
                git log 5.10.0-239.0.0..5.10.0-242.0.0 --oneline --no-merges  | wc -l
 
CVE（31）:
        CVE-2024-50201  https://gitee.com/openeuler/kernel/pulls/13995
        CVE-2024-49991  https://gitee.com/openeuler/kernel/pulls/14008
        CVE-2024-49906  https://gitee.com/openeuler/kernel/pulls/13948
        CVE-2024-50116  https://gitee.com/openeuler/kernel/pulls/14010
        CVE-2024-49861  https://gitee.com/openeuler/kernel/pulls/13988
        CVE-2022-48868  https://gitee.com/openeuler/kernel/pulls/14172
        CVE-2024-50267  https://gitee.com/openeuler/kernel/pulls/14092
        CVE-2024-50103  https://gitee.com/openeuler/kernel/pulls/13871
        CVE-2024-50290  https://gitee.com/openeuler/kernel/pulls/14124
        CVE-2024-49993  https://gitee.com/openeuler/kernel/pulls/14024
        CVE-2024-53130  https://gitee.com/openeuler/kernel/pulls/14104
        CVE-2024-40927  https://gitee.com/openeuler/kernel/pulls/14043
        CVE-2024-50127  https://gitee.com/openeuler/kernel/pulls/14054
        CVE-2024-53104  https://gitee.com/openeuler/kernel/pulls/14114
        CVE-2024-49863  https://gitee.com/openeuler/kernel/pulls/14007
        CVE-2024-50218  https://gitee.com/openeuler/kernel/pulls/14137
        CVE-2024-49923  https://gitee.com/openeuler/kernel/pulls/14027
        CVE-2024-50302  https://gitee.com/openeuler/kernel/pulls/14073
        CVE-2024-47713  https://gitee.com/openeuler/kernel/pulls/14055
        CVE-2024-53114  https://gitee.com/openeuler/kernel/pulls/14142
        CVE-2024-50272  https://gitee.com/openeuler/kernel/pulls/14006
        CVE-2024-53125  https://gitee.com/openeuler/kernel/pulls/14119
        CVE-2024-50292  https://gitee.com/openeuler/kernel/pulls/14018
        CVE-2024-50187  https://gitee.com/openeuler/kernel/pulls/14009
        CVE-2024-50278  https://gitee.com/openeuler/kernel/pulls/14033
        CVE-2024-53142  https://gitee.com/openeuler/kernel/pulls/14149
        CVE-2024-53112  https://gitee.com/openeuler/kernel/pulls/14086
        CVE-2024-50134  https://gitee.com/openeuler/kernel/pulls/14030
        CVE-2024-53054  https://gitee.com/openeuler/kernel/pulls/14062
        CVE-2024-53095  https://gitee.com/openeuler/kernel/pulls/14046
        CVE-2024-53110  https://gitee.com/openeuler/kernel/pulls/14064
 
Bugfix（14）:
mm: only enforce minimum stack gap size if it's sensible
                https://gitee.com/openeuler/kernel/pulls/14123
watchdog/perf: properly initialize the turbo mode timestamp and rearm counter
                https://gitee.com/openeuler/kernel/pulls/14196
xfs: allow inode inactivation during a ro mount log recovery
                https://gitee.com/openeuler/kernel/pulls/14180
bus: integrator-lm: fix OF node leak in probe()
                https://gitee.com/openeuler/kernel/pulls/14129
nfs: fix the loss of superblock's initialized flags
                https://gitee.com/openeuler/kernel/pulls/14193
perf cs-etm: Use evlist__event2evsel() in cs-etm.c
                https://gitee.com/openeuler/kernel/pulls/14216
v2  xfs: revert fix patchs about attr inactive
                https://gitee.com/openeuler/kernel/pulls/14148
intel: backport TPMI base driver and PMT fix and update for 5.10
                https://gitee.com/openeuler/kernel/pulls/13917
Intel: backport intel uncore frequency driver update and bugfix from 6.11
                https://gitee.com/openeuler/kernel/pulls/14146
Intel: backport ISST driver update and bugfix from 6.11
                https://gitee.com/openeuler/kernel/pulls/14145
RDMA/hns: Fix flush cqe error when racing with destroy qp
                https://gitee.com/openeuler/kernel/pulls/13896
ACPI: Fix Generic Initiator Affinity _OSC bit
                https://gitee.com/openeuler/kernel/pulls/14057
v2  ACPI: APEI: handle synchronous errors in task work
                https://gitee.com/openeuler/kernel/pulls/14132
IMA: Fix hungtask issue of digestlist importing
                https://gitee.com/openeuler/kernel/pulls/13401
​ 
feature
cpufreq: Add SEEP governor for hardware-managed P-states
                https://gitee.com/openeuler/kernel/pulls/13327
Script execution control
                https://gitee.com/openeuler/kernel/pulls/13903
 
amd
AMD Genoa and Turin Perf patches backport for OLK-5.10
                https://gitee.com/openeuler/kernel/pulls/12311
AMD Genoa and Turin iommu patches backport for OLK-5.10
                https://gitee.com/openeuler/kernel/pulls/12266
AMD Genoa and Turin Crypto and Edac patches backport for OLK-5.10
                https://gitee.com/openeuler/kernel/pulls/12309
 
海思
RDMA/hns: backport some bugfix from maillist linux
                https://gitee.com/openeuler/kernel/pulls/14109
sdma-dae: bugfix of channel operation
                https://gitee.com/openeuler/kernel/pulls/14041
drivers/perf: hisi: Add support for HiSilicon DDRC v3 PMU driver
                https://gitee.com/openeuler/kernel/pulls/14087
perf: Add PMCG platform information for HiSilicon HIP09A
                https://gitee.com/openeuler/kernel/pulls/14121
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20241220：
OLK-6.6进展同步：

新分支已合入PR 52个，commit 318个
近两周(12.07-12.20)新合入特性PR：

特性(14)：
        mm: some mTHPs improve https://gitee.com/openeuler/kernel/pulls/13824 
        MPTCP Upstream part 23
                https://gitee.com/openeuler/kernel/pulls/14069 
        virtio-fs: introduce multi-queue support：https://gitee.com/openeuler/kernel/pulls/13991
        [virtcca] delete unused interfaces: tmi_data_destroy and tmi_ttt_unmap_range https://gitee.com/openeuler/kernel/pulls/14130 
        KVM:arm64:Add a kvm parameter to control guest wfi trapping https://gitee.com/openeuler/kernel/pulls/14143 
        ACPI: CPPC: Introduce new EPP capabilities and update auto selection functions https://gitee.com/openeuler/kernel/pulls/14088 
        kabi预留(8)：
                fs: Allow fine-grained control of folio sizes：https://gitee.com/openeuler/kernel/pulls/14220 
                v2  kabi: restrict the KABI fix to a specific architecture and dist：https://gitee.com/openeuler/kernel/pulls/14177 
                seq_file: kabi: KABI reservation for seq_file：https://gitee.com/openeuler/kernel/pulls/14218 
                iommu: Reserve extra KABI entry for struct iopf_group：https://gitee.com/openeuler/kernel/pulls/14215 
                net/kabi: Reserve space for net structures：https://gitee.com/openeuler/kernel/pulls/14224 
                KABI for cgroup：https://gitee.com/openeuler/kernel/pulls/14221 
                v2  statx: kabi: KABI reservation for kstat：https://gitee.com/openeuler/kernel/pulls/14236 
                include/msi: modify kabi size of msi_desc https://gitee.com/openeuler/kernel/pulls/12108 

处理器及板卡支持专项(25)：
        loongarch(5):
                Synchronization with patch for loongarch virtualization https://gitee.com/openeuler/kernel/pulls/13998 
                LoongArch: backport ptw&set_pte patches from upstream https://gitee.com/openeuler/kernel/pulls/13981 
                LoongArch: fix AVEC related issue https://gitee.com/openeuler/kernel/pulls/13970 
                add iommu support for loongarch https://gitee.com/openeuler/kernel/pulls/13999 
                Add interrupt controller emulation in the kernel https://gitee.com/openeuler/kernel/pulls/13997 
        申威(2)：
                [6.6] [Feature] : update patches for sw64 architecture https://gitee.com/openeuler/kernel/pulls/14099 
                [6.6] [Feature] : update patches for sw64 architecture https://gitee.com/openeuler/kernel/pulls/14144 
        海光(2)：
                [OLK-6.6] Enhanced Hygon processor's processing capabilities for large memory copying https://gitee.com/openeuler/kernel/pulls/11509 
                [OLK-6.6]Hygon: Enable CONFIG_CMA by default on X86 architecture https://gitee.com/openeuler/kernel/pulls/14195 
        兆芯(3)：
                [OLK-6.6] i2c: smbus: Add support for Zhaoxin SMBUS controller https://gitee.com/openeuler/kernel/pulls/9184 
                [OLK-6.6] cpufreq: acpi-cpufreq: Zhaoxin: fix incorrect max-freq issue https://gitee.com/openeuler/kernel/pulls/13846 
                [OLK-6.6] x86/hpet: Read HPET directly if panic in progress https://gitee.com/openeuler/kernel/pulls/9223 
        LeapIOraid(3)：
                LeapIOraid： Remove Unnecessary header file references: version.h https://gitee.com/openeuler/kernel/pulls/14163 
                LeapIOraid： Fix the compilation warnings in LeapIOraid driver in loongarch64 https://gitee.com/openeuler/kernel/pulls/14111 
                LeapIOraid： Fix too many invalid interruptes in arm64 https://gitee.com/openeuler/kernel/pulls/14162 
        海思(5)：
                [OLK-6.6]perf:Add PMCG platform information for HiSilicon HIP09A https://gitee.com/openeuler/kernel/pulls/14126 
                uacce: some bugfix and cleanup https://gitee.com/openeuler/kernel/pulls/14106 
                crypto: hisilicon/sec2 - the aead algorithm of sec2 is fixed. https://gitee.com/openeuler/kernel/pulls/14152 
                v3  irqchip: gic: some bugfix of hip10 https://gitee.com/openeuler/kernel/pulls/14079 
                [sync] PR-14087: v2  drivers/perf: hisi: Add support for HiSilicon DDRC v3 PMU driver https://gitee.com/openeuler/kernel/pulls/14101 

bugfix(12)：
ima: Fix violation digests extending issue in virtcca
                https://gitee.com/openeuler/kernel/pulls/14095 
Fix livepatch selftest
                https://gitee.com/openeuler/kernel/pulls/13841 
sched: Optimize the latency of select_task_rq and pick_next_task.
                https://gitee.com/openeuler/kernel/pulls/14128 
mm/dynamic_pool: use __GENKSYMS__ to revert the kabi change
                https://gitee.com/openeuler/kernel/pulls/14183 
ata: libata-core: Set ATA_QCFLAG_RTF_FILLED in fill_result_tf()
                https://gitee.com/openeuler/kernel/pulls/14107 
tcp: Fix use-after-free of nreq in reqsk_timer_handler().
                https://gitee.com/openeuler/kernel/pulls/14203 
xfs: Fix data overflow
                https://gitee.com/openeuler/kernel/pulls/14112 
Align per_cpu osq_node to 64 Byte size cacheline
                https://gitee.com/openeuler/kernel/pulls/14166 
nfs: fix the loss of superblock's initialized flags
                https://gitee.com/openeuler/kernel/pulls/14191 
mm/page_alloc: Separate THP PCP into movable and non-movable categories
                https://gitee.com/openeuler/kernel/pulls/14117 
[OLK-6.6] Backport bugfixes for mm LRU from Linux upstream
                https://gitee.com/openeuler/kernel/pulls/10305 
v2  kabi: net: reserve space for xdp subsystem related structure
                https://gitee.com/openeuler/kernel/pulls/14223

CVE(6):
CVE-2024-53130
                https://gitee.com/openeuler/kernel/pulls/14103 
CVE-2024-53112
                https://gitee.com/openeuler/kernel/pulls/14085 
CVE-2024-53142
                https://gitee.com/openeuler/kernel/pulls/14151 
CVE-2024-53108
                https://gitee.com/openeuler/kernel/pulls/14155 
CVE-2024-53125
                https://gitee.com/openeuler/kernel/pulls/14120 
CVE-2024-53129
                https://gitee.com/openeuler/kernel/pulls/14161 

        最新tag 6.6.0-69.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS


议题二：OLK5.10/6.6 增加3260/2230系列RAIDHBA卡驱动（灵达-刘洁）

会上意见：24.03 SP1已封板，OLK-6.6需要1230后的版本再支持；可合入到OLK-5.10 update版本；需要由兼容性SIG同步评审。


议题三：议题征集中，可直接在此填报（请备注申报人）


三、本期遗留问题

gitee issue、pr例行跟踪工作  (李楠)

-------------------------------------------------------------------------------------------------------------------------------------

【2024/12/6 Kernel SIG 双周例会】
轮值主持：李楠 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/962386363
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表
议题一： 进展update（李楠&仉鹏）

OLK-5.10进展同步
近两周(2024.11.22 ~ 12.6)内进展同步:
                OLK-5.10主干更新到tag 5.10.0-239.0.0
                openEuler-22.03-LTS-SP3、SP4分支，更新到tag 5.10.0-239.0.0
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
                openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.104.0，
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
                从 5.10.0-237.0.0 更新至 5.10.0-239.0.0, 回合补丁数126个
                git log 5.10.0-237.0.0..5.10.0-239.0.0 --oneline --no-merges  | wc -l
 
CVE (56)
        CVE-2024-50143  https://gitee.com/openeuler/kernel/pulls/13411
        CVE-2024-49899  https://gitee.com/openeuler/kernel/pulls/13797
        CVE-2024-53073  https://gitee.com/openeuler/kernel/pulls/13905
        CVE-2024-47707  https://gitee.com/openeuler/kernel/pulls/13937
        CVE-2024-49929  https://gitee.com/openeuler/kernel/pulls/13433
        CVE-2024-50044  https://gitee.com/openeuler/kernel/pulls/13935
        CVE-2024-53099  https://gitee.com/openeuler/kernel/pulls/13967
        CVE-2024-50148  https://gitee.com/openeuler/kernel/pulls/13864
        CVE-2024-50141  https://gitee.com/openeuler/kernel/pulls/13303
        CVE-2024-50202  https://gitee.com/openeuler/kernel/pulls/13396
        CVE-2024-50289  https://gitee.com/openeuler/kernel/pulls/13800
        CVE-2024-47745  https://gitee.com/openeuler/kernel/pulls/13392
        CVE-2024-50195  https://gitee.com/openeuler/kernel/pulls/13323
        CVE-2024-53066  https://gitee.com/openeuler/kernel/pulls/13421
        CVE-2024-46713  https://gitee.com/openeuler/kernel/pulls/13371
        CVE-2024-53101  https://gitee.com/openeuler/kernel/pulls/13956
        CVE-2024-49944  https://gitee.com/openeuler/kernel/pulls/13930
        CVE-2024-50234  https://gitee.com/openeuler/kernel/pulls/13867
        CVE-2024-53063  https://gitee.com/openeuler/kernel/pulls/14014
        CVE-2024-50273  https://gitee.com/openeuler/kernel/pulls/13418
        CVE-2024-49891  https://gitee.com/openeuler/kernel/pulls/13887
        CVE-2024-53059  https://gitee.com/openeuler/kernel/pulls/13854
        CVE-2024-49938  https://gitee.com/openeuler/kernel/pulls/13929
        CVE-2024-50045  https://gitee.com/openeuler/kernel/pulls/13436
        CVE-2024-49977  https://gitee.com/openeuler/kernel/pulls/13931
        CVE-2024-50180  https://gitee.com/openeuler/kernel/pulls/13379
        CVE-2024-53090  https://gitee.com/openeuler/kernel/pulls/13839
        CVE-2024-50248  https://gitee.com/openeuler/kernel/pulls/13398
        CVE-2024-50299  https://gitee.com/openeuler/kernel/pulls/13853
        CVE-2024-50236  https://gitee.com/openeuler/kernel/pulls/13921
        CVE-2024-53061  https://gitee.com/openeuler/kernel/pulls/13419
        CVE-2024-50269  https://gitee.com/openeuler/kernel/pulls/13387
        CVE-2024-50171  https://gitee.com/openeuler/kernel/pulls/13862
        CVE-2024-50089  https://gitee.com/openeuler/kernel/pulls/13319
        CVE-2024-53052  https://gitee.com/openeuler/kernel/pulls/13458
        CVE-2024-50265  https://gitee.com/openeuler/kernel/pulls/13462
        CVE-2024-47747  https://gitee.com/openeuler/kernel/pulls/13439
        CVE-2024-50135  https://gitee.com/openeuler/kernel/pulls/13337
        CVE-2024-50205  https://gitee.com/openeuler/kernel/pulls/13386
        CVE-2024-43817  https://gitee.com/openeuler/kernel/pulls/13792
        CVE-2024-50229  https://gitee.com/openeuler/kernel/pulls/13793
        CVE-2024-46813  https://gitee.com/openeuler/kernel/pulls/13898
        CVE-2024-50208  https://gitee.com/openeuler/kernel/pulls/13920
        CVE-2024-50024  https://gitee.com/openeuler/kernel/pulls/13932
        CVE-2024-47749  https://gitee.com/openeuler/kernel/pulls/13441
        CVE-2024-50209  https://gitee.com/openeuler/kernel/pulls/13881
        CVE-2024-47718  https://gitee.com/openeuler/kernel/pulls/13936
        CVE-2024-50241  https://gitee.com/openeuler/kernel/pulls/13356
        CVE-2024-50196  https://gitee.com/openeuler/kernel/pulls/13802
        CVE-2024-49930  https://gitee.com/openeuler/kernel/pulls/13928
        CVE-2024-49952  https://gitee.com/openeuler/kernel/pulls/13435
        CVE-2024-50179  https://gitee.com/openeuler/kernel/pulls/13397
        CVE-2024-50039  https://gitee.com/openeuler/kernel/pulls/13934
        CVE-2024-50062  https://gitee.com/openeuler/kernel/pulls/13444
        CVE-2024-49997  https://gitee.com/openeuler/kernel/pulls/13933
        CVE-2024-50230  https://gitee.com/openeuler/kernel/pulls/13813
        CVE-2024-50192  https://gitee.com/openeuler/kernel/pulls/13829
 
bugfix (14)
arm64: mm: Stop use spinlock during pbha early init
    https://gitee.com/openeuler/kernel/pulls/13964
Fix problems of mounting nfs
    https://gitee.com/openeuler/kernel/pulls/13878
sched/topology: Prevent race condition in sched_domain topology
    https://gitee.com/openeuler/kernel/pulls/13414
filelock: Correct the file lock owner in fcntl_setlk64
    https://gitee.com/openeuler/kernel/pulls/10939
crypto: pcrypt - Call crypto layer directly when padata_do_parallel() return -EBUSY
    https://gitee.com/openeuler/kernel/pulls/13844
xfs: Fix missing interval for missing_owner in xfs fsmap
    https://gitee.com/openeuler/kernel/pulls/13234
ipvlan: fix UAF after skb has been consumed by xdp generic
    https://gitee.com/openeuler/kernel/pulls/13982
xfs: fix log recovery when unknown rocompat bits are set
    https://gitee.com/openeuler/kernel/pulls/11338
Fix xfs fsmap error
    https://gitee.com/openeuler/kernel/pulls/11339
hwpoison, memory_hotplug: lock page before unmap for hwpoisoned page
    https://gitee.com/openeuler/kernel/pulls/14040
xfs: Fix data overflow in xfs_mod_fdblocks()
    https://gitee.com/openeuler/kernel/pulls/14036
some bugfix of ksmbd smb2_open()
    https://gitee.com/openeuler/kernel/pulls/13403
ipmi: Use regspacings passed as a module parameter
    https://gitee.com/openeuler/kernel/pulls/13890
bugfix of nfs
    https://gitee.com/openeuler/kernel/pulls/13448
 
特性
blk-mq/scsi: tracking device queue depth via sbitmap
    https://gitee.com/openeuler/kernel/pulls/13966
 
云脉芯联
drivers: update yunsilicon drivers to version rel_2406_rc16.2
    https://gitee.com/openeuler/kernel/pulls/12547
 
海思
RDMA/hns backport some bugfix from mainline linux
    https://gitee.com/openeuler/kernel/pulls/13281
[HNS3]Add the reliability check of guid_tbl_space
    https://gitee.com/openeuler/kernel/pulls/13823

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20241206：
OLK-6.6进展同步：

新分支已合入PR 85个，commit 656个
近两周(11.23-12.06)新合入特性PR：

LTS(2)：
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.53-6.6.54 LTS Conflicts Patches        https://gitee.com/openeuler/kernel/pulls/13906
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.49-6.6.50 LTS Conflicts Patches        https://gitee.com/openeuler/kernel/pulls/13816

特性(15)：
                net: tcp: add a new congestion control algorithm, CAQM, with endhost-network coordination        https://gitee.com/openeuler/kernel/pulls/12343
                v2 block: support hierarchy stats        https://gitee.com/openeuler/kernel/pulls/13894
                add ebpf sched        https://gitee.com/openeuler/kernel/pulls/13805
                【OLK-6.6】Support SMMU vSVA feature        https://gitee.com/openeuler/kernel/pulls/13402
                Support haltpoll feature        https://gitee.com/openeuler/kernel/pulls/14004
                cppc_driver新增与BIOS交互的sysfs接口，使能BIOS调频 cpufreq: Add SEEP governor for hardware-managed P-states        https://gitee.com/openeuler/kernel/pulls/13340

                virtCCA feature(3)：
virtcca feature : security rectification        https://gitee.com/openeuler/kernel/pulls/14056
virtcca bugfix: correct array copy for hpre_addr        https://gitee.com/openeuler/kernel/pulls/13836
virtcca: fix the double map of cvm secure memory        https://gitee.com/openeuler/kernel/pulls/13243

                xcall/xint(3)：
arm64: entry: Fix some warnings when enable nohz full CPU        https://gitee.com/openeuler/kernel/pulls/13965
genirq/proc: Fix warning of no previous prototype for register_irqchip_proc()        https://gitee.com/openeuler/kernel/pulls/13926
v4 arm64: Add xcall/xint support        https://gitee.com/openeuler/kernel/pulls/13822

                性能优化(3)：
mm, slab: put should_failslab() back behind CONFIG_SHOULD_FAILSLAB        https://gitee.com/openeuler/kernel/pulls/14091
v2 Optimize functions like get_user and put_user        https://gitee.com/openeuler/kernel/pulls/14005
arm64: optimize tlb flush        https://gitee.com/openeuler/kernel/pulls/13974


处理器及板卡支持专项(21)：
                intel(4)：
                intel: backport intel_pstate driver update from 6.11        https://gitee.com/openeuler/kernel/pulls/13851
                intel: backport TPMI uncore frequency driver update from 6.10        https://gitee.com/openeuler/kernel/pulls/13850
                intel: backport Intel SST TPMI update from 6.10        https://gitee.com/openeuler/kernel/pulls/13849
                intel: backport tpmi base driver and pmt update from 6.10 to 6.6        https://gitee.com/openeuler/kernel/pulls/13847

                申威(1)：
                update patches for sw64 architecture        https://gitee.com/openeuler/kernel/pulls/13837

                兆芯(3):
                [OLK-6.6] ata: ahci: Add support for AHCI SGPIO Enclosure Management        https://gitee.com/openeuler/kernel/pulls/9158
                [OLK-6.6] efi: cper: Add Zhaoxin/Centaur ZDI/ZPI error decode        https://gitee.com/openeuler/kernel/pulls/9162
                [OLK-6.6] perf/x86/zhaoxin/uncore: fix pci_driver conflict issue        https://gitee.com/openeuler/kernel/pulls/14022

                海光(1):
                [OLK-6.6]HYGON: CSV3 patch series part 2 (Support launch, run, migrate CSV3 guest)        https://gitee.com/openeuler/kernel/pulls/12279

                LeapIO RAID(1):
                【openEuler 24.03 LTS SP1】SCSI: LeapIO RAID: Support leapioraid RAID controllers        https://gitee.com/openeuler/kernel/pulls/14015

                海思(11)：
                arm64/perf: Enable branch stack sampling        https://gitee.com/openeuler/kernel/pulls/11950
                [OLK-6.6] arm64: errata: Unify and expand speculative SSBS workaround        https://gitee.com/openeuler/kernel/pulls/13151
                scsi: hisi_sas: Some fixes for hisi_sas        https://gitee.com/openeuler/kernel/pulls/13809
                Add support for FEAT_HAFT        https://gitee.com/openeuler/kernel/pulls/13843
                RDMA/hns: Fix accessing invalid dip_ctx during destroying QP        https://gitee.com/openeuler/kernel/pulls/13901
                acc some patch rounds        https://gitee.com/openeuler/kernel/pulls/13373
                backport some patches from upstream about HCCS low power        https://gitee.com/openeuler/kernel/pulls/13845
                【olk 6.6】 net: hns3: add mac tunnel number query        https://gitee.com/openeuler/kernel/pulls/13810
                net/hinic3: Support new NIC feature        https://gitee.com/openeuler/kernel/pulls/13818
                perf: Add PMCG platform information for HiSilicon HIP09A        https://gitee.com/openeuler/kernel/pulls/13808
                RDMA/hns: Fix bonding failure due to wrong reset_state        https://gitee.com/openeuler/kernel/pulls/13449

bugfix(24)：
                Revert "Revert "net: libwx: fix alloc msix vectors failed""        https://gitee.com/openeuler/kernel/pulls/14072
                block, bfq: fix bfqq uaf in bfq_limit_depth()        https://gitee.com/openeuler/kernel/pulls/14094
                xfs: Fix fsmap error        https://gitee.com/openeuler/kernel/pulls/13230
                xfs: split xfs_mod_freecounter        https://gitee.com/openeuler/kernel/pulls/13977
                Various memory tiering fixes        https://gitee.com/openeuler/kernel/pulls/14031
                ext4: show the default enabled prefetch_block_bitmaps option        https://gitee.com/openeuler/kernel/pulls/14025
                Fix UAF in __update_blocked_fair        https://gitee.com/openeuler/kernel/pulls/13951
                Fix SCHED_WARN_ON(cfs_rq->throttled_clock) in throttle_cfs_rq        https://gitee.com/openeuler/kernel/pulls/13950
                sched/fair: Fix qos_timer deadlock when cpuhp offline        https://gitee.com/openeuler/kernel/pulls/13949
                libbpf: Fix output .symtab byte-order during linking        https://gitee.com/openeuler/kernel/pulls/13969
                ipmi: Use regspacings passed as a module parameter        https://gitee.com/openeuler/kernel/pulls/13889
                [OLK-6.6][Backport] tracing/selftests: Update kprobe args char/string to match new functions        https://gitee.com/openeuler/kernel/pulls/13454
                [OLK-6.6][Backport] selftest: net: Fix the problem that run veth.sh failed        https://gitee.com/openeuler/kernel/pulls/13453
                [OLK-6.6][Backport] tools/nolibc: add support for constructors and destructors        https://gitee.com/openeuler/kernel/pulls/13450
                [OLK-6.6][Backport] selftests/intel_pstate: fix operand expected error        https://gitee.com/openeuler/kernel/pulls/13815
                [OLK-6.6][Backport] selftest: net/af_unix: Fix the problem that run test_unix_oob failed        https://gitee.com/openeuler/kernel/pulls/13417
                [OLK-6.6][Backport] selftests/watchdog-test: Fix system accidentally reset after watchdog-test        https://gitee.com/openeuler/kernel/pulls/13806
                Fix problems of mounting nfs        https://gitee.com/openeuler/kernel/pulls/13880
                crypto: pcrypt - Call crypto layer directly when padata_do_parallel() return -EBUSY        https://gitee.com/openeuler/kernel/pulls/13828
                migration: fix reference counting exception issue        https://gitee.com/openeuler/kernel/pulls/11952
                sched/topology: Prevent race condition in sched_domain topology        https://gitee.com/openeuler/kernel/pulls/13413
                rseq/mm_cid: change KABI consistency interface        https://gitee.com/openeuler/kernel/pulls/13408
                ima: rot: remove misguiding message printing        https://gitee.com/openeuler/kernel/pulls/13407
                ima: fix buffer overrun in ima_eventdigest_init_common        https://gitee.com/openeuler/kernel/pulls/13842
CVE(23):
                CVE-2024-53110        https://gitee.com/openeuler/kernel/pulls/14065
                CVE-2024-53054        https://gitee.com/openeuler/kernel/pulls/14059
                CVE-2024-49923        https://gitee.com/openeuler/kernel/pulls/14026
                CVE-2024-49991        https://gitee.com/openeuler/kernel/pulls/14012
                CVE-2024-49897        https://gitee.com/openeuler/kernel/pulls/14011
                CVE-2024-50200        https://gitee.com/openeuler/kernel/pulls/14013
                CVE-2024-53090        https://gitee.com/openeuler/kernel/pulls/14019
                CVE-2024-50164        https://gitee.com/openeuler/kernel/pulls/13993
                CVE-2024-53063        https://gitee.com/openeuler/kernel/pulls/13912
                CVE-2024-50191        https://gitee.com/openeuler/kernel/pulls/13961
                CVE-2024-46808        https://gitee.com/openeuler/kernel/pulls/13955
                CVE-2024-49861        https://gitee.com/openeuler/kernel/pulls/13913
                CVE-2024-50137        https://gitee.com/openeuler/kernel/pulls/13317
                CVE-2024-46813        https://gitee.com/openeuler/kernel/pulls/13897
                CVE-2024-53073        https://gitee.com/openeuler/kernel/pulls/13904
                CVE-2024-49891        https://gitee.com/openeuler/kernel/pulls/13888
                CVE-2024-53089        https://gitee.com/openeuler/kernel/pulls/13827
                CVE-2024-53085        https://gitee.com/openeuler/kernel/pulls/13416
                CVE-2024-50192        https://gitee.com/openeuler/kernel/pulls/13831
                CVE-2024-49915        https://gitee.com/openeuler/kernel/pulls/13794
                CVE-2024-49899        https://gitee.com/openeuler/kernel/pulls/13795
                CVE-2024-50289        https://gitee.com/openeuler/kernel/pulls/13799
                CVE-2024-50217        https://gitee.com/openeuler/kernel/pulls/13306

        最新tag 6.6.0-61.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS
议题二：申请成为openEuler Kernel sig的committer - （麒麟软件-温志伟）
1.多年Linux内核开发经验，熟悉UEFI、内存管理，进程调度，KVM等领域.
2.熟悉openEuler社区的工作流程，承担6.6主线分支维护工作，backport 2300+ patch.
3.承担社区维护常规事宜--issue、PR分析跟踪.
会议结论：通过

议题三：gitee issue、pr例行跟踪工作  (李楠)

议题四：LoongArch PR审核(张洪臣)
https://gitee.com/openeuler/kernel/pulls/13981 OLK-6.6: LoongArch: 回合上游ptw及set_pte修复补丁
https://gitee.com/openeuler/kernel/pulls/13970 OLK-6.6: LoongArch: 修复AVEC中断控制器相关问题
https://gitee.com/openeuler/kernel/pulls/14049 OLK-6.6: LoongArch: LS7A2000默认不使用内核自带的loongson drm驱动

议题四：征集中，可直接在此填报申请（请备注汇报人）

三、本期遗留问题



-------------------------------------------------------------------------------------------------------------------------------------
【2024/11/22 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：李楠
会议链接：https://meeting.huaweicloud.com:36443/#/j/961483852
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表
议题一： 进展update（李楠&仉鹏）
OLK-5.10进展同步
近两周(2024.11.6 ~ 11.20)内进展同步:
                OLK-5.10主干更新到tag 5.10.0-237.0.0
                openEuler-22.03-LTS-SP3、SP4分支，更新到tag 5.10.0-237.0.0
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
                openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.102.0，
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
                从 5.10.0-235.0.0 更新至 5.10.0-237.0.0, 回合补丁数100个
                git log 5.10.0-235.0.0..5.10.0-237.0.0 --oneline --no-merges  | wc -l

CVE（45）
        CVE-2024-49949  https://gitee.com/openeuler/kernel/pulls/13055
        CVE-2024-50013  https://gitee.com/openeuler/kernel/pulls/12970
        CVE-2024-50247  https://gitee.com/openeuler/kernel/pulls/13225
        CVE-2024-47728  https://gitee.com/openeuler/kernel/pulls/13261
        CVE-2024-50133  https://gitee.com/openeuler/kernel/pulls/13167
        CVE-2024-45018  https://gitee.com/openeuler/kernel/pulls/12154
        CVE-2024-49945  https://gitee.com/openeuler/kernel/pulls/13190
        CVE-2024-50099  https://gitee.com/openeuler/kernel/pulls/13146
        CVE-2023-52920  https://gitee.com/openeuler/kernel/pulls/13277
        CVE-2024-50153  https://gitee.com/openeuler/kernel/pulls/13260
        CVE-2024-50244  https://gitee.com/openeuler/kernel/pulls/13310 
        CVE-2024-50082  https://gitee.com/openeuler/kernel/pulls/13124
        CVE-2024-50262  https://gitee.com/openeuler/kernel/pulls/13328
        CVE-2024-50006  https://gitee.com/openeuler/kernel/pulls/12975
        CVE-2024-50203  https://gitee.com/openeuler/kernel/pulls/13299
        CVE-2024-50014  https://gitee.com/openeuler/kernel/pulls/12972
        CVE-2024-47666  https://gitee.com/openeuler/kernel/pulls/13239
        CVE-2024-50154  https://gitee.com/openeuler/kernel/pulls/13156
        CVE-2024-49963  https://gitee.com/openeuler/kernel/pulls/13276
        CVE-2024-43911  https://gitee.com/openeuler/kernel/pulls/12375
        CVE-2024-50073  https://gitee.com/openeuler/kernel/pulls/13042
        CVE-2024-49982  https://gitee.com/openeuler/kernel/pulls/13221
        CVE-2024-46815  https://gitee.com/openeuler/kernel/pulls/12949 
        CVE-2024-50246  https://gitee.com/openeuler/kernel/pulls/13227
        CVE-2024-49960  https://gitee.com/openeuler/kernel/pulls/12974
        CVE-2024-49948  https://gitee.com/openeuler/kernel/pulls/13054
        CVE-2024-49914  https://gitee.com/openeuler/kernel/pulls/13128
        CVE-2024-50142  https://gitee.com/openeuler/kernel/pulls/13157
        CVE-2024-50198  https://gitee.com/openeuler/kernel/pulls/13201
        CVE-2024-50184  https://gitee.com/openeuler/kernel/pulls/13186
        CVE-2024-50095  https://gitee.com/openeuler/kernel/pulls/13154
        CVE-2024-50131  https://gitee.com/openeuler/kernel/pulls/13144
        CVE-2024-47663  https://gitee.com/openeuler/kernel/pulls/13237
        CVE-2024-50242  https://gitee.com/openeuler/kernel/pulls/13196
        CVE-2024-50138  https://gitee.com/openeuler/kernel/pulls/13178
        CVE-2024-46685  https://gitee.com/openeuler/kernel/pulls/13099
        CVE-2024-50151  https://gitee.com/openeuler/kernel/pulls/13343
        CVE-2024-49983  https://gitee.com/openeuler/kernel/pulls/12971
        CVE-2024-46702  https://gitee.com/openeuler/kernel/pulls/13101
        CVE-2024-50245  https://gitee.com/openeuler/kernel/pulls/13226
        CVE-2024-50115  https://gitee.com/openeuler/kernel/pulls/13194
        CVE-2024-49878  https://gitee.com/openeuler/kernel/pulls/13103
        CVE-2024-49967  https://gitee.com/openeuler/kernel/pulls/12976
        CVE-2024-47679  https://gitee.com/openeuler/kernel/pulls/12973
        CVE-2024-50237  https://gitee.com/openeuler/kernel/pulls/13285

bugfix（12）
arm64: restore pc after fixup iff mcs failed in arm64_do_kernel_sea
        https://gitee.com/openeuler/kernel/pulls/13182
bpf, net: Fix a potential race in do_sock_getsockopt()
        https://gitee.com/openeuler/kernel/pulls/13089
mm,hwpoison: check mm when killing accessing process
        https://gitee.com/openeuler/kernel/pulls/13344
Fix 'cgroup/cpuset: Prevent UAF in proc_cpuset_show()' issue with commmunity patches
        https://gitee.com/openeuler/kernel/pulls/13164
Fix UAF of rpc_task
        https://gitee.com/openeuler/kernel/pulls/13067
arm64: support page mapping percpu first chunk allocator
        https://gitee.com/openeuler/kernel/pulls/13212
selinux: clarify return code in filename_trans_read_helper_compat()
        https://gitee.com/openeuler/kernel/pulls/13073
serial: core: Fix atomicity violation in uart_tiocmget
        https://gitee.com/openeuler/kernel/pulls/13080 
sched: smart_grid: Prevent double-free in sched_grid_qos_free
        https://gitee.com/openeuler/kernel/pulls/13173 
Fix objtool error for AMX instruction decoding
        https://gitee.com/openeuler/kernel/pulls/13318
Update ASPM sysfs on MFD function removal to avoid use-after-free
        https://gitee.com/openeuler/kernel/pulls/13095
network_mgmt: Change print_ip_notify_pkt_en sysfs_attr priority
        https://gitee.com/openeuler/kernel/pulls/12587

feature
mm: support poison recover for more
        https://gitee.com/openeuler/kernel/pulls/13125

海思
RDMA/hns: Fix DCA mmap area PUAF
        https://gitee.com/openeuler/kernel/pulls/13094
sdma-dae: change authority of debugfs
        https://gitee.com/openeuler/kernel/pulls/13294
sdma-dae: add ida validation
        https://gitee.com/openeuler/kernel/pulls/13048
RDMA/hns: Fix the valid QP bank set to improve performance
        https://gitee.com/openeuler/kernel/pulls/13255
Support SMT control on arm64
        https://gitee.com/openeuler/kernel/pulls/12996

intel
Intel: Backport KVM Fix for Clearing SGX EDECCSSA to OLK-5.10
        https://gitee.com/openeuler/kernel/pulls/13013
Intel: Backport to fix In Field Scan(IFS) Scan At Field(SAF)
        https://gitee.com/openeuler/kernel/pulls/13280
intel: backport GNR and SRF intel_idle fix for 5.10
        https://gitee.com/openeuler/kernel/pulls/12858
Backport Intel Trace Hub support on GNR and SPR platforms
        https://gitee.com/openeuler/kernel/pulls/11286

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20241122：
OLK-6.6进展同步：

新分支已合入PR 82个，commit 1026个
近两周(11.09-11.22)新合入特性PR：

LTS(7)：
        [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.47-6.6.48 LTS Conflicts Patches        https://gitee.com/openeuler/kernel/pulls/13362
        [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.61-6.6.62 LTS Patches        https://gitee.com/openeuler/kernel/pulls/13321
        [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.60-6.6.61 LTS Patches        https://gitee.com/openeuler/kernel/pulls/13287
        [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.59-6.6.60 LTS Patches        https://gitee.com/openeuler/kernel/pulls/13244
        [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.58-6.6.59 LTS Patches        https://gitee.com/openeuler/kernel/pulls/13189
        [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.57-6.6.58 LTS Patches        https://gitee.com/openeuler/kernel/pulls/13130
        [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.55-6.6.57 LTS Patches        https://gitee.com/openeuler/kernel/pulls/13092

特性(11)：
                支持shmem large folio的swap-out和swap-in(1)：
                mm: support large folio swap-out and swap-in for shmem        https://gitee.com/openeuler/kernel/pulls/11561
                
                virtCCA feature(2)：
                virtcca feature :SM Cryptographic Acceleration        https://gitee.com/openeuler/kernel/pulls/13047
                virtcca feature: support transfer smmu_vmid to tmm        https://gitee.com/openeuler/kernel/pulls/13240

                麒麟 MPTCP支持(4)：
                MPTCP Upstream part 22        https://gitee.com/openeuler/kernel/pulls/13331
                MPTCP Upstream part 21        https://gitee.com/openeuler/kernel/pulls/13251
                MPTCP Upstream part 20        https://gitee.com/openeuler/kernel/pulls/13111
                MPTCP Upstream part 19        https://gitee.com/openeuler/kernel/pulls/13110

                支持脚本病毒防御 (was O_MAYEXEC)(2)：
                ima: fix a compilation error with ima_bprm_creds_for_exec()        https://gitee.com/openeuler/kernel/pulls/13300
                Script execution control        https://gitee.com/openeuler/kernel/pulls/13210

                IMA安全特性(1)：
                IMA RoT        https://gitee.com/openeuler/kernel/pulls/13257

                性能优化(1)：
                fs: 6.6 performance improve patches        https://gitee.com/openeuler/kernel/pulls/13122

处理器及板卡支持专项(20)：
                intel(2)：
                [OLK-6.6] Support Intel Sierra Forest CPU MAXPHYSADDR and fix KVM_STATS_TYPE_MAX        https://gitee.com/openeuler/kernel/pulls/13372
                intel: backport GNR and SRF intel_idle fix for 6.6        https://gitee.com/openeuler/kernel/pulls/12859

                澜起(1)：
                [OLK-6.6]Update Mont-TSSE driver        https://gitee.com/openeuler/kernel/pulls/12240

                兆芯(1):
                [OLK-6.6] cpufreq: ACPI: add ITMT support when CPPC enabled        https://gitee.com/openeuler/kernel/pulls/9157

                龙芯(7):
                Revert "Loongarch: Dynamic enable writecombine"        https://gitee.com/openeuler/kernel/pulls/13269
                Add objtool, orc and livepatch support for LoongArch        https://gitee.com/openeuler/kernel/pulls/13180
                Revert "LoongArch: Add workaround for 3C6000 about io wr/rd"        https://gitee.com/openeuler/kernel/pulls/12877
                LoongArch: disable cpufreq driver        https://gitee.com/openeuler/kernel/pulls/12886
                drm/loongson: use old version of ast driver for LoongArch platform        https://gitee.com/openeuler/kernel/pulls/12840
                LoongArch: add loongson SE support        https://gitee.com/openeuler/kernel/pulls/12496
                LoongArch: Add AVEC irqchip support        https://gitee.com/openeuler/kernel/pulls/12492

                星云智联(2):
                nebula-matrix: fix ci build err        https://gitee.com/openeuler/kernel/pulls/13117
                fix ci compile nbl_ethtool.c warning        https://gitee.com/openeuler/kernel/pulls/13313

                海思/hns(7)：
                net/hinic3: Support New SDK and NIC features        https://gitee.com/openeuler/kernel/pulls/13335
                [olk 6.6] net: hibmcge: add support for hibmcge driver        https://gitee.com/openeuler/kernel/pulls/12431
                Add the spidev.ko to OLK-6.6        https://gitee.com/openeuler/kernel/pulls/12160
                Some patches for RDMA/hns        https://gitee.com/openeuler/kernel/pulls/13376
                Some patches of RDMA from Linux to olk-6.6        https://gitee.com/openeuler/kernel/pulls/13161
                Update ASPM sysfs on MFD function removal to avoid use-after-free        https://gitee.com/openeuler/kernel/pulls/13096
                RDMA/hns: Fix different dgids mapping to the same dip_idx        https://gitee.com/openeuler/kernel/pulls/13389

bugfix(14)：
                麒麟软件6个PR、凝思软件1个PR，风河mpt3sas相关1个PR
                IMA: Fix hungtask issue of digestlist importing        https://gitee.com/openeuler/kernel/pulls/13400
                mm: replace xa_get_order with xas_get_order where appropriate        https://gitee.com/openeuler/kernel/pulls/13350
                ocfs2: fix unexpected zeroing of virtual disk        https://gitee.com/openeuler/kernel/pulls/13345
                selftests: udpgro: no need to load xdp for gro        https://gitee.com/openeuler/kernel/pulls/13377
                netdevsim: fix rtnetlink.sh selftest        https://gitee.com/openeuler/kernel/pulls/13374
                x86/selftests: Skip the tests if prerequisites aren't fulfilled        https://gitee.com/openeuler/kernel/pulls/13357
                [OLK-6.6][Backport] selftests/mount_setattr: fix idmap_mount_tree_invalid failed to run        https://gitee.com/openeuler/kernel/pulls/13248
                [OLK-6.6] [Backport] mpt3sas_scsih: don't set QUEUE_FLAG_NOMERGES        https://gitee.com/openeuler/kernel/pulls/13148
                v2 mm, mmap: limit THP alignment of anonymous mappings to PMD-aligned sizes        https://gitee.com/openeuler/kernel/pulls/13259
                fork: do not expose incomplete mm on fork        https://gitee.com/openeuler/kernel/pulls/13215
                [OLK-6.6][Backport] exec: don't WARN for racy path_noexec check        https://gitee.com/openeuler/kernel/pulls/13131
                serial: core: Fix atomicity violation in uart_tiocmget        https://gitee.com/openeuler/kernel/pulls/13079
                selinux: clarify return code in filename_trans_read_helper_compat()        https://gitee.com/openeuler/kernel/pulls/13074
                Revert "perf callchain: Fix stitch LBR memory leaks"        https://gitee.com/openeuler/kernel/pulls/13126

CVE(30):
                CVE-2024-50191        https://gitee.com/openeuler/kernel/pulls/13308
                CVE-2024-50241        https://gitee.com/openeuler/kernel/pulls/13355
                CVE-2024-50157        https://gitee.com/openeuler/kernel/pulls/13301
                CVE-2024-47745        https://gitee.com/openeuler/kernel/pulls/13391
                CVE-2024-49885        https://gitee.com/openeuler/kernel/pulls/13394
                CVE-2024-46713        https://gitee.com/openeuler/kernel/pulls/13370
                CVE-2023-52920        https://gitee.com/openeuler/kernel/pulls/13324
                CVE-2024-49914        https://gitee.com/openeuler/kernel/pulls/13129
                CVE-2024-50223        https://gitee.com/openeuler/kernel/pulls/13296
                CVE-2024-50203        https://gitee.com/openeuler/kernel/pulls/13298
                CVE-2024-46698        https://gitee.com/openeuler/kernel/pulls/13275
                CVE-2024-50215        https://gitee.com/openeuler/kernel/pulls/13235
                CVE-2024-50115        https://gitee.com/openeuler/kernel/pulls/13193
                CVE-2024-50138        https://gitee.com/openeuler/kernel/pulls/13179
                CVE-2024-47728        https://gitee.com/openeuler/kernel/pulls/13263
                CVE-2024-46749        https://gitee.com/openeuler/kernel/pulls/12249
                CVE-2024-38546        https://gitee.com/openeuler/kernel/pulls/9721
                CVE-2024-43911        https://gitee.com/openeuler/kernel/pulls/12376
                CVE-2024-50056        https://gitee.com/openeuler/kernel/pulls/13140
                CVE-2024-49945        https://gitee.com/openeuler/kernel/pulls/13192
                CVE-2024-49945        https://gitee.com/openeuler/kernel/pulls/13172
                CVE-2024-50156        https://gitee.com/openeuler/kernel/pulls/13181
                CVE-2024-50145        https://gitee.com/openeuler/kernel/pulls/13133
                CVE-2024-50131        https://gitee.com/openeuler/kernel/pulls/13142
                CVE-2024-49920        https://gitee.com/openeuler/kernel/pulls/13137
                CVE-2024-50152        https://gitee.com/openeuler/kernel/pulls/13120
                CVE-2024-50120        https://gitee.com/openeuler/kernel/pulls/13115
                CVE-2024-47726        https://gitee.com/openeuler/kernel/pulls/13113
                CVE-2024-50082        https://gitee.com/openeuler/kernel/pulls/13121
                CVE-2024-47702        https://gitee.com/openeuler/kernel/pulls/13064


        最新tag 6.6.0-56.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS
议题二：virtcca特性commiter申报（何静娴）
1. virtcca核心特性补丁贡献者，检视vircca安全加固、远程证明、设备直通等特性补丁10+；
2. 5年Linux 内核开发经验，熟悉内存管理、进程调度、中断管理、kvm等模块；
3. 申请看护文件列表：
arch/arm64/include/asm/kvm_tmi.h
arch/arm64/include/asm/kvm_tmm.h
arch/arm64/include/asm/virtcca_cvm_host.h
arch/arm64/kernel/virtcca_cvm_host.c
arch/arm64/kvm/tmi.c
arch/arm64/kvm/virtcca_cvm.c
arch/arm64/kvm/virtcca_cvm_exit.c
drivers/iommu/arm/arm-smmu-v3/arm-s-smmu-v3.c
drivers/iommu/arm/arm-smmu-v3/arm-s-smmu-v3.h
drivers/coda/coda.c
drivers/coda/coda_pci.c
drivers/coda/coda_vfio.c
arch/arm64/include/asm/virtcca_cvm_guest.h
arch/arm64/include/asm/virtcca_cvm_smc.h
arch/arm64/include/uapi/asm/virtcca_cvm_tsi.h
arch/arm64/kernel/virtcca_cvm_guest.c
arch/arm64/kernel/virtcca_cvm_tsi.c
结论：同意增加virtcca特性看护committer。

议题三：征集中，可直接在此填报申请（请备注汇报人）

Vkernel特性介绍（华科&武汉金银湖实验室-陶志恒 taozhiheng@jyhlab.org.cn）
可能与中关村的安全特性有冲突，先沟通了解中关村所做的内容
中关村PATCH: ?

三、本期遗留问题

-------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2024/11/8 Kernel SIG 双周例会】
轮值主持：仉鹏（廖涛代） 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：桑力鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/983782327
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表
议题一： 进展update（李楠&仉鹏）

OLK-5.10进展同步
近两周(2024.10.23 ~ 11.6)内进展同步:
                OLK-5.10主干更新到tag 5.10.0-235.0.0
                openEuler-22.03-LTS-SP3、SP4分支，更新到tag 5.10.0-235.0.0
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
                openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.100.0，
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
                从 5.10.0-231.0.0 更新至 5.10.0-233.0.0, 回合补丁数192个
                git log 5.10.0-231.0.0..5.10.0-233.0.0 --oneline --no-merges  | wc -l

CVE（127）
        CVE-2024-49950      https://gitee.com/openeuler/kernel/pulls/13009
        CVE-2024-50064      https://gitee.com/openeuler/kernel/pulls/13003
        CVE-2024-47701      https://gitee.com/openeuler/kernel/pulls/13051
        CVE-2024-50047      https://gitee.com/openeuler/kernel/pulls/12680
        CVE-2024-50002      https://gitee.com/openeuler/kernel/pulls/13039
        CVE-2024-47726      https://gitee.com/openeuler/kernel/pulls/13017
        CVE-2024-49859      https://gitee.com/openeuler/kernel/pulls/13016
        CVE-2024-49896      https://gitee.com/openeuler/kernel/pulls/13015
        CVE-2024-49940      https://gitee.com/openeuler/kernel/pulls/13019
        CVE-2024-50008      https://gitee.com/openeuler/kernel/pulls/13022
        CVE-2024-49858      https://gitee.com/openeuler/kernel/pulls/13034
        CVE-2024-50040      https://gitee.com/openeuler/kernel/pulls/12992
        CVE-2024-46809      https://gitee.com/openeuler/kernel/pulls/12994
        CVE-2024-49882      https://gitee.com/openeuler/kernel/pulls/12901
        CVE-2024-49883      https://gitee.com/openeuler/kernel/pulls/12897
        CVE-2024-49881      https://gitee.com/openeuler/kernel/pulls/12958
        CVE-2024-50016      https://gitee.com/openeuler/kernel/pulls/12884
        CVE-2024-49860      https://gitee.com/openeuler/kernel/pulls/12844
        CVE-2024-47690      https://gitee.com/openeuler/kernel/pulls/12998
        CVE-2024-47660      https://gitee.com/openeuler/kernel/pulls/12911
        CVE-2024-50060      https://gitee.com/openeuler/kernel/pulls/12908
        CVE-2024-49992      https://gitee.com/openeuler/kernel/pulls/12879
        CVE-2022-48961      https://gitee.com/openeuler/kernel/pulls/12915
        CVE-2024-47723      https://gitee.com/openeuler/kernel/pulls/12944
        CVE-2024-49913      https://gitee.com/openeuler/kernel/pulls/12950
        CVE-2024-45021      https://gitee.com/openeuler/kernel/pulls/12954
        CVE-2024-47691      https://gitee.com/openeuler/kernel/pulls/12824
        CVE-2024-49934      https://gitee.com/openeuler/kernel/pulls/12548
        CVE-2024-47703      https://gitee.com/openeuler/kernel/pulls/12870
        CVE-2024-49889      https://gitee.com/openeuler/kernel/pulls/12893
        CVE-2022-48975      https://gitee.com/openeuler/kernel/pulls/12934
        CVE-2024-47668      https://gitee.com/openeuler/kernel/pulls/12831
        CVE-2024-49958      https://gitee.com/openeuler/kernel/pulls/12689
        CVE-2024-49877      https://gitee.com/openeuler/kernel/pulls/12920
        CVE-2024-49917      https://gitee.com/openeuler/kernel/pulls/12890
        CVE-2024-49995      https://gitee.com/openeuler/kernel/pulls/12875
        CVE-2024-49975      https://gitee.com/openeuler/kernel/pulls/12781
        CVE-2024-50083      https://gitee.com/openeuler/kernel/pulls/12928
        CVE-2024-49978      https://gitee.com/openeuler/kernel/pulls/12926
        CVE-2024-47696      https://gitee.com/openeuler/kernel/pulls/12927
        CVE-2024-50058      https://gitee.com/openeuler/kernel/pulls/12812
        CVE-2024-50033      https://gitee.com/openeuler/kernel/pulls/12790
        CVE-2024-49884      https://gitee.com/openeuler/kernel/pulls/12801
        CVE-2024-49973      https://gitee.com/openeuler/kernel/pulls/12737
        CVE-2024-49936      https://gitee.com/openeuler/kernel/pulls/12741
        CVE-2024-47739      https://gitee.com/openeuler/kernel/pulls/12407
        CVE-2022-49004      https://gitee.com/openeuler/kernel/pulls/12778
        CVE-2024-49862      https://gitee.com/openeuler/kernel/pulls/12525
        CVE-2024-49981      https://gitee.com/openeuler/kernel/pulls/12818
        CVE-2024-49922      https://gitee.com/openeuler/kernel/pulls/12825
        CVE-2024-50067      https://gitee.com/openeuler/kernel/pulls/12798
        CVE-2024-50028      https://gitee.com/openeuler/kernel/pulls/12764
        CVE-2024-47699      https://gitee.com/openeuler/kernel/pulls/12658
        CVE-2024-49886      https://gitee.com/openeuler/kernel/pulls/12794
        CVE-2024-50063      https://gitee.com/openeuler/kernel/pulls/12754
        CVE-2024-46677      https://gitee.com/openeuler/kernel/pulls/12488
        CVE-2024-47659      https://gitee.com/openeuler/kernel/pulls/12762
        CVE-2024-49996      https://gitee.com/openeuler/kernel/pulls/12551
        CVE-2024-49879      https://gitee.com/openeuler/kernel/pulls/12713
        CVE-2024-50035      https://gitee.com/openeuler/kernel/pulls/12723
        CVE-2024-50059      https://gitee.com/openeuler/kernel/pulls/12733
        CVE-2024-49954      https://gitee.com/openeuler/kernel/pulls/12373
        CVE-2024-49924      https://gitee.com/openeuler/kernel/pulls/12705
        CVE-2024-47742      https://gitee.com/openeuler/kernel/pulls/12517
        CVE-2024-49955      https://gitee.com/openeuler/kernel/pulls/12665
        CVE-2024-47705      https://gitee.com/openeuler/kernel/pulls/12685
        CVE-2024-47748      https://gitee.com/openeuler/kernel/pulls/12701
        CVE-2024-47673      https://gitee.com/openeuler/kernel/pulls/12678
        CVE-2024-47693      https://gitee.com/openeuler/kernel/pulls/12676
        CVE-2024-49855      https://gitee.com/openeuler/kernel/pulls/12499
        CVE-2024-49933      https://gitee.com/openeuler/kernel/pulls/12610
        CVE-2024-50007      https://gitee.com/openeuler/kernel/pulls/12633
        CVE-2024-49965      https://gitee.com/openeuler/kernel/pulls/12672
        CVE-2024-49894      https://gitee.com/openeuler/kernel/pulls/12670
        CVE-2024-47669      https://gitee.com/openeuler/kernel/pulls/12248
        CVE-2024-47684      https://gitee.com/openeuler/kernel/pulls/12641
        CVE-2024-47710      https://gitee.com/openeuler/kernel/pulls/12640
        CVE-2024-47695      https://gitee.com/openeuler/kernel/pulls/12642
        CVE-2024-50036      https://gitee.com/openeuler/kernel/pulls/12639
        CVE-2024-50025      https://gitee.com/openeuler/kernel/pulls/12596
        CVE-2024-49966      https://gitee.com/openeuler/kernel/pulls/12505
        CVE-2022-48952      https://gitee.com/openeuler/kernel/pulls/12620
        CVE-2024-50046      https://gitee.com/openeuler/kernel/pulls/12556
        CVE-2024-46802      https://gitee.com/openeuler/kernel/pulls/12605
        CVE-2024-47757      https://gitee.com/openeuler/kernel/pulls/12445
        CVE-2024-49892      https://gitee.com/openeuler/kernel/pulls/12466
        CVE-2024-47720      https://gitee.com/openeuler/kernel/pulls/12581
        CVE-2024-49974      https://gitee.com/openeuler/kernel/pulls/12460
        CVE-2024-49900      https://gitee.com/openeuler/kernel/pulls/12560
        CVE-2024-47667      https://gitee.com/openeuler/kernel/pulls/12569
        CVE-2024-49895      https://gitee.com/openeuler/kernel/pulls/12459
        CVE-2024-49911      https://gitee.com/openeuler/kernel/pulls/12453
        CVE-2024-49969      https://gitee.com/openeuler/kernel/pulls/12442
        CVE-2024-47698      https://gitee.com/openeuler/kernel/pulls/12402
        CVE-2024-49902      https://gitee.com/openeuler/kernel/pulls/12424
        CVE-2024-49903      https://gitee.com/openeuler/kernel/pulls/12425
        CVE-2024-49868      https://gitee.com/openeuler/kernel/pulls/12422
        CVE-2024-49867      https://gitee.com/openeuler/kernel/pulls/12423
        CVE-2024-47685      https://gitee.com/openeuler/kernel/pulls/12523
        CVE-2023-52918      https://gitee.com/openeuler/kernel/pulls/12542
        CVE-2024-49927      https://gitee.com/openeuler/kernel/pulls/12369
        CVE-2024-43858      https://gitee.com/openeuler/kernel/pulls/12511
        CVE-2024-43871      https://gitee.com/openeuler/kernel/pulls/12510
        CVE-2024-42315      https://gitee.com/openeuler/kernel/pulls/12509
        CVE-2024-46830      https://gitee.com/openeuler/kernel/pulls/12252
        CVE-2024-46853      https://gitee.com/openeuler/kernel/pulls/12387
        CVE-2024-46724      https://gitee.com/openeuler/kernel/pulls/12385
        CVE-2024-46675      https://gitee.com/openeuler/kernel/pulls/12382
        CVE-2024-46757      https://gitee.com/openeuler/kernel/pulls/12360
        CVE-2022-48916      https://gitee.com/openeuler/kernel/pulls/12451
        CVE-2024-42301      https://gitee.com/openeuler/kernel/pulls/12467
        CVE-2024-40965      https://gitee.com/openeuler/kernel/pulls/12310
        CVE-2024-38667      https://gitee.com/openeuler/kernel/pulls/12484
        CVE-2024-36286      https://gitee.com/openeuler/kernel/pulls/12480
        CVE-2024-38635      https://gitee.com/openeuler/kernel/pulls/12454
        CVE-2024-43894      https://gitee.com/openeuler/kernel/pulls/12411
        CVE-2024-49985      https://gitee.com/openeuler/kernel/pulls/12350
        CVE-2024-46722      https://gitee.com/openeuler/kernel/pulls/12272
        CVE-2024-49866      https://gitee.com/openeuler/kernel/pulls/12395
        CVE-2024-43841      https://gitee.com/openeuler/kernel/pulls/12406
        CVE-2024-47737      https://gitee.com/openeuler/kernel/pulls/12318
        CVE-2024-35878      https://gitee.com/openeuler/kernel/pulls/12344
        CVE-2024-42152      https://gitee.com/openeuler/kernel/pulls/12342
        CVE-2024-43867      https://gitee.com/openeuler/kernel/pulls/12334
        CVE-2023-52917      https://gitee.com/openeuler/kernel/pulls/12336
        CVE-2024-46689      https://gitee.com/openeuler/kernel/pulls/12305
        CVE-2024-50049      https://gitee.com/openeuler/kernel/pulls/12611

bugfix（18）
scsi: core: Avoid leaving shost->last_reset with stale value if EH does not run
        https://gitee.com/openeuler/kernel/pulls/12449
hisilicon/hisi_hbmdev: prevent NULL pointer dereference when corrently
        https://gitee.com/openeuler/kernel/pulls/12867
selinux: add the processing of the failure of avc_add_xperms_decision()
        https://gitee.com/openeuler/kernel/pulls/12758
v2 hisilicon/hisi_hbmcache: Use mutex_trylock to prevent hung task
        https://gitee.com/openeuler/kernel/pulls/12770
mm: memcg: don't periodically flush stats when memcg is disabled
        https://gitee.com/openeuler/kernel/pulls/12697
crypto: xor - fix template benchmarking
        https://gitee.com/openeuler/kernel/pulls/12694
blk-mq: Fix kmemleak in blk_mq_init_allocated_queue
        https://gitee.com/openeuler/kernel/pulls/12629
randomize_kstack: Improve entropy diffusion
        https://gitee.com/openeuler/kernel/pulls/12667
selinux: fix potential counting error in avc_add_xperms_decision()
        https://gitee.com/openeuler/kernel/pulls/12668
apparmor: fix policy_unpack_test on big endian systems
        https://gitee.com/openeuler/kernel/pulls/12621
blk-mq: fix blk_mq_hw_ctx active request accounting
        https://gitee.com/openeuler/kernel/pulls/12275
writeback: Fix inode->i_io_list not be protected by inode->i_lock error
        https://gitee.com/openeuler/kernel/pulls/12615
ext4: avoid deadlock in fs reclaim with page writeback
        https://gitee.com/openeuler/kernel/pulls/8925
mm/swapfile: skip HugeTLB pages for unuse_vma
        https://gitee.com/openeuler/kernel/pulls/12391
nfsd: return -EINVAL when namelen is 0
        https://gitee.com/openeuler/kernel/pulls/12294
Randomized Kmalloc 5.10 Backport V2
        https://gitee.com/openeuler/kernel/pulls/12571
kabi: use CONFIG_KABI_RESERVE to control reservation in ucount_type and user_table
        https://gitee.com/openeuler/kernel/pulls/12536
neighbour: fix data-races around n->output        
        https://gitee.com/openeuler/kernel/pulls/12349

海思
UNIC: Eliminate compile warnings when the option CONFIG_HNS3_UBL is not set
        https://gitee.com/openeuler/kernel/pulls/12878
perf pmu: resolve CPU map for "cpu" PMUs
        https://gitee.com/openeuler/kernel/pulls/12315
hns3 udma: delete irrl and trrl table.        
        https://gitee.com/openeuler/kernel/pulls/12332
security/keys: fix slab-out-of-bounds in key_task_permission
        https://gitee.com/openeuler/kernel/pulls/12686

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20241108：
OLK-6.6进展同步：

新分支已合入PR 189个，commit 1252个
近两周(10.26-11.08)新合入特性PR：

LTS(2)：
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.54-6.6.55 LTS Patches        https://gitee.com/openeuler/kernel/pulls/13077
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.53-6.6.54 LTS Patches        https://gitee.com/openeuler/kernel/pulls/12634

特性(8)：
                virtCCA feature: GPU supports maximum 1G page table mapping        https://gitee.com/openeuler/kernel/pulls/12940
                
                麒麟 MPTCP支持：
                MPTCP Upstream part 18        https://gitee.com/openeuler/kernel/pulls/13087
                MPTCP Upstream part 17        https://gitee.com/openeuler/kernel/pulls/13086
                MPTCP Upstream part 16        https://gitee.com/openeuler/kernel/pulls/12772
                MPTCP Upstream part 15        https://gitee.com/openeuler/kernel/pulls/12771
                MPTCP Upstream part 14        https://gitee.com/openeuler/kernel/pulls/12715

                openeuler 2403 x86支持内核态vdpa基本功能以及热迁移:
                v4 add vdpa support for x86 and enable vdpa migration.        https://gitee.com/openeuler/kernel/pulls/12773

                rseq/mm_cid: change the mm_cid macro default status and keep KABI consistent        https://gitee.com/openeuler/kernel/pulls/12957
处理器及板卡支持专项(22)：
                Hygon(4):
                [OLK-6.6] perf/x86/uncore: Add support for Hygon family 18h model 4h-7h and 10h DF PMU        https://gitee.com/openeuler/kernel/pulls/10861
                Hygon model 4h~fh and 10h ATL issue fix        https://gitee.com/openeuler/kernel/pulls/12612
                fix Hygon TKM may execute fail in CSV VM        https://gitee.com/openeuler/kernel/pulls/12280
                drivers/crypto/ccp: fix a build error        https://gitee.com/openeuler/kernel/pulls/12720
                
                兆芯(5):
                [OLK-6.6] perf/x86/zhaoxin/uncore: update KX-7000 support        https://gitee.com/openeuler/kernel/pulls/9209
                [OLK-6.6] x86/cpu: Remove pointless evaluation of x86_coreid_bits        https://gitee.com/openeuler/kernel/pulls/9191
                [OLK-6.6] USB: Fix kernel NULL pointer when unbind UHCI form vfio-pci        https://gitee.com/openeuler/kernel/pulls/9156
                [OLK-6.6] fix intel-lkp compilation issues for DMA patch        https://gitee.com/openeuler/kernel/pulls/7927
                [OLK-6.6] iommu/dma: Move iova_reserve_domain_addr to header dma-iommu.h        https://gitee.com/openeuler/kernel/pulls/7874
                
                AMD(2):
                [OLK-6.6] AMD Address Translation Library (ATL) patches        https://gitee.com/openeuler/kernel/pulls/12300
                [OLK-6.6] AMD Turin perf vendor event patches        https://gitee.com/openeuler/kernel/pulls/12288

                龙芯(4):
                LoongArch: fix some 3C6000&LS7A related problems        https://gitee.com/openeuler/kernel/pulls/12491
                LoongArch: prevent LS7A Bus Master clearing on kexec        https://gitee.com/openeuler/kernel/pulls/12331
                LoongArch: backport 3 patches from upstream        https://gitee.com/openeuler/kernel/pulls/12321
                LoongArch: fix dma-direct.h not found        https://gitee.com/openeuler/kernel/pulls/12322

                星云智联(2):
                nebula-matrix: fix ci build warning when use clang        https://gitee.com/openeuler/kernel/pulls/13018
                Net: nebula-matrix: fix ci build warning        https://gitee.com/openeuler/kernel/pulls/12835
                
                云脉芯联(2)：
                [OLK-6.6] drivers: load Yunsilicon ethernet driver when xsc_pci probing        https://gitee.com/openeuler/kernel/pulls/12834
                [OLK-6.6] drivers: update Yunsilicon driver to version rel_2406_rc16        https://gitee.com/openeuler/kernel/pulls/12345

                海思/hns(3)：
                RDMA/hns: Fix DCA mmap area PUAF        https://gitee.com/openeuler/kernel/pulls/13109
                Some patches of RDMA/hns from Linux to OLK-6.6        https://gitee.com/openeuler/kernel/pulls/13044
                RDMA/hns: Fix missing spin_lock_init() for qp flush lock        https://gitee.com/openeuler/kernel/pulls/12390
bugfix(16)：
                sched/fair: Take the scheduling domain into account in select_idle_smt()        https://gitee.com/openeuler/kernel/pulls/13081
                Fix UAF of rpc_task        https://gitee.com/openeuler/kernel/pulls/13066
                NFSD: Mark filecache "down" if init fails        https://gitee.com/openeuler/kernel/pulls/13069
                drm/amd/display: Revert "drm/amd/display: Fix potential index out of bounds in color transformation function"        https://gitee.com/openeuler/kernel/pulls/13012
                security/keys: fix slab-out-of-bounds in key_task_permission        https://gitee.com/openeuler/kernel/pulls/12688
                v4 openeuler_defconfig: Disable CONFIG_DEBUG_INFO_BTF_MODULES        https://gitee.com/openeuler/kernel/pulls/12821
                v2 bpf lts backport        https://gitee.com/openeuler/kernel/pulls/12816
                drivers: misc: uacce: bugfix for MAX_ORDER        https://gitee.com/openeuler/kernel/pulls/12780
                Backport "ima: Avoid blocking in RCU read-side critical section"        https://gitee.com/openeuler/kernel/pulls/12728
                mm: memcg: don't periodically flush stats when memcg is disabled        https://gitee.com/openeuler/kernel/pulls/12698
                bpf: lsm: Set bpf_lsm_blob_sizes.lbs_task to 0        https://gitee.com/openeuler/kernel/pulls/12635
                some bugfixs for khuegpaged        https://gitee.com/openeuler/kernel/pulls/12631
                Fix VMAPP/VMOVP races        https://gitee.com/openeuler/kernel/pulls/12065
                mm/swapfile: skip HugeTLB pages for unuse_vma        https://gitee.com/openeuler/kernel/pulls/12389
                md: use RCU lock to protect traversal in md_spares_need_change()        https://gitee.com/openeuler/kernel/pulls/12363
                nfsd: return -EINVAL when namelen is 0        https://gitee.com/openeuler/kernel/pulls/12293
CVE(141):
                CVE-2024-50121        https://gitee.com/openeuler/kernel/pulls/13108
                CVE-2024-50077        https://gitee.com/openeuler/kernel/pulls/12848
                CVE-2024-49926        https://gitee.com/openeuler/kernel/pulls/13112
                CVE-2024-49988        https://gitee.com/openeuler/kernel/pulls/13084
                CVE-2024-49888        https://gitee.com/openeuler/kernel/pulls/12943
                CVE-2024-49894        https://gitee.com/openeuler/kernel/pulls/13088
                CVE-2024-50073        https://gitee.com/openeuler/kernel/pulls/13043
                CVE-2024-49947        https://gitee.com/openeuler/kernel/pulls/13062
                CVE-2024-49948        https://gitee.com/openeuler/kernel/pulls/13060
                CVE-2024-49949        https://gitee.com/openeuler/kernel/pulls/13061
                CVE-2024-49960        https://gitee.com/openeuler/kernel/pulls/12979
                CVE-2024-49967        https://gitee.com/openeuler/kernel/pulls/12980
                CVE-2024-49968        https://gitee.com/openeuler/kernel/pulls/12983
                CVE-2024-49983        https://gitee.com/openeuler/kernel/pulls/12981
                CVE-2024-50006        https://gitee.com/openeuler/kernel/pulls/12982
                CVE-2024-50013        https://gitee.com/openeuler/kernel/pulls/12978
                CVE-2024-50014        https://gitee.com/openeuler/kernel/pulls/12977
                CVE-2024-50041        https://gitee.com/openeuler/kernel/pulls/12866
                CVE-2024-50025        https://gitee.com/openeuler/kernel/pulls/12595
                CVE-2024-50064        https://gitee.com/openeuler/kernel/pulls/13004
                CVE-2024-47701        https://gitee.com/openeuler/kernel/pulls/13049
                CVE-2024-50047        https://gitee.com/openeuler/kernel/pulls/12682
                CVE-2024-49940        https://gitee.com/openeuler/kernel/pulls/13023
                CVE-2024-50008        https://gitee.com/openeuler/kernel/pulls/13025
                CVE-2024-49937        https://gitee.com/openeuler/kernel/pulls/13024
                CVE-2024-50040        https://gitee.com/openeuler/kernel/pulls/12993
                CVE-2024-50066        https://gitee.com/openeuler/kernel/pulls/12988
                CVE-2024-49870        https://gitee.com/openeuler/kernel/pulls/12800
                CVE-2024-49882        https://gitee.com/openeuler/kernel/pulls/12900
                CVE-2024-49883        https://gitee.com/openeuler/kernel/pulls/12896
                CVE-2024-49881        https://gitee.com/openeuler/kernel/pulls/12960
                CVE-2024-50087        https://gitee.com/openeuler/kernel/pulls/12909
                CVE-2024-50060        https://gitee.com/openeuler/kernel/pulls/12906
                CVE-2024-49889        https://gitee.com/openeuler/kernel/pulls/12892
                CVE-2024-47686        https://gitee.com/openeuler/kernel/pulls/12377
                CVE-2024-49992        https://gitee.com/openeuler/kernel/pulls/12497
                CVE-2024-50076        https://gitee.com/openeuler/kernel/pulls/12775
                CVE-2024-50016        https://gitee.com/openeuler/kernel/pulls/12883
                CVE-2024-50084        https://gitee.com/openeuler/kernel/pulls/12774
                CVE-2024-49896        https://gitee.com/openeuler/kernel/pulls/12776
                CVE-2024-49913        https://gitee.com/openeuler/kernel/pulls/12952
                CVE-2024-47704        https://gitee.com/openeuler/kernel/pulls/12942
                CVE-2024-44943        https://gitee.com/openeuler/kernel/pulls/12953
                CVE-2024-49934        https://gitee.com/openeuler/kernel/pulls/12550
                CVE-2024-47703        https://gitee.com/openeuler/kernel/pulls/12871
                CVE-2024-49879        https://gitee.com/openeuler/kernel/pulls/12712
                CVE-2024-49958        https://gitee.com/openeuler/kernel/pulls/12838
                CVE-2024-49954        https://gitee.com/openeuler/kernel/pulls/12372
                CVE-2024-49852        https://gitee.com/openeuler/kernel/pulls/12358
                CVE-2024-49874        https://gitee.com/openeuler/kernel/pulls/12822
                CVE-2024-49871        https://gitee.com/openeuler/kernel/pulls/12918
                CVE-2024-49995        https://gitee.com/openeuler/kernel/pulls/12874
                CVE-2024-50058        https://gitee.com/openeuler/kernel/pulls/12916
                CVE-2024-50063        https://gitee.com/openeuler/kernel/pulls/12843
                CVE-2024-49978        https://gitee.com/openeuler/kernel/pulls/12932
                CVE-2024-50083        https://gitee.com/openeuler/kernel/pulls/12933
                CVE-2024-49877        https://gitee.com/openeuler/kernel/pulls/12922
                CVE-2024-49901        https://gitee.com/openeuler/kernel/pulls/12913
                CVE-2024-49917        https://gitee.com/openeuler/kernel/pulls/12888
                CVE-2024-49975        https://gitee.com/openeuler/kernel/pulls/12769
                CVE-2024-49931        https://gitee.com/openeuler/kernel/pulls/12717
                CVE-2024-49936        https://gitee.com/openeuler/kernel/pulls/12742
                CVE-2024-49973        https://gitee.com/openeuler/kernel/pulls/12738
                CVE-2024-49884        https://gitee.com/openeuler/kernel/pulls/12805
                CVE-2024-50019        https://gitee.com/openeuler/kernel/pulls/12637
                CVE-2024-50026        https://gitee.com/openeuler/kernel/pulls/12473
                CVE-2024-50033        https://gitee.com/openeuler/kernel/pulls/12791
                CVE-2024-50055        https://gitee.com/openeuler/kernel/pulls/12607
                CVE-2024-50055        https://gitee.com/openeuler/kernel/pulls/12759
                CVE-2024-49981        https://gitee.com/openeuler/kernel/pulls/12817
                CVE-2024-46824        https://gitee.com/openeuler/kernel/pulls/12599
                CVE-2024-50067        https://gitee.com/openeuler/kernel/pulls/12793
                CVE-2024-49898        https://gitee.com/openeuler/kernel/pulls/12829
                CVE-2024-49961        https://gitee.com/openeuler/kernel/pulls/12826
                CVE-2024-49922        https://gitee.com/openeuler/kernel/pulls/12827
                CVE-2024-50072        https://gitee.com/openeuler/kernel/pulls/12767
                CVE-2024-49966        https://gitee.com/openeuler/kernel/pulls/12506
                CVE-2024-50022        https://gitee.com/openeuler/kernel/pulls/12482
                CVE-2024-49886        https://gitee.com/openeuler/kernel/pulls/12795
                CVE-2024-50074        https://gitee.com/openeuler/kernel/pulls/12747
                CVE-2024-50028        https://gitee.com/openeuler/kernel/pulls/12718
                CVE-2024-49909        https://gitee.com/openeuler/kernel/pulls/12707
                CVE-2024-50029        https://gitee.com/openeuler/kernel/pulls/12768
                CVE-2024-50000        https://gitee.com/openeuler/kernel/pulls/12674
                CVE-2024-50003        https://gitee.com/openeuler/kernel/pulls/12736
                CVE-2024-50049        https://gitee.com/openeuler/kernel/pulls/12604
                CVE-2024-50009        https://gitee.com/openeuler/kernel/pulls/12591
                CVE-2024-49892        https://gitee.com/openeuler/kernel/pulls/12465
                CVE-2024-50070        https://gitee.com/openeuler/kernel/pulls/12755
                CVE-2024-50088        https://gitee.com/openeuler/kernel/pulls/12711
                CVE-2024-47742        https://gitee.com/openeuler/kernel/pulls/12516
                CVE-2024-49924        https://gitee.com/openeuler/kernel/pulls/12710
                CVE-2024-50059        https://gitee.com/openeuler/kernel/pulls/12729
                CVE-2024-49994        https://gitee.com/openeuler/kernel/pulls/12666
                CVE-2024-49933        https://gitee.com/openeuler/kernel/pulls/12608
                CVE-2024-49955        https://gitee.com/openeuler/kernel/pulls/12656
                CVE-2024-49989        https://gitee.com/openeuler/kernel/pulls/12662
                CVE-2024-49912        https://gitee.com/openeuler/kernel/pulls/12617
                CVE-2024-44951        https://gitee.com/openeuler/kernel/pulls/12545
                CVE-2024-50036        https://gitee.com/openeuler/kernel/pulls/12648
                CVE-2024-49996        https://gitee.com/openeuler/kernel/pulls/12553
                CVE-2024-47743        https://gitee.com/openeuler/kernel/pulls/12565
                CVE-2024-49855        https://gitee.com/openeuler/kernel/pulls/12498
                CVE-2024-49965        https://gitee.com/openeuler/kernel/pulls/12673
                CVE-2024-50057        https://gitee.com/openeuler/kernel/pulls/12653
                CVE-2024-50007        https://gitee.com/openeuler/kernel/pulls/12632
                CVE-2024-50065        https://gitee.com/openeuler/kernel/pulls/12557
                CVE-2024-50046        https://gitee.com/openeuler/kernel/pulls/12554
                CVE-2024-47757        https://gitee.com/openeuler/kernel/pulls/12444
                CVE-2024-47689        https://gitee.com/openeuler/kernel/pulls/12464
                CVE-2024-47720        https://gitee.com/openeuler/kernel/pulls/12584
                CVE-2024-49974        https://gitee.com/openeuler/kernel/pulls/12461
                CVE-2024-49900        https://gitee.com/openeuler/kernel/pulls/12559
                CVE-2024-49895        https://gitee.com/openeuler/kernel/pulls/12462
                CVE-2024-49911        https://gitee.com/openeuler/kernel/pulls/12455
                CVE-2024-49919        https://gitee.com/openeuler/kernel/pulls/12448
                CVE-2024-49969        https://gitee.com/openeuler/kernel/pulls/12443
                CVE-2024-49918        https://gitee.com/openeuler/kernel/pulls/12533
                CVE-2024-47698        https://gitee.com/openeuler/kernel/pulls/12400
                CVE-2024-49903        https://gitee.com/openeuler/kernel/pulls/12429
                CVE-2024-49902        https://gitee.com/openeuler/kernel/pulls/12428
                CVE-2024-49868        https://gitee.com/openeuler/kernel/pulls/12426
                CVE-2024-49867        https://gitee.com/openeuler/kernel/pulls/12427
                CVE-2024-47685        https://gitee.com/openeuler/kernel/pulls/12524
                CVE-2024-46775        https://gitee.com/openeuler/kernel/pulls/12515
                CVE-2024-49927        https://gitee.com/openeuler/kernel/pulls/12365
                CVE-2024-50012        https://gitee.com/openeuler/kernel/pulls/12361
                CVE-2024-40965        https://gitee.com/openeuler/kernel/pulls/12476
                CVE-2024-35964        https://gitee.com/openeuler/kernel/pulls/12440
                CVE-2024-35949        https://gitee.com/openeuler/kernel/pulls/12438
                CVE-2024-36884        https://gitee.com/openeuler/kernel/pulls/12410
                CVE-2024-49985        https://gitee.com/openeuler/kernel/pulls/12351
                CVE-2024-49866        https://gitee.com/openeuler/kernel/pulls/12394
                CVE-2024-49976        https://gitee.com/openeuler/kernel/pulls/12397
                CVE-2024-47681        https://gitee.com/openeuler/kernel/pulls/12399
                CVE-2024-46722        https://gitee.com/openeuler/kernel/pulls/12273
                CVE-2024-47661        https://gitee.com/openeuler/kernel/pulls/12263
                CVE-2023-52917        https://gitee.com/openeuler/kernel/pulls/12335
                CVE-2024-42122        https://gitee.com/openeuler/kernel/pulls/12338
                CVE-2024-47737        https://gitee.com/openeuler/kernel/pulls/12317
                CVE-2024-46802        https://gitee.com/openeuler/kernel/pulls/12066

        最新tag 6.6.0-52.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS
议题二：  龙芯PR评审  (张天洋&赵群钦&张洪臣)
https://gitee.com/openeuler/kernel/pulls/12492 OLK-6.6: LoongArch: 添加AVEC irqchip支持
https://gitee.com/openeuler/kernel/pulls/12496 OLK-6.6: LoongArch: 添加loongson SE&SDF驱动支持
https://gitee.com/openeuler/kernel/pulls/12840 OLK-6.6: LoongArch: 针对loongarch平台使用旧版本ast驱动
https://gitee.com/openeuler/kernel/pulls/12886 OLK-6.6: LoongArch: 关闭调频驱动
https://gitee.com/openeuler/kernel/pulls/12877 OLK-6.6: LoongArch: revert 3C6000 workaround补丁，新3c6000芯片不再需要

结论：龙芯的commiter review无误后合入。

议题三：申请成为openEuler Kernel sig的committer - （风河软件-商保根）
1.多年Linux开发经验，熟悉内存管理，进程调度，文件系统，KVM/USB子系统等领域.
2.了解过openEuler社区的工作流程，从上游移植过大概10多个patch到内核5.10分支.
3.咨询个问题，之前例会通过申报的committer名字不在sig-info.yaml中.
https://gitee.com/openeuler/community/blob/master/sig/Kernel/sig-info.yaml

通过会议纪要https://etherpad.openeuler.org/p/Kernel-meetings可以看到
2023/12/8 Kernel SIG的双周例会，当时通过了胡勇申报committer的请求:
-------------------------------------------------
议题二：scsi下部分驱动commiter申报 -- (风河软件-胡勇)
drivers/scsi/lpfc
drivers/scsi/qla2xxx
drivers/scsi/mpt3sas
结论：通过，已经在openEuler社区提交并合入相关的bugfix，之前这部分驱动缺少committer

结论：1. 先持续贡献USB子系统模块，后续再上会正式申请；2. 补充胡勇到sig-info.yaml名单中。

议题四：兆芯PR评审（柳辛）
https://gitee.com/openeuler/kernel/pulls/9157 OLK-6.6: 兆芯KX7000/KX30000 处理器平台添加ITMT特性支持。
https://gitee.com/openeuler/kernel/pulls/9158 OLK-6.6: 兆芯KH30000处理器平台对AHCI SGPIO的支持驱动。
https://gitee.com/openeuler/kernel/pulls/9162 OLK-6.6: 兆芯处理器平台上添加对ZDI/ZPI错误的解析。
https://gitee.com/openeuler/kernel/pulls/9184 OLK-6.6: 兆芯处理器平台添加对SMbus控制器的驱动。

结论：曾昭荣、仉鹏等review无误后合入。

议题五：新增李楠为kernel sig committer
1. 多年Linux开发经验，专长存储领域；
2. 已在openeuler kernel review 补丁1400+；

结论：同意

议题六：committer、maintainer名单更新，https://gitee.com/openeuler/community/blob/master/sig/Kernel/sig-info.yaml
删除成员：zhangjialin11@huawei.com、cj.chengjian@huawei.com
新增committer：AMD 王文宽
branch-keeper变更：22.03分支变更为李楠

结论：同意

议题七：澜起PR评审（蔡仲斐）。
https://gitee.com/openeuler/kernel/pulls/12240 OLK-6.6:更新 Mont-TSSE driver

结论：仉鹏跟踪，找drivers/crypto模块的committer review无误后合入。

议题八：海光PR评审（韩里洋&杨葛）。
https://gitee.com/openeuler/kernel/pulls/12279 OLK-6.6:支持CSV3虚拟机创建，运行 & CSV3虚拟机支持

结论：曾昭荣、仉鹏跟踪，需要内核、兼容性、虚拟化等领域的committer review无误后再合入。

议题九：Vkernel特性介绍（华科武汉金银湖实验室-陶志恒）

后续例会再进一步介绍相关内容。


三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------
【2024/10/25 Kernel SIG 双周例会】
轮值主持：曾昭荣 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：仉鹏（廖涛代）
会议链接：https://meeting.huaweicloud.com:36443/#/j/965848565
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

openEuler 24.03 LTS 构建出的驱动二进制文件无法查询内核符号 - 刘彦泽

二、议题列表
议题一： 进展update（李楠&仉鹏）

OLK-5.10进展同步
近两周(2024.10.9 ~ 10.23)内进展同步:
                OLK-5.10主干更新到tag 5.10.0-233.0.0
                openEuler-22.03-LTS-SP3、SP4分支，更新到tag 5.10.0-233.0.0
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
                openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.98.0，
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
                从 5.10.0-231.0.0 更新至 5.10.0-233.0.0, 回合补丁数173个
                git log 5.10.0-231.0.0..5.10.0-233.0.0 --oneline --no-merges  | wc -l
 
同步linux 5.10.y社区LTS补丁集1个: 5.10.217~5.10.218
https://gitee.com/openeuler/kernel/pulls/12164
https://gitee.com/openeuler/kernel/pulls/12135
 
CVE（41）
        CVE-2024-46822      https://gitee.com/openeuler/kernel/pulls/12298
        CVE-2024-35829      https://gitee.com/openeuler/kernel/pulls/12261
        CVE-2024-27074      https://gitee.com/openeuler/kernel/pulls/12262
        CVE-2024-27030      https://gitee.com/openeuler/kernel/pulls/12257
        CVE-2024-47661      https://gitee.com/openeuler/kernel/pulls/12264
        CVE-2024-38608      https://gitee.com/openeuler/kernel/pulls/12244
        CVE-2024-27397      https://gitee.com/openeuler/kernel/pulls/12245
        CVE-2024-39495      https://gitee.com/openeuler/kernel/pulls/12254
        CVE-2024-44990      https://gitee.com/openeuler/kernel/pulls/12155
        CVE-2024-44989      https://gitee.com/openeuler/kernel/pulls/12153
        CVE-2024-44931      https://gitee.com/openeuler/kernel/pulls/11299
        CVE-2024-46817      https://gitee.com/openeuler/kernel/pulls/12234
        CVE-2024-46716      https://gitee.com/openeuler/kernel/pulls/12236
        CVE-2024-40958      https://gitee.com/openeuler/kernel/pulls/12182
        CVE-2024-36244      https://gitee.com/openeuler/kernel/pulls/12179
        CVE-2024-38612      https://gitee.com/openeuler/kernel/pulls/12176
        CVE-2024-36927      https://gitee.com/openeuler/kernel/pulls/12186
        CVE-2024-42321      https://gitee.com/openeuler/kernel/pulls/12197
        CVE-2024-42289      https://gitee.com/openeuler/kernel/pulls/12213
        CVE-2024-46859      https://gitee.com/openeuler/kernel/pulls/12212
        CVE-2024-46826      https://gitee.com/openeuler/kernel/pulls/12102
        CVE-2024-43855      https://gitee.com/openeuler/kernel/pulls/12121
        CVE-2024-47658      https://gitee.com/openeuler/kernel/pulls/12166
        CVE-2024-44998      https://gitee.com/openeuler/kernel/pulls/12207
        CVE-2024-47672      https://gitee.com/openeuler/kernel/pulls/12149
        CVE-2024-44940      https://gitee.com/openeuler/kernel/pulls/12172
        CVE-2024-45006      https://gitee.com/openeuler/kernel/pulls/12170
        CVE-2024-42067      https://gitee.com/openeuler/kernel/pulls/12163
        CVE-2024-44954      https://gitee.com/openeuler/kernel/pulls/12133
        CVE-2024-46828      https://gitee.com/openeuler/kernel/pulls/12127
        CVE-2024-46770      https://gitee.com/openeuler/kernel/pulls/12126
        CVE-2024-46754      https://gitee.com/openeuler/kernel/pulls/12125
        CVE-2024-45026      https://gitee.com/openeuler/kernel/pulls/12045
        CVE-2024-44969      https://gitee.com/openeuler/kernel/pulls/12043
        CVE-2024-46858      https://gitee.com/openeuler/kernel/pulls/12096
        CVE-2024-46854      https://gitee.com/openeuler/kernel/pulls/12095
        CVE-2024-46855      https://gitee.com/openeuler/kernel/pulls/12094
        CVE-2024-47671      https://gitee.com/openeuler/kernel/pulls/12089
        CVE-2022-48893      https://gitee.com/openeuler/kernel/pulls/12084
        CVE-2024-46840      https://gitee.com/openeuler/kernel/pulls/12078
        CVE-2024-46819      https://gitee.com/openeuler/kernel/pulls/12053
 
bugfix（13）
tracing: Have tracing_max_latency inc the trace array ref count
        https://gitee.com/openeuler/kernel/pulls/12088
xfs: atomic write file dio convert to mark IOCB_ATOMIC 6f31e5b4ecef !12219 v7 xfs: some fix for forcealign
        https://gitee.com/openeuler/kernel/pulls/12250
md/raid1: don't free conf on raid0_run failure
        https://gitee.com/openeuler/kernel/pulls/12115
nbd: Fix signal handling
        https://gitee.com/openeuler/kernel/pulls/12227
Some bugfixs for ubi/fs
        https://gitee.com/openeuler/kernel/pulls/12208
ext4: dax: Fix inconsistent isize during writing
        https://gitee.com/openeuler/kernel/pulls/11910
blk-mq: fix lockdep hardirq warning in __blk_mq_tag_idle()
        https://gitee.com/openeuler/kernel/pulls/12075
Backport "ima: Avoid blocking in RCU read-side critical section"
        https://gitee.com/openeuler/kernel/pulls/12204
arm64/mpam: Be compatible with MPAM architecture v1.x
        https://gitee.com/openeuler/kernel/pulls/12139
sched/fair: Fix the condition in overload_clear
        https://gitee.com/openeuler/kernel/pulls/12105
sched/debug: Fix h_nr_running/steal_h_nr_running in sched_debug
        https://gitee.com/openeuler/kernel/pulls/12103
acpi/arm64: Do not add CPU to node_to_cpumask_map in acpi_map_cpu()
        https://gitee.com/openeuler/kernel/pulls/11856
mm/ksm: fix possible UAF of stable_node
        https://gitee.com/openeuler/kernel/pulls/11558
 
特性
支持在ipvlan网卡上使用xdp native模式
        https://gitee.com/openeuler/kernel/pulls/12048
 
海思
perf pmu: resolve CPU map for "cpu" PMUs
        https://gitee.com/openeuler/kernel/pulls/12315
net/hinic3: fix version showed in ethtool
        https://gitee.com/openeuler/kernel/pulls/12215
UNIC: Invoke the hns3_unic_set_default_cc in advance and modify ublhdr struct
        https://gitee.com/openeuler/kernel/pulls/11889
perf cpumap: Wrapper for CPU map indices
        https://gitee.com/openeuler/kernel/pulls/12003
 
海光
Add support for Hygon model 10h processors
        https://gitee.com/openeuler/kernel/pulls/8834

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20241025：
OLK-6.6进展同步：

新分支已合入PR 51个，commit 925个
近两周(10.12-10.25)新合入特性PR：

LTS(6)：
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.52-6.6.53 LTS Patches        https://gitee.com/openeuler/kernel/pulls/12314
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.51-6.6.52 LTS Patches        https://gitee.com/openeuler/kernel/pulls/12306
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.50-6.6.51 LTS Patches        https://gitee.com/openeuler/kernel/pulls/12291
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.49-6.6.50 LTS Patches        https://gitee.com/openeuler/kernel/pulls/12286
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.48-6.6.49 LTS Patches        https://gitee.com/openeuler/kernel/pulls/12281
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.47-6.6.48 LTS Patches        https://gitee.com/openeuler/kernel/pulls/12112

特性(1)：
                Virtcca feature: modify vfio/msi/iommu driver to enable confidential device assignment        https://gitee.com/openeuler/kernel/pulls/11502


处理器及板卡支持专项(7)：
                Hygon(1):
                [OLK-6.6]HYGON: CSV3 patch series part 1 (Secure memory management and initialization for CSV3)        https://gitee.com/openeuler/kernel/pulls/9955

                星云智联(1):
                S1000系列网卡驱动支持 Adds Nebula S1000 series network snic driver        https://gitee.com/openeuler/kernel/pulls/11667

                海思(2)：
                KVM: arm64: Add new HiSi CPU type for supporting DVMBM 增加新的hisi CPU型号来支持DVMBM特性，并且修改HIP09型号为HIP10        https://gitee.com/openeuler/kernel/pulls/12036
                ACPI/IORT: Add PMCG platform information for HiSilicon HIP10/11        https://gitee.com/openeuler/kernel/pulls/12216

bugfix(6)：
                [sync] PR-11910: ext4: dax: Fix inconsistent isize during writing        https://gitee.com/openeuler/kernel/pulls/12223
                mm: page_cache_ra_order: Restore 'PF_MEMALLOC_NOFS' flag in 'fallback' branch        https://gitee.com/openeuler/kernel/pulls/12146
                mm: mem_reliable: Initialize reliable_nr_page when mm_init()        https://gitee.com/openeuler/kernel/pulls/12276
                RDMA/hns: Fix flush cqe error when racing with destroy qp        https://gitee.com/openeuler/kernel/pulls/12253
                v2 RDMA/hns: Fix new mmaped pages during resetting        https://gitee.com/openeuler/kernel/pulls/12217
                net/hinic3: fix version showed in ethtool        https://gitee.com/openeuler/kernel/pulls/12209

CVE(31):
                CVE-2024-47658        https://gitee.com/openeuler/kernel/pulls/12168
                CVE-2024-47741        https://gitee.com/openeuler/kernel/pulls/12304
                CVE-2024-46676        https://gitee.com/openeuler/kernel/pulls/12151
                CVE-2024-46709        https://gitee.com/openeuler/kernel/pulls/12141
                CVE-2024-46754        https://gitee.com/openeuler/kernel/pulls/12129
                CVE-2024-47731        https://gitee.com/openeuler/kernel/pulls/12296
                CVE-2024-38608        https://gitee.com/openeuler/kernel/pulls/12200
                CVE-2024-27397        https://gitee.com/openeuler/kernel/pulls/12201
                CVE-2024-47665        https://gitee.com/openeuler/kernel/pulls/12295
                CVE-2024-47675        https://gitee.com/openeuler/kernel/pulls/12301
                CVE-2024-46691        https://gitee.com/openeuler/kernel/pulls/12289
                CVE-2024-47671        https://gitee.com/openeuler/kernel/pulls/12090
                CVE-2024-38594        https://gitee.com/openeuler/kernel/pulls/12178
                CVE-2024-40999        https://gitee.com/openeuler/kernel/pulls/12181
                CVE-2024-46726        https://gitee.com/openeuler/kernel/pulls/12255
                CVE-2024-46859        https://gitee.com/openeuler/kernel/pulls/12214
                CVE-2024-47672        https://gitee.com/openeuler/kernel/pulls/12147
                CVE-2024-46830        https://gitee.com/openeuler/kernel/pulls/12218
                CVE-2024-46822        https://gitee.com/openeuler/kernel/pulls/12087
                CVE-2024-46840        https://gitee.com/openeuler/kernel/pulls/6996
                CVE-2024-46819        https://gitee.com/openeuler/kernel/pulls/12080
                CVE-2024-46838        https://gitee.com/openeuler/kernel/pulls/12052
                CVE-2024-46826        https://gitee.com/openeuler/kernel/pulls/12082
                CVE-2024-46836        https://gitee.com/openeuler/kernel/pulls/12077
                CVE-2024-46855        https://gitee.com/openeuler/kernel/pulls/12068
                CVE-2024-46805        https://gitee.com/openeuler/kernel/pulls/12057
                CVE-2024-46858        https://gitee.com/openeuler/kernel/pulls/11954
                CVE-2024-46854        https://gitee.com/openeuler/kernel/pulls/12059
                CVE-2024-46810        https://gitee.com/openeuler/kernel/pulls/12058
                CVE-2024-46821        https://gitee.com/openeuler/kernel/pulls/12076
                CVE-2024-45011        https://gitee.com/openeuler/kernel/pulls/11966



        最新tag 6.6.0-47.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS





议题二：征集中，可直接在此申报，需要备注汇报人。
议题三：Kernel SIG TC 委员推举 - 谢秀奇
会议结论：同意推举谢秀奇代表 Kernel SIG 担任下届TC委员。


议题四：bcache的两个影响性能的上游补丁合入（浪潮云车烈权）
问题描述：
https://gitee.com/openeuler/kernel/issues/IAUP56?from=project-issue
主线6.10中的补丁链接
https://gitee.com/openeuler/kernel/pulls/11993
https://gitee.com/openeuler/kernel/pulls/11994

议题五：一个适配海光4h-7h DF PMU的补丁合入
OLK-6.6分支的提交链接：https://gitee.com/openeuler/kernel/pulls/10861
OLK-5.10分支的提交链接：https://gitee.com/openeuler/kernel/pulls/10860
openEuler-1.0-LTS分支的提交链接：https://gitee.com/openeuler/kernel/pulls/10859

议题六：openEuler 24.03 LTS SP1版本需求收集中，请大家提交需要合入的特性到release plan --苏锦铃
截止日期：10.31
openEuler 24.03 LTS SP1版本release plan详细版本计划：
https://gitee.com/openeuler/release-management/blob/master/openEuler-24.03-LTS-SP1/release-plan.md
需求申请流程链接，请按照流程步骤提交，issue 类型选择需求， issue 标题以 [openEuler-24.03 LTS SP1] 开头：
https://gitee.com/openeuler/release-management/blob/master/Goverance/openEuler%E9%9C%80%E6%B1%82%E7%94%B3%E8%AF%B7%E6%B5%81%E7%A8%8B.md

议题七：新增袁灿为kernel sig committer
1、多年Linux开发经验，专长内存、异构等领域；
2、已经负责review 4.19各类分支128个；
3、申请为4.19分支的branch-keeper；
会议结论：同意袁灿成为openEuler Kernel sig的committer以及4.19分支的branch-keeper；

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------
【2024/10/11 Kernel SIG 双周例会】
轮值主持：廖涛（仉鹏代） 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：曾昭荣
会议链接：https://meeting.huaweicloud.com:36443/#/j/960499088
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表
议题一： 进展update（李楠&仉鹏）

OLK-5.10进展同步
近两周(2024.9.20 ~ 10.9)内进展同步:
                OLK-5.10主干更新到tag 5.10.0-231.0.0
                openEuler-22.03-LTS-SP3、SP4分支，更新到tag 5.10.0-231.0.0
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
                openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.96.0，
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
                从 5.10.0-225.0.0 更新至 5.10.0-229.0.0, 回合补丁数165个

CVE（87）
            CVE-2024-46821      https://gitee.com/openeuler/kernel/pulls/11964
            CVE-2024-46857      https://gitee.com/openeuler/kernel/pulls/12062
            CVE-2024-46844      https://gitee.com/openeuler/kernel/pulls/12050
            CVE-2024-46818      https://gitee.com/openeuler/kernel/pulls/12020
            CVE-2024-46849      https://gitee.com/openeuler/kernel/pulls/12024
            CVE-2024-41030      https://gitee.com/openeuler/kernel/pulls/12034
            CVE-2024-46816      https://gitee.com/openeuler/kernel/pulls/12038
            CVE-2024-46804      https://gitee.com/openeuler/kernel/pulls/11998
            CVE-2024-46829      https://gitee.com/openeuler/kernel/pulls/12011
            CVE-2024-44958      https://gitee.com/openeuler/kernel/pulls/12028
            CVE-2024-44950      https://gitee.com/openeuler/kernel/pulls/12032
            CVE-2024-46732      https://gitee.com/openeuler/kernel/pulls/12002
            CVE-2024-46737      https://gitee.com/openeuler/kernel/pulls/11999
            CVE-2024-46795      https://gitee.com/openeuler/kernel/pulls/11907
            CVE-2024-46814      https://gitee.com/openeuler/kernel/pulls/11976
            CVE-2024-46719      https://gitee.com/openeuler/kernel/pulls/11941
            CVE-2024-46743      https://gitee.com/openeuler/kernel/pulls/11939
            CVE-2024-46707      https://gitee.com/openeuler/kernel/pulls/11938
            CVE-2024-46841      https://gitee.com/openeuler/kernel/pulls/11946
            CVE-2024-46679      https://gitee.com/openeuler/kernel/pulls/11916
            CVE-2024-46751      https://gitee.com/openeuler/kernel/pulls/11935
            CVE-2024-46758      https://gitee.com/openeuler/kernel/pulls/11922
            CVE-2024-46780      https://gitee.com/openeuler/kernel/pulls/11925
            CVE-2024-46771      https://gitee.com/openeuler/kernel/pulls/11843
            CVE-2024-41095      https://gitee.com/openeuler/kernel/pulls/11896
            CVE-2024-36894      https://gitee.com/openeuler/kernel/pulls/11900
            CVE-2024-39482      https://gitee.com/openeuler/kernel/pulls/11899
            CVE-2024-38560      https://gitee.com/openeuler/kernel/pulls/11898
            CVE-2024-38659      https://gitee.com/openeuler/kernel/pulls/11897
            CVE-2024-27436      https://gitee.com/openeuler/kernel/pulls/11895
            CVE-2024-46681      https://gitee.com/openeuler/kernel/pulls/11867
            CVE-2024-46756      https://gitee.com/openeuler/kernel/pulls/11890
            CVE-2024-46738      https://gitee.com/openeuler/kernel/pulls/11864
            CVE-2024-46673      https://gitee.com/openeuler/kernel/pulls/11903
            CVE-2024-46753      https://gitee.com/openeuler/kernel/pulls/11875
            CVE-2024-46761      https://gitee.com/openeuler/kernel/pulls/11887
            CVE-2024-46750      https://gitee.com/openeuler/kernel/pulls/11881
            CVE-2024-46674      https://gitee.com/openeuler/kernel/pulls/11882
            CVE-2024-46726      https://gitee.com/openeuler/kernel/pulls/11866
            CVE-2024-46781      https://gitee.com/openeuler/kernel/pulls/11791
            CVE-2024-44982      https://gitee.com/openeuler/kernel/pulls/11828
            CVE-2024-45008      https://gitee.com/openeuler/kernel/pulls/11767
            CVE-2024-46798      https://gitee.com/openeuler/kernel/pulls/11749
            CVE-2024-46739      https://gitee.com/openeuler/kernel/pulls/11817
            CVE-2024-46755      https://gitee.com/openeuler/kernel/pulls/11677
            CVE-2024-45016      https://gitee.com/openeuler/kernel/pulls/11673
            CVE-2024-46721      https://gitee.com/openeuler/kernel/pulls/11810
            CVE-2024-46725      https://gitee.com/openeuler/kernel/pulls/11805
            CVE-2024-46777      https://gitee.com/openeuler/kernel/pulls/11678
            CVE-2024-46740      https://gitee.com/openeuler/kernel/pulls/11680
            CVE-2024-46695      https://gitee.com/openeuler/kernel/pulls/11815
            CVE-2024-46774      https://gitee.com/openeuler/kernel/pulls/11741
            CVE-2024-46791      https://gitee.com/openeuler/kernel/pulls/11801
            CVE-2024-43900      https://gitee.com/openeuler/kernel/pulls/11730
            CVE-2024-46759      https://gitee.com/openeuler/kernel/pulls/11738
            CVE-2024-46715      https://gitee.com/openeuler/kernel/pulls/11752
            CVE-2024-45025      https://gitee.com/openeuler/kernel/pulls/11771
            CVE-2024-40978      https://gitee.com/openeuler/kernel/pulls/11729
            CVE-2024-46752      https://gitee.com/openeuler/kernel/pulls/11706
            CVE-2024-46733      https://gitee.com/openeuler/kernel/pulls/11707
            CVE-2024-46744      https://gitee.com/openeuler/kernel/pulls/11723
            CVE-2024-46751      https://gitee.com/openeuler/kernel/pulls/11708
            CVE-2024-43846      https://gitee.com/openeuler/kernel/pulls/11728
            CVE-2024-44939      https://gitee.com/openeuler/kernel/pulls/11727
            CVE-2024-43863      https://gitee.com/openeuler/kernel/pulls/11726
            CVE-2024-46800      https://gitee.com/openeuler/kernel/pulls/11690
            CVE-2024-39501      https://gitee.com/openeuler/kernel/pulls/11693
            CVE-2024-46742      https://gitee.com/openeuler/kernel/pulls/11625
            CVE-2024-46787      https://gitee.com/openeuler/kernel/pulls/11701
            CVE-2024-44965      https://gitee.com/openeuler/kernel/pulls/11698
            CVE-2024-46731      https://gitee.com/openeuler/kernel/pulls/11665
            CVE-2024-46747      https://gitee.com/openeuler/kernel/pulls/11640
            CVE-2024-46714      https://gitee.com/openeuler/kernel/pulls/11649
            CVE-2024-46723      https://gitee.com/openeuler/kernel/pulls/11632
            CVE-2024-45025      https://gitee.com/openeuler/kernel/pulls/11555
            CVE-2024-42119      https://gitee.com/openeuler/kernel/pulls/11588
            CVE-2024-41017      https://gitee.com/openeuler/kernel/pulls/11586
            CVE-2024-42292      https://gitee.com/openeuler/kernel/pulls/11579
            CVE-2024-36270      https://gitee.com/openeuler/kernel/pulls/11637
            CVE-2024-46745      https://gitee.com/openeuler/kernel/pulls/11612
            CVE-2024-45028      https://gitee.com/openeuler/kernel/pulls/11615
            CVE-2024-36915      https://gitee.com/openeuler/kernel/pulls/11592
            CVE-2024-42121      https://gitee.com/openeuler/kernel/pulls/10933
            CVE-2024-41098      https://gitee.com/openeuler/kernel/pulls/10936
            CVE-2024-44999      https://gitee.com/openeuler/kernel/pulls/11593
            CVE-2024-45003      https://gitee.com/openeuler/kernel/pulls/11584
            CVE-2024-42104      https://gitee.com/openeuler/kernel/pulls/11574
 
bugfix（13）
kprobes: Fix deadlock issue with kmemleak
        https://gitee.com/openeuler/kernel/pulls/12073
sbitmap: backport bugfix patches
        https://gitee.com/openeuler/kernel/pulls/11942
v3 add steal_task for cgroup
        https://gitee.com/openeuler/kernel/pulls/12006
sched: fix a deadlock in task_net_group()
        https://gitee.com/openeuler/kernel/pulls/11914
NFSD: Reset cb_seq_status after NFS4ERR_DELAY
        https://gitee.com/openeuler/kernel/pulls/11871
bpf: verifier: prevent userspace memory access
        https://gitee.com/openeuler/kernel/pulls/11847
ext4: Fix race in buffer_head read fault injection
        https://gitee.com/openeuler/kernel/pulls/11494
perf/x86: Serialize set_attr_rdpmc()
        https://gitee.com/openeuler/kernel/pulls/11784
A group of optimization and bug fix for numa-affinity
        https://gitee.com/openeuler/kernel/pulls/11773
Backport bugfix from mainline
        https://gitee.com/openeuler/kernel/pulls/11562
nfs: always check dreq->error after a commit
        https://gitee.com/openeuler/kernel/pulls/11583
tcp: fix one compile error in __inet_hash_connect() 5ca8b1ea1434 !11578 net: fix one compile error in net_rship_refresh_timeout()
        https://gitee.com/openeuler/kernel/pulls/11577
perf/x86/intel: Limit the period on Haswell
        https://gitee.com/openeuler/kernel/pulls/12015
The ip_notify_sysfs_create function logs are recorded using the netdev_err interface.        
        https://gitee.com/openeuler/kernel/pulls/11788
 
feature
支持按容器级使能 steal task 功能
        https://gitee.com/openeuler/kernel/pulls/12006
 
intel
Intel: Enable CONFIG_PCIE_EDR in openeuler_defconfig for x86 to enable PCIe eDPC
        https://gitee.com/openeuler/kernel/pulls/11958
 
海思
Some bug fix patches for OLK-5.10 hns RoCE
        https://gitee.com/openeuler/kernel/pulls/11928
Some updates for HiSilicon PCIe PMU
        https://gitee.com/openeuler/kernel/issues/IAQG4B
Add description for HiSilicon PCIe PMU driver,Some updates for HiSilicon PCIe PMU
        https://gitee.com/openeuler/kernel/pulls/11628
Fix iBMA bug and change version
        https://gitee.com/openeuler/kernel/pulls/11606
hns3 udma: add resource allocation and change name of struct
        https://gitee.com/openeuler/kernel/pulls/11604
 
浪潮云
enable CONFIG_BPF_LSM option by default to use safegurad
        https://gitee.com/openeuler/kernel/pulls/9476
 
海光
Add support for Hygon model 7h processors
        https://gitee.com/openeuler/kernel/pulls/8831


议题二：《操作系统大会＆openEuler Summit 2024》峰会议题征集  （李楠）
https://www.openeuler.org/zh/interaction/summit-list/summit2024/

议题三：openeuler缺陷管理系统以及新增pull request门禁  （李楠）
https://gitee.com/Coopermassaki/cve-manager/blob/master/cve-vulner-manager/doc/md/defect-manager-manual.md#4.5-%E5%85%B6%E4%BD%99issue%E7%8A%B6%E6%80%81%E5%88%87%E6%8D%A2%E8%AF%B4%E6%98%8E%EF%BC%9
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20241011：
OLK-6.6进展同步：

新分支已合入PR 136个，commit 375个
近两周(9.20-10.11)新合入特性PR：

特性(4)：
                memory posion feature (2)：
                support poison recover from migrate folio        https://gitee.com/openeuler/kernel/pulls/11569
                mm: hwpoison: two more poison recovery        https://gitee.com/openeuler/kernel/pulls/11783

                perf(1):
                v3 arm64: perf: Add support for event counting threshold        https://gitee.com/openeuler/kernel/pulls/11608

                sched: Support to enable/disable dynamic_affinity        https://gitee.com/openeuler/kernel/pulls/11971

处理器及板卡支持专项(8)：
                Hygon(3):
                Add support for Hygon model 7h processors        https://gitee.com/openeuler/kernel/pulls/8819
                [OLK-6.6] Support Hygon Trusted Key Management run on CSV Guest        https://gitee.com/openeuler/kernel/pulls/11157
                Add support for Hygon model 10h processors        https://gitee.com/openeuler/kernel/pulls/8822

                Intel(1):
                [OLK-6.6] Intel: Backport to support Intel IFS(In Field Scan) SBAF on GNR        https://gitee.com/openeuler/kernel/pulls/11763

                RDMA/hns(4)：
                [OLK 6.6] some bugfixes for hns3        https://gitee.com/openeuler/kernel/pulls/11747
                【OLK 6.6】net: hns3: some bugfixes for hns3 driver        https://gitee.com/openeuler/kernel/pulls/11675
                RDMA/hns: Fix ah error counter in sw stat not increasing        https://gitee.com/openeuler/kernel/pulls/11618
                Some patches of RDMA from Linux to openEuler-6.6        https://gitee.com/openeuler/kernel/pulls/11554
bugfix(18)：
                cpufreq: intel_pstate: Revise global turbo disable check        https://gitee.com/openeuler/kernel/pulls/12063
                v2 Fix VSYNC referencing an unmapped VPE on GIC v4.0/v4.1        https://gitee.com/openeuler/kernel/pulls/11617
                perf/x86/intel: Limit the period on Haswell        https://gitee.com/openeuler/kernel/pulls/12016
                cppc_cpufreq: Fix possible null pointer dereference        https://gitee.com/openeuler/kernel/pulls/12017
                Merge some hns RoCE patches from the mainline to OLK-6.6        https://gitee.com/openeuler/kernel/pulls/11929
                NFSD: Reset cb_seq_status after NFS4ERR_DELAY        https://gitee.com/openeuler/kernel/pulls/11870
                arm64/mpam: Fix redefined reference of 'mpam_detect_is_enabled'        https://gitee.com/openeuler/kernel/pulls/11857
                ext4: Fix race in buffer_head read fault injection        https://gitee.com/openeuler/kernel/pulls/11495
                bpf: verifier: prevent userspace memory access        https://gitee.com/openeuler/kernel/pulls/11845
                Fix iBMA bug and change version        https://gitee.com/openeuler/kernel/pulls/11624
                efi/libstub: add checking validity of memory regions        https://gitee.com/openeuler/kernel/pulls/11790
                tools: move alignment-related macros to new <linux/align.h>        https://gitee.com/openeuler/kernel/pulls/11769
                arm64/mpam: Check mpam_detect_is_enabled() before accessing MPAM registers        https://gitee.com/openeuler/kernel/pulls/11757
                large folio: Performance and bugfix        https://gitee.com/openeuler/kernel/pulls/11651
                v3 mm/migration: do not folio copy in MIGRATE_SYNC_NO_COPY mode        https://gitee.com/openeuler/kernel/pulls/11721
                cgroup-psi-add-PSI_STATE_LAST-for-kabi-reserve        https://gitee.com/openeuler/kernel/pulls/11669
                mm: set hugepage to false when anon mthp allocation        https://gitee.com/openeuler/kernel/pulls/11641
                mm/ksm: fix possible UAF of stable_node        https://gitee.com/openeuler/kernel/pulls/11559

CVE(106):
                CVE-2024-46857        https://gitee.com/openeuler/kernel/pulls/12061
                CVE-2024-46728        https://gitee.com/openeuler/kernel/pulls/12074
                CVE-2024-46844        https://gitee.com/openeuler/kernel/pulls/12051
                CVE-2024-46849        https://gitee.com/openeuler/kernel/pulls/12023
                CVE-2024-46818        https://gitee.com/openeuler/kernel/pulls/12022
                CVE-2024-46812        https://gitee.com/openeuler/kernel/pulls/12049
                CVE-2024-45009        https://gitee.com/openeuler/kernel/pulls/11949
                CVE-2024-46816        https://gitee.com/openeuler/kernel/pulls/12039
                CVE-2024-42312        https://gitee.com/openeuler/kernel/pulls/12033
                CVE-2024-46852        https://gitee.com/openeuler/kernel/pulls/12014
                CVE-2024-46829        https://gitee.com/openeuler/kernel/pulls/12009
                CVE-2024-46732        https://gitee.com/openeuler/kernel/pulls/11995
                CVE-2024-42067        https://gitee.com/openeuler/kernel/pulls/11796
                CVE-2024-46846        https://gitee.com/openeuler/kernel/pulls/12004
                CVE-2024-46737        https://gitee.com/openeuler/kernel/pulls/12000
                CVE-2024-46776        https://gitee.com/openeuler/kernel/pulls/11969
                CVE-2024-44950        https://gitee.com/openeuler/kernel/pulls/11963
                CVE-2024-46845        https://gitee.com/openeuler/kernel/pulls/11985
                CVE-2024-46795        https://gitee.com/openeuler/kernel/pulls/11909
                CVE-2024-46827        https://gitee.com/openeuler/kernel/pulls/11983
                CVE-2024-46804        https://gitee.com/openeuler/kernel/pulls/11984
                CVE-2024-46811        https://gitee.com/openeuler/kernel/pulls/11989
                CVE-2024-46842        https://gitee.com/openeuler/kernel/pulls/11992
                CVE-2024-46814        https://gitee.com/openeuler/kernel/pulls/11979
                CVE-2024-46843        https://gitee.com/openeuler/kernel/pulls/11960
                CVE-2024-46806        https://gitee.com/openeuler/kernel/pulls/11944
                CVE-2024-46767        https://gitee.com/openeuler/kernel/pulls/11951
                CVE-2024-44958        https://gitee.com/openeuler/kernel/pulls/11956
                CVE-2024-46841        https://gitee.com/openeuler/kernel/pulls/11945
                CVE-2024-46734        https://gitee.com/openeuler/kernel/pulls/11919
                CVE-2024-46758        https://gitee.com/openeuler/kernel/pulls/11920
                CVE-2024-46797        https://gitee.com/openeuler/kernel/pulls/11820
                CVE-2024-46679        https://gitee.com/openeuler/kernel/pulls/11915
                CVE-2024-46751        https://gitee.com/openeuler/kernel/pulls/11936
                CVE-2024-46796        https://gitee.com/openeuler/kernel/pulls/11912
                CVE-2024-46746        https://gitee.com/openeuler/kernel/pulls/11908
                CVE-2024-46780        https://gitee.com/openeuler/kernel/pulls/11926
                CVE-2024-46768        https://gitee.com/openeuler/kernel/pulls/11927
                CVE-2024-46771        https://gitee.com/openeuler/kernel/pulls/11844
                CVE-2024-46761        https://gitee.com/openeuler/kernel/pulls/11885
                CVE-2024-45029        https://gitee.com/openeuler/kernel/pulls/11795
                CVE-2024-46725        https://gitee.com/openeuler/kernel/pulls/11804
                CVE-2024-46673        https://gitee.com/openeuler/kernel/pulls/11901
                CVE-2024-45011        https://gitee.com/openeuler/kernel/pulls/11859
                CVE-2024-46681        https://gitee.com/openeuler/kernel/pulls/11865
                CVE-2024-46753        https://gitee.com/openeuler/kernel/pulls/11876
                CVE-2024-46788        https://gitee.com/openeuler/kernel/pulls/11893
                CVE-2024-46787        https://gitee.com/openeuler/kernel/pulls/11840
                CVE-2024-46760        https://gitee.com/openeuler/kernel/pulls/11891
                CVE-2024-46738        https://gitee.com/openeuler/kernel/pulls/11860
                CVE-2024-46701        https://gitee.com/openeuler/kernel/pulls/11874
                CVE-2024-46736        https://gitee.com/openeuler/kernel/pulls/11689
                CVE-2024-46674        https://gitee.com/openeuler/kernel/pulls/11883
                CVE-2024-46750        https://gitee.com/openeuler/kernel/pulls/11884
                CVE-2024-46756        https://gitee.com/openeuler/kernel/pulls/11862
                CVE-2024-46686        https://gitee.com/openeuler/kernel/pulls/11758
                CVE-2024-45028        https://gitee.com/openeuler/kernel/pulls/11823
                CVE-2024-46739        https://gitee.com/openeuler/kernel/pulls/11819
                CVE-2024-46798        https://gitee.com/openeuler/kernel/pulls/11748
                CVE-2024-46741        https://gitee.com/openeuler/kernel/pulls/11850
                CVE-2024-46773        https://gitee.com/openeuler/kernel/pulls/11655
                CVE-2024-46777        https://gitee.com/openeuler/kernel/pulls/11686
                CVE-2024-46740        https://gitee.com/openeuler/kernel/pulls/11685
                CVE-2024-46784        https://gitee.com/openeuler/kernel/pulls/11798
                CVE-2024-46695        https://gitee.com/openeuler/kernel/pulls/11814
                CVE-2024-46721        https://gitee.com/openeuler/kernel/pulls/11811
                CVE-2024-46717        https://gitee.com/openeuler/kernel/pulls/11681
                CVE-2024-46755        https://gitee.com/openeuler/kernel/pulls/11679
                CVE-2024-45016        https://gitee.com/openeuler/kernel/pulls/11672
                CVE-2024-46781        https://gitee.com/openeuler/kernel/pulls/11787
                CVE-2024-46774        https://gitee.com/openeuler/kernel/pulls/11744
                CVE-2024-46772        https://gitee.com/openeuler/kernel/pulls/11766
                CVE-2024-46791        https://gitee.com/openeuler/kernel/pulls/11802
                CVE-2024-46715        https://gitee.com/openeuler/kernel/pulls/11753
                CVE-2024-46759        https://gitee.com/openeuler/kernel/pulls/11740
                CVE-2024-45008        https://gitee.com/openeuler/kernel/pulls/11733
                CVE-2024-45025        https://gitee.com/openeuler/kernel/pulls/11543
                CVE-2024-46733        https://gitee.com/openeuler/kernel/pulls/11713
                CVE-2024-46744        https://gitee.com/openeuler/kernel/pulls/11725
                CVE-2024-46752        https://gitee.com/openeuler/kernel/pulls/11715
                CVE-2024-46751        https://gitee.com/openeuler/kernel/pulls/11714
                CVE-2024-43904        https://gitee.com/openeuler/kernel/pulls/11717
                CVE-2024-41008        https://gitee.com/openeuler/kernel/pulls/11718
                CVE-2024-46800        https://gitee.com/openeuler/kernel/pulls/11691
                CVE-2024-45002        https://gitee.com/openeuler/kernel/pulls/11719
                CVE-2024-46742        https://gitee.com/openeuler/kernel/pulls/11626
                CVE-2024-46720        https://gitee.com/openeuler/kernel/pulls/11644
                CVE-2024-46731        https://gitee.com/openeuler/kernel/pulls/11666
                CVE-2024-46706        https://gitee.com/openeuler/kernel/pulls/11607
                CVE-2024-44995        https://gitee.com/openeuler/kernel/pulls/11646
                CVE-2024-44996        https://gitee.com/openeuler/kernel/pulls/11648
                CVE-2024-46714        https://gitee.com/openeuler/kernel/pulls/11656
                CVE-2024-46723        https://gitee.com/openeuler/kernel/pulls/11631
                CVE-2024-46747        https://gitee.com/openeuler/kernel/pulls/11642
                CVE-2024-44991        https://gitee.com/openeuler/kernel/pulls/11638
                CVE-2024-46785        https://gitee.com/openeuler/kernel/pulls/11629
                CVE-2024-46745        https://gitee.com/openeuler/kernel/pulls/11613
                CVE-2024-44974        https://gitee.com/openeuler/kernel/pulls/11460
                CVE-2024-45019        https://gitee.com/openeuler/kernel/pulls/11598
                CVE-2024-44959        https://gitee.com/openeuler/kernel/pulls/11566
                CVE-2024-46786        https://gitee.com/openeuler/kernel/pulls/11609
                CVE-2024-45000        https://gitee.com/openeuler/kernel/pulls/11474
                CVE-2024-44994        https://gitee.com/openeuler/kernel/pulls/11563
                CVE-2024-44999        https://gitee.com/openeuler/kernel/pulls/11594
                CVE-2024-46687        https://gitee.com/openeuler/kernel/pulls/11573
                CVE-2024-45003        https://gitee.com/openeuler/kernel/pulls/11585


        最新tag 6.6.0-46.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS
议题四：海光CSV3特性引入，以及海光CSV3虚拟机专有内存管理的PR review - 杨葛/韩里洋
PR：https://gitee.com/openeuler/kernel/pulls/9955

议题五：openEuler 24.03 LTS 构建出的驱动二进制文件无法查询内核符号 - 刘彦泽
（本次例会暂不讲解，需要进一步分析问题，此议题遗留至下一次例会）

议题六：AMD平台new ATL (Address Translation Library）引入 -- 王文宽
主线ATL补丁链接
https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=3f3174996be6
https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=6c9058f49084
openeuler中冲突PR和补丁
https://gitee.com/openeuler/kernel/pulls/3838
https://gitee.com/openeuler/kernel/commit/845ff73148337


三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------
【2024/9/20 Kernel SIG 双周例会】
轮值主持：李楠 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/988452631
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表
议题一： 进展update（李楠&仉鹏）
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20240920：
OLK-6.6进展同步：

新分支已合入PR 59个，commit 229个
近两周(8.30-9.20)新合入特性PR：

特性(10)：
                virtCCA(3):
                virtcca feature：Fix warnings        https://gitee.com/openeuler/kernel/pulls/11496
                virtcca feature: secure smmu init        https://gitee.com/openeuler/kernel/pulls/11063
                virtcca compile warning clean        https://gitee.com/openeuler/kernel/pulls/11119
                
                folio feature (6)：
                support poison recover from migrate folio        https://gitee.com/openeuler/kernel/pulls/11569
                mm: mTHP user controls to pagecache large folio        https://gitee.com/openeuler/kernel/pulls/11503
                Bugfix introduced when support folio        https://gitee.com/openeuler/kernel/pulls/11485
                ext4: Track data blocks freeing operation in journal        https://gitee.com/openeuler/kernel/pulls/11433
                large folios swap-in: handle refault cases first        https://gitee.com/openeuler/kernel/pulls/11342
                v3 mm/shmem: mTHP support for anon shmem        https://gitee.com/openeuler/kernel/pulls/11300
                
                kporbe support %pd/%pD (1):
                kprobe support %pd/%pD type        https://gitee.com/openeuler/kernel/pulls/11206

处理器及板卡支持专项(7)：
                Hygon(2):
                Add support for Hygon model 10h processors        https://gitee.com/openeuler/kernel/pulls/8822
                Add GM Driver Support for Hygon platform（Cryptographic Coprocessor，OLK-6.6)        https://gitee.com/openeuler/kernel/pulls/5453

                RDMA/hns(4)：
                RDMA/hns: Fix ah error counter in sw stat not increasing        https://gitee.com/openeuler/kernel/pulls/11618
                Some patches of RDMA from Linux to openEuler-6.6        https://gitee.com/openeuler/kernel/pulls/11554
                【olk 6.6】net: hns3: some bugfixes for netdev        https://gitee.com/openeuler/kernel/pulls/11465
                Incorporate some bonding patches as follows(OLK-6.6)        https://gitee.com/openeuler/kernel/pulls/10875
                【OLK-6.6】ROH sync patch from OLK-5.10        https://gitee.com/openeuler/kernel/pulls/11303

                [OLK-6.6]Some updates for HiSilicon PCIe PMU        https://gitee.com/openeuler/kernel/pulls/11531


bugfix(12)：
                ata: libata: Fix memory leak for error path in ata_host_alloc()        https://gitee.com/openeuler/kernel/pulls/11546
                mm/memory_hotplug: prevent accessing by index=-1        https://gitee.com/openeuler/kernel/pulls/11551
                OLK-6.6 Revert gpiolib bugfix        https://gitee.com/openeuler/kernel/pulls/11469
                mm/ksm: fix ksm_zero_pages accounting        https://gitee.com/openeuler/kernel/pulls/11464
                nfs: fix memory leak in error path of nfs4_do_reclaim        https://gitee.com/openeuler/kernel/pulls/11454
                Some fixes About cpuset partition        https://gitee.com/openeuler/kernel/pulls/11421
                iomap: fault in smaller chunks for non-large folio mappings        https://gitee.com/openeuler/kernel/pulls/11304
                mm/dynamic_pool: use batch to add free pages to dpool        https://gitee.com/openeuler/kernel/pulls/11381
                ext4: Fix wrong da count caused by concurrent racing on extent tree        https://gitee.com/openeuler/kernel/pulls/11355
                Revert SPI bugfixs        https://gitee.com/openeuler/kernel/pulls/11335
                jbd2: avoid mount failed when commit block is partial submitted        https://gitee.com/openeuler/kernel/pulls/11328
                NFSD: simplify error paths in nfsd_svc()        https://gitee.com/openeuler/kernel/pulls/11321

CVE(29):
                CVE-2024-45019        https://gitee.com/openeuler/kernel/pulls/11598
                CVE-2024-44959        https://gitee.com/openeuler/kernel/pulls/11566
                CVE-2024-46786        https://gitee.com/openeuler/kernel/pulls/11609
                CVE-2024-45000        https://gitee.com/openeuler/kernel/pulls/11474
                CVE-2024-44994        https://gitee.com/openeuler/kernel/pulls/11563
                CVE-2024-44999        https://gitee.com/openeuler/kernel/pulls/11594
                CVE-2024-46687        https://gitee.com/openeuler/kernel/pulls/11573
                CVE-2024-45003        https://gitee.com/openeuler/kernel/pulls/11585
                CVE-2024-44984        https://gitee.com/openeuler/kernel/pulls/11461
                CVE-2024-45020        https://gitee.com/openeuler/kernel/pulls/11556
                CVE-2024-44987        https://gitee.com/openeuler/kernel/pulls/11522
                CVE-2024-44986        https://gitee.com/openeuler/kernel/pulls/11518
                CVE-2024-44988        https://gitee.com/openeuler/kernel/pulls/11515
                CVE-2024-44985        https://gitee.com/openeuler/kernel/pulls/11513
                CVE-2024-43857        https://gitee.com/openeuler/kernel/pulls/11411
                CVE-2024-44972        https://gitee.com/openeuler/kernel/pulls/11455
                CVE-2024-43899        https://gitee.com/openeuler/kernel/pulls/11443
                CVE-2024-44946        https://gitee.com/openeuler/kernel/pulls/11336
                CVE-2024-43826        https://gitee.com/openeuler/kernel/pulls/11222
                CVE-2024-41082        https://gitee.com/openeuler/kernel/pulls/11314
                CVE-2024-41016        https://gitee.com/openeuler/kernel/pulls/10762
                CVE-2024-43913        https://gitee.com/openeuler/kernel/pulls/11270
                CVE-2024-42107        https://gitee.com/openeuler/kernel/pulls/11279
                CVE-2024-42139        https://gitee.com/openeuler/kernel/pulls/11280
                CVE-2024-43892        https://gitee.com/openeuler/kernel/pulls/11233
                CVE-2024-43891        https://gitee.com/openeuler/kernel/pulls/11229
                CVE-2024-43884        https://gitee.com/openeuler/kernel/pulls/11228
                CVE-2024-44946        https://gitee.com/openeuler/kernel/pulls/11363
                CVE-2024-44947        https://gitee.com/openeuler/kernel/pulls/11328

        最新tag 6.6.0-42.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS





议题二：海光增强用户态与内核态间的大数据块的拷贝优化（朱超&邱志腾）
https://gitee.com/openeuler/kernel/pulls/11509

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------
【2024/9/6 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：李楠
会议链接：https://meeting.huaweicloud.com:36443/#/j/989033877
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表
议题一： 进展update（李楠&仉鹏）
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20240830：
OLK-6.6进展同步：

新分支已合入PR 30个，commit 338个
近两周(8.17-8.30)新合入特性PR：

特性&优化(7)：
                基于ARM机密计算架构(CCA)，实现virtCCA远程证明报告获取能力        add support for arm virtcca attestation        https://gitee.com/openeuler/kernel/pulls/10942
                IMA支持virtCCA度量扩展：基于openEuler IMA机制，将度量日志度量扩展到CVM度量寄存器中。
                IMA: Support the measurement extending of TSI TMM        https://gitee.com/openeuler/kernel/pulls/11077
                
                folio相关支持PR 5个：
                mm: lazyfree THP support        https://gitee.com/openeuler/kernel/pulls/11040
                make HPAGE_PXD_* macros even if !THP         https://lkml.kernel.org/r/20240327152332.950956-4-peterx@redhat.com
                huge_memory: use !CONFIG_64BIT to relax huge page alignment on 32 bit machines         https://lkml.kernel.org/r/20240712155855.1130330-1-yang@os.amperecomputing.com
                v4 Backport bugfix of folio from v6.11        https://gitee.com/openeuler/kernel/pulls/11094
                ext4: some bugfixs for large iomap&folio        https://gitee.com/openeuler/kernel/pulls/11044

处理器及板卡支持专项(3)：
                Intel：
                Intel: Backport SPR/EMR CXL and HBM perfmon support to kernel 6.6        https://gitee.com/openeuler/kernel/pulls/10407
                Intel: Backport 3 core PMU bugfixes to kernel 6.6        https://gitee.com/openeuler/kernel/pulls/10411

                云脉芯联：
                支持GPU Peer Memory 特性让rdma网卡设备能够直接使用GPU提供的Memory进行通信，不必拷贝数据到主机内存，提升使用GPU集群进行计算/训练的效率：
                [OLK-6.6] drivers: add GPU Peer Memory support        https://gitee.com/openeuler/kernel/pulls/11043


LTS(2):
                [openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.46-47 LTS Patches        https://gitee.com/openeuler/kernel/pulls/11168
                Backport LTS conflicting patches        https://gitee.com/openeuler/kernel/pulls/11081

bugfix(5)：
                【OLK 6.6】net: hns3: use the user's cfg after reset        https://gitee.com/openeuler/kernel/pulls/10918
                cpufreq: CPPC: Eliminate the impact of cpc_read() latency error        https://gitee.com/openeuler/kernel/pulls/11108
                net: usb: qmi_wwan: fix memory leak for not ip packets        https://gitee.com/openeuler/kernel/pulls/11018
                block: Fix lockdep warning in blk_mq_mark_tag_wait        https://gitee.com/openeuler/kernel/pulls/10927
                v2 perf/x86: Fix smp_processor_id()-in-preemptible warnings        https://gitee.com/openeuler/kernel/pulls/10907

CVE(13):
                CVE-2024-43892        https://gitee.com/openeuler/kernel/pulls/11233
                CVE-2024-43891        https://gitee.com/openeuler/kernel/pulls/11229
                CVE-2024-43884        https://gitee.com/openeuler/kernel/pulls/11228
                CVE-2024-41071        https://gitee.com/openeuler/kernel/pulls/10698
                CVE-2024-43883        https://gitee.com/openeuler/kernel/pulls/11158
                CVE-2024-43869        https://gitee.com/openeuler/kernel/pulls/11156
                CVE-2024-43882        https://gitee.com/openeuler/kernel/pulls/11100
                CVE-2024-43868        https://gitee.com/openeuler/kernel/pulls/11106
                CVE-2024-39298        https://gitee.com/openeuler/kernel/pulls/11125
                CVE-2024-43824        https://gitee.com/openeuler/kernel/pulls/10998
                CVE-2024-43819        https://gitee.com/openeuler/kernel/pulls/11004
                CVE-2024-43840        https://gitee.com/openeuler/kernel/pulls/10969
                CVE-2024-40966        https://gitee.com/openeuler/kernel/pulls/10911

        最新tag 6.6.0-39.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
OLK-5.10进展同步
近两周(2024.8.16 ~ 8.30)内进展同步:
                OLK-5.10主干更新到tag 5.10.0-225.0.0
                openEuler-22.03-LTS-SP3、SP4分支，更新到tag 5.10.0-225.0.0
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
                openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.91.0，
                                ISO镜像和update rpm包获取链接: 
                                                https://repo.openeuler.org/openEuler-22.03-LTS-SP1
                以OLK-5.10为例:
                从 5.10.0-223.0.0 更新至 5.10.0-225.0.0, 回合补丁数283个
                
同步linux 5.10.y社区LTS补丁集2个: 5.10.214 - 5.10.215      https://gitee.com/openeuler/kernel/pulls/11079
 
CVE(50)
        CVE-2024-42288      https://gitee.com/openeuler/kernel/pulls/11123
        CVE-2022-48920      https://gitee.com/openeuler/kernel/pulls/11163
        CVE-2024-42265      https://gitee.com/openeuler/kernel/pulls/11151
        CVE-2024-42280      https://gitee.com/openeuler/kernel/pulls/11092
        CVE-2024-42297      https://gitee.com/openeuler/kernel/pulls/11085
        CVE-2024-42308      https://gitee.com/openeuler/kernel/pulls/11138
        CVE-2024-43882      https://gitee.com/openeuler/kernel/pulls/11099
        CVE-2024-42302      https://gitee.com/openeuler/kernel/pulls/11118
        CVE-2024-43860      https://gitee.com/openeuler/kernel/pulls/11028
        CVE-2024-43879      https://gitee.com/openeuler/kernel/pulls/11075
        CVE-2024-42284      https://gitee.com/openeuler/kernel/pulls/11003
        CVE-2024-42285      https://gitee.com/openeuler/kernel/pulls/10985
        CVE-2024-42271      https://gitee.com/openeuler/kernel/pulls/11115
        CVE-2024-38613      https://gitee.com/openeuler/kernel/pulls/11054
        CVE-2024-36946      https://gitee.com/openeuler/kernel/pulls/11055
        CVE-2024-42120      https://gitee.com/openeuler/kernel/pulls/11126
        CVE-2024-43866      https://gitee.com/openeuler/kernel/pulls/11091
        CVE-2024-42318      https://gitee.com/openeuler/kernel/pulls/11027
        CVE-2024-42281      https://gitee.com/openeuler/kernel/pulls/11045
        CVE-2024-43823      https://gitee.com/openeuler/kernel/pulls/11038
        CVE-2024-42313      https://gitee.com/openeuler/kernel/pulls/10999
        CVE-2024-43831      https://gitee.com/openeuler/kernel/pulls/11013
        CVE-2024-43828      https://gitee.com/openeuler/kernel/pulls/10971
        CVE-2024-42306      https://gitee.com/openeuler/kernel/pulls/11022
        CVE-2024-41059      https://gitee.com/openeuler/kernel/pulls/11012
        CVE-2024-42322      https://gitee.com/openeuler/kernel/pulls/10993
        CVE-2024-42126      https://gitee.com/openeuler/kernel/pulls/10976
        CVE-2024-42122      https://gitee.com/openeuler/kernel/pulls/10990
        CVE-2024-43819      https://gitee.com/openeuler/kernel/pulls/11006
        CVE-2024-41015      https://gitee.com/openeuler/kernel/pulls/11023
        CVE-2024-41068      https://gitee.com/openeuler/kernel/pulls/10991
        CVE-2024-42309      https://gitee.com/openeuler/kernel/pulls/10962
        CVE-2024-39490      https://gitee.com/openeuler/kernel/pulls/10453
        CVE-2024-42290      https://gitee.com/openeuler/kernel/pulls/10995
        CVE-2024-42131      https://gitee.com/openeuler/kernel/pulls/11007
        CVE-2024-42304      https://gitee.com/openeuler/kernel/pulls/10979
        CVE-2024-43840      https://gitee.com/openeuler/kernel/pulls/10968
        CVE-2024-42310      https://gitee.com/openeuler/kernel/pulls/10982
        CVE-2024-43839      https://gitee.com/openeuler/kernel/pulls/10958
        CVE-2024-41088      https://gitee.com/openeuler/kernel/pulls/10614
        CVE-2024-36880      https://gitee.com/openeuler/kernel/pulls/10951
        CVE-2024-43830      https://gitee.com/openeuler/kernel/pulls/10956
        CVE-2024-42127      https://gitee.com/openeuler/kernel/pulls/10931
        CVE-2024-42283      https://gitee.com/openeuler/kernel/pulls/10947
        CVE-2024-40902      https://gitee.com/openeuler/kernel/pulls/10745
        CVE-2024-40966      https://gitee.com/openeuler/kernel/pulls/10912
        CVE-2024-42236      https://gitee.com/openeuler/kernel/pulls/10914
        CVE-2024-42070      https://gitee.com/openeuler/kernel/pulls/10846
        CVE-2024-42232       https://gitee.com/openeuler/kernel/pulls/10928
 
bugfix(7)
        net: usb: qmi_wwan: fix memory leak for not ip packets
            https://gitee.com/openeuler/kernel/pulls/11019
        perf: Optimize perf_pmu_migrate_context()
            https://gitee.com/openeuler/kernel/pulls/10965
        sched: fix numa_group uninitialized in show_numa_stats()
            https://gitee.com/openeuler/kernel/pulls/10963
        v4 Some clean up and bugfix for hisi_hbmdev
            https://gitee.com/openeuler/kernel/pulls/10945
        Fixed two memory leak issues of the Perf tool
            https://gitee.com/openeuler/kernel/pulls/10113
        IP notify code optimization
            https://gitee.com/openeuler/kernel/issues/IALRBD
        ima: dont disable digest_list if the file is not processed
            https://gitee.com/openeuler/kernel/pulls/10813
 
鲲鹏
        roh/rdma: Support rdma_cm and cnp configure
            https://gitee.com/openeuler/kernel/pulls/11010
        v2 Some bugfix for HNS RoCE
            https://gitee.com/openeuler/kernel/pulls/11036
        UNIC: fixup the problem of print and free mguid'memory after init failed
            https://gitee.com/openeuler/kernel/pulls/10925
        sdma: fix input validate problems
            https://gitee.com/openeuler/kernel/pulls/10689
        net: hns3: add some feature patches
            https://gitee.com/openeuler/kernel/pulls/11071
 
intel
        Intel: backport RAPL bugfixes up to v6.9
            https://gitee.com/openeuler/kernel/pulls/9573
        Intel: Backport SPR/EMR CXL and HBM support to kernel 5.10
            https://gitee.com/openeuler/kernel/pulls/10797
        Intel: Backport 3 core PMU bugfixes to kernel 5.10
            https://gitee.com/openeuler/kernel/pulls/10799


议题二： 内核 CONFIG_BPF_LSM 选项开关启用
https://gitee.com/openeuler/kernel/issues/IAGNKW#note_30148219
https://gitee.com/openeuler/kernel/pulls/9476

议题三： 海光CCP国密驱动适配
https://gitee.com/openeuler/kernel/pulls/5453

议题四：海光可信密钥管理在CSV虚拟机中运行
https://gitee.com/openeuler/kernel/pulls/11157

议题五：申请成为openEuler Kernel sig的committer - 韩里洋
主要负责arch/x86/kvm, virt/kvm, drivers/crypto/ccp这3个目录的内容。
1. 线下与海光蒲文协调海光CPU在openEuler Kernel的支持工作。海光蒲文同意韩里洋作为committer维护海光安全和海光CPU通用的支持工作。
2. 线下与openEuler仉鹏老师沟通申请成为openEuler Kernel sig的committer相关流程工作
会议结论：同意韩里洋申请成为openEuler Kernel sig的committer

议题六：海光申请将CONFIG_CMA=y设置为openEuler kernel 6.6 x86架构默认配置进展 - 韩里洋
1. 海光参与兼容性sig例会，添加议题就CONFIG_CMA=y的问题进行讨


三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------------------
【2024/8/16 Kernel SIG 双周例会】
轮值主持：仉鹏（廖涛代）【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：桑力鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/966224457
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（李楠&仉鹏）

OLK-5.10进展同步
近两周(2024.8.5 ~ 8.16)内进展同步:
        OLK-5.10主干更新到tag 5.10.0-223.0.0
        openEuler-22.03-LTS-SP3、SP4分支，**更新到tag** 5.10.0-223.0.0
                ISO镜像和update rpm包获取链接: 
                        https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                        https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        openEuler-22.03-LTS-SP1分支，**更新到tag** 5.10.0-136.89.0，
                ISO镜像和update rpm包获取链接: 
                        https://repo.openeuler.org/openEuler-22.03-LTS-SP1
        以OLK-5.10为例:
        从 5.10.0-221.0.0 更新至 5.10.0-223.0.0, 回合补丁数324个
 
同步linux 5.10.y社区LTS补丁集2个: 5.10.212 - 5.10.213
 
 CVE（103）
        CVE-2024-42087      https://gitee.com/openeuler/kernel/pulls/10877
        CVE-2024-42143      https://gitee.com/openeuler/kernel/pulls/10878
        CVE-2024-41092      https://gitee.com/openeuler/kernel/pulls/10876
        CVE-2024-42229      https://gitee.com/openeuler/kernel/pulls/10885
        CVE-2024-42156      https://gitee.com/openeuler/kernel/pulls/10888
        CVE-2024-41065      https://gitee.com/openeuler/kernel/pulls/10820
        CVE-2024-41042      https://gitee.com/openeuler/kernel/pulls/10842
        CVE-2024-42246      https://gitee.com/openeuler/kernel/pulls/10869
        CVE-2024-42244      https://gitee.com/openeuler/kernel/pulls/10873
        CVE-2024-42247      https://gitee.com/openeuler/kernel/pulls/10849
        CVE-2024-42223      https://gitee.com/openeuler/kernel/pulls/10817
        CVE-2024-41035      https://gitee.com/openeuler/kernel/pulls/10616
        CVE-2024-42095      https://gitee.com/openeuler/kernel/pulls/10801
        CVE-2024-42126      https://gitee.com/openeuler/kernel/pulls/10514
        CVE-2024-42096      https://gitee.com/openeuler/kernel/pulls/10704
        CVE-2024-42225      https://gitee.com/openeuler/kernel/pulls/10836
        CVE-2024-42148      https://gitee.com/openeuler/kernel/pulls/10839
        CVE-2024-40942      https://gitee.com/openeuler/kernel/pulls/10807
        CVE-2024-42154      https://gitee.com/openeuler/kernel/pulls/10810
        CVE-2024-41078      https://gitee.com/openeuler/kernel/pulls/10752
        CVE-2024-41034      https://gitee.com/openeuler/kernel/pulls/10781
        CVE-2024-41012      https://gitee.com/openeuler/kernel/pulls/10733
        CVE-2024-42128      https://gitee.com/openeuler/kernel/pulls/10761
        CVE-2024-42098      https://gitee.com/openeuler/kernel/pulls/10681
        CVE-2024-42158      https://gitee.com/openeuler/kernel/pulls/10798
        CVE-2021-47582      https://gitee.com/openeuler/kernel/pulls/10778
        CVE-2024-42157      https://gitee.com/openeuler/kernel/pulls/10784
        CVE-2022-48827      https://gitee.com/openeuler/kernel/pulls/10787
        CVE-2024-41027      https://gitee.com/openeuler/kernel/pulls/10764
        CVE-2024-42089      https://gitee.com/openeuler/kernel/pulls/10666
        CVE-2024-41087      https://gitee.com/openeuler/kernel/pulls/10624
        CVE-2024-41073      https://gitee.com/openeuler/kernel/pulls/10652
        CVE-2024-42155      https://gitee.com/openeuler/kernel/pulls/10785
        CVE-2024-42093      https://gitee.com/openeuler/kernel/pulls/10737
        CVE-2023-52888      https://gitee.com/openeuler/kernel/pulls/10743
        CVE-2024-42160      https://gitee.com/openeuler/kernel/pulls/10759
        CVE-2024-42084      https://gitee.com/openeuler/kernel/pulls/10530
        CVE-2024-41066      https://gitee.com/openeuler/kernel/pulls/10679
        CVE-2024-42124      https://gitee.com/openeuler/kernel/pulls/10725
        CVE-2024-42161      https://gitee.com/openeuler/kernel/pulls/10582
        CVE-2024-42101      https://gitee.com/openeuler/kernel/pulls/10717
        CVE-2024-41079      https://gitee.com/openeuler/kernel/pulls/10713
        CVE-2024-42094      https://gitee.com/openeuler/kernel/pulls/10727
        CVE-2024-39497      https://gitee.com/openeuler/kernel/pulls/10694
        CVE-2024-42162      https://gitee.com/openeuler/kernel/pulls/10715
        CVE-2024-42137      https://gitee.com/openeuler/kernel/pulls/10691
        CVE-2024-42129      https://gitee.com/openeuler/kernel/pulls/10621
        CVE-2024-38546      https://gitee.com/openeuler/kernel/pulls/9682
        CVE-2024-38594      https://gitee.com/openeuler/kernel/pulls/10427
        CVE-2024-41055      https://gitee.com/openeuler/kernel/pulls/10697
        CVE-2024-40910      https://gitee.com/openeuler/kernel/pulls/10589
        CVE-2024-42077      https://gitee.com/openeuler/kernel/pulls/10683
        CVE-2024-42092      https://gitee.com/openeuler/kernel/pulls/10566
        CVE-2024-42076      https://gitee.com/openeuler/kernel/pulls/10670
        CVE-2024-41062      https://gitee.com/openeuler/kernel/pulls/10661
        CVE-2024-41014      https://gitee.com/openeuler/kernel/pulls/10519
        CVE-2024-41013      https://gitee.com/openeuler/kernel/pulls/10650
        CVE-2024-41070      https://gitee.com/openeuler/kernel/pulls/10654
        CVE-2024-41023      https://gitee.com/openeuler/kernel/pulls/10630
        CVE-2024-42090      https://gitee.com/openeuler/kernel/pulls/10391
        CVE-2024-41097      https://gitee.com/openeuler/kernel/pulls/10642
        CVE-2024-42106      https://gitee.com/openeuler/kernel/pulls/10644
        CVE-2024-42080      https://gitee.com/openeuler/kernel/pulls/10636
        CVE-2024-42224      https://gitee.com/openeuler/kernel/pulls/10648
        CVE-2024-41089      https://gitee.com/openeuler/kernel/pulls/10598
        CVE-2024-42155      https://gitee.com/openeuler/kernel/pulls/10503
        CVE-2024-42105      https://gitee.com/openeuler/kernel/pulls/10557
        CVE-2024-41044      https://gitee.com/openeuler/kernel/pulls/10600
        CVE-2024-41072      https://gitee.com/openeuler/kernel/pulls/10612
        CVE-2024-42145      https://gitee.com/openeuler/kernel/pulls/10603
        CVE-2024-41048      https://gitee.com/openeuler/kernel/pulls/10554
        CVE-2024-42082      https://gitee.com/openeuler/kernel/pulls/10536
        CVE-2024-41046      https://gitee.com/openeuler/kernel/pulls/10594
        CVE-2024-41081      https://gitee.com/openeuler/kernel/pulls/10569
        CVE-2023-52887      https://gitee.com/openeuler/kernel/pulls/10564
        CVE-2024-41020      https://gitee.com/openeuler/kernel/pulls/10586
        CVE-2024-41090      https://gitee.com/openeuler/kernel/pulls/10541
        CVE-2024-41091      https://gitee.com/openeuler/kernel/pulls/10540
        CVE-2024-40961      https://gitee.com/openeuler/kernel/pulls/10534
        CVE-2024-42068      https://gitee.com/openeuler/kernel/pulls/10544
        CVE-2024-41064      https://gitee.com/openeuler/kernel/pulls/10548
        CVE-2024-41063      https://gitee.com/openeuler/kernel/pulls/10527
        CVE-2024-38627      https://gitee.com/openeuler/kernel/pulls/10420
        CVE-2024-42097      https://gitee.com/openeuler/kernel/pulls/10475
        CVE-2024-41077      https://gitee.com/openeuler/kernel/pulls/10465
        CVE-2024-42115      https://gitee.com/openeuler/kernel/pulls/10476
        CVE-2024-41080      https://gitee.com/openeuler/kernel/pulls/10467
        CVE-2024-41019      https://gitee.com/openeuler/kernel/pulls/10454
        CVE-2024-41049      https://gitee.com/openeuler/kernel/pulls/10383
        CVE-2024-41041      https://gitee.com/openeuler/kernel/pulls/10460
        CVE-2024-42228      https://gitee.com/openeuler/kernel/pulls/10493
        CVE-2024-42086      https://gitee.com/openeuler/kernel/pulls/10487
        CVE-2024-40988      https://gitee.com/openeuler/kernel/pulls/10384
        CVE-2024-38561      https://gitee.com/openeuler/kernel/pulls/10425
        CVE-2024-38561      https://gitee.com/openeuler/kernel/pulls/10424
        CVE-2024-40959      https://gitee.com/openeuler/kernel/pulls/10458
        CVE-2024-41069      https://gitee.com/openeuler/kernel/pulls/10404
        CVE-2024-40976      https://gitee.com/openeuler/kernel/pulls/10352
        CVE-2024-35825      https://gitee.com/openeuler/kernel/pulls/10406
        CVE-2024-39509      https://gitee.com/openeuler/kernel/pulls/10271
        CVE-2021-47382      https://gitee.com/openeuler/kernel/pulls/10431
        CVE-2024-41040      https://gitee.com/openeuler/kernel/pulls/10440
 
 Bugfix（6）
        v2 ext4: flexibly control whether to enable dioread_nolock by default
                https://gitee.com/openeuler/kernel/pulls/10862
        sched/cputime: Fix mul_u64_u64_div_u64() precision for cputime
                https://gitee.com/openeuler/kernel/pulls/10814
        backport mainline patches
                https://gitee.com/openeuler/kernel/pulls/10489
        PCI/ROM: Fix PCI ROM header check bug
                https://gitee.com/openeuler/kernel/pulls/10361
        irqchip/mbigen: Fix mbigen node address layout
                https://e.gitee.com/open_euler/dashboard?issue=IAI2U3
        mbigen: add kvm dependency
                https://gitee.com/openeuler/kernel/pulls/10765
 
 特性
        sched/fair: Prefer physical cores when migrating tasks
                https://gitee.com/openeuler/kernel/pulls/10887
        net/smc: enable smcrv1 when RNIC supports rocev2
                https://gitee.com/openeuler/kernel/pulls/10328
 
云脉芯联
        Add GPU Direct RDMA support
                https://gitee.com/openeuler/kernel/pulls/10523




+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
202408016：
OLK-6.6进展同步：

新分支已合入PR 62个，commit 1071个
近两周(8.3-8.16)新合入特性PR：

特性&优化(3)：
                基于ARM64机密计算架构(CCA)，在使能了Trustzone SEL2的芯片平台上，利用软件实现virtCCA提供机密虚机能力        https://gitee.com/openeuler/kernel/pulls/10653
                smart_grid特性的优化        https://gitee.com/openeuler/kernel/pulls/10556
                sdei watchdog检测机制优化        https://gitee.com/openeuler/kernel/pulls/6863

处理器及板卡支持专项(2)：
                海光：
                [OLK-6.6] Support Hygon Trusted Key Management virtualization        https://gitee.com/openeuler/kernel/pulls/10819
                [OLK-6.6] Support Trusted computing(TC) feature for hygon CPU        https://gitee.com/openeuler/kernel/pulls/10690

LTS(2):
                Backport 6.6.40-6.6.44 LTS Patches        https://gitee.com/openeuler/kernel/pulls/10657
                Backport 6.6.45 LTS Patches        https://gitee.com/openeuler/kernel/pulls/10893

bugfix(15)：
                Fix the issue that vm can't access to host with virtio-net        https://gitee.com/openeuler/kernel/pulls/10585
                ima: dont disable digest_list if the file is not processed        https://gitee.com/openeuler/kernel/pulls/10812
                selftests/bpf: Add netlink helper library        https://gitee.com/openeuler/kernel/pulls/10899
                v2 ext4: flexibly control whether to enable dioread_nolock by default        https://gitee.com/openeuler/kernel/pulls/10863
                sched/cputime: Fix mul_u64_u64_div_u64() precision for cputime        https://gitee.com/openeuler/kernel/pulls/10816
                dummy_struct_ops selftest failed        https://gitee.com/openeuler/kernel/pulls/10805
                blk-wbt: don't throttle swap writes in direct reclaim        https://gitee.com/openeuler/kernel/pulls/10345
                perf util: Add a function for replacing characters in a string        https://gitee.com/openeuler/kernel/pulls/10793
                Backport vmalloc 2 bugfix        https://gitee.com/openeuler/kernel/pulls/10729
                irqchip/mbigen: Fix mbigen node address layout        https://gitee.com/openeuler/kernel/pulls/10746
                backport mainline patchs        https://gitee.com/openeuler/kernel/pulls/10533
                block: propagate partition scanning errors to the BLKRRPART ioctl        https://gitee.com/openeuler/kernel/pulls/10319
                mm/dynamic_pool: two bugfix about THP and migration        https://gitee.com/openeuler/kernel/pulls/10517
                Make cpuset.cpus.exclusive independent of cpuset.cpus        https://gitee.com/openeuler/kernel/pulls/10470
                bpf: Fix null-pointer-deref in resolve_prog_type()        https://gitee.com/openeuler/kernel/pulls/10351

CVE(37):
                CVE-2024-42156        https://gitee.com/openeuler/kernel/pulls/10720
                CVE-2024-41042        https://gitee.com/openeuler/kernel/pulls/10843
                CVE-2024-36881        https://gitee.com/openeuler/kernel/pulls/10823
                CVE-2024-40956        https://gitee.com/openeuler/kernel/pulls/10824
                CVE-2024-36971        https://gitee.com/openeuler/kernel/pulls/10855
                CVE-2024-41035        https://gitee.com/openeuler/kernel/pulls/10615
                CVE-2024-42114        https://gitee.com/openeuler/kernel/pulls/10834
                CVE-2024-42158        https://gitee.com/openeuler/kernel/pulls/10772
                CVE-2024-26944        https://gitee.com/openeuler/kernel/pulls/10722
                CVE-2024-41073        https://gitee.com/openeuler/kernel/pulls/10635
                CVE-2024-41045        https://gitee.com/openeuler/kernel/pulls/10757
                CVE-2024-41014        https://gitee.com/openeuler/kernel/pulls/10518
                CVE-2024-42129        https://gitee.com/openeuler/kernel/pulls/10622
                CVE-2024-42162        https://gitee.com/openeuler/kernel/pulls/10677
                CVE-2024-41021        https://gitee.com/openeuler/kernel/pulls/10639
                CVE-2024-35860        https://gitee.com/openeuler/kernel/pulls/10658
                CVE-2024-41013        https://gitee.com/openeuler/kernel/pulls/10649
                CVE-2024-41023        https://gitee.com/openeuler/kernel/pulls/10631
                CVE-2024-42155        https://gitee.com/openeuler/kernel/pulls/10500
                CVE-2024-41072        https://gitee.com/openeuler/kernel/pulls/10610
                CVE-2024-41044        https://gitee.com/openeuler/kernel/pulls/10599
                CVE-2024-41091        https://gitee.com/openeuler/kernel/pulls/10539
                CVE-2024-41090        https://gitee.com/openeuler/kernel/pulls/10538
                CVE-2024-41048        https://gitee.com/openeuler/kernel/pulls/10555
                CVE-2024-41046        https://gitee.com/openeuler/kernel/pulls/10596
                CVE-2024-41062        https://gitee.com/openeuler/kernel/pulls/10579
                CVE-2024-42068        https://gitee.com/openeuler/kernel/pulls/10545
                CVE-2024-41064        https://gitee.com/openeuler/kernel/pulls/10547
                CVE-2024-41085        https://gitee.com/openeuler/kernel/pulls/10443
                CVE-2024-41056        https://gitee.com/openeuler/kernel/pulls/10401
                CVE-2024-42126        https://gitee.com/openeuler/kernel/pulls/10512
                CVE-2024-41063        https://gitee.com/openeuler/kernel/pulls/10524
                CVE-2024-42086        https://gitee.com/openeuler/kernel/pulls/10486
                CVE-2024-41077        https://gitee.com/openeuler/kernel/pulls/10466
                CVE-2024-42097        https://gitee.com/openeuler/kernel/pulls/10480
                CVE-2024-41039        https://gitee.com/openeuler/kernel/pulls/10385
                CVE-2024-41069        https://gitee.com/openeuler/kernel/pulls/10403


        最新tag 6.6.0-38.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS

议题二： 内核网络栈CAQM拥塞算法介绍（张泽&贾成君）


议题三：征集中，可在此处直接填写申报（注意备注申报人）


三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------------------
【2024/8/2 Kernel SIG 双周例会】
轮值主持：曾昭荣 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：仉鹏（廖涛代）
会议链接：https://meeting.huaweicloud.com:36443/#/j/983058635
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（李楠&仉鹏）
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20240802：
OLK-6.6进展同步：

新分支已合入PR 76个，commit 1534个
近两周(7.20-8.2)新合入特性PR：

特性&优化(3)：
                support for SMC-D loopback_lo feature        https://gitee.com/openeuler/kernel/pulls/9892
                mm: filemap: optimize semantic when thp_exec_enabled is set to 3        https://gitee.com/openeuler/kernel/pulls/10264
                Part of "mm: mapcount for large folios + page_mapcount() cleanups"        https://gitee.com/openeuler/kernel/pulls/10188

处理器及板卡支持专项(3)：
                海思hns：
                [RoCE]从社区回合patch到openEuler（OLK-6.6）        https://gitee.com/openeuler/kernel/pulls/10260

                海光：
                [OLK-6.6]HYGON: Support CSV Reuse ASID feature on Hygon CPUs        https://gitee.com/openeuler/kernel/pulls/5264
                [OLK-6.6]HYGON: Support Hygon DCU passthrough to VMs        https://gitee.com/openeuler/kernel/pulls/5262

LTS(2):
                Backport 6.6.35-40 LTS patches from upstream        https://gitee.com/openeuler/kernel/pulls/10507
                Backport 6.6.33-34 LTS patches from upstream        https://gitee.com/openeuler/kernel/pulls/10369

bugfix(13)：
                iommu/arm-smmu-v3: Reducing the CMD_SYNC times        https://gitee.com/openeuler/kernel/pulls/10371
                PCI/ROM: Fix PCI ROM header check bug        https://gitee.com/openeuler/kernel/pulls/10228
                [sync] PR-10408: iommu/arm-smmu-v3: Fix the compile warning        https://gitee.com/openeuler/kernel/pulls/10416
                ovl: simplify ovl_parse_param_lowerdir()        https://gitee.com/openeuler/kernel/pulls/10388
                BMA: Fix DMA reset problem and change the version        https://gitee.com/openeuler/kernel/pulls/10398
                jbd2: stop waiting for space when jbd2_cleanup_journal_tail() returns error        https://gitee.com/openeuler/kernel/pulls/10358
                ext4: improve buffered write with more than one blocks_per_folio        https://gitee.com/openeuler/kernel/pulls/9904
                improve dump_page() robustness        https://gitee.com/openeuler/kernel/pulls/10317
                x86: resctrl: Fix illegal access by the chips not having RDT        https://gitee.com/openeuler/kernel/pulls/10170
                wifi: mac80211: mesh: Fix leak of mesh_preq_queue objects        https://gitee.com/openeuler/kernel/pulls/10311
                [OLK-6.6] drivers: Fix compile warning "argument used uninitialized"        https://gitee.com/openeuler/kernel/pulls/10294
                media: dvb-usb: Fix unexpected infinite loop in dvb_usb_read_remote_control()        https://gitee.com/openeuler/kernel/pulls/10257
                fpga: bridge: add owner module and take its refcount        https://gitee.com/openeuler/kernel/pulls/10233

CVE(52):
                CVE-2024-42115  https://gitee.com/openeuler/kernel/pulls/10474
                CVE-2024-41080  https://gitee.com/openeuler/kernel/pulls/10463
                CVE-2024-41076  https://gitee.com/openeuler/kernel/pulls/10456
                CVE-2024-41019  https://gitee.com/openeuler/kernel/pulls/10450
                CVE-2024-41020  https://gitee.com/openeuler/kernel/pulls/10394
                CVE-2024-41096  https://gitee.com/openeuler/kernel/pulls/10496
                CVE-2024-41049  https://gitee.com/openeuler/kernel/pulls/10380
                CVE-2024-41018  https://gitee.com/openeuler/kernel/pulls/10378
                CVE-2024-42141  https://gitee.com/openeuler/kernel/pulls/10491
                CVE-2024-42228  https://gitee.com/openeuler/kernel/pulls/10495
                CVE-2024-41040  https://gitee.com/openeuler/kernel/pulls/10442
                CVE-2024-41041  https://gitee.com/openeuler/kernel/pulls/10457
                CVE-2024-39486  https://gitee.com/openeuler/kernel/pulls/9824
                CVE-2024-39471  https://gitee.com/openeuler/kernel/pulls/10344
                CVE-2024-38556  https://gitee.com/openeuler/kernel/pulls/9533
                CVE-2024-38607  https://gitee.com/openeuler/kernel/pulls/9361
                CVE-2024-41006  https://gitee.com/openeuler/kernel/pulls/10171
                CVE-2024-41010  https://gitee.com/openeuler/kernel/pulls/10312
                CVE-2024-39475  https://gitee.com/openeuler/kernel/pulls/10254
                CVE-2024-40908  https://gitee.com/openeuler/kernel/pulls/10078
                CVE-2024-40981  https://gitee.com/openeuler/kernel/pulls/10261
                CVE-2024-40967  https://gitee.com/openeuler/kernel/pulls/10066
                CVE-2024-40953  https://gitee.com/openeuler/kernel/pulls/9971
                CVE-2024-38619  https://gitee.com/openeuler/kernel/pulls/9782
                CVE-2024-36979  https://gitee.com/openeuler/kernel/pulls/10287
                CVE-2024-40952  https://gitee.com/openeuler/kernel/pulls/10018
                CVE-2024-40962  https://gitee.com/openeuler/kernel/pulls/9985
                CVE-2024-40982  https://gitee.com/openeuler/kernel/pulls/10248
                CVE-2024-35966  https://gitee.com/openeuler/kernel/pulls/9243
                CVE-2024-40915  https://gitee.com/openeuler/kernel/pulls/10160
                CVE-2024-41007  https://gitee.com/openeuler/kernel/pulls/10231
                CVE-2024-40951  https://gitee.com/openeuler/kernel/pulls/10237
                CVE-2024-40974  https://gitee.com/openeuler/kernel/pulls/9915
                CVE-2024-36923  https://gitee.com/openeuler/kernel/pulls/10148
                CVE-2024-40922  https://gitee.com/openeuler/kernel/pulls/10056
                CVE-2024-40936  https://gitee.com/openeuler/kernel/pulls/10226
                CVE-2024-39494  https://gitee.com/openeuler/kernel/pulls/10177
                CVE-2024-41009  https://gitee.com/openeuler/kernel/pulls/10220
                CVE-2024-35931  https://gitee.com/openeuler/kernel/pulls/10219
                CVE-2024-36022  https://gitee.com/openeuler/kernel/pulls/10167
                CVE-2024-37021  https://gitee.com/openeuler/kernel/pulls/9598
                CVE-2024-40968  https://gitee.com/openeuler/kernel/pulls/10139
                CVE-2024-39496  https://gitee.com/openeuler/kernel/pulls/10044
                CVE-2024-38578  https://gitee.com/openeuler/kernel/pulls/10114
                CVE-2024-38618  https://gitee.com/openeuler/kernel/pulls/10133
                CVE-2024-36936  https://gitee.com/openeuler/kernel/pulls/10115
                CVE-2024-38617  https://gitee.com/openeuler/kernel/pulls/10131
                CVE-2024-38572  https://gitee.com/openeuler/kernel/pulls/10132
                CVE-2024-36016  https://gitee.com/openeuler/kernel/pulls/10001
                CVE-2024-33847  https://gitee.com/openeuler/kernel/pulls/10176
                CVE-2024-40975  https://gitee.com/openeuler/kernel/pulls/10106
                CVE-2024-41004  https://gitee.com/openeuler/kernel/pulls/10109

        最新tag 6.6.0-35.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS
        
OLK 5.10进展同步
近两周(2024.7.19 ~ 8.2)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-221.0.0
        openEuler-22.03-LTS-SP4分支，**更新到tag** 5.10.0-221.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP4/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4/update/
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-221.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP1分支，**更新到tag** 5.10.0-136.87.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
以OLK-5.10为例:
从 5.10.0-219.0.0 更新至 5.10.0-221.0.0, 回合补丁数538个
 
同步linux 5.10.y社区LTS补丁集2个: 5.10.210 - 5.10.211
 
CVE (57):       
        CVE-2024-39476      https://gitee.com/openeuler/kernel/pulls/10436
        CVE-2024-40945      https://gitee.com/openeuler/kernel/pulls/10065
        CVE-2024-36479      https://gitee.com/openeuler/kernel/pulls/10334
        CVE-2024-41011      https://gitee.com/openeuler/kernel/pulls/10363
        CVE-2024-35837      https://gitee.com/openeuler/kernel/pulls/10058
        CVE-2024-35884      https://gitee.com/openeuler/kernel/pulls/10057
        CVE-2024-38611      https://gitee.com/openeuler/kernel/pulls/10321
        CVE-2024-39471      https://gitee.com/openeuler/kernel/pulls/10342
        CVE-2024-38607      https://gitee.com/openeuler/kernel/pulls/9362
        CVE-2024-40953      https://gitee.com/openeuler/kernel/pulls/9976
        CVE-2024-40967      https://gitee.com/openeuler/kernel/pulls/10073
        CVE-2024-41006      https://gitee.com/openeuler/kernel/pulls/10172
        CVE-2024-39475      https://gitee.com/openeuler/kernel/pulls/10253
        CVE-2022-48859      https://gitee.com/openeuler/kernel/pulls/10309
        CVE-2024-36031      https://gitee.com/openeuler/kernel/pulls/9035
        CVE-2024-27012      https://gitee.com/openeuler/kernel/pulls/9182
        CVE-2024-27065      https://gitee.com/openeuler/kernel/pulls/10303
        CVE-2024-40981      https://gitee.com/openeuler/kernel/pulls/10258
        CVE-2022-48816      https://gitee.com/openeuler/kernel/pulls/10280
        CVE-2023-4458       https://gitee.com/openeuler/kernel/pulls/9780
        CVE-2024-38619      https://gitee.com/openeuler/kernel/pulls/10278
        CVE-2024-40982      https://gitee.com/openeuler/kernel/pulls/10246
        CVE-2021-47622      https://gitee.com/openeuler/kernel/pulls/10224
        CVE-2022-48844      https://gitee.com/openeuler/kernel/pulls/10245
        CVE-2024-41007      https://gitee.com/openeuler/kernel/pulls/10232
        CVE-2022-48814      https://gitee.com/openeuler/kernel/pulls/10202
        CVE-2024-40904      https://gitee.com/openeuler/kernel/pulls/10266
        CVE-2022-48703      https://gitee.com/openeuler/kernel/pulls/9430
        CVE-2024-40956      https://gitee.com/openeuler/kernel/pulls/10255
        CVE-2024-40915      https://gitee.com/openeuler/kernel/pulls/10189
        CVE-2021-47205      https://gitee.com/openeuler/kernel/pulls/10187
        CVE-2024-40974      https://gitee.com/openeuler/kernel/pulls/9913
        CVE-2024-35931      https://gitee.com/openeuler/kernel/pulls/10217
        CVE-2024-41009      https://gitee.com/openeuler/kernel/pulls/10222
        CVE-2024-34777      https://gitee.com/openeuler/kernel/pulls/10203
        CVE-2024-40932      https://gitee.com/openeuler/kernel/pulls/10019
        CVE-2024-39494      https://gitee.com/openeuler/kernel/pulls/10178
        CVE-2024-38618      https://gitee.com/openeuler/kernel/pulls/10135
        CVE-2024-38578      https://gitee.com/openeuler/kernel/pulls/10104
        CVE-2024-40968      https://gitee.com/openeuler/kernel/pulls/10138
        CVE-2024-41004      https://gitee.com/openeuler/kernel/pulls/10107
        CVE-2024-40912      https://gitee.com/openeuler/kernel/pulls/10156
        CVE-2024-37021      https://gitee.com/openeuler/kernel/pulls/9836
        CVE-2024-40980      https://gitee.com/openeuler/kernel/pulls/10165
        CVE-2024-40990      https://gitee.com/openeuler/kernel/pulls/10162
        CVE-2024-40983      https://gitee.com/openeuler/kernel/pulls/10048
        CVE-2024-39506      https://gitee.com/openeuler/kernel/pulls/10022
        CVE-2024-40963      https://gitee.com/openeuler/kernel/pulls/10150
        CVE-2024-36939      https://gitee.com/openeuler/kernel/pulls/10041
        CVE-2024-40941      https://gitee.com/openeuler/kernel/pulls/10128
        CVE-2024-40929      https://gitee.com/openeuler/kernel/pulls/10118
        CVE-2024-40987      https://gitee.com/openeuler/kernel/pulls/10079
        CVE-2024-39499      https://gitee.com/openeuler/kernel/pulls/10052
        CVE-2024-40995      https://gitee.com/openeuler/kernel/pulls/10088
        CVE-2024-39508      https://gitee.com/openeuler/kernel/pulls/9992
        CVE-2024-40905      https://gitee.com/openeuler/kernel/pulls/9901
        CVE-2024-38559      https://gitee.com/openeuler/kernel/pulls/10096
 
bugfix（16）
    net: move to_gnet_bpf_attach_type() to filter.c
        https://gitee.com/openeuler/kernel/pulls/10418
    iommu/arm-smmu-v3: Fix the compile warning
        https://gitee.com/openeuler/kernel/pulls/10408
    net/sched: initialize noop_qdisc owner
        https://gitee.com/openeuler/kernel/pulls/10339
    v2 mm: numa-affinity: support THP migration
        https://gitee.com/openeuler/kernel/pulls/10336
    [RoCE]从社区回合patch到openEuler（OLK-5.10）
        https://gitee.com/openeuler/kernel/pulls/10184
    media: dvb-usb: Fix unexpected infinite loop in dvb_usb_read_remote_control()
        https://gitee.com/openeuler/kernel/pulls/10262
    openvswitch触发软锁
        https://gitee.com/openeuler/kernel/pulls/10179
        https://gitee.com/openeuler/kernel/pulls/10383    
    nfs: Ensure that the NFS client returns a correct writeback error code
        https://gitee.com/openeuler/kernel/pulls/10046
    arm64: mm: Pass pbha-performance-only bit under chosen node
        https://gitee.com/openeuler/kernel/pulls/9817
    xfs: fix mount hung while sb recover fail
        https://gitee.com/openeuler/kernel/pulls/10009
    nvdimm: Backport some bugfixs
        https://gitee.com/openeuler/kernel/pulls/9931
    sched/fair: Take the scheduling domain into account in select_idle_core()
        https://gitee.com/openeuler/kernel/pulls/10194
    jbd2: stop waiting for space when jbd2_cleanup_journal_tail() returns error
        https://gitee.com/openeuler/kernel/pulls/10366
    net: phy: add set_loopback interface to realtek phy driver
        https://gitee.com/openeuler/kernel/pulls/10318
 
特性：
    mm: numa-affinity: support THP migration
        https://gitee.com/openeuler/kernel/pulls/10336
    鲲鹏920支持自适应NUMA
        https://gitee.com/openeuler/kernel/pulls/10316
 
iBMA driver:
     BMA: Fix DMA reset problem and change the version
         https://gitee.com/openeuler/kernel/pulls/10398
 
sdma-dae driver:
    sdma-dae: fix interrupt handle logic
       https://gitee.com/openeuler/kernel/pulls/10295
 
hisilicon:
    hns3 udma: functions related to CQ bank IDs are supported.
        https://gitee.com/openeuler/kernel/pulls/10210
    Backport bugfixes for RDMA/hns from mainline linux
        https://gitee.com/openeuler/kernel/pulls/10061
 
议题二：中苏移动有关内核kabi接口特性的澄清说明    申报人：杨汉弛

议题三：征集中，可在此处直接填写申报（注意备注申报人）

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------------------
【2024/7/19 Kernel SIG 双周例会】
轮值主持：廖涛（仉鹏代） 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->张伽琳->廖涛】
下次轮值主持：曾昭荣
会议链接：https://meeting.huaweicloud.com:36443/#/j/961167952
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（李楠&仉鹏）
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20240719：
OLK-6.6进展同步：

新分支已合入PR 89个，commit 243个
近两周(7.6-7.19)新合入特性PR：

特性(3)：
                MPTCP Upstream part 13 https://gitee.com/openeuler/kernel/pulls/9861
                按需加载支持failover特性 https://gitee.com/openeuler/kernel/pulls/9240
                clang编译性能优化特性PGO支持 https://gitee.com/openeuler/kernel/pulls/9294

处理器及板卡支持专项(3)：
                海光：
                海光CSV/CSV2 特性增强与bugfix https://gitee.com/openeuler/kernel/pulls/5261
                海光CSV/CSV2 客户端热迁移特性与重启 https://gitee.com/openeuler/kernel/pulls/5260

                龙芯：
                loongarch平台config配置对kdump的支持 https://gitee.com/openeuler/kernel/pulls/9801

bugfix(13)：
                nvdimm: Backport some bugfixs https://gitee.com/openeuler/kernel/pulls/9933
                xfs: fix mount hung while sb recover fail https://gitee.com/openeuler/kernel/pulls/10011
                iommu/arm-smmu-v3: Change the style to identify the the hisi_platform https://gitee.com/openeuler/kernel/pulls/9962
                v3 Fix xfs file creation issue https://gitee.com/openeuler/kernel/pulls/9876
                gfs2: Fix potential glock use-after-free on unmount https://gitee.com/openeuler/kernel/pulls/9877
                block: enable BLK_IO_HUNG_TASK_CHECK by default https://gitee.com/openeuler/kernel/pulls/9859
                cgroup: Fix AA deadlock caused by cgroup_bpf_release https://gitee.com/openeuler/kernel/pulls/9838
                net: fix wrong return value in bpf_sock_ops_get_uid_gid https://gitee.com/openeuler/kernel/pulls/9788
                mm: mem_reliable: Make counting reliable task usage compatible with folio https://gitee.com/openeuler/kernel/pulls/9816
                Add a switch to enable hungtask check for io https://gitee.com/openeuler/kernel/pulls/9770
                mm/slub: Reduce memory consumption in extreme scenarios https://gitee.com/openeuler/kernel/pulls/9775
                cgroup: fix uaf when proc_cpuset_show https://gitee.com/openeuler/kernel/pulls/9709
                修改ipvlan模式兼容其他操作系统        https://gitee.com/openeuler/kernel/pulls/9862

CVE(70):
                CVE-2024-40980        https://gitee.com/openeuler/kernel/pulls/10166
                CVE-2024-40990        https://gitee.com/openeuler/kernel/pulls/10161
                CVE-2024-40916        https://gitee.com/openeuler/kernel/pulls/10111
                CVE-2024-40912        https://gitee.com/openeuler/kernel/pulls/10155
                CVE-2024-40963        https://gitee.com/openeuler/kernel/pulls/10149
                CVE-2024-35247        https://gitee.com/openeuler/kernel/pulls/10103
                CVE-2024-38559        https://gitee.com/openeuler/kernel/pulls/10097
                CVE-2024-40932        https://gitee.com/openeuler/kernel/pulls/10021
                CVE-2024-40941        https://gitee.com/openeuler/kernel/pulls/10127
                CVE-2024-40929        https://gitee.com/openeuler/kernel/pulls/10117
                CVE-2024-40977        https://gitee.com/openeuler/kernel/pulls/10116
                CVE-2024-39506        https://gitee.com/openeuler/kernel/pulls/10017
                CVE-2024-40983        https://gitee.com/openeuler/kernel/pulls/10051
                CVE-2024-40923        https://gitee.com/openeuler/kernel/pulls/10102
                CVE-2024-36014        https://gitee.com/openeuler/kernel/pulls/10093
                CVE-2024-39508        https://gitee.com/openeuler/kernel/pulls/9989
                CVE-2024-40955        https://gitee.com/openeuler/kernel/pulls/10083
                CVE-2024-38600        https://gitee.com/openeuler/kernel/pulls/10069
                CVE-2024-34030        https://gitee.com/openeuler/kernel/pulls/10074
                CVE-2024-40995        https://gitee.com/openeuler/kernel/pulls/10087
                CVE-2024-40906        https://gitee.com/openeuler/kernel/pulls/10064
                CVE-2024-39485        https://gitee.com/openeuler/kernel/pulls/10038
                CVE-2024-39503        https://gitee.com/openeuler/kernel/pulls/9970
                CVE-2024-39499        https://gitee.com/openeuler/kernel/pulls/10050
                CVE-2024-40987        https://gitee.com/openeuler/kernel/pulls/10006
                CVE-2024-40918        https://gitee.com/openeuler/kernel/pulls/9959
                CVE-2024-40960        https://gitee.com/openeuler/kernel/pulls/10028
                CVE-2024-40957        https://gitee.com/openeuler/kernel/pulls/10005
                CVE-2024-38583        https://gitee.com/openeuler/kernel/pulls/10059
                CVE-2024-39463        https://gitee.com/openeuler/kernel/pulls/10025
                CVE-2024-39479        https://gitee.com/openeuler/kernel/pulls/9835
                CVE-2024-38388        https://gitee.com/openeuler/kernel/pulls/9998
                CVE-2024-38614        https://gitee.com/openeuler/kernel/pulls/9997
                CVE-2024-39505        https://gitee.com/openeuler/kernel/pulls/9956
                CVE-2024-39488        https://gitee.com/openeuler/kernel/pulls/9914
                CVE-2024-40971        https://gitee.com/openeuler/kernel/pulls/9944
                CVE-2024-39500        https://gitee.com/openeuler/kernel/pulls/9909
                CVE-2024-36973        https://gitee.com/openeuler/kernel/pulls/10045
                CVE-2024-39464        https://gitee.com/openeuler/kernel/pulls/10055
                CVE-2024-40905        https://gitee.com/openeuler/kernel/pulls/9900
                CVE-2024-40972        https://gitee.com/openeuler/kernel/pulls/9979
                CVE-2024-41005        https://gitee.com/openeuler/kernel/pulls/9988
                CVE-2024-40984        https://gitee.com/openeuler/kernel/pulls/9945
                CVE-2024-40964        https://gitee.com/openeuler/kernel/pulls/9935
                CVE-2024-39487        https://gitee.com/openeuler/kernel/pulls/9896
                CVE-2024-40943        https://gitee.com/openeuler/kernel/pulls/9928
                CVE-2024-40934        https://gitee.com/openeuler/kernel/pulls/9938
                CVE-2024-39502        https://gitee.com/openeuler/kernel/pulls/9899
                CVE-2024-40997        https://gitee.com/openeuler/kernel/pulls/9898
                CVE-2024-40931        https://gitee.com/openeuler/kernel/pulls/9903
                CVE-2024-39478        https://gitee.com/openeuler/kernel/pulls/9878
                CVE-2024-39489        https://gitee.com/openeuler/kernel/pulls/9888
                CVE-2024-38576        https://gitee.com/openeuler/kernel/pulls/9610
                CVE-2024-39472        https://gitee.com/openeuler/kernel/pulls/9845
                CVE-2024-38581        https://gitee.com/openeuler/kernel/pulls/9857
                CVE-2024-38620        https://gitee.com/openeuler/kernel/pulls/9829
                CVE-2024-39473        https://gitee.com/openeuler/kernel/pulls/9841
                CVE-2024-39484        https://gitee.com/openeuler/kernel/pulls/9834
                CVE-2024-39461        https://gitee.com/openeuler/kernel/pulls/9779
                CVE-2024-39481        https://gitee.com/openeuler/kernel/pulls/9811
                CVE-2024-39483        https://gitee.com/openeuler/kernel/pulls/9810
                CVE-2024-39480        https://gitee.com/openeuler/kernel/pulls/9821
                CVE-2024-38664        https://gitee.com/openeuler/kernel/pulls/9807
                CVE-2024-36478        https://gitee.com/openeuler/kernel/pulls/9804
                CVE-2024-38598        https://gitee.com/openeuler/kernel/pulls/9805
                CVE-2024-38554        https://gitee.com/openeuler/kernel/pulls/9802
                CVE-2024-38548        https://gitee.com/openeuler/kernel/pulls/9793
                CVE-2024-39467        https://gitee.com/openeuler/kernel/pulls/9649
                CVE-2024-39469        https://gitee.com/openeuler/kernel/pulls/9732
                CVE-2024-38567        https://gitee.com/openeuler/kernel/pulls/9614

        最新tag 6.6.0-34.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS
    
    
    
OLK-5.10进展同步
近两周(2024.7.8 ~ 7.19)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-219.0.0
        openEuler-22.03-LTS-SP4分支，**更新到tag** 5.10.0-219.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP4/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4/update/
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-219.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP1分支，**更新到tag** 5.10.0-136.85.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        以OLK-5.10为例:
        从 5.10.0-217.0.0 更新至 5.10.0-219.0.0, 回合补丁数156个
        
5.10.0-217.0.0..5.10.0-219.0.0
CVE（54）：
        CVE-2024-40960        https://gitee.com/openeuler/kernel/pulls/10031
        CVE-2024-37078        https://gitee.com/openeuler/kernel/pulls/9984
        CVE-2024-41005        https://gitee.com/openeuler/kernel/pulls/9990
        CVE-2021-47432        https://gitee.com/openeuler/kernel/pulls/10040
        CVE-2024-40971        https://gitee.com/openeuler/kernel/pulls/9950
        CVE-2024-40972        https://gitee.com/openeuler/kernel/pulls/9968
        CVE-2024-40943        https://gitee.com/openeuler/kernel/pulls/9926
        CVE-2024-39488        https://gitee.com/openeuler/kernel/pulls/9910
        CVE-2024-39500        https://gitee.com/openeuler/kernel/pulls/9908
        CVE-2024-40984        https://gitee.com/openeuler/kernel/pulls/9946
        CVE-2024-40934        https://gitee.com/openeuler/kernel/pulls/9936
        CVE-2024-39505        https://gitee.com/openeuler/kernel/pulls/9953
        CVE-2024-39502        https://gitee.com/openeuler/kernel/pulls/9897
        CVE-2021-47200        https://gitee.com/openeuler/kernel/pulls/9924
        CVE-2024-40931        https://gitee.com/openeuler/kernel/pulls/9905
        CVE-2024-39487        https://gitee.com/openeuler/kernel/pulls/9893
        CVE-2023-52755        https://gitee.com/openeuler/kernel/pulls/9827
        CVE-2023-52757        https://gitee.com/openeuler/kernel/pulls/9825
        CVE-2024-39489        https://gitee.com/openeuler/kernel/pulls/9889
        CVE-2024-27416        https://gitee.com/openeuler/kernel/pulls/9368
        CVE-2024-38570        https://gitee.com/openeuler/kernel/pulls/9872
        CVE-2024-39469        https://gitee.com/openeuler/kernel/pulls/9745
        CVE-2024-39472        https://gitee.com/openeuler/kernel/pulls/9843
        CVE-2024-38583        https://gitee.com/openeuler/kernel/pulls/9853
        CVE-2024-39484        https://gitee.com/openeuler/kernel/pulls/9831
        CVE-2024-39467        https://gitee.com/openeuler/kernel/pulls/9643
        CVE-2024-39480        https://gitee.com/openeuler/kernel/pulls/9820
        CVE-2024-36478        https://gitee.com/openeuler/kernel/pulls/9799
        CVE-2024-38598        https://gitee.com/openeuler/kernel/pulls/9783
        CVE-2022-48733        https://gitee.com/openeuler/kernel/pulls/9772
        CVE-2024-38548        https://gitee.com/openeuler/kernel/pulls/9795
        CVE-2024-38623        https://gitee.com/openeuler/kernel/pulls/9363
        CVE-2024-38605        https://gitee.com/openeuler/kernel/pulls/9373
        CVE-2024-37353        https://gitee.com/openeuler/kernel/pulls/9538
        CVE-2024-34027        https://gitee.com/openeuler/kernel/pulls/9766
        CVE-2022-48765        https://gitee.com/openeuler/kernel/pulls/9719
        CVE-2024-38565        https://gitee.com/openeuler/kernel/pulls/9764
        CVE-2024-38615        https://gitee.com/openeuler/kernel/pulls/9711
        CVE-2024-26816        https://gitee.com/openeuler/kernel/pulls/9761
        CVE-2024-38558        https://gitee.com/openeuler/kernel/pulls/9756
        CVE-2024-38602        https://gitee.com/openeuler/kernel/pulls/9716
        CVE-2024-38554        https://gitee.com/openeuler/kernel/pulls/9672
        CVE-2024-39301        https://gitee.com/openeuler/kernel/pulls/9735
        CVE-2024-39277        https://gitee.com/openeuler/kernel/pulls/9572
        CVE-2024-38547        https://gitee.com/openeuler/kernel/pulls/9571
        CVE-2024-38621        https://gitee.com/openeuler/kernel/pulls/9440
        CVE-2024-38780        https://gitee.com/openeuler/kernel/pulls/9701
        CVE-2024-38582        https://gitee.com/openeuler/kernel/pulls/9640
        CVE-2024-36489        https://gitee.com/openeuler/kernel/pulls/9662
        CVE-2024-38586        https://gitee.com/openeuler/kernel/pulls/9657
        CVE-2024-38637        https://gitee.com/openeuler/kernel/pulls/9686
        CVE-2024-38579        https://gitee.com/openeuler/kernel/pulls/9675
        CVE-2024-35988        https://gitee.com/openeuler/kernel/pulls/8096
        CVE-2024-38540        https://gitee.com/openeuler/kernel/pulls/9712
  
Bugfix（12）：      
        https://gitee.com/openeuler/kernel/pulls/9850
power: supply: bq27xxx-i2c: Do not free non existing IRQ
        https://gitee.com/openeuler/kernel/pulls/10060
ipvlan: Dont Use skb->sk in ipvlan_process_v{4,6}_outbound
        https://gitee.com/openeuler/kernel/pulls/9871
cifs: Fix deadlock in cifs_writepages during reconnect
        https://gitee.com/openeuler/kernel/pulls/9884
cgroup: Fix AA deadlock caused by cgroup_bpf_release
        https://gitee.com/openeuler/kernel/pulls/9879
fs: improve dump_mapping() robustness
        https://gitee.com/openeuler/kernel/pulls/9881
v2 iommu/arm-smmu-v3: Change the style to identify the the hisi_platform
        https://gitee.com/openeuler/kernel/pulls/9851
net/sched: act_skbmod: prevent kernel-infoleak
        https://gitee.com/openeuler/kernel/pulls/9792
v3 net: fix one NULL pointer dereference bug in net_rship module
        https://gitee.com/openeuler/kernel/pulls/9616
v2 wifi: carl9170: add a proper sanity check for endpoints
        https://gitee.com/openeuler/kernel/pulls/9768
iomap: Don't finish dio under irq when there exists pages
        https://gitee.com/openeuler/kernel/pulls/9753
v2 arm64: arm_pmuv3: Correctly extract and check the PMUVer
        https://gitee.com/openeuler/kernel/pulls/9731
v2 Backport bpf bugfixes
  
Driver Support:
net/hinic3: Add pcie device ID adaption for DPU_NIC card
                https://gitee.com/openeuler/kernel/pulls/9705
roh/core: Support macvlan in roh.
                https://gitee.com/openeuler/kernel/pulls/9884

议题二：海光CSV3技术要求内核配置CONFIG_CMA=y，这通过海光的Kconfig entry HYGON_CSV主动select CMA实现，但是推送PR之后，由于CONFIG_CMA=y，导致了openEuler/kernel的x86 kabi测试失败，x86的openeuler_defconfig是否可以默认配置CONFIG_CMA=y。

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------------------
【2024/7/5 Kernel SIG 双周例会】
轮值主持：张伽琳 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->张伽琳->廖涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/980862324
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳&仉鹏）
OLK-5.10进展同步
近两周(2024.6.24 ~ 7.5)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-217.0.0
        openEuler-22.03-LTS-SP4分支，更新到tag 5.10.0-217.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP4/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4/update/
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-217.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.83.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        以OLK-5.10为例:
        从 5.10.0-209.0.0 更新至 5.10.0-217.0.0, 回合补丁数193个
        git log 5.10.0-209.0.0..5.10.0-217.0.0 --oneline | wc -l
        193

## 5.10.0-209.0.0..5.10.0-217.0.0
### Fix CVE (58):
        CVE-2024-27405 https://gitee.com/openeuler/kernel/pulls/9429  usb: gadget: ncm: Avoid dropping datagrams of properly parsed NTBs
        CVE-2024-37356 https://gitee.com/openeuler/kernel/pulls/9532  CVE-2024-37356
        CVE-2024-38589 https://gitee.com/openeuler/kernel/pulls/9496  netrom: fix possible dead-lock in nr_rt_ioctl()
        CVE-2024-38544 https://gitee.com/openeuler/kernel/pulls/9514  RDMA/rxe: Fix seg fault in rxe_comp_queue_pkt
        CVE-2024-38597 https://gitee.com/openeuler/kernel/pulls/9559  CVE-2024-38597
        CVE-2024-36014 https://gitee.com/openeuler/kernel/pulls/9595  drm/arm/malidp: fix a possible null pointer dereference
        CVE-2021-47618 https://gitee.com/openeuler/kernel/pulls/9593  ARM: 9170/1: fix panic when kasan and kprobe are enabled
        CVE-2024-39292 https://gitee.com/openeuler/kernel/pulls/9504  um: Add winch to winch_handlers before registering winch IRQ
        CVE-2024-38661 https://gitee.com/openeuler/kernel/pulls/9587  s390/ap: Fix crash in AP internal function modify_bitmap()
        CVE-2024-38553 https://gitee.com/openeuler/kernel/pulls/9569  net: fec: remove .ndo_poll_controller to avoid deadlocks
        CVE-2022-48744 https://gitee.com/openeuler/kernel/pulls/9540  net/mlx5e: Avoid field-overflowing memcpy()
        CVE-2024-37354 https://gitee.com/openeuler/kernel/pulls/9577 v2  btrfs: fix crash on racing fsync and size-extending write into prealloc
        CVE-2024-38625 https://gitee.com/openeuler/kernel/pulls/9563  fs/ntfs3: Check 'folio' pointer for NULL
        CVE-2024-38633 https://gitee.com/openeuler/kernel/pulls/9383  serial: max3100: Update uart_driver_registered on driver removal
        CVE-2024-35969 https://gitee.com/openeuler/kernel/pulls/9499  ipv6: fix race condition between ipv6_get_ifaddr and ipv6_del_addr
        CVE-2024-35899 https://gitee.com/openeuler/kernel/pulls/9500  netfilter: nf_tables: flush pending destroy work before exit_net release
        CVE-2024-38599 https://gitee.com/openeuler/kernel/pulls/9453  jffs2: prevent xattr node from overflowing the eraseblock
        CVE-2024-35947 https://gitee.com/openeuler/kernel/pulls/9202  dyndbg: fix old BUG_ON in >control parser
        CVE-2024-27052 https://gitee.com/openeuler/kernel/pulls/9193  wifi: rtl8xxxu: add cancel_work_sync() for c2hcmd_work
        CVE-2024-27417 https://gitee.com/openeuler/kernel/pulls/9201  ipv6: fix potential "struct net" leak in inet6_rtm_getaddr()
        CVE-2024-27038 https://gitee.com/openeuler/kernel/pulls/9190  clk: Fix clk_core_get NULL dereference
        CVE-2024-27047 https://gitee.com/openeuler/kernel/pulls/9188  net: phy: fix phy_get_internal_delay accessing an empty array
        CVE-2024-27032 https://gitee.com/openeuler/kernel/pulls/9462 v2  CVE-2024-27032
        CVE-2024-38549 https://gitee.com/openeuler/kernel/pulls/9408  drm/mediatek: Add 0 size check to mtk_drm_gem_obj
        CVE-2024-38577 https://gitee.com/openeuler/kernel/pulls/9447  rcu-tasks: Fix show_rcu_tasks_trace_gp_kthread buffer overflow
        CVE-2021-47381 https://gitee.com/openeuler/kernel/pulls/9425  ASoC: SOF: Fix DSP oops stack dump output contents
        CVE-2024-38552 https://gitee.com/openeuler/kernel/pulls/9321  drm/amd/display: Fix potential index out of bounds in color transformation function
        CVE-2021-47599 https://gitee.com/openeuler/kernel/pulls/9297  CVE-2021-47599
        CVE-2024-31076 https://gitee.com/openeuler/kernel/pulls/9401  Fix CVE-2024-31076
        CVE-2024-38587 https://gitee.com/openeuler/kernel/pulls/9395  CVE-2024-38587
        CVE-2024-38632 https://gitee.com/openeuler/kernel/pulls/9386  vfio/pci: fix potential memory leak in vfio_intx_enable()
        CVE-2024-26988 https://gitee.com/openeuler/kernel/pulls/9199  init/main.c: Fix potential static_command_line memory overflow
        CVE-2024-35879 https://gitee.com/openeuler/kernel/pulls/8683 v4  Fix CVE-2024-35879
        CVE-2024-38634 https://gitee.com/openeuler/kernel/pulls/9339  serial: max3100: Lock port->lock when calling uart_handle_cts_change()
        CVE-2024-38556 https://gitee.com/openeuler/kernel/pulls/9470  net/mlx5: Add a timeout to acquire the command queue semaphore
        CVE-2024-38555 https://gitee.com/openeuler/kernel/pulls/9442  net/mlx5: Discard command completions in internal error
        CVE-2024-38538 https://gitee.com/openeuler/kernel/pulls/9290  net: bridge: xmit: make sure we have at least eth header len bytes
        CVE-2024-38541 https://gitee.com/openeuler/kernel/pulls/9284  of: module: add buffer overflow check in of_modalias()
        CVE-2024-38630 https://gitee.com/openeuler/kernel/pulls/9477  watchdog: cpu5wdt.c: Fix use-after-free bug caused by cpu5wdt_trigger
        CVE-2024-39276 https://gitee.com/openeuler/kernel/pulls/9544  ext4: fix mb_cache_entry's e_refcnt leak in ext4_xattr_block_cache_find()
        CVE-2024-38624 https://gitee.com/openeuler/kernel/pulls/9483  fs/ntfs3: Use 64 bit variable to avoid 32 bit overflow
        CVE-2024-39362 https://gitee.com/openeuler/kernel/pulls/9558  CVE-2024-39362
        CVE-2024-38564 https://gitee.com/openeuler/kernel/pulls/9456  bpf: Add BPF_PROG_TYPE_CGROUP_SKB attach type enforcement in BPF_LINK_CREATE
        CVE-2022-48772 https://gitee.com/openeuler/kernel/pulls/9527  media: lgdt3306a: Add a check against null-pointer-def
        CVE-2024-36974 https://gitee.com/openeuler/kernel/pulls/9333  net/sched: taprio: always validate TCA_TAPRIO_ATTR_PRIOMAP
        CVE-2024-26925 https://gitee.com/openeuler/kernel/pulls/8098  netfilter: nf_tables: release mutex after nft_gc_seq_end from abort path
        CVE-2024-26592 https://gitee.com/openeuler/kernel/pulls/5860  ksmbd: fix UAF issue in ksmbd_tcp_new_connection()
        CVE-2024-38596 https://gitee.com/openeuler/kernel/pulls/9327  af_unix: Fix data races in unix_release_sock/unix_stream_sendmsg
        CVE-2024-38601 https://gitee.com/openeuler/kernel/pulls/9264  ring-buffer: Fix a race between readers and resize checks
        CVE-2024-26661 https://gitee.com/openeuler/kernel/pulls/9305  CVE-2024-26661 following bugfix
        CVE-2023-39180 https://gitee.com/openeuler/kernel/pulls/9246  ksmbd: no response from compound read
        CVE-2024-36978 https://gitee.com/openeuler/kernel/pulls/9268  net: sched: sch_multiq: fix possible OOB write in multiq_tune()
        CVE-2023-39179 https://gitee.com/openeuler/kernel/pulls/9103  ksmbd: no response from compound read
        CVE-2021-47469 https://gitee.com/openeuler/kernel/pulls/9186  spi: Fix deadlock when adding SPI controllers on SPI buses
        CVE-2024-27053 https://gitee.com/openeuler/kernel/pulls/9180  wifi: wilc1000: fix RCU usage in connect path
        CVE-2024-36969 https://gitee.com/openeuler/kernel/pulls/9212  drm/amd/display: Fix division by zero in setup_dsc_config
        CVE-2024-35830 https://gitee.com/openeuler/kernel/pulls/9000  media: tc358743: register v4l2 async device only after successful setup
        CVE-2024-36923 https://gitee.com/openeuler/kernel/pulls/9087  fs/9p: fix uninitialized values during inode evict

### Processors Support:
#### phytium:
        https://gitee.com/openeuler/kernel/pulls/9039 [OLK-5.10] drm/phytium: Replace default efi fb0 with dc fb
#### Kunpeng:
        https://gitee.com/openeuler/kernel/pulls/9283 hns3 udma: support non share jfr mode in UM
        https://gitee.com/openeuler/kernel/pulls/9244 urma: cannot uninstall uburma driver

### performance
        https://gitee.com/openeuler/kernel/pulls/9507  Enable SIS_UTIL for arm64 and optimize load_balance
        https://gitee.com/openeuler/kernel/pulls/9508  Revert "fs: Use CHECK_DATA_CORRUPTION() when
        https://gitee.com/openeuler/kernel/pulls/9391  fs: Use CHECK_DATA_CORRUPTION() when kernel bugs are detected

### bugfix
        https://gitee.com/openeuler/kernel/pulls/9160  xfs: don't use current->journal_info
        https://gitee.com/openeuler/kernel/pulls/9644  fix uaf when proc_cpuset_show
        https://gitee.com/openeuler/kernel/pulls/8744  ext4 bugfix from mainline
        https://gitee.com/openeuler/kernel/pulls/9434  cvm: delete dead code and resolve macro definition holes
        https://gitee.com/openeuler/kernel/pulls/9511  blk-throttle: check for overflow in calculate_bytes_allowed
        https://gitee.com/openeuler/kernel/pulls/9421 v3  block: fix WARNING in init_blk_queue_async_dispatch
        https://gitee.com/openeuler/kernel/pulls/9350  tracing: Fix permissions for the buffer_percent file
        https://gitee.com/openeuler/kernel/pulls/9347  sched: ARM64 enables SIS_PROP and disables SIS_UTIL"
        https://gitee.com/openeuler/kernel/pulls/9318  Revert "sched/fair:ARM64 enables SIS_UTIL and disables SIS_PROP"
        https://gitee.com/openeuler/kernel/pulls/9277 ima: Fix violation digests extending issue in cvm
        https://gitee.com/openeuler/kernel/pulls/9250  Fix token error issue when concurrent calls
        https://gitee.com/openeuler/kernel/pulls/9241 v2  Bugfix backport for rcu
        https://gitee.com/openeuler/kernel/pulls/9239  Fix allmodconfig build frame size error
        https://gitee.com/openeuler/kernel/pulls/9207 v2  sched: smart_grid: fix potential NULL pointer dereference
        https://gitee.com/openeuler/kernel/pulls/7729  loop: use lo->lo_disk for kobject_uevent
        https://gitee.com/openeuler/kernel/pulls/9211  memcg: attach memcg async reclaim worker to curcpu
        https://gitee.com/openeuler/kernel/pulls/9168  UBIFS: fixes a series of issues that caused by power cut

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20240705：
OLK-6.6进展同步：

新分支已合入PR 83个，commit 320个
近两周(6.22-7.5)新合入特性PR：

特性：
                MPTCP Upstream part 6~12
                https://gitee.com/openeuler/kernel/pulls/9262
                https://gitee.com/openeuler/kernel/pulls/9266
                https://gitee.com/openeuler/kernel/pulls/9301
                https://gitee.com/openeuler/kernel/pulls/9304
                https://gitee.com/openeuler/kernel/pulls/9352
                https://gitee.com/openeuler/kernel/pulls/9371
                https://gitee.com/openeuler/kernel/pulls/9519

处理器及板卡支持专项：
                海思：
                【OLK-6.6】RDMA/hns: Fix some mutex UAF https://gitee.com/openeuler/kernel/pulls/9438
                沐创：
                Fix os crash while enable sriov for rnp https://gitee.com/openeuler/kernel/pulls/9486

bugfix（4）：
                Port patches from OLK-5.10 https://gitee.com/openeuler/kernel/pulls/9295
                Some folio bugfix https://gitee.com/openeuler/kernel/pulls/9331
                Revert "ACPI: processor: Add support for processors described as container packages" https://gitee.com/openeuler/kernel/pulls/9746
                mm: drop the 'anon_' prefix for swap-out mTHP counters https://gitee.com/openeuler/kernel/pulls/9415

CVE（71）:
                CVE-2024-38601 https://gitee.com/openeuler/kernel/pulls/9302
                CVE-2024-38541 https://gitee.com/openeuler/kernel/pulls/9307
                CVE-2024-38552 https://gitee.com/openeuler/kernel/pulls/9320
                CVE-2024-38596 https://gitee.com/openeuler/kernel/pulls/9329
                CVE-2024-36974 https://gitee.com/openeuler/kernel/pulls/9332
                CVE-2024-38634 https://gitee.com/openeuler/kernel/pulls/9341
                CVE-2024-36978 https://gitee.com/openeuler/kernel/pulls/9345
                CVE-2024-38538 https://gitee.com/openeuler/kernel/pulls/9346
                ...

        最新tag 6.6.0-32.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS

议题二：kernel支持llvm pgo (姜海波&夏景泽)
https://gitee.com/openeuler/kernel/pulls/9294
会上评审意见：同意
Commiter：姜海波

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------------------------------
【2024/6/21 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->张伽琳->廖涛】
下次轮值主持：张伽琳
会议链接：https://meeting.huaweicloud.com:36443/#/j/960944013
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳&仉鹏）
20240621：
OLK-5.10进展同步
近两周(2024.6.11 ~ 6.21)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-209.0.0
        openEuler-22.03-LTS-SP4 rc4版本，tag 5.10.0-209.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-209.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.80.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        以OLK-5.10为例:
        从 5.10.0-206.0.0 更新至 5.10.0-209.0.0, 回合补丁数241个
        git log 5.10.0-206.0.0..5.10.0-209.0.0 --oneline | wc -l
        241
## 5.10.0-206.0.0..5.10.0-209.0.0

### Fix CVE (68):
        CVE-2024-26936 https://gitee.com/openeuler/kernel/pulls/9092 v2  ksmbd: validate request buffer size in smb2_allocate_rsp_buf()
        CVE-2024-36938 https://gitee.com/openeuler/kernel/pulls/9030  bpf, skmsg: Fix NULL pointer dereference in sk_psock_skb_ingress_enqueue
        CVE-2024-36968 https://gitee.com/openeuler/kernel/pulls/9099  Bluetooth: L2CAP: Fix div-by-zero in l2cap_le_flowctl_init()
        CVE-2024-35819 https://gitee.com/openeuler/kernel/pulls/9149 [sync] PR-9054:  soc: fsl: qbman: Use raw spinlock for cgr_lock
        CVE-2024-36971 https://gitee.com/openeuler/kernel/pulls/9138 v2  CVE-2024-36971
        CVE-2023-52670 https://gitee.com/openeuler/kernel/pulls/8494  rpmsg: virtio: Free driver_override when rpmsg_remove()
        CVE-2024-26960 https://gitee.com/openeuler/kernel/pulls/9131  mm: swap: fix race between free_swap_and_cache() and swapoff()
        CVE-2024-26947 https://gitee.com/openeuler/kernel/pulls/9129  ARM: 9359/1: flush: check if the folio is reserved for no-mapping addresses
        CVE-2024-35966 https://gitee.com/openeuler/kernel/pulls/9068  Bluetooth: RFCOMM: Fix not validating setsockopt user input
        CVE-2024-35937 https://gitee.com/openeuler/kernel/pulls/8700  wifi: cfg80211: check A-MSDU format more carefully
        CVE-2024-36919 https://gitee.com/openeuler/kernel/pulls/8999  scsi: bnx2fc: Remove spin_lock_bh while releasing resources after upload
        CVE-2023-52882 https://gitee.com/openeuler/kernel/pulls/8938  clk: sunxi-ng: h6: Reparent CPUX during PLL CPUX rate change
        CVE-2024-36950 https://gitee.com/openeuler/kernel/pulls/8940  firewire: ohci: mask bus reset interrupts between ISR and bottom half
        CVE-2024-35833 https://gitee.com/openeuler/kernel/pulls/8747  dmaengine: fsl-qdma: Fix a memory leak related to the queue command DMA
        CVE-2024-35915 https://gitee.com/openeuler/kernel/pulls/9074 [sync] PR-8963:  Fix CVE-2024-35915
        CVE-2024-35965 https://gitee.com/openeuler/kernel/pulls/9083  Bluetooth: L2CAP: Fix not validating setsockopt user input
        CVE-2024-36020 https://gitee.com/openeuler/kernel/pulls/9055  CVE-2024-36020
        CVE-2024-36953 https://gitee.com/openeuler/kernel/pulls/9015  CVE-2024-36953
        CVE-2024-35932 https://gitee.com/openeuler/kernel/pulls/9014  drm/vc4: don't check if plane->state->fb == state->fb
        CVE-2024-35796 https://gitee.com/openeuler/kernel/pulls/9050  CVE-2024-35796
        CVE-2024-35828 https://gitee.com/openeuler/kernel/pulls/9020  wifi: libertas: fix some memleaks in lbs_allocate_cmd_buffer()
        CVE-2024-36914 https://gitee.com/openeuler/kernel/pulls/8774  CVE-2024-36914
        CVE-2024-36016 https://gitee.com/openeuler/kernel/pulls/9027  tty: n_gsm: fix possible out-of-bounds in gsm0_receive()
        CVE-2024-35951 https://gitee.com/openeuler/kernel/pulls/8828  drm/panfrost: Fix the error path in panfrost_mmu_map_fault_addr()
        CVE-2024-35887 https://gitee.com/openeuler/kernel/pulls/8719  CVE-2024-35887
        CVE-2024-36960 https://gitee.com/openeuler/kernel/pulls/8872  drm/vmwgfx: Fix invalid reads in fence signaled events
        CVE-2024-36952 https://gitee.com/openeuler/kernel/pulls/8882  scsi: lpfc: Move NPIV's transport unregistration to after resource clean up
        CVE-2024-36905 https://gitee.com/openeuler/kernel/pulls/8982  fix CVE-2024-36905
        CVE-2024-36959 https://gitee.com/openeuler/kernel/pulls/8996  pinctrl: devicetree: fix refcount leak in pinctrl_dt_to_map()
        CVE-2024-26889 https://gitee.com/openeuler/kernel/pulls/8599  Bluetooth: hci_core: Fix possible buffer overflow
        CVE-2022-48652 https://gitee.com/openeuler/kernel/pulls/8949  CVE-2022-48652
        CVE-2024-26835 https://gitee.com/openeuler/kernel/pulls/8602  netfilter: nf_tables: set dormant flag on hook register failure
        CVE-2024-36901 https://gitee.com/openeuler/kernel/pulls/8867  ipv6: prevent NULL dereference in ip6_output()
        CVE-2024-35870 https://gitee.com/openeuler/kernel/pulls/8779  smb: client: fix UAF in smb2_reconnect_server()
        CVE-2024-36898 https://gitee.com/openeuler/kernel/pulls/8893 [sync] PR-8531:  gpiolib: cdev: fix uninitialised kfifo
        CVE-2024-35853 https://gitee.com/openeuler/kernel/pulls/8686  mlxsw: spectrum_acl_tcam: Fix memory leak during rehash
        CVE-2024-35821 https://gitee.com/openeuler/kernel/pulls/8711  ubifs: Set page uptodate in the correct place
        CVE-2024-36908 https://gitee.com/openeuler/kernel/pulls/8860  blk-iocost: do not WARN if iocg was already offlined
        CVE-2024-36928 https://gitee.com/openeuler/kernel/pulls/8639  s390/qeth: Fix kernel panic after setting hsuid
        CVE-2024-35924 https://gitee.com/openeuler/kernel/pulls/8946  usb: typec: ucsi: Limit read size on v1.2
        CVE-2024-36949 https://gitee.com/openeuler/kernel/pulls/8969  Fix CVE-2024-36949
        CVE-2023-52693 https://gitee.com/openeuler/kernel/pulls/8216  ACPI: video: check for error while searching for backlight device parent
        CVE-2023-52680 https://gitee.com/openeuler/kernel/pulls/8903  ALSA: scarlett2: Add missing error checks to *_ctl_get()
        CVE-2023-52762 https://gitee.com/openeuler/kernel/pulls/8584  virtio-blk: fix implicit overflow on virtio_max_dma_size
        CVE-2024-36916 https://gitee.com/openeuler/kernel/pulls/8838  blk-iocost: avoid out of bounds shift
        CVE-2024-35809 https://gitee.com/openeuler/kernel/pulls/8856  PCI/PM: Drain runtime-idle callbacks before driver removal
        CVE-2021-47247 https://gitee.com/openeuler/kernel/pulls/8906  net/mlx5e: Fix use-after-free of encap entry in neigh update handler
        CVE-2024-36899 https://gitee.com/openeuler/kernel/pulls/8910  gpiolib: cdev: Fix use after free in lineinfo_changed_notify
        CVE-2024-36929 https://gitee.com/openeuler/kernel/pulls/8879  net: core: reject skb_copy(_expand) for fraglist GSO skbs
        CVE-2024-26924 https://gitee.com/openeuler/kernel/pulls/6695  netfilter: nft_set_pipapo: do not free live element
        CVE-2024-36883 https://gitee.com/openeuler/kernel/pulls/8891  net: fix out-of-bounds access in ops_init
        CVE-2024-36886 https://gitee.com/openeuler/kernel/pulls/8762  tipc: fix UAF in error path
        CVE-2024-36957 https://gitee.com/openeuler/kernel/pulls/8742  octeontx2-af: avoid off-by-one read from userspace
        CVE-2024-36889 https://gitee.com/openeuler/kernel/pulls/8734  mptcp: ensure snd_nxt is properly initialized on connect
        CVE-2024-35982 https://gitee.com/openeuler/kernel/pulls/8634  batman-adv: Avoid infinite loop trying to resize local TT
        CVE-2024-36900 https://gitee.com/openeuler/kernel/pulls/8736  net: hns3: fix kernel crash when devlink reload during initialization
        CVE-2021-47366 https://gitee.com/openeuler/kernel/pulls/8745  afs: Fix corruption in reads at fpos 2G-4G from an OpenAFS server
        CVE-2024-36933 https://gitee.com/openeuler/kernel/pulls/8887  nsh: Restore skb->{protocol,data,mac_header} for outer header in nsh_gso_segment().
        CVE-2023-52880 https://gitee.com/openeuler/kernel/pulls/8785  tty: n_gsm: require CAP_NET_ADMIN to attach N_GSM0710 ldisc
        CVE-2024-36902 https://gitee.com/openeuler/kernel/pulls/8849  ipv6: fib6_rules: avoid possible NULL dereference in fib6_rule_action()
        CVE-2024-27402 https://gitee.com/openeuler/kernel/pulls/8666  phonet/pep: fix racy skb_queue_empty() use
        CVE-2024-35910 https://gitee.com/openeuler/kernel/pulls/8684  tcp: properly terminate timers for kernel sockets
        CVE-2024-35888 https://gitee.com/openeuler/kernel/pulls/8629  erspan: make sure erspan_base_hdr is present in skb->head
        CVE-2024-36903 https://gitee.com/openeuler/kernel/pulls/8635  ipv6: Fix potential uninit-value access in __ip6_make_skb()
        CVE-2024-36954 https://gitee.com/openeuler/kernel/pulls/8550  tipc: fix a possible memleak in tipc_buf_append
        CVE-2024-36904 https://gitee.com/openeuler/kernel/pulls/8726  tcp: Use refcount_inc_not_zero() in tcp_twsk_unique().
        CVE-2024-36964 https://gitee.com/openeuler/kernel/pulls/8623  fs/9p: only translate RWX permissions for plain 9P2000
        CVE-2024-36924 https://gitee.com/openeuler/kernel/pulls/8479  scsi: lpfc: Release hbalock before calling lpfc_worker_wake_up()

### Processors Support:
#### Kunpeng:
        https://gitee.com/openeuler/kernel/pulls/9112  Backport some optimizing patches for kunpeng920
        https://gitee.com/openeuler/kernel/pulls/9064 drivers/perf: hisi_pcie: Fix out-of-bound access when valid event group
        https://gitee.com/openeuler/kernel/pulls/9059 roh/hns3: Add ROH client case in hclgevf_init_client_instance.
        https://gitee.com/openeuler/kernel/pulls/8908  Refactor hbmdev a bit
        https://gitee.com/openeuler/kernel/pulls/9001 roh/hns3: Fix IMP reset vlan unusable.

### Devices Support:
#### sdma-dae
        https://gitee.com/openeuler/kernel/pulls/8871 add sdma-dae for openeuler 22.03 SP4

### Features:
#### xfs文件系统支持atomic write
        https://gitee.com/openeuler/kernel/pulls/9084 v5  xfs: atomic writes for xfs

#### 打开CONFIG_BLK_CGROUP_IOCOST 选项，支持iocost隔离
        https://gitee.com/openeuler/kernel/pulls/9067  config: enable CONFIG_BLK_CGROUP_IOCOST by default

#### openeuler支持io切换到指定cpu异步下发
        https://gitee.com/openeuler/kernel/pulls/9063 v3  block: support to dispatch bio asynchronously

#### virtCCA机密虚机安全加固
        https://gitee.com/openeuler/kernel/pulls/8965  cvm: enhance security for cvm host feature

#### 支持PCC opeartion region
        https://gitee.com/openeuler/kernel/pulls/8808 v2  Add support for PCC Operation Region
        
### performance
        https://gitee.com/openeuler/kernel/pulls/3547  fs: mitigatin cacheline false sharing in struct file

### bugfix
        https://gitee.com/openeuler/kernel/pulls/9166  A Solution to Re-enable hugetlb vmemmap optimize on ARM64
        https://gitee.com/openeuler/kernel/pulls/9163  genirq: introduce handle_fasteoi_edge_irq flow handler
        https://gitee.com/openeuler/kernel/pulls/8753  memcg: fix input of try_to_free_mem_cgroup_pages
        https://gitee.com/openeuler/kernel/pulls/9125  arm64: armv8_deprecated: Fix warning in isndep cpuhp starting process
        https://gitee.com/openeuler/kernel/pulls/9073 v2  Fix UAF problem of hpool
        https://gitee.com/openeuler/kernel/pulls/9081 v2  arm64: mm: Replace global variable in pbha with static key
        https://gitee.com/openeuler/kernel/pulls/9066 change sdma-dae default mode to n
        https://gitee.com/openeuler/kernel/pulls/8827 v2  iomap: fix sub-page not set dirty state
        https://gitee.com/openeuler/kernel/pulls/7205  mm: memcontrol: do not miss MEMCG_MAX events for enforced allocations
        https://gitee.com/openeuler/kernel/pulls/8921  hugetlbfs: fix hugetlbfs_statfs() locking
        https://gitee.com/openeuler/kernel/pulls/8985  cvm_tsi: Fix security issue for Confidential cVM TSI

OLK-6.6进展同步：

新分支已合入PR 17个，commit 507个
近两周(6.8-6.21)新合入特性PR：

特性（6）：
                MPTCP Upstream part 1~5
                https://gitee.com/openeuler/kernel/pulls/8809
                https://gitee.com/openeuler/kernel/pulls/9173
                https://gitee.com/openeuler/kernel/pulls/9226
                https://gitee.com/openeuler/kernel/pulls/9230
                https://gitee.com/openeuler/kernel/pulls/9245
                memcg: attach memcg async reclaim worker to curcpu https://gitee.com/openeuler/kernel/pulls/9217
LTS（1）:
                Backport 6.6.31&6.6.32 LTS patches from upstream https://gitee.com/openeuler/kernel/pulls/9010

处理器及板卡支持专项（4）：
                intel：
                Intel: Backport QuickAssist Technology(QAT) live migration support for in-tree driver https://gitee.com/openeuler/kernel/pulls/8058
                Backport TPMI based RAPL PMU support for next Intel Xeon Granite Rapids (GNR) https://gitee.com/openeuler/kernel/pulls/8304
                Intel IAA Compression Accelerator Crypto Driver (iaa_crypto)  https://gitee.com/openeuler/kernel/pulls/8422
                海光：
                [OLK-6.6] Support DOWNLOAD_FIRMWARE feature for hygon CSV https://gitee.com/openeuler/kernel/pulls/5257

bugfix（6）：
                openeuler_defconfig: fix checkdefconfig fail https://gitee.com/openeuler/kernel/pulls/9085
                ext4: Skip moving extents if page writeback failed https://gitee.com/openeuler/kernel/pulls/9101
                [OLK-6.6] drm/phytium: Fix make allmodconfig build fail https://gitee.com/openeuler/kernel/pulls/9104
                arm64: armv8_deprecated: Fix warning in isndep cpuhp starting process https://gitee.com/openeuler/kernel/pulls/9126
                Fix allmodconfig build frame size error https://gitee.com/openeuler/kernel/pulls/9141
                sched: smart_grid: fix potential NULL pointer dereference https://gitee.com/openeuler/kernel/pulls/9229

        kabi检查使能
        最新tag 6.6.0-30.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS

议题二：申请Kernel组下添加ubifs  fsck工具的仓库（程志浩）
上游社区仓库地址： https://git.infradead.org/mtd-utils.git
仓库名称：mtd-utils
mtd-utils为flash驱动和flash文件系统（主要是RTOS场景）提供用户态工具，fsck是flash文件系统的fsck，类比fsck.ext4

会上评审意见：建议先评估社区中是否有更合适的SIG建仓
https://gitee.com/src-openeuler/mtd-utils/pulls/22

三、本期遗留问题
ubifs  fsck工具相关代码合入仓库待确定

--------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------------------------------
【2024/6/7 Kernel SIG 双周例会】
轮值主持：廖涛（代仉鹏） 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->张伽琳->廖涛】
下次轮值主持：桑力鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/962955607
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&仉鹏）

OLK-6.6进展同步：

新分支已合入PR 25个，commit 185个
近两周(5.25-6.7)新合入PR：

处理器及板卡支持专项：
        华为（4）：
        net: hns3: fix kernel crash when devlink reload during pf/vf initialization https://gitee.com/openeuler/kernel/pulls/8107
        Fix vf init and common user permissions issue https://gitee.com/openeuler/kernel/pulls/8481
        backport PCC patches to support shared interrupt for multiple subspaces and platform notification handling https://gitee.com/openeuler/kernel/pulls/8576
        v2 perf parse-events: Make legacy events lower priority than sysfs/JSON https://gitee.com/openeuler/kernel/pulls/7482
        龙芯（4）：
        LoongArch: Fix secondary bridge routing errors https://gitee.com/openeuler/kernel/pulls/8151
        LoongArch: add GMAC&GNET support https://gitee.com/openeuler/kernel/pulls/8435
        LoongArch: fix HT RX INT TRANS register not initialized https://gitee.com/openeuler/kernel/pulls/8621
        backport upstream stmmac related patches. https://gitee.com/openeuler/kernel/pulls/7896
        北中网芯（1）：
        Fix BUILD REGRESSION warnings in bzwx N5/N6 series NIC drivers https://gitee.com/openeuler/kernel/pulls/7948

特性（1）：
        v2 IMA: Introduce a config to bypass i_version detection for Overlayfs issue https://gitee.com/openeuler/kernel/pulls/8703

bugfix（13）：
        mm: some misc bugfix https://gitee.com/openeuler/kernel/pulls/7997
        mm/mempolicy.c: fix the out-of-bounds access issue in mpol_parse_str https://gitee.com/openeuler/kernel/pulls/8010
        fix deadlock in cgroup1_writeback V2 https://gitee.com/openeuler/kernel/pulls/6283
        ubifs: ubifs_link: Fix wrong name len calculating when UBIFS is encrypted https://gitee.com/openeuler/kernel/pulls/8228
        perf pmu: Count sys and cpuid JSON events separately https://gitee.com/openeuler/kernel/pulls/8183
        xfs: Fix file creation failure https://gitee.com/openeuler/kernel/pulls/8309
        mm/dynamic_pool: clear PG_hugetlb when promote hugepages https://gitee.com/openeuler/kernel/pulls/8353
        arm64: cpufeature: Both the major and the minor version numbers need to be checked https://gitee.com/openeuler/kernel/pulls/8440
        sched/core: Fix incorrect initialization of the 'burst' parameter in cpu_max_write() https://gitee.com/openeuler/kernel/pulls/8450
        ext4: Fixes len calculation in mpage_journal_page_buffers https://gitee.com/openeuler/kernel/pulls/8471
        mm/mlock: return EINVAL for illegal user memory range in mlock https://gitee.com/openeuler/kernel/pulls/8496
        ubifs: Check @c->dirty_[n|p https://gitee.com/openeuler/kernel/pulls/8750
        v4 block: dicard bugfix https://gitee.com/openeuler/kernel/pulls/7077

CVE（1）:
        CVE-2024-27010 https://gitee.com/openeuler/kernel/pulls/8036

config兼容性（1）：
        openeuler_defconfig: Modify openeuler-defconfig https://gitee.com/openeuler/kernel/pulls/7966

继承特性回合事项： closed

        最新tag 6.6.0-29.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS

openEuler-1.0-LTS进展同步：
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2405.5.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                        对应update rpm包下载地址:
                        https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-1.0-LTS从 4.19.90-2405.1.0 更新至 4.19.90-2405.5.0, 回合补丁数142个
        git log --no-merges 4.19.90-2405.1.0..4.19.90-2405.5.0 --oneline | wc -l
        142

        修复CVE 108个
        CVE-2023-52818  https://gitee.com/openeuler/kernel/pulls/8066  drm/amd: Fix UBSAN array-index-out-of-bounds for SMU7
        CVE-2023-52817  https://gitee.com/openeuler/kernel/pulls/8038  CVE-2023-52817
        CVE-2021-47269  https://gitee.com/openeuler/kernel/pulls/8106  usb: dwc3: ep0: fix NULL pointer exception
        CVE-2024-35806  https://gitee.com/openeuler/kernel/pulls/8059  soc: fsl: qbman: Always disable interrupts when taking cgr_lock
        CVE-2023-52835  https://gitee.com/openeuler/kernel/pulls/8017  perf/core: Bail out early if the request AUX area is out of bound
        CVE-2021-47284  https://gitee.com/openeuler/kernel/pulls/8064  isdn: mISDN: netjet: Fix crash in nj_probe:
        CVE-2024-35976  https://gitee.com/openeuler/kernel/pulls/8049  xsk: validate user input for XDP_{UMEM|COMPLETION}_FILL_RING
        CVE-2024-35950  https://gitee.com/openeuler/kernel/pulls/8055  drm/client: Fully protect modes[
        CVE-2021-47496  https://gitee.com/openeuler/kernel/pulls/8000  v2  net/tls: Fix flipped sign in tls_err_abort() calls
        CVE-2024-35898  https://gitee.com/openeuler/kernel/pulls/8032  netfilter: nf_tables: Fix potential data-race in __nft_flowtable_type_get()
        CVE-2021-47473  https://gitee.com/openeuler/kernel/pulls/8056  scsi: qla2xxx: Fix a memory leak in an error path of qla2x00_process_els()
        CVE-2024-35997  https://gitee.com/openeuler/kernel/pulls/7999  HID: i2c-hid: remove I2C_HID_READ_PENDING flag to prevent lock-up
        CVE-2024-27403  https://gitee.com/openeuler/kernel/pulls/7817  netfilter: nft_flow_offload: reset dst in route object after setting up flow
        CVE-2021-47497  https://gitee.com/openeuler/kernel/pulls/7965  nvmem: Fix shift-out-of-bound (UBSAN) with byte size cells
        CVE-2021-47455  https://gitee.com/openeuler/kernel/pulls/7981  Fix CVE-2021-47455
        CVE-2021-47335  https://gitee.com/openeuler/kernel/pulls/7901  f2fs: fix to avoid racing on fsync_entry_slab by multi filesystem instances
        CVE-2024-35930  https://gitee.com/openeuler/kernel/pulls/7700  scsi: lpfc: Fix possible memory leak in lpfc_rcv_padisc()
        CVE-2024-35805  https://gitee.com/openeuler/kernel/pulls/7682  dm snapshot: fix lockup in dm_exception_table_exit
        CVE-2023-52847  https://gitee.com/openeuler/kernel/pulls/7867  media: bttv: fix use after free error due to btv->timeout timer
        CVE-2024-35922  https://gitee.com/openeuler/kernel/pulls/7971  fbmon: prevent division by zero in fb_videomode_from_videomode()
        CVE-2024-35886  https://gitee.com/openeuler/kernel/pulls/7963  ipv6: Fix infinite recursion in fib6_dump_done().
        CVE-2022-48710  https://gitee.com/openeuler/kernel/pulls/7979  drm/radeon: fix a possible null pointer dereference
        CVE-2024-27426  https://gitee.com/openeuler/kernel/pulls/7944  v2  netrom: Fix a data-race around sysctl_netrom_transport_maximum_tries
        CVE-2023-52840  https://gitee.com/openeuler/kernel/pulls/7811  Input: synaptics-rmi4 - fix use after free in rmi_unregister_function()
        CVE-2023-52868  https://gitee.com/openeuler/kernel/pulls/7892  CVE-2023-52868
        CVE-2021-47393  https://gitee.com/openeuler/kernel/pulls/7910  hwmon: (mlxreg-fan) Return non-zero value when fan current state is enforced from sysfs
        CVE-2024-27428  https://gitee.com/openeuler/kernel/pulls/7851  netrom: Fix data-races around sysctl_netrom_network_ttl_initialiser
        CVE-2024-35835  https://gitee.com/openeuler/kernel/pulls/7854  net/mlx5e: fix a double-free in arfs_create_groups
        CVE-2023-52656  https://gitee.com/openeuler/kernel/pulls/7794  v2  Fix CVE-2023-52656
        CVE-2024-27427  https://gitee.com/openeuler/kernel/pulls/7840  netrom: Fix a data-race around sysctl_netrom_transport_timeout
        CVE-2023-52691  https://gitee.com/openeuler/kernel/pulls/7770  drm/amd/pm: fix a double-free in si_dpm_init
        CVE-2024-35847  https://gitee.com/openeuler/kernel/pulls/7589  irqchip/gic-v3-its: Prevent double free on error
        CVE-2024-35936  https://gitee.com/openeuler/kernel/pulls/7713  CVE-2024-35936
        CVE-2023-52698  https://gitee.com/openeuler/kernel/pulls/7751  Fix CVE-2023-52698
        CVE-2024-27419  https://gitee.com/openeuler/kernel/pulls/7742  netrom: Fix data-races around sysctl_net_busy_read
        CVE-2023-52867  https://gitee.com/openeuler/kernel/pulls/7748  drm/radeon: possible buffer overflow
        CVE-2024-35935  https://gitee.com/openeuler/kernel/pulls/7669  btrfs: send: handle path ref underflow in header iterate_inode_ref()
        CVE-2024-26886  https://gitee.com/openeuler/kernel/pulls/7694  Bluetooth: af_bluetooth: Fix deadlock
        CVE-2024-35807  https://gitee.com/openeuler/kernel/pulls/7701  ext4: fix corruption during on-line resize
        CVE-2023-52685  https://gitee.com/openeuler/kernel/pulls/7573  pstore: ram_core: fix possible overflow in persistent_ram_init_ecc()
        CVE-2024-35849  https://gitee.com/openeuler/kernel/pulls/7547  btrfs: fix information leak in btrfs_ioctl_logical_to_ino()
        CVE-2023-52675  https://gitee.com/openeuler/kernel/pulls/7586  powerpc/imc-pmu: Add a null pointer check in update_events_in_group()
        CVE-2024-27401  https://gitee.com/openeuler/kernel/pulls/7477  firewire: nosy: ensure user_length is taken into account when fetching packet contents
        CVE-2024-27398  https://gitee.com/openeuler/kernel/pulls/7483  Bluetooth: Fix use-after-free bugs caused by sco_sock_timeout
        CVE-2024-27396  https://gitee.com/openeuler/kernel/pulls/7425  net: gtp: Fix Use-After-Free in gtp_dellink
        CVE-2024-27395  https://gitee.com/openeuler/kernel/pulls/7434  net: openvswitch: Fix Use-After-Free in ovs_ct_exit
        CVE-2024-26957  https://gitee.com/openeuler/kernel/pulls/7228  s390/zcrypt: fix reference counting on zcrypt card objects
        CVE-2024-26921  https://gitee.com/openeuler/kernel/pulls/7193  CVE-2024-26921
        CVE-2024-26865  https://gitee.com/openeuler/kernel/pulls/7096  fix CVE-2024-26865
        CVE-2024-27054  https://gitee.com/openeuler/kernel/pulls/7194  s390/dasd: fix double module refcount decrement
        CVE-2024-26955  https://gitee.com/openeuler/kernel/pulls/7059  nilfs2: prevent kernel bug at submit_bh_wbc()
        CVE-2024-26996  https://gitee.com/openeuler/kernel/pulls/7163  v2  usb: gadget: f_ncm: Fix UAF ncm object at re-bind after usb ep transport error
        CVE-2024-26976  https://gitee.com/openeuler/kernel/pulls/7104  KVM: Always flush async #PF workqueue when vCPU is being destroyed
        CVE-2023-52652  https://gitee.com/openeuler/kernel/pulls/7203  NTB: fix possible name leak in ntb_register_device()
        CVE-2024-26982  https://gitee.com/openeuler/kernel/pulls/7158  v2  Squashfs: check the inode number is not the invalid value of zero
        CVE-2024-26958  https://gitee.com/openeuler/kernel/pulls/7181  nfs: fix UAF in direct writes
        CVE-2024-27062  https://gitee.com/openeuler/kernel/pulls/7091  nouveau: lock the client object tree.
        CVE-2024-27037  https://gitee.com/openeuler/kernel/pulls/7120  v2  clk: zynq: Prevent null pointer dereference caused by kmalloc failure
        CVE-2024-26956  https://gitee.com/openeuler/kernel/pulls/7089  nilfs2: fix failure to detect DAT corruption in btree and direct mappings
        CVE-2021-47182  https://gitee.com/openeuler/kernel/pulls/7151  v2  scsi: sd: Fix sd_do_mode_sense() buffer length handling
        CVE-2024-26920  https://gitee.com/openeuler/kernel/pulls/7033  Revert "tracing/trigger: Fix to return error if failed to alloc snapshot"
        CVE-2022-48697  https://gitee.com/openeuler/kernel/pulls/7079  nvmet: fix a use-after-free
        CVE-2024-27072  https://gitee.com/openeuler/kernel/pulls/7140  media: usbtv: Remove useless locks in usbtv_video_free()
        CVE-2023-52653  https://gitee.com/openeuler/kernel/pulls/7137  v2  SUNRPC: fix a memleak in gss_import_v2_context
        CVE-2024-27388  https://gitee.com/openeuler/kernel/pulls/7138  SUNRPC: fix some memleaks in gssx_dec_option_array
        CVE-2024-27019  https://gitee.com/openeuler/kernel/pulls/7100  netfilter: nf_tables: Fix potential data-race in __nft_obj_type_get()
        CVE-2024-27020  https://gitee.com/openeuler/kernel/pulls/7095  CVE-2024-27020
        CVE-2024-27001  https://gitee.com/openeuler/kernel/pulls/7034  fix CVE-2024-27001 for 4.19
        CVE-2024-26966  https://gitee.com/openeuler/kernel/pulls/7032  clk: qcom: mmcc-apq8084: fix terminating of frequency table arrays
        CVE-2022-48704  https://gitee.com/openeuler/kernel/pulls/7115  drm/radeon: add a force flush to delay work when radeon
        CVE-2024-26931  https://gitee.com/openeuler/kernel/pulls/7055  scsi: qla2xxx: Fix command flush on cable pull
        CVE-2024-26960  https://gitee.com/openeuler/kernel/pulls/7109  fix CVE-2024-26960
        CVE-2024-27059  https://gitee.com/openeuler/kernel/pulls/7046  USB: usb-storage: Prevent divide-by-0 error in isd200_ata_command
        CVE-2024-27024  https://gitee.com/openeuler/kernel/pulls/7053  CVE-2024-27024
        CVE-2022-48701  https://gitee.com/openeuler/kernel/pulls/6970  ALSA: usb-audio: Fix an out-of-bounds bug in __snd_usb_parse_audio_interface()
        CVE-2024-27014  https://gitee.com/openeuler/kernel/pulls/6995  v2  net/mlx5e: Prevent deadlock while disabling aRFS
        CVE-2021-47184  https://gitee.com/openeuler/kernel/pulls/7038  i40e: Fix NULL ptr dereference on VSI filter sync
        CVE-2024-27078  https://gitee.com/openeuler/kernel/pulls/7037  media: v4l2-tpg: fix some memleaks in tpg_alloc
        CVE-2024-27043  https://gitee.com/openeuler/kernel/pulls/6992  media: edia: dvbdev: fix a use-after-free
        CVE-2023-52644  https://gitee.com/openeuler/kernel/pulls/7045  v2  b43: fix CVE-2023-52644
        CVE-2024-26897  https://gitee.com/openeuler/kernel/pulls/7017  v2  net: ath9k: fix CVE-2024-26897
        CVE-2022-48693  https://gitee.com/openeuler/kernel/pulls/7016  v3  Fix CVE-2022-48693
        CVE-2024-26969  https://gitee.com/openeuler/kernel/pulls/7012  clk: qcom: gcc-ipq8074: fix terminating of frequency table arrays
        CVE-2024-26961  https://gitee.com/openeuler/kernel/pulls/6991  mac802154: fix llsec key resources release in mac802154_llsec_key_del
        CVE-2024-27073  https://gitee.com/openeuler/kernel/pulls/7005  media: ttpci: fix two memleaks in budget_av_attach
        CVE-2024-26981  https://gitee.com/openeuler/kernel/pulls/7014  nilfs2: fix OOB in nilfs_set_de_type
        CVE-2024-27010  https://gitee.com/openeuler/kernel/pulls/7001  fix CVE-2024-27010
        CVE-2024-27074  https://gitee.com/openeuler/kernel/pulls/6880  media: go7007: fix a memleak in go7007_load_encoder
        CVE-2024-26965  https://gitee.com/openeuler/kernel/pulls/6984  clk: qcom: mmcc-msm8974: fix terminating of frequency table arrays
        CVE-2024-27051  https://gitee.com/openeuler/kernel/pulls/6893  cpufreq: brcmstb-avs-cpufreq: add check for cpufreq_cpu_get's return value
        CVE-2024-27011  https://gitee.com/openeuler/kernel/pulls/6958  netfilter: nf_tables: fix memleak in map from abort path
        CVE-2022-48636  https://gitee.com/openeuler/kernel/pulls/6820  s390/dasd: fix Oops in dasd_alias_get_start_dev due to missing pavgroup
        CVE-2024-27008  https://gitee.com/openeuler/kernel/pulls/6940  drm: nv04: Fix out of bounds access
        CVE-2024-26974  https://gitee.com/openeuler/kernel/pulls/6968  CVE-2024-26974
        CVE-2024-27046  https://gitee.com/openeuler/kernel/pulls/6976  nfp: flower: handle acti_netdevs allocation failure
        CVE-2024-26934  https://gitee.com/openeuler/kernel/pulls/6944  USB: core: Fix deadlock in usb_deauthorize_interface()
        CVE-2022-48695  https://gitee.com/openeuler/kernel/pulls/6870  scsi: mpt3sas: Fix use-after-free warning
        CVE-2024-26994  https://gitee.com/openeuler/kernel/pulls/6966  speakup: Avoid crash on very long word
        CVE-2024-27000  https://gitee.com/openeuler/kernel/pulls/6963  v2  CVE-2024-27000
        CVE-2024-27028  https://gitee.com/openeuler/kernel/pulls/6951  v2  spi: spi-mt65xx: Fix NULL pointer access in interrupt handler
        CVE-2024-26846  https://gitee.com/openeuler/kernel/pulls/6881  v4  CVE-2024-26846
        CVE-2024-27013  https://gitee.com/openeuler/kernel/pulls/6894  tun: limit printing rate when illegal packet received by tun dev
        CVE-2024-24858  https://gitee.com/openeuler/kernel/pulls/6883  Bluetooth: Fix TOCTOU in HCI debugfs implementation
        CVE-2024-27075  https://gitee.com/openeuler/kernel/pulls/6856  media: dvb-frontends: avoid stack overflow warnings with clang
        CVE-2023-52650  https://gitee.com/openeuler/kernel/pulls/6839  CVE-2023-52650
        CVE-2024-27077  https://gitee.com/openeuler/kernel/pulls/6869  v2  media: v4l2-mem2mem: fix a memleak in v4l2_m2m_register_entity
        CVE-2024-26984  https://gitee.com/openeuler/kernel/pulls/6867  v2  nouveau: fix instmem race condition around ptr stores
        CVE-2024-26999  https://gitee.com/openeuler/kernel/pulls/6852  serial/pmac_zilog: Remove flawed mitigation for rx irq flood

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/7951  sched/rt: Fix rt_runtime leaks with cpu hotplug and RT_RUNTIME_SHARE
        https://gitee.com/openeuler/kernel/pulls/7421  x86/CPU/AMD: Update the Zenbleed microcode revisions
        https://gitee.com/openeuler/kernel/pulls/7415  cpu/SMT: Make SMT control more robust against enumeration failures
        https://gitee.com/openeuler/kernel/pulls/7451  v2  ip: Treat IPv4 segment's lowest address as unicast
        https://gitee.com/openeuler/kernel/pulls/7393  v2  scsi: sr: Do not leak information in ioctl
        https://gitee.com/openeuler/kernel/pulls/7676  sched/all: Change all BUG_ON() instances in the scheduler to WARN_ON_ONCE()
        https://gitee.com/openeuler/kernel/pulls/7114  v2  backport patch for thp deferred list for 4.19
        https://gitee.com/openeuler/kernel/pulls/6260  packet: move from strlcpy with unused retval to strscpy
        https://gitee.com/openeuler/kernel/pulls/6942  v2  ima: fix deadlock when traversing "ima_default_rules".


议题二：征集中，可在此直接申报

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------------------------------
【2024/5/24 Kernel SIG 双周例会】
轮值主持：曾昭荣 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->张伽琳->廖涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/969333120
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&仉鹏）
近三周(2024.5.13 ~ 5.24)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-200.0.0
        openEuler-22.03-LTS-SP4 alpha版本，tag 5.10.0-200.0.0，预计本周发布
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-200.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.55.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.76.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.138.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-198.0.0 更新至 5.10.0-200.0.0, 回合补丁数364个
        git log 5.10.0-198.0.0..5.10.0-200.0.0 --oneline | wc -l
        364

## 5.10.0-198.0.0..5.10.0-200.0.0

### Backport patches from upstream LTS (5.10.206):
        https://gitee.com/openeuler/kernel/pulls/7128 Backport 5.10.206 LTS patches from upstream

### Fix CVE (81):
        CVE-2023-52615: https://gitee.com/openeuler/kernel/pulls/7644  hwrng: core - Fix page fault dead lock on mmap-ed hwrng
        CVE-2024-35943: https://gitee.com/openeuler/kernel/pulls/7705  pmdomain: ti: Add a null pointer check to the omap_prm_domain_init
        CVE-2024-35845: https://gitee.com/openeuler/kernel/pulls/7749 v2  wifi: iwlwifi: dbg-tlv: ensure NUL termination
        CVE-2024-35791: https://gitee.com/openeuler/kernel/pulls/7655 v3  KVM: SVM: Flush pages under kvm->lock to fix UAF in svm_register_enc_region()
        CVE-2023-52676: https://gitee.com/openeuler/kernel/pulls/7675  bpf: Guard stack limits against 32bit overflow
        CVE-2024-35807: https://gitee.com/openeuler/kernel/pulls/7686  ext4: fix corruption during on-line resize
        CVE-2024-35847: https://gitee.com/openeuler/kernel/pulls/7599  irqchip/gic-v3-its: Prevent double free on error
        CVE-2024-35934: https://gitee.com/openeuler/kernel/pulls/7674  net/smc: reduce rtnl pressure in smc_pnet_create_pnetids_list()
        CVE-2023-52690: https://gitee.com/openeuler/kernel/pulls/7579  powerpc/powernv: Add a null pointer check to scom_debug_init_one()
        CVE-2023-52675: https://gitee.com/openeuler/kernel/pulls/7665 [sync] PR-7586:  powerpc/imc-pmu: Add a null pointer check in update_events_in_group()
        CVE-2023-52694: https://gitee.com/openeuler/kernel/pulls/7661 [sync] PR-7590:  drm/bridge: tpd12s015: Drop buggy __exit annotation for remove function
        CVE-2023-52685: https://gitee.com/openeuler/kernel/pulls/7574  pstore: ram_core: fix possible overflow in persistent_ram_init_ecc()
        CVE-2024-27431: https://gitee.com/openeuler/kernel/pulls/7601  cpumap: Zero-initialise xdp_rxq_info struct before running XDP program
        CVE-2024-27002: https://gitee.com/openeuler/kernel/pulls/7385  CVE-2024-27002
        CVE-2024-35849: https://gitee.com/openeuler/kernel/pulls/7548  btrfs: fix information leak in btrfs_ioctl_logical_to_ino()
        CVE-2024-26937: https://gitee.com/openeuler/kernel/pulls/7520  drm/i915/gt: Reset queue_priority_hint on parking
        CVE-2024-27398: https://gitee.com/openeuler/kernel/pulls/7515 [sync] PR-7483:  Bluetooth: Fix use-after-free bugs caused by sco_sock_timeout
        CVE-2023-52630: https://gitee.com/openeuler/kernel/pulls/7356  blk-iocost: Fix an UBSAN shift-out-of-bounds warning
        CVE-2023-52635: https://gitee.com/openeuler/kernel/pulls/7351  PM / devfreq: Synchronize devfreq_monitor_[start/stop
        CVE-2023-52629: https://gitee.com/openeuler/kernel/pulls/7361  sh: push-switch: Reorder cleanup operations to avoid use-after-free bug
        CVE-2024-26661: https://gitee.com/openeuler/kernel/pulls/7484  fix CVE-2024-26661
        CVE-2024-27401: https://gitee.com/openeuler/kernel/pulls/7476  firewire: nosy: ensure user_length is taken into account when fetching packet contents
        CVE-2024-26851: https://gitee.com/openeuler/kernel/pulls/7456  netfilter: nf_conntrack_h323: Add protection for bmp length out of range
        CVE-2024-24860: https://gitee.com/openeuler/kernel/pulls/6524  Bluetooth: Fix atomicity violation in {min,max}_key_size_set
        CVE-2024-27395: https://gitee.com/openeuler/kernel/pulls/7424  net: openvswitch: Fix Use-After-Free in ovs_ct_exit
        CVE-2024-26675: https://gitee.com/openeuler/kernel/pulls/7346  ppp_async: limit MRU to 64K
        CVE-2023-52633: https://gitee.com/openeuler/kernel/pulls/5793  um: time-travel: fix time corruption
        CVE-2024-26686: https://gitee.com/openeuler/kernel/pulls/7315  CVE-2024-26686
        CVE-2024-26712: https://gitee.com/openeuler/kernel/pulls/7297  powerpc/kasan: Fix addr error caused by page alignment
        CVE-2024-26957: https://gitee.com/openeuler/kernel/pulls/7229  s390/zcrypt: fix reference counting on zcrypt card objects
        CVE-2023-52623: https://gitee.com/openeuler/kernel/pulls/7234  SUNRPC: Fix a suspicious RCU usage warning
        CVE-2023-52621: https://gitee.com/openeuler/kernel/pulls/7235  bpf: Check rcu_read_lock_trace_held() before calling bpf map helpers
        CVE-2024-26702: https://gitee.com/openeuler/kernel/pulls/7308  iio: magnetometer: rm3100: add boundary check for the value read from RM3100_REG_TMRC
        CVE-2024-27396: https://gitee.com/openeuler/kernel/pulls/7426  net: gtp: Fix Use-After-Free in gtp_dellink
        CVE-2024-26970: https://gitee.com/openeuler/kernel/pulls/7414  clk: qcom: gcc-ipq6018: fix terminating of frequency table arrays
        CVE-2024-27017: https://gitee.com/openeuler/kernel/pulls/7218  CVE-2024-27017
        CVE-2024-26610: https://gitee.com/openeuler/kernel/pulls/5469  wifi: iwlwifi: fix a memory corruption
        CVE-2024-26865: https://gitee.com/openeuler/kernel/pulls/7018  fix CVE-2024-26865
        CVE-2024-26955: https://gitee.com/openeuler/kernel/pulls/7048  nilfs2: prevent kernel bug at submit_bh_wbc()
        CVE-2022-48689: https://gitee.com/openeuler/kernel/pulls/7174  CVE-2022-48689
        CVE-2023-52652: https://gitee.com/openeuler/kernel/pulls/7189  NTB: fix possible name leak in ntb_register_device()
        CVE-2024-26972: https://gitee.com/openeuler/kernel/pulls/7177  ubifs: ubifs_symlink: Fix memleak of inode->i_link in error path
        CVE-2024-27037: https://gitee.com/openeuler/kernel/pulls/7122 v2  clk: zynq: Prevent null pointer dereference caused by kmalloc failure
        CVE-2024-26920: https://gitee.com/openeuler/kernel/pulls/7031  Revert "tracing/trigger: Fix to return error if failed to alloc snapshot"
        CVE-2024-26811: https://gitee.com/openeuler/kernel/pulls/6972  ksmbd: validate payload size in ipc response
        CVE-2024-27072: https://gitee.com/openeuler/kernel/pulls/7143  media: usbtv: Remove useless locks in usbtv_video_free()
        CVE-2021-47182: https://gitee.com/openeuler/kernel/pulls/7148  scsi: sd: Fix sd_do_mode_sense() buffer length handling
        CVE-2024-27388: https://gitee.com/openeuler/kernel/pulls/7139  SUNRPC: fix some memleaks in gssx_dec_option_array
        CVE-2023-52653: https://gitee.com/openeuler/kernel/pulls/7129  SUNRPC: fix a memleak in gss_import_v2_context
        CVE-2024-26958: https://gitee.com/openeuler/kernel/pulls/7044 v2  nfs: fix UAF in direct writes
        CVE-2024-26982: https://gitee.com/openeuler/kernel/pulls/7092  Squashfs: check the inode number is not the invalid value of zero
        CVE-2024-27024: https://gitee.com/openeuler/kernel/pulls/7054  CVE-2024-27024
        CVE-2024-27008: https://gitee.com/openeuler/kernel/pulls/7080  drm: nv04: Fix out of bounds access
        CVE-2024-27073: https://gitee.com/openeuler/kernel/pulls/7086  media: ttpci: fix two memleaks in budget_av_attach
        CVE-2024-27034: https://gitee.com/openeuler/kernel/pulls/7042  CVE-2024-27034
        CVE-2024-27043: https://gitee.com/openeuler/kernel/pulls/7013  media: edia: dvbdev: fix a use-after-free
        CVE-2024-27014: https://gitee.com/openeuler/kernel/pulls/6994 v2  net/mlx5e: Prevent deadlock while disabling aRFS
        CVE-2024-27059: https://gitee.com/openeuler/kernel/pulls/7039  USB: usb-storage: Prevent divide-by-0 error in isd200_ata_command
        CVE-2024-26931: https://gitee.com/openeuler/kernel/pulls/7056  scsi: qla2xxx: Fix command flush on cable pull
        CVE-2023-52644: https://gitee.com/openeuler/kernel/pulls/7006  wifi: b43: Stop/wake correct queue in DMA Tx path when QoS is disabled
        CVE-2024-26897: https://gitee.com/openeuler/kernel/pulls/7003  wifi: ath9k: delay all of ath9k_wmi_event_tasklet() until init is complete
        CVE-2024-27019: https://gitee.com/openeuler/kernel/pulls/7041  netfilter: nf_tables: Fix potential data-race in __nft_obj_type_get()
        CVE-2024-27020: https://gitee.com/openeuler/kernel/pulls/6990  netfilter: nf_tables: Fix potential data-race in __nft_expr_type_get()
        CVE-2024-27010: https://gitee.com/openeuler/kernel/pulls/7000  fix CVE-2024-27010
        CVE-2024-26829: https://gitee.com/openeuler/kernel/pulls/6843 v2  scsi: core: Fix unremoved procfs host directory regression
        CVE-2024-26934: https://gitee.com/openeuler/kernel/pulls/6939  USB: core: Fix deadlock in usb_deauthorize_interface()
        CVE-2024-27045: https://gitee.com/openeuler/kernel/pulls/6906  drm/amd/display: Fix a potential buffer overflow in 'dp_dsc_clock_en_read()'
        CVE-2024-26950: https://gitee.com/openeuler/kernel/pulls/6977  wireguard: netlink: access device through ctx instead of peer
        CVE-2024-27011: https://gitee.com/openeuler/kernel/pulls/6956  netfilter: nf_tables: fix memleak in map from abort path
        CVE-2024-26965: https://gitee.com/openeuler/kernel/pulls/6988  clk: qcom: mmcc-msm8974: fix terminating of frequency table arrays
        CVE-2024-26996: https://gitee.com/openeuler/kernel/pulls/6914  usb: gadget: f_ncm: Fix UAF ncm object at re-bind after usb ep transport error
        CVE-2024-26976: https://gitee.com/openeuler/kernel/pulls/6855  KVM: Always flush async #PF workqueue when vCPU is being destroyed
        CVE-2024-26994: https://gitee.com/openeuler/kernel/pulls/6943  speakup: Avoid crash on very long word
        CVE-2024-26961: https://gitee.com/openeuler/kernel/pulls/6959  mac802154: fix llsec key resources release in mac802154_llsec_key_del
        CVE-2022-48645: https://gitee.com/openeuler/kernel/pulls/6932  net: enetc: deny offload of tc-based TSN features on VF interfaces
        CVE-2024-26878: https://gitee.com/openeuler/kernel/pulls/6689  quota: Fix potential NULL pointer dereference
        CVE-2024-27000: https://gitee.com/openeuler/kernel/pulls/6964 v2  CVE-2024-27000
        CVE-2024-27389: https://gitee.com/openeuler/kernel/pulls/6872  pstore: inode: Only d_invalidate() is needed
        CVE-2024-27035: https://gitee.com/openeuler/kernel/pulls/6882  f2fs: compress: fix to guarantee persisting compressed blocks by CP
        CVE-2024-27013: https://gitee.com/openeuler/kernel/pulls/6895  tun: limit printing rate when illegal packet received by tun dev
        CVE-2022-48673: https://gitee.com/openeuler/kernel/pulls/6879  net/smc: Fix possible access to freed memory in link clear

### Processors Support:
#### Kunpeng:
        https://gitee.com/openeuler/kernel/pulls/7651 fix the SPI driver failed to obtain the GPIO pin
        https://gitee.com/openeuler/kernel/pulls/7732 HNS3: Fixed a deadlock issue caused by concurrent VF deactivation and PF reset
        https://gitee.com/openeuler/kernel/pulls/7563 udma: fix a bug of segment
        https://gitee.com/openeuler/kernel/pulls/7722 urma: fix bugs of urma and udma
        https://gitee.com/openeuler/kernel/pulls/7577 spi: hisi-kunpeng：backport some bugfixes
        https://gitee.com/openeuler/kernel/pulls/7204 udma: fix bugs of DCA and record db
        https://gitee.com/openeuler/kernel/pulls/6954 [OLK-5.10]Fix some bugs of the Mini-IO module

#### Hygon:
        https://gitee.com/openeuler/kernel/pulls/4642 Add support for Hygon family 18h model 5h HD-Audio
        https://gitee.com/openeuler/kernel/pulls/4640 Add support for Hygon model 6h L3 PMU
        https://gitee.com/openeuler/kernel/pulls/4639 Some fixes for Hygon model 4h~6h processors
        https://gitee.com/openeuler/kernel/pulls/4641 Add support for Hygon model 4h QoS

#### Zhaoxin:
        https://gitee.com/openeuler/kernel/pulls/2583 [OLK-5.10] Driver for Zhaoxin AES and SHA algorithm

#### AMD:
        https://gitee.com/openeuler/kernel/pulls/6783 [OLK-5.10] fix HEST memory usage is too high

### Devices Support:
#### Mont-TSSE
        https://gitee.com/openeuler/kernel/pulls/5557 [OLK-5.10]Add support for Mont-TSSE

#### mucse
        https://gitee.com/openeuler/kernel/pulls/6655 [OLK-5.10] mucse rnpm driver fw mailbox maybe failed to communicate with PF for mucse N10/N400 chips

#### yusur
        https://gitee.com/openeuler/kernel/pulls/5964 drivers: close default yusur KPU FLEXFLOW-2100P driver support

#### windriver
        https://gitee.com/openeuler/kernel/pulls/7402  scsi: lpfc: Fix possible file string name overflow when updating firmware
        https://gitee.com/openeuler/kernel/pulls/7404  scsi: lpfc: Fix possible memory leak in lpfc_rcv_padisc()
        https://gitee.com/openeuler/kernel/pulls/7403  scsi: mpt3sas: Prevent sending diag_reset when the controller is ready
        https://gitee.com/openeuler/kernel/pulls/7400  net/tg3: fix race condition in tg3_reset_task()
        https://gitee.com/openeuler/kernel/pulls/7401  nvme-core: check for too small lba shift
        https://gitee.com/openeuler/kernel/pulls/7396  drm/amdgpu: Fix cat debugfs amdgpu_regs_didt causes kernel null pointer
        https://gitee.com/openeuler/kernel/pulls/7397  drm/amd/display: Fix potential NULL pointer dereferences in 'dcn10_set_output_transfer_func()'
        https://gitee.com/openeuler/kernel/pulls/7398  drm/amd/display: Fix memory leak in dm_sw_fini()
        https://gitee.com/openeuler/kernel/pulls/7399  drm/amd/pm: fix a double-free in si_dpm_init

OLK-6.6进展同步：
新分支已合入PR 57个，commit 278个
最新tag 6.6.0-27.0.0
近两周(5.11-5.24)新合入PR：
性能提升专项（6）：
        entry: inline syscall enter/exit functions https://gitee.com/openeuler/kernel/pulls/7190
        Avoiding false sharing in field access of tk_core https://gitee.com/openeuler/kernel/pulls/7521
        ext4 iomap performance optimize https://gitee.com/openeuler/kernel/pulls/7527
        jbd2: speed up jbd2_transaction_committed() https://gitee.com/openeuler/kernel/pulls/7595
        ext4: default enable iomap for buffered IO and large folio https://gitee.com/openeuler/kernel/pulls/7771
        mm: add thp anon pmd size mapping align control https://gitee.com/openeuler/kernel/pulls/7888
处理器及板卡支持专项：
        华为（10）：
        RDMA/hns: Some bugfixes and cleanups https://gitee.com/openeuler/kernel/pulls/7075
        net: hns3: some bugfixes for hns3 driver https://gitee.com/openeuler/kernel/pulls/7126
        net: hns3: Fix ROH mac address initialization. https://gitee.com/openeuler/kernel/pulls/7131
        Fix allmodconfig build error https://gitee.com/openeuler/kernel/pulls/7607
        v2 Fix two soc bugs of hip09 https://gitee.com/openeuler/kernel/pulls/6778
        Fix failed in acpi_gpiochip_find() by adding parent node match https://gitee.com/openeuler/kernel/pulls/7136
        arm64: arm_pmuv3: Correctly extract and check the PMUVer https://gitee.com/openeuler/kernel/pulls/7227
        spi: hisi-kunpeng: Add validation for the minimum value of speed_hz https://gitee.com/openeuler/kernel/pulls/7141
        irqchip/gic-v3: Fix one race condition due to NMI withdraw https://gitee.com/openeuler/kernel/pulls/7537
        Fix pseudo nmi identifier undeclaration complilation error https://gitee.com/openeuler/kernel/pulls/7572
        龙芯（4）：
        add pmu support for loongarch kvm https://gitee.com/openeuler/kernel/pulls/6241
        irqchip/loongson-eiointc: fix gsi register error https://gitee.com/openeuler/kernel/pulls/7767
        LoongArch: fix kdump not work when legacy mode disabled https://gitee.com/openeuler/kernel/pulls/7823
        LoongArch: limit min pci msi-x/msi vector number when request more than 32 vectors https://gitee.com/openeuler/kernel/pulls/7822
        网讯（1）：
        merge upstream 4 wangxun related patches to fix i2c bug https://gitee.com/openeuler/kernel/pulls/6774
        兆芯（4）：
        iommu/dma: Fix not fully traversing iova reservations issue https://gitee.com/openeuler/kernel/pulls/5291
        x86/mce: Set bios_cmci_threshold for CMCI threshold https://gitee.com/openeuler/kernel/pulls/5644
        iommu/vt-d:Add support for detecting ACPI device in RMRR https://gitee.com/openeuler/kernel/pulls/3133
        Fix DMA RW sequence disorder issue https://gitee.com/openeuler/kernel/pulls/5480
        海光（3）：
        Add HGSC_CERT_IMPORT ioctl interface for Hygon CPUs https://gitee.com/openeuler/kernel/pulls/5218
        Hygon model 6h L3 PMU event duplicate creating issue fix https://gitee.com/openeuler/kernel/pulls/7219
        Support PSP identification for Hygon 4th CPU and print secure features when running on Hygon CPUs https://gitee.com/openeuler/kernel/pulls/5243
        飞腾（1）：
        Fixed display error for ps23xx when using ast and pe2201 bmc card https://gitee.com/openeuler/kernel/pulls/7583
        云芯智联（1）：
        【3snic】 use same string “sssnic" for "Kernel driver in use" and "Kernel modules" https://gitee.com/openeuler/kernel/pulls/7180
        沐创（1）：
        Fix warnings for RNPVF driver with loongarch-allmodconfig https://gitee.com/openeuler/kernel/pulls/6386
        AMD（1）：
        bugfix from upstream v6.9 for AMD EPYC https://gitee.com/openeuler/kernel/pulls/7721
特性（5）：
        v3 Backport folio feature and bugfix https://gitee.com/openeuler/kernel/pulls/7196
        v2 mm: prepare more high-order pages on pcplist https://gitee.com/openeuler/kernel/pulls/7198
        mm: mglru: reuse some legacy trace https://gitee.com/openeuler/kernel/pulls/7182
        mm: more thp control for large folio https://gitee.com/openeuler/kernel/pulls/7530
        mm: Some bugfix and optimization https://gitee.com/openeuler/kernel/pulls/7764
        
bugfix（13）：
        ext4: fix uninitialized ratelimit_state->lock access in __ext4_fill_super() https://gitee.com/openeuler/kernel/pulls/7069
        backport some mailist patches for perf https://gitee.com/openeuler/kernel/pulls/7159
        Backports for OLK-6.6 https://gitee.com/openeuler/kernel/pulls/7153
        kernfs: RCU protect kernfs_nodes and avoid kernfs_idr_lock in kernfs_find_and_get_node_by_id() https://gitee.com/openeuler/kernel/pulls/7068
        v2 tick/broadcast-hrtimer: Prevent the timer device on broadcast duty CPU from being disabled https://gitee.com/openeuler/kernel/pulls/7165
        v3 md: do not delete safemode_timer in mddev_suspend https://gitee.com/openeuler/kernel/pulls/7184
        v2 sched: programmable: Allow set tag for pid 1. https://gitee.com/openeuler/kernel/pulls/7206
        v2 ima: Avoid blocking in RCU read-side critical section https://gitee.com/openeuler/kernel/pulls/6311
        USB: UAS: return ENODEV when submit urbs fail with device not attached https://gitee.com/openeuler/kernel/pulls/5654
        sched/fair: set burst to zero when cfs bandwidth is cancelled https://gitee.com/openeuler/kernel/pulls/7474
        memcg_swap_qos: Backport two bugfix https://gitee.com/openeuler/kernel/pulls/7593
        sched: smart_grid: silence complier error https://gitee.com/openeuler/kernel/pulls/7370
        sched: QOS_SCHED_DYNAMIC_AFFINITY depend on FAIR_CGROUP_SCHED https://gitee.com/openeuler/kernel/pulls/7730
CVE（3）:
        CVE-2024-27072 https://gitee.com/openeuler/kernel/pulls/7164
        CVE-2024-26993 https://gitee.com/openeuler/kernel/pulls/6837
        CVE-2024-35965 https://gitee.com/openeuler/kernel/pulls/7808
config兼容性（1）：
        v2 openeuler_defconfig: update oedefconfig for the minimum set https://gitee.com/openeuler/kernel/pulls/7130
KABI预留（2）：
        v2 mm: prepare to support weighted interleaving mempolicy https://gitee.com/openeuler/kernel/pulls/7405
        add new kvm_type for Confidential VMs https://gitee.com/openeuler/kernel/pulls/7454
继承特性回合事项： closed
        openEuler-24.03-LTS ISO镜像下载链接：http://121.36.84.172/dailybuild/EBS-openEuler-24.03-LTS/

议题二：新增叶炜华（华为）为kernel sig committer
1、多年Linux开发经验，专长调测、ebpf与livepatch等领域；
2、在openEuler社区合入68个patch(livepatch\printk等特性相关)，review openEuler PR 114个
3、申请调测、ebpf与livepatch等相关领域committer，相关领域committer缺失，影响review与代码合入进度；

议题三：申请Kernel组下添加cloudphone_kernel新仓（黄浩纯）
该仓库用于存放适配鲲鹏BoostKit Kbox云手机方案的内核代码
https://gitee.com/openeuler/community/pulls/5638
结论：当前4位Maintainer已经达成一致，同意在Kernel sig组下添加cloudphone_kernel新仓

议题四：

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/5/10 Kernel SIG 双周例会】
轮值主持：仉鹏 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->张伽琳->廖涛】
下次轮值主持：曾昭荣
会议链接：https://meeting.huaweicloud.com:36443/#/j/987502806
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&仉鹏）
近三周(2024.4.22 ~ 5.10)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-198.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-198.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.53.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.74.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.136.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-196.0.0 更新至 5.10.0-198.0.0, 回合补丁数387个
        git log 5.10.0-196.0.0..5.10.0-198.0.0 --oneline | wc -l
        387

## 5.10.0-196.0.0..5.10.0-198.0.0

### Backport patches from upstream LTS (5.10.204 - 5.10.205):
        https://gitee.com/openeuler/kernel/pulls/6631 Backport 5.10.205 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/6539 Backport 5.10.204 LTS patches from upstream

### Fix CVE (73):
        CVE-2024-26885: https://gitee.com/openeuler/kernel/pulls/6904  bpf: Fix DEVMAP_HASH overflow check on 32-bit arches
        CVE-2024-26884: https://gitee.com/openeuler/kernel/pulls/6918  bpf: Fix hashtab overflow check on 32-bit arches
        CVE-2022-48655: https://gitee.com/openeuler/kernel/pulls/6928  firmware: arm_scmi: Harden accesses to the reset domains
        CVE-2024-26883: https://gitee.com/openeuler/kernel/pulls/6924  bpf: Fix stackmap overflow check on 32-bit arches
        CVE-2024-27075: https://gitee.com/openeuler/kernel/pulls/6861  media: dvb-frontends: avoid stack overflow warnings with clang
        CVE-2023-52650: https://gitee.com/openeuler/kernel/pulls/6840  CVE-2023-52650
        CVE-2024-26999: https://gitee.com/openeuler/kernel/pulls/6851  serial/pmac_zilog: Remove flawed mitigation for rx irq flood
        CVE-2024-26973: https://gitee.com/openeuler/kernel/pulls/6826  fat: fix uninitialized field in nostale filehandles
        CVE-2024-26993: https://gitee.com/openeuler/kernel/pulls/6838  fs: sysfs: Fix reference leak in sysfs_break_active_protection()
        CVE-2024-26923: https://gitee.com/openeuler/kernel/pulls/6808  CVE-2024-26923
        CVE-2022-48674: https://gitee.com/openeuler/kernel/pulls/6849  erofs: fix pcluster use-after-free on UP platforms
        CVE-2024-26846: https://gitee.com/openeuler/kernel/pulls/6473  nvme-fc: do not wait in vain when unloading module
        CVE-2024-26845: https://gitee.com/openeuler/kernel/pulls/6797  scsi: target: core: Add TMF to tmr_list handling
        CVE-2024-26829: https://gitee.com/openeuler/kernel/pulls/6798  media: ir_toy: fix a memleak in irtoy_tx
        CVE-2024-26814: https://gitee.com/openeuler/kernel/pulls/6756  vfio/fsl-mc: Block calling interrupt handler without trigger
        CVE-2024-26926: https://gitee.com/openeuler/kernel/pulls/6755  binder: check offset alignment in binder_get_object()
        CVE-2024-26870: https://gitee.com/openeuler/kernel/pulls/6669  NFSv4.2: fix nfs4_listxattr kernel BUG at mm/usercopy.c:102
        CVE-2024-26828: https://gitee.com/openeuler/kernel/pulls/6680  cifs: fix underflow in parse_server_interfaces()
        CVE-2024-26922: https://gitee.com/openeuler/kernel/pulls/6719  drm/amdgpu: validate the parameters of bo mapping operations more clearly
        CVE-2024-26852: https://gitee.com/openeuler/kernel/pulls/6654  net/ipv6: avoid possible UAF in ip6_route_mpath_notify()
        CVE-2024-26921: https://gitee.com/openeuler/kernel/pulls/6683 v2  CVE-2024-26921
        CVE-2024-26840: https://gitee.com/openeuler/kernel/pulls/6501  cachefiles: fix memory leak in cachefiles_add_cache()
        CVE-2024-26896: https://gitee.com/openeuler/kernel/pulls/6567  CVE-2024-26896
        CVE-2024-26874: https://gitee.com/openeuler/kernel/pulls/6580  drm/mediatek: Fix a null pointer crash in mtk_drm_crtc_finish_page_flip
        CVE-2024-26863: https://gitee.com/openeuler/kernel/pulls/6640  hsr: Fix uninit-value access in hsr_get_node()
        CVE-2024-26862: https://gitee.com/openeuler/kernel/pulls/6620  packet: annotate data-races around ignore_outgoing
        CVE-2024-26859: https://gitee.com/openeuler/kernel/pulls/6618  net/bnx2x: Prevent access to a freed page in page_pool
        CVE-2024-26882: https://gitee.com/openeuler/kernel/pulls/6592  net: ip_tunnel: make sure to pull inner header in ip_tunnel_rcv()
        CVE-2024-24860: https://gitee.com/openeuler/kernel/pulls/6619  Bluetooth: Fix atomicity violation in {min,max}_key_size_set
        CVE-2024-26817: https://gitee.com/openeuler/kernel/pulls/6623  amdkfd: use calloc instead of kzalloc to avoid integer overflow
        CVE-2024-26900: https://gitee.com/openeuler/kernel/pulls/6561  md: fix kmemleak of rdev->serial
        CVE-2024-26843: https://gitee.com/openeuler/kernel/pulls/6485  CVE-2024-26843
        CVE-2024-25739: https://gitee.com/openeuler/kernel/pulls/6247  ubi: Check for too small LEB size in VTBL code
        CVE-2024-26907: https://gitee.com/openeuler/kernel/pulls/6546 v2  CVE-2024-26907
        CVE-2024-26869: https://gitee.com/openeuler/kernel/pulls/6597 v3  Fix CVE-2024-26869
        CVE-2024-26904: https://gitee.com/openeuler/kernel/pulls/6401  btrfs: fix data race at btrfs_use_block_rsv() when accessing block reserve
        CVE-2024-26839: https://gitee.com/openeuler/kernel/pulls/6568  IB/hfi1: Fix a memleak in init_credit_return
        CVE-2023-52642: https://gitee.com/openeuler/kernel/pulls/6579  media: rc: bpf attach/detach requires write permission
        CVE-2024-26855: https://gitee.com/openeuler/kernel/pulls/6543  net: ice: Fix potential NULL pointer dereference in ice_bridge_setlink()
        CVE-2024-26893: https://gitee.com/openeuler/kernel/pulls/6520  firmware: arm_scmi: Fix double free in SMC transport cleanup path
        CVE-2024-26894: https://gitee.com/openeuler/kernel/pulls/6584  ACPI: processor_idle: Fix memory leak in acpi_processor_power_exit()
        CVE-2024-26825: https://gitee.com/openeuler/kernel/pulls/6566  nfc: nci: free rx_data_reassembly skb on NCI device cleanup
        CVE-2024-26880: https://gitee.com/openeuler/kernel/pulls/6437  dm: call the resume method on internal suspend
        CVE-2021-47193: https://gitee.com/openeuler/kernel/pulls/6442  scsi: pm80xx: Fix memory leak during rmmod
        CVE-2024-26901: https://gitee.com/openeuler/kernel/pulls/6474  do_sys_name_to_handle(): use kzalloc() to fix kernel-infoleak
        CVE-2024-26875: https://gitee.com/openeuler/kernel/pulls/6417  media: pvrusb2: fix uaf in pvr2_context_set_notify
        CVE-2024-26872: https://gitee.com/openeuler/kernel/pulls/6493  RDMA/srpt: Do not register event handler until srpt device is fully setup
        CVE-2024-26813: https://gitee.com/openeuler/kernel/pulls/6458  CVE-2024-26813
        CVE-2024-26615: https://gitee.com/openeuler/kernel/pulls/5273  net/smc: fix illegal rmb_desc access in SMC-D connection dump
        CVE-2024-26734: https://gitee.com/openeuler/kernel/pulls/6486  devlink: fix possible use-after-free and memory leaks in devlink_init()
        CVE-2023-52498: https://gitee.com/openeuler/kernel/pulls/6515  fix CVE-2023-52498
        CVE-2023-52491: https://gitee.com/openeuler/kernel/pulls/5468  media: mtk-jpeg: Fix use after free bug due to error path handling in mtk_jpeg_dec_device_run
        CVE-2024-26908: https://gitee.com/openeuler/kernel/pulls/6314  fixup CVE-2024-26908
        CVE-2024-26917: https://gitee.com/openeuler/kernel/pulls/6316  scsi: fnic: Move fnic_fnic_flush_tx() to a work queue
        CVE-2024-26895: https://gitee.com/openeuler/kernel/pulls/6399  wifi: wilc1000: prevent use-after-free on vif when cleaning up all interfaces
        CVE-2023-7042:  https://gitee.com/openeuler/kernel/pulls/6407  wifi: ath10k: fix NULL pointer dereference in ath10k_wmi_tlv_op_pull_mgmt_tx_compl_ev()
        CVE-2021-47182: https://gitee.com/openeuler/kernel/pulls/6455  CVE-2021-47182
        CVE-2024-26920: https://gitee.com/openeuler/kernel/pulls/6423  tracing/trigger: Fix to return error if failed to alloc snapshot
        CVE-2021-47212: https://gitee.com/openeuler/kernel/pulls/6281 v2  net/mlx5: Update error handler for UCTX and UMEM
        CVE-2023-47233: https://gitee.com/openeuler/kernel/pulls/6267  wifi: brcmfmac: Fix use-after-free bug in brcmf_cfg80211_detach
        CVE-2024-26801: https://gitee.com/openeuler/kernel/pulls/6279  Bluetooth: Avoid potential use-after-free in hci_error_reset
        CVE-2024-26733: https://gitee.com/openeuler/kernel/pulls/6259  arp: Prevent overflow in arp_req_get().
        CVE-2024-24861: https://gitee.com/openeuler/kernel/pulls/6312  fix CVE-2024-24861 for 5.10
        CVE-2023-6270:  https://gitee.com/openeuler/kernel/pulls/6291  aoe: fix the potential use-after-free problem in aoecmd_cfg_pkts
        CVE-2021-47211: https://gitee.com/openeuler/kernel/pulls/6202  ALSA: usb-audio: fix null pointer dereference on pointer cs_desc
        CVE-2021-47199: https://gitee.com/openeuler/kernel/pulls/6284  net/mlx5e: CT, Fix multiple allocations and memleak of mod acts
        CVE-2024-26764: https://gitee.com/openeuler/kernel/pulls/6076  Fix CVE-2024-26764
        CVE-2023-52441: https://gitee.com/openeuler/kernel/pulls/5965  Fix CVE-2023-52441 and integrate the pre-patch
        CVE-2024-26808: https://gitee.com/openeuler/kernel/pulls/6086  netfilter: nft_chain_filter: handle NETDEV_UNREGISTER for inet/ingress basechain
        CVE-2024-26805: https://gitee.com/openeuler/kernel/pulls/6085  netlink: Fix kernel-infoleak-after-free in __skb_datagram_iter
        CVE-2024-26739: https://gitee.com/openeuler/kernel/pulls/6087  net/sched: act_mirred: don't override retval if we already lost the skb
        CVE-2023-52637: https://gitee.com/openeuler/kernel/pulls/6082  can: j1939: Fix UAF in j1939_sk_match_filter during setsockopt(SO_J1939_FILTER)
        CVE-2024-26804: https://gitee.com/openeuler/kernel/pulls/6058  net: ip_tunnel: prevent perpetual headroom growth

### Fearures:
#### arm virtcca
        https://gitee.com/openeuler/kernel/pulls/6676  cvm feature patches

#### hugetlb MADV_DONTNEED
        https://gitee.com/openeuler/kernel/pulls/6588  Add hugetlb MADV_DONTNEED support

### Processors Support:
#### Kunpeng:
        https://gitee.com/openeuler/kernel/pulls/5905 [OLK 5.10] RDMA/hns: Fix incorrect iteration number of DCA umem sg entries and error return in hns_roce_v2_modify_srq()
        https://gitee.com/openeuler/kernel/pulls/6660 udma: fix bugs of record_db
        https://gitee.com/openeuler/kernel/pulls/6635 backport RDMA/hns: Fix DCA's dependence on ib_uverbs from OLK-6.6
        https://gitee.com/openeuler/kernel/pulls/6257 HNS3: Do some optimizing job and support fast path
        https://gitee.com/openeuler/kernel/pulls/6555 udma: fix bugs in non-share jfr and remove rm mode
        https://gitee.com/openeuler/kernel/pulls/6295 hns3 udma: adjustment of the maximum number of Jettys
        https://gitee.com/openeuler/kernel/pulls/6263 udma: fix a bug of jfr record_db
        https://gitee.com/openeuler/kernel/pulls/6262 scsi: hisi_sas: Remove hisi_hba->timer for v3 hw

### Devices Support:
#### Huawei SP600 Network Card RDMA Driver
        https://gitee.com/openeuler/kernel/pulls/6684  infiniband/hw/hiroce3: Add Huawei Intelligent Network Card RDMA Driver

### Bugfix：
        https://gitee.com/openeuler/kernel/pulls/6846  perf/x86/amd: Fix crash due to race between amd_pmu_enable_all, perf NMI and throttling
        https://gitee.com/openeuler/kernel/pulls/6740  V2 cpuset: fix race between rebuild scheduler domains and hotplug work
        https://gitee.com/openeuler/kernel/pulls/6802  x86,static_call: Fix __static_call_return0 for i386
        https://gitee.com/openeuler/kernel/pulls/6835  kprobes: Fix check for probe enabled in kill_kprobe()
        https://gitee.com/openeuler/kernel/pulls/6799  rtmutex: Add acquire semantics for rtmutex lock acquisition slow path
        https://gitee.com/openeuler/kernel/pulls/6704  x86/thermal: Fix LVT thermal setup for SMI delivery mode
        https://gitee.com/openeuler/kernel/pulls/6702  static_call: Don't make __static_call_return0 static
        https://gitee.com/openeuler/kernel/pulls/6700  PCI/IOV: Enlarge virtfn sysfs name buffer
        https://gitee.com/openeuler/kernel/pulls/6729  PCI/IOV: Improve performance of creating VFs concurrently
        https://gitee.com/openeuler/kernel/pulls/6739 v2  Apply patches of ses from stable
        https://gitee.com/openeuler/kernel/pulls/6677 v3  olk-5.10: bugfix for mm
        https://gitee.com/openeuler/kernel/pulls/6428  net/sched: flower: Fix unable to handle page fault bug in fl_init
        https://gitee.com/openeuler/kernel/pulls/6308 v3  ima: Avoid blocking in RCU read-side critical section
        https://gitee.com/openeuler/kernel/pulls/6294 [sync] PR-6177:  arm64/mpam: Not allowed setting 0 to cache portion bit mask
        https://gitee.com/openeuler/kernel/pulls/6293 [sync] PR-6176:  arm64/mpam: return EOPNOTSUPP when changing rmid of monitor group or resource group with monitor
        https://gitee.com/openeuler/kernel/pulls/6199  writeback fix softlockup


近三周(2024.4.22 ~ 5.10)内进展同步:
总体上openEuler-1.0-LTS更新到tag 4.19.90-2405.1.0
openEuler-20.03-LTS-SP1分支
release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
        对应update rpm包下载地址:
        https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
openEuler-1.0-LTS从 4.19.90-2404.2.0 更新至 4.19.90-2405.1.0, 回合补丁数85个
git log --no-merges 4.19.90-2404.2.0..4.19.90-2405.1.0 --oneline | wc -l
85

修复CVE 56个
CVE-2024-26883  https://gitee.com/openeuler/kernel/pulls/6858  CVE-2024-26883
CVE-2024-26993  https://gitee.com/openeuler/kernel/pulls/6836  fs: sysfs: Fix reference leak in sysfs_break_active_protection()
CVE-2022-48674  https://gitee.com/openeuler/kernel/pulls/6845  erofs: fix pcluster use-after-free on UP platforms
CVE-2024-26973  https://gitee.com/openeuler/kernel/pulls/6827  fat: fix uninitialized field in nostale filehandles
CVE-2024-26923  https://gitee.com/openeuler/kernel/pulls/6807  CVE-2024-26923
CVE-2022-48702  https://gitee.com/openeuler/kernel/pulls/6847  ALSA: emu10k1: Fix out of bounds access in snd_emu10k1_pcm_channel_alloc()
CVE-2022-48664  https://gitee.com/openeuler/kernel/pulls/6758  CVE-2022-48664
CVE-2024-26845  https://gitee.com/openeuler/kernel/pulls/6803  scsi: target: core: Add TMF to tmr_list handling
CVE-2024-26878  https://gitee.com/openeuler/kernel/pulls/6705  quota: fix CVE-2024-26878
CVE-2024-26828  https://gitee.com/openeuler/kernel/pulls/6674  cifs: fix underflow in parse_server_interfaces()
CVE-2024-26926  https://gitee.com/openeuler/kernel/pulls/6754  binder: check offset alignment in binder_get_object()
CVE-2024-26922  https://gitee.com/openeuler/kernel/pulls/6716  CVE-2024-26922
CVE-2024-26857  https://gitee.com/openeuler/kernel/pulls/6652  geneve: make sure to pull inner header in geneve_rx()
CVE-2024-26876  https://gitee.com/openeuler/kernel/pulls/6664  drm/bridge: adv7511: fix crash on irq during probe
CVE-2024-26852  https://gitee.com/openeuler/kernel/pulls/6653  net/ipv6: avoid possible UAF in ip6_route_mpath_notify()
CVE-2024-26840  https://gitee.com/openeuler/kernel/pulls/6510  cachefiles: fix memory leak in cachefiles_add_cache()
CVE-2024-26874  https://gitee.com/openeuler/kernel/pulls/6578  drm/mediatek: Fix a null pointer crash in mtk_drm_crtc_finish_page_flip
CVE-2024-26863  https://gitee.com/openeuler/kernel/pulls/6641  CVE-2024-26863
CVE-2021-47217  https://gitee.com/openeuler/kernel/pulls/6642  v3  x86/hyperv: Fix NULL deref in set_hv_tscchange_cb() if Hyper-V setup fails
CVE-2024-26817  https://gitee.com/openeuler/kernel/pulls/6621  amdkfd: use calloc instead of kzalloc to avoid integer overflow
CVE-2024-26859  https://gitee.com/openeuler/kernel/pulls/6617  net/bnx2x: Prevent access to a freed page in page_pool
CVE-2024-26882  https://gitee.com/openeuler/kernel/pulls/6611  net: ip_tunnel: make sure to pull inner header in ip_tunnel_rcv()
CVE-2024-26904  https://gitee.com/openeuler/kernel/pulls/6397  btrfs: fix data race at btrfs_use_block_rsv() when accessing block reserve
CVE-2024-26915  https://gitee.com/openeuler/kernel/pulls/6616  drm/amdgpu: Reset IH OVERFLOW_CLEAR bit
CVE-2024-24860  https://gitee.com/openeuler/kernel/pulls/6525  v2  CVE-2024-24860 bugfix
CVE-2024-26901  https://gitee.com/openeuler/kernel/pulls/6478  do_sys_name_to_handle(): use kzalloc() to fix kernel-infoleak
CVE-2024-26894  https://gitee.com/openeuler/kernel/pulls/6582  ACPI: processor_idle: Fix memory leak in acpi_processor_power_exit()
CVE-2023-52642  https://gitee.com/openeuler/kernel/pulls/6577  media: rc: bpf attach/detach requires write permission
CVE-2024-26839  https://gitee.com/openeuler/kernel/pulls/6560  IB/hfi1: Fix a memleak in init_credit_return
CVE-2024-26880  https://gitee.com/openeuler/kernel/pulls/6436  dm: call the resume method on internal suspend
CVE-2024-26825  https://gitee.com/openeuler/kernel/pulls/6562  nfc: nci: free rx_data_reassembly skb on NCI device cleanup
CVE-2024-26875  https://gitee.com/openeuler/kernel/pulls/6481  CVE-2024-26875
CVE-2024-26872  https://gitee.com/openeuler/kernel/pulls/6495  RDMA/srpt: Do not register event handler until srpt device is fully setup
CVE-2024-26813  https://gitee.com/openeuler/kernel/pulls/6457  CVE-2024-26813
CVE-2021-47183  https://gitee.com/openeuler/kernel/pulls/6517  scsi: lpfc: Fix link down processing to address NULL pointer dereference
CVE-2024-26851  https://gitee.com/openeuler/kernel/pulls/6521  netfilter: nf_conntrack_h323: Add protection for bmp length out of range
CVE-2021-47182  https://gitee.com/openeuler/kernel/pulls/6454  CVE-2021-47182
CVE-2024-26908  https://gitee.com/openeuler/kernel/pulls/6313  fixup CVE-2024-26908
CVE-2023-52638  https://gitee.com/openeuler/kernel/pulls/6447  can: j1939: prevent deadlock by changing j1939_socks_lock to rwlock
CVE-2023-7042  https://gitee.com/openeuler/kernel/pulls/6405  wifi: ath10k: fix NULL pointer dereference in ath10k_wmi_tlv_op_pull_mgmt_tx_compl_ev()
CVE-2024-26884  https://gitee.com/openeuler/kernel/pulls/6466  bpf: Fix hashtab overflow check on 32-bit arches
CVE-2024-26920  https://gitee.com/openeuler/kernel/pulls/6396  tracing/trigger: Fix to return error if failed to alloc snapshot
CVE-2024-26801  https://gitee.com/openeuler/kernel/pulls/6278  Bluetooth: Avoid potential use-after-free in hci_error_reset
CVE-2021-47211  https://gitee.com/openeuler/kernel/pulls/6203  ALSA: usb-audio: fix null pointer dereference on pointer cs_desc
CVE-2023-6270  https://gitee.com/openeuler/kernel/pulls/6292  aoe: fix the potential use-after-free problem in aoecmd_cfg_pkts
CVE-2024-26663  https://gitee.com/openeuler/kernel/pulls/6301  v2  tipc: Check the bearer type before calling tipc_udp_nl_bearer_add()
CVE-2021-47210  https://gitee.com/openeuler/kernel/pulls/6266  usb: typec: tipd: Remove WARN_ON in tps6598x_block_read
CVE-2024-24861  https://gitee.com/openeuler/kernel/pulls/6290  CVE-2024-24861
CVE-2021-47203  https://gitee.com/openeuler/kernel/pulls/6269  scsi: lpfc: Fix list_add() corruption in lpfc_drain_txq()
CVE-2023-47233  https://gitee.com/openeuler/kernel/pulls/6276  wifi: brcmfmac: Fix use-after-free bug in brcmf_cfg80211_detach
CVE-2024-26793  https://gitee.com/openeuler/kernel/pulls/6277  gtp: fix use-after-free and null-ptr-deref in gtp_newlink()
CVE-2024-26733  https://gitee.com/openeuler/kernel/pulls/6275  arp: Prevent overflow in arp_req_get().
CVE-2021-47216  https://gitee.com/openeuler/kernel/pulls/6280  scsi: advansys: Fix kernel pointer leak
CVE-2024-26764  https://gitee.com/openeuler/kernel/pulls/6075  Fix CVE-2024-26764
CVE-2024-26805  https://gitee.com/openeuler/kernel/pulls/6084  netlink: Fix kernel-infoleak-after-free in __skb_datagram_iter
CVE-2024-25739  https://gitee.com/openeuler/kernel/pulls/6246  ubi: Check for too small LEB size in VTBL code


社区问题修复以及上游社区bugfix补丁回合：
https://gitee.com/openeuler/kernel/pulls/6795  rtmutex: Add acquire semantics for rtmutex lock acquisition slow path
https://gitee.com/openeuler/kernel/pulls/6777  tun: Fix xdp_rxq_info's queue_index when detaching
https://gitee.com/openeuler/kernel/pulls/6494  v2  oom_kill.c: futex: delay the OOM reaper to allow time for proper futex cleanup
https://gitee.com/openeuler/kernel/pulls/6745  PCI/IOV: Improve performance of creating VFs concurrently
https://gitee.com/openeuler/kernel/pulls/6746  v3  openEuler-1.0-LTS: bugfix for mm
https://gitee.com/openeuler/kernel/pulls/6662  sched/rt: Disallow writing invalid values to sched_rt_period_us
https://gitee.com/openeuler/kernel/pulls/6661  sched/rt: sysctl_sched_rr_timeslice show default timeslice after reset
https://gitee.com/openeuler/kernel/pulls/6659  sched/rt: Fix sysctl_sched_rr_timeslice intial value
https://gitee.com/openeuler/kernel/pulls/6646  fix race between rebuild scheduler domains and hotplug work
https://gitee.com/openeuler/kernel/pulls/6420  tty: fix read of tty->pgrp outside of ctrl_lock
https://gitee.com/openeuler/kernel/pulls/6309  v5  ima: Avoid blocking in RCU read-side critical section
https://gitee.com/openeuler/kernel/pulls/6177  arm64/mpam: Not allowed setting 0 to cache portion bit mask
https://gitee.com/openeuler/kernel/pulls/6176  arm64/mpam: return EOPNOTSUPP when changing rmid of monitor group or resource group with monitor


OLK-6.6进展同步：

新分支已合入PR 42个，commit 2044个
近两周(4.19-5.10)新合入PR：

Backport patches from upstream LTS (6.6.23-6.6.30):
        https://gitee.com/openeuler/kernel/pulls/6859

性能提升专项：
        v3 m: convert mm's rss stats to use atomic mode https://gitee.com/openeuler/kernel/pulls/6439
        Backport page fault and fork optimization https://gitee.com/openeuler/kernel/pulls/6626
        sched: disable sched_autogroup by default https://gitee.com/openeuler/kernel/pulls/6658
        Fixes and cleanups to fs-writeback https://gitee.com/openeuler/kernel/pulls/7015
        v2 arm64: mmap: disable align larger anonymous mappings on THP boundaries https://gitee.com/openeuler/kernel/pulls/6905
        maple_tree: avoid checking other gaps after getting the largest gap https://gitee.com/openeuler/kernel/pulls/6877
        Introduce CONFIG_ARCH_CUSTOM_NUMA_DISTANCE https://gitee.com/openeuler/kernel/pulls/6824

处理器及板卡支持专项：
        华为网卡：
        RDMA/hns: Some bugfixes and cleanups https://gitee.com/openeuler/kernel/pulls/6467
        net: hns3: backport some maillist patches https://gitee.com/openeuler/kernel/pulls/6759
        net: hns3: add support for Hisilicon ptp sync device https://gitee.com/openeuler/kernel/pulls/6651
        infiniband/hw/hiroce3: Add Huawei Intelligent Network Card RDMA Driver https://gitee.com/openeuler/kernel/pulls/6647
        hisi：
        irqchip: gic-v3: Collection table support muti pages https://gitee.com/openeuler/kernel/pulls/6409
        hisi-acc-vfio-pci:add DFX for acc migration driver https://gitee.com/openeuler/kernel/pulls/6624
        i2c: hisi: Add I2C controller reset and initialization proccess in bus recovery action https://gitee.com/openeuler/kernel/pulls/6782
        spi: hisi-kunpeng: Delete the dump interface of data registers in debugfs https://gitee.com/openeuler/kernel/pulls/6760
        龙芯：
        LoongArch: fix KASLR can not be disabled by nokaslr when boot from old BPI https://gitee.com/openeuler/kernel/pulls/6581
        LoongArch: 修复ioremap_page_range报错 https://gitee.com/openeuler/kernel/pulls/6483

特性：
        ext4: use iomap for regular file's buffered IO path and enable large foilo https://gitee.com/openeuler/kernel/pulls/6632
        A Solution to Re-enable hugetlb vmemmap optimize on ARM64 https://gitee.com/openeuler/kernel/pulls/6595
        v6 Introduce BPF_READAHEAD option for optimizing read performance https://gitee.com/openeuler/kernel/pulls/6590

bugfix（11）：
        ipvlan: Fix warning while IPVLAN_L2E disabled https://gitee.com/openeuler/kernel/pulls/6385
        mm/migrate: correct nr_failed in migrate_pages_sync() https://gitee.com/openeuler/kernel/pulls/6424
        iommu/arm-smmu-v3: fix using uninitialized or unchecked symbol https://gitee.com/openeuler/kernel/pulls/6403
        bpf: Add missing BPF_LINK_TYPE invocations https://gitee.com/openeuler/kernel/pulls/6402
        v2 perf data convert: Fix segfault when converting to json when cpu_desc isn't set https://gitee.com/openeuler/kernel/pulls/6625
        v2 SUNRPC: Fix a slow server-side memory leak with RPC-over-TCP https://gitee.com/openeuler/kernel/pulls/6735
        watchdog: Fix call trace when failed to initialize sdei https://gitee.com/openeuler/kernel/pulls/6731
        ipvlan: enable CONFIG_IPVLAN_L2E option in openeuler config https://gitee.com/openeuler/kernel/pulls/6692
        v3 bugfix patches from OLK-5.10 https://gitee.com/openeuler/kernel/pulls/7011
        fix general protection fault in update_cpumask https://gitee.com/openeuler/kernel/pulls/6930
        block: fix deadlock between bd_link_disk_holder and partition scan https://gitee.com/openeuler/kernel/pulls/6844

CVE（10）:     
        CVE-2024-26868 https://gitee.com/openeuler/kernel/pulls/6390
        CVE-2024-26869 https://gitee.com/openeuler/kernel/pulls/6444
        CVE-2024-26904 https://gitee.com/openeuler/kernel/pulls/6400
        CVE-2024-26871 https://gitee.com/openeuler/kernel/pulls/6443
        CVE-2024-26875 https://gitee.com/openeuler/kernel/pulls/6418
        CVE-2024-26894 https://gitee.com/openeuler/kernel/pulls/6585
        CVE-2024-26901 https://gitee.com/openeuler/kernel/pulls/6479
        CVE-2024-26917 https://gitee.com/openeuler/kernel/pulls/6468
        CVE-2024-26878 https://gitee.com/openeuler/kernel/pulls/6730
        CVE-2024-26905 https://gitee.com/openeuler/kernel/pulls/6681
        

KABI专项： closed  
继承特性回合事项： closed  

        最新tag 6.6.0-25.0.0
        openEuler-24.03-LTS ISO镜像下载链接：http://121.36.84.172/dailybuild/EBS-openEuler-24.03-LTS/


议题二：仉鹏申请成为kernel sig committer
申请packing相关committer，负责6.6版本的集成、打包、发布

主要贡献：
release相关PR：
release 6.6.0-25.0.0
https://gitee.com/src-openeuler/kernel/pulls/1564
release 6.6.0-24.0.0
https://gitee.com/src-openeuler/kernel/pulls/1563
release 6.6.0-23.0.0
https://gitee.com/src-openeuler/kernel/pulls/1555
release 6.6.0-21.0.0
https://gitee.com/src-openeuler/kernel/pulls/1544
release 6.6.0-19.0.0
https://gitee.com/src-openeuler/kernel/pulls/1526

LTS补丁Backport PR：
Backport 6.6.8~6.6.30 LTS 补丁
https://gitee.com/openeuler/kernel/pulls/6859
https://gitee.com/openeuler/kernel/pulls/5369
https://gitee.com/openeuler/kernel/pulls/5318

相关review PR数量:
当前共有100+
https://datastat.openeuler.org/zh/user/anred

性能优化PR：
Backport page fault optimization
https://gitee.com/openeuler/kernel/issues/I9JAY9
mm: convert mm's rss stats to use atomic mode
https://gitee.com/openeuler/kernel/issues/I9IA1I
Backport mm: batch mm counter updating in filemap_map_pages()
https://gitee.com/openeuler/kernel/issues/I9GBVL
maple_tree: iterator state changes
https://gitee.com/openeuler/kernel/issues/I9EHBO
arch/mm/fault: accelerate pagefault when badaccess
https://gitee.com/openeuler/kernel/issues/I9E07B
Backport slub优化
https://gitee.com/openeuler/kernel/issues/I9CSFJ
userfaultfd: early return in dup_userfaultfd()
https://gitee.com/openeuler/kernel/issues/I9CKXN
Backport Introduce __mt_dup() to improve the performance of fork()
https://gitee.com/openeuler/kernel/issues/I9AYM3
缓解vmap/vmalloc的锁争用，提升vmalloc多核性能
https://gitee.com/openeuler/kernel/issues/I9CHG1

特性PR：
Backport numa balancing相关的folio conversation
https://gitee.com/openeuler/kernel/pulls/3018
Backport mlock支持large folio
https://gitee.com/openeuler/kernel/pulls/4199
支持userswap特性
https://gitee.com/openeuler/kernel/pulls/3352
Backport memcg维测特性：
https://gitee.com/openeuler/kernel/pulls/4154
日常CVE与bugfix

评审意见：
同意仉鹏成为 packing 领域的 Committer，负责6.6版本的集成、打包、发布等工作。
并接替郑增凯成为 OLK-6.6 分支的 Branch Keeper.

议题三：buffer io限速关系自动绑定PR review：https://gitee.com/openeuler/kernel/pulls/7111

议题四：议题征集中，可直接在此处填写申报
三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/4/19 Kernel SIG 双周例会】
轮值主持：张伽琳 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->张伽琳->廖涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/985175986
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&仉鹏）
近两周(2024.4.3 ~ 4.19)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-196.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-196.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.51.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.72.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.134.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-194.0.0 更新至 5.10.0-196.0.0, 回合补丁数720个
        git log 5.10.0-194.0.0..5.10.0-196.0.0 --oneline | wc -l
        720

        同步linux 5.10.y社区LTS补丁集3个: 5.10.201 - 5.10.203
        https://gitee.com/openeuler/kernel/pulls/6161 Backport 5.10.203 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/5736 Backport 5.10.202 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/5711 Backport 5.10.201 LTS patches from upstream

        修复CVE 77个
        CVE-2024-26787
        https://gitee.com/openeuler/kernel/pulls/6074  Fix CVE-2024-26787
        CVE-2021-47070
        https://gitee.com/openeuler/kernel/pulls/6193  uio_hv_generic: Fix another memory leak in error handling paths
        CVE-2023-52561
        https://gitee.com/openeuler/kernel/pulls/6192  arm64: dts: qcom: sdm845-db845c: Mark cont splash memory region as reserved
        CVE-2024-26812
        https://gitee.com/openeuler/kernel/pulls/6178  CVE-2024-26812
        CVE-2023-52572
        https://gitee.com/openeuler/kernel/pulls/6112  cifs: Fix UAF in cifs_demultiplex_thread()
        CVE-2024-26687
        https://gitee.com/openeuler/kernel/pulls/6124  xen/events: close evtchn after mapping cleanup
        CVE-2024-26810
        https://gitee.com/openeuler/kernel/pulls/6137  vfio/pci: Lock external INTx masking ops
        CVE-2024-26754
        https://gitee.com/openeuler/kernel/pulls/6033  gtp: fix use-after-free and null-ptr-deref in gtp_genl_dump_pdp()
        CVE-2023-52639
        https://gitee.com/openeuler/kernel/pulls/6003  KVM: s390: vsie: fix race during shadow creation
        CVE-2024-26795
        https://gitee.com/openeuler/kernel/pulls/6103  riscv: Sparse-Memory/vmemmap out-of-bounds fix
        CVE-2023-52595
        https://gitee.com/openeuler/kernel/pulls/6116  wifi: rt2x00: restart beacon queue when hardware reset
        CVE-2024-26698
        https://gitee.com/openeuler/kernel/pulls/6047  hv_netvsc: Fix race condition between netvsc_probe and netvsc_remove
        CVE-2024-27437
        https://gitee.com/openeuler/kernel/pulls/6101  vfio/pci: Disable auto-enable of exclusive INTx IRQ
        CVE-2023-52587
        https://gitee.com/openeuler/kernel/pulls/5717 v2  fix CVE-2023-52587
        CVE-2024-26779
        https://gitee.com/openeuler/kernel/pulls/6050  wifi: mac80211: fix race condition on enabling fast-xmit
        CVE-2023-52560
        https://gitee.com/openeuler/kernel/pulls/4923  mm/damon/vaddr-test: fix memory leak in damon_do_test_apply_three_regions()
        CVE-2024-26726
        https://gitee.com/openeuler/kernel/pulls/6016  btrfs: don't drop extent_map for free space inode on write error
        CVE-2024-26685
        https://gitee.com/openeuler/kernel/pulls/6031  nilfs2: fix potential bug in end_buffer_async_write
        CVE-2024-26772
        https://gitee.com/openeuler/kernel/pulls/5847  ext4: avoid allocating blocks from corrupted group in ext4_mb_find_by_goal()
        CVE-2023-52631
        https://gitee.com/openeuler/kernel/pulls/5803  fs/ntfs3: Fix an NULL dereference bug
        CVE-2024-26791
        https://gitee.com/openeuler/kernel/pulls/5977  btrfs: dev-replace: properly validate device names
        CVE-2024-26704
        https://gitee.com/openeuler/kernel/pulls/5921  ext4: fix double-free of blocks due to wrong extents moved_len
        CVE-2024-26689
        https://gitee.com/openeuler/kernel/pulls/6029  ceph: prevent use-after-free in encode_cap_msg()
        CVE-2023-52464
        https://gitee.com/openeuler/kernel/pulls/5973  EDAC/thunderx: Fix possible out-of-bounds string access
        CVE-2023-52640
        https://gitee.com/openeuler/kernel/pulls/6052  fs/ntfs3: fix lbk-CVE-2023-52640
        CVE-2024-26706
        https://gitee.com/openeuler/kernel/pulls/6037  fix-CVE-2024-26706
        CVE-2024-26697
        https://gitee.com/openeuler/kernel/pulls/6040  nilfs2: fix data corruption in dsync block recovery for small block sizes
        CVE-2024-26656
        https://gitee.com/openeuler/kernel/pulls/6017  drm/amdgpu: fix use-after-free bug
        CVE-2024-26740
        https://gitee.com/openeuler/kernel/pulls/6020  net/sched: act_mirred: use the backlog for mirred ingress
        CVE-2024-26759
        https://gitee.com/openeuler/kernel/pulls/5995  mm/swap: fix race when skipping swapcache
        CVE-2024-26669
        https://gitee.com/openeuler/kernel/pulls/6006  fix CVE-2024-26669
        CVE-2024-26778
        https://gitee.com/openeuler/kernel/pulls/5969  fbdev: savage: Error out if pixclock equals zero
        CVE-2024-26763
        https://gitee.com/openeuler/kernel/pulls/5976  dm-crypt: don't modify the data when using authenticated encryption
        CVE-2024-26766
        https://gitee.com/openeuler/kernel/pulls/6018 v2  IB/hfi1: Fix sdma.h tx->num_descs off-by-one error
        CVE-2024-26720
        https://gitee.com/openeuler/kernel/pulls/5979  mm/writeback: fix possible divide-by-zero in wb_dirty_limits(), again
        CVE-2024-26751
        https://gitee.com/openeuler/kernel/pulls/5970  fixup CVE-2024-26751
        CVE-2024-26743
        https://gitee.com/openeuler/kernel/pulls/5950  RDMA/qedr: Fix qedr_create_user_qp error flow
        CVE-2024-26707
        https://gitee.com/openeuler/kernel/pulls/5998  net: hsr: remove WARN_ONCE() in send_hsr_supervision_frame()
        CVE-2024-26782
        https://gitee.com/openeuler/kernel/pulls/5996  mptcp: fix double-free on socket dismantle
        CVE-2024-26735
        https://gitee.com/openeuler/kernel/pulls/5993  ipv6: sr: fix possible use-after-free and null-ptr-deref
        CVE-2024-26684
        https://gitee.com/openeuler/kernel/pulls/5763  CVE-2024-26684 bugfix for OLK-5.10
        CVE-2024-26695
        https://gitee.com/openeuler/kernel/pulls/5901  CVE-2024-26695
        CVE-2024-26771
        https://gitee.com/openeuler/kernel/pulls/5853  dmaengine: ti: edma: Add some null pointer checks to the edma_probe
        CVE-2024-26744
        https://gitee.com/openeuler/kernel/pulls/5930  RDMA/srpt: Support specifying the srpt_service_guid parameter
        CVE-2024-26665
        https://gitee.com/openeuler/kernel/pulls/5758  tunnels: fix out of bounds access when building IPv6 PMTU error
        CVE-2024-26736
        https://gitee.com/openeuler/kernel/pulls/5812  afs: Increase buffer size in afs_update_volume_status()
        CVE-2024-26809
        https://gitee.com/openeuler/kernel/pulls/5852  CVE-2024-26809
        CVE-2021-46926
        https://gitee.com/openeuler/kernel/pulls/5943  CVE-2021-46926
        CVE-2024-26773
        https://gitee.com/openeuler/kernel/pulls/5781  ext4: avoid allocating blocks from corrupted group in ext4_mb_try_best_found()
        CVE-2024-26598
        https://gitee.com/openeuler/kernel/pulls/5884  KVM: arm64: vgic-its: Fix CVE-2024-26598 fix patch issue
        CVE-2024-26777
        https://gitee.com/openeuler/kernel/pulls/5831  fbdev: sis: Error out if pixclock equals zero
        CVE-2023-52479
        https://gitee.com/openeuler/kernel/pulls/5861  ksmbd: fix uaf in smb20_oplock_break_ack
        CVE-2023-52484
        https://gitee.com/openeuler/kernel/pulls/5911  CVE-2023-52484
        CVE-2024-26593
        https://gitee.com/openeuler/kernel/pulls/5895  i2c: i801: Fix block process call transactions
        CVE-2023-52469
        https://gitee.com/openeuler/kernel/pulls/5870  drivers/amd/pm: fix a use-after-free in kv_parse_power_table
        CVE-2024-26788
        https://gitee.com/openeuler/kernel/pulls/5863  CVE-2024-26788
        CVE-2021-47037
        https://gitee.com/openeuler/kernel/pulls/5811  Fixed CVE-2021-47037
        CVE-2024-26696
        https://gitee.com/openeuler/kernel/pulls/5808  nilfs2: fix hang in nilfs_lookup_dirty_data_buffers()
        CVE-2024-26608
        https://gitee.com/openeuler/kernel/pulls/5747  ksmbd: fix global oob in ksmbd_nl_policy
        CVE-2023-52467
        https://gitee.com/openeuler/kernel/pulls/5832  CVE-2023-52467
        CVE-2024-26668
        https://gitee.com/openeuler/kernel/pulls/5795  netfilter: nft_limit: reject configurations that cause integer overflow
        CVE-2024-26680
        https://gitee.com/openeuler/kernel/pulls/5751  net: atlantic: Fix DMA mapping for PTP hwts ring
        CVE-2024-26597
        https://gitee.com/openeuler/kernel/pulls/5785  net: qualcomm: rmnet: fix global oob in rmnet_policy
        CVE-2023-52476
        https://gitee.com/openeuler/kernel/pulls/5789  perf/x86/lbr: Filter vsyscall addresses
        CVE-2024-26589
        https://gitee.com/openeuler/kernel/pulls/5780  bpf: Reject variable offset alu on PTR_TO_FLOW_KEYS
        CVE-2023-52462
        https://gitee.com/openeuler/kernel/pulls/5787  bpf: fix check for attempt to corrupt spilled pointer
        CVE-2023-52633
        https://gitee.com/openeuler/kernel/pulls/5794  um: time-travel: fix time corruption
        CVE-2023-52617
        https://gitee.com/openeuler/kernel/pulls/5773  patches for CVE-2023-52617
        CVE-2023-52608
        https://gitee.com/openeuler/kernel/pulls/5772  firmware: arm_scmi: Check mailbox/SMT channel for consistency
        CVE-2023-52454
        https://gitee.com/openeuler/kernel/pulls/5788 v2  Patches to Fix CVE-2023-52454
        CVE-2024-26654
        https://gitee.com/openeuler/kernel/pulls/5724  ALSA: sh: aica: reorder cleanup operations to avoid UAF bugs
        CVE-2024-26679
        https://gitee.com/openeuler/kernel/pulls/5757  inet: read sk->sk_family once in inet_recv_error()
        CVE-2024-26651
        https://gitee.com/openeuler/kernel/pulls/5698  sr9800: Add check for usbnet_get_endpoints
        CVE-2021-47101
        https://gitee.com/openeuler/kernel/pulls/5728  fix CVE-2021-47101
        CVE-2024-26644
        https://gitee.com/openeuler/kernel/pulls/5642  btrfs: don't abort filesystem when attempting to snapshot deleted subvolume
        CVE-2024-26641
        https://gitee.com/openeuler/kernel/pulls/5530  net: Fix CVE-2024-26641
        CVE-2024-26633
        https://gitee.com/openeuler/kernel/pulls/5532  ip6_tunnel: fix NEXTHDR_FRAGMENT handling in ip6_tnl_parse_tlv_enc_lim()

        ebpf trampoline
        https://gitee.com/openeuler/kernel/pulls/6065 v4  arm64 bpf trampoline for olk-5.10
        
        hisilicon
        https://gitee.com/openeuler/kernel/pulls/6108 udma: optimize latency for non-share-jfr mode
        https://gitee.com/openeuler/kernel/pulls/6011 udma: fix a bug in udma dfx
        https://gitee.com/openeuler/kernel/pulls/5975 udma: fix a bug in QP creation
        https://gitee.com/openeuler/kernel/pulls/5845 [OLK 5.10] bugfixes of vf id of mailbox and port duplex configure
        https://gitee.com/openeuler/kernel/pulls/5770 v2  scsi: hisi_sas: Fixed some issues in the SAS
        https://gitee.com/openeuler/kernel/pulls/5738 [OLK 5.10] net: hns3: fix port vlan filter not disabled problem in dynamic vlan mode
        
        AMD
        https://gitee.com/openeuler/kernel/pulls/5486 [OLK-5.10] support the AMD Zen5 Turin

        BeiZhongWangXin
        https://gitee.com/openeuler/kernel/pulls/5612 【OLK-5.10】Add Chengdu BeiZhongWangXin Technology N5/N6 Series Network Card Driver
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/5745 v2  iommu/arm-smmu-v3: fix using uninitialized or unchecked symbol
        https://gitee.com/openeuler/kernel/pulls/5712 [sync] PR-5672:  arm64/mpam_ctrlmon: Update ctrl group config with rdtgrp's partid
        https://gitee.com/openeuler/kernel/pulls/5189 vhost_vdpa: Fix the error of not executing atomic_dec
        https://gitee.com/openeuler/kernel/pulls/5670  cpufreq: CPPC: Eliminate the impact of cpc_read() latency error
        https://gitee.com/openeuler/kernel/pulls/5506  ext4: dio: Put endio under irq context for overwrite
        https://gitee.com/openeuler/kernel/pulls/5507  ext4: Validate inode pa before using preallocation blocks

近两周(2024.4.4 ~ 4.19)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2404.2.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                        对应update rpm包下载地址:
                        https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-1.0-LTS从 4.19.90-2403.4.0 更新至 4.19.90-2404.2.0, 回合补丁数106个
        git log --no-merges 4.19.90-2403.4.0..4.19.90-2404.2.0 --oneline | wc -l
        106

        修复CVE 67个
        CVE-2023-52637
        CVE-2024-26739
        CVE-2024-26812
        CVE-2021-47201
        CVE-2021-47194
        CVE-2024-26687
        CVE-2024-26804
        CVE-2023-52639
        CVE-2024-27437
        CVE-2024-26686
        CVE-2024-26779
        CVE-2024-26704
        CVE-2024-26810
        CVE-2024-26754
        CVE-2024-26763
        CVE-2024-26697
        CVE-2024-26685
        CVE-2024-26726
        CVE-2024-26791
        CVE-2024-26759
        CVE-2024-26740
        CVE-2023-52635
        CVE-2024-26772
        CVE-2024-26735
        CVE-2024-26743
        CVE-2024-26778
        CVE-2024-26771
        CVE-2024-26744
        CVE-2024-26773
        CVE-2024-26777
        CVE-2024-26696
        CVE-2024-26751
        CVE-2021-47144
        CVE-2024-26668
        CVE-2023-52629
        CVE-2021-47150
        CVE-2024-26654
        CVE-2024-26644
        CVE-2021-47101
        CVE-2024-26633
        CVE-2024-26641
        CVE-2024-26651
        CVE-2021-47170
        CVE-2023-52587
        CVE-2021-47163
        CVE-2021-47167
        CVE-2021-47162
        CVE-2021-47091
        CVE-2021-47145
        CVE-2024-23307
        CVE-2023-52622
        CVE-2021-47131
        CVE-2021-47173
        CVE-2021-47159
        CVE-2021-47153
        CVE-2023-52601
        CVE-2021-47146
        CVE-2024-26645
        CVE-2021-47171
        CVE-2021-47160
        CVE-2021-47169
        CVE-2021-47142
        CVE-2021-47149
        CVE-2021-47180
        CVE-2021-47143
        CVE-2023-52620
        CVE-2024-26642

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/6231  v2  drm/vkms: call drm_atomic_helper_shutdown before drm_dev_put()
        https://gitee.com/openeuler/kernel/pulls/5874  scsi: hisi_sas: Update disk locked timeout to 7 seconds
        https://gitee.com/openeuler/kernel/pulls/5715  net: hns3: updates 2024.04.02
        https://gitee.com/openeuler/kernel/pulls/5702  ext4: Validate inode pa before using preallocation blocks
        https://gitee.com/openeuler/kernel/pulls/5672  arm64/mpam_ctrlmon: Update ctrl group config with rdtgrp's partid
        https://gitee.com/openeuler/kernel/pulls/5645  [sync] PR-5493:  arm64/mpam: Fix repeated enabling in mpam_enable()
        https://gitee.com/openeuler/kernel/pulls/5517  dm: revert partial fix for redundant bio-based IO accounting
        https://gitee.com/openeuler/kernel/pulls/5571  v2  mm/mlock: return EINVAL for illegal user memory range in mlock
        https://gitee.com/openeuler/kernel/pulls/5579  mm: ksm: fix use-after-free kasan report in ksm_might_need_to_copy
        https://gitee.com/openeuler/kernel/pulls/5290  crypto: algif_aead - Only wake up when ctx->more is zero
        https://gitee.com/openeuler/kernel/pulls/5446  keys: safe concurrent user->{session,uid}_keyring access
        https://gitee.com/openeuler/kernel/pulls/5550  pciehp: clear p_slot->work.data after powering off a slot

20240419：
OLK-6.6进展同步：

新分支已合入PR 26个，commit 212个
近两周(4.4-4.19)新合入特性PR：

虚拟化：
                ARM虚拟机对NMI中断的支持 Support NMI in the virtual machine https://gitee.com/openeuler/kernel/pulls/5815

性能提升专项：
                mm: batch mm counter updating in filemap_map_pages() https://gitee.com/openeuler/kernel/pulls/6068
                xarray: inline xas_descend to improve performance https://gitee.com/openeuler/kernel/pulls/6230
                Backport maple_tree: iterator state changes https://gitee.com/openeuler/kernel/pulls/5744
                Make Cluster Scheduling Configurable https://gitee.com/openeuler/kernel/pulls/5854
                locking/osq_lock: Avoid false sharing in optimistic_spin_node https://gitee.com/openeuler/kernel/pulls/6008
                optimize eevdf scheduler https://gitee.com/openeuler/kernel/pulls/5877
                mm: some optimization about hugetlb and thp https://gitee.com/openeuler/kernel/pulls/6201

处理器及板卡支持专项：
                华为：
                RDMA/hns: support roh https://gitee.com/openeuler/kernel/pulls/6069
                RDMA/hns: Support hns roce DCA mode https://gitee.com/openeuler/kernel/pulls/5971
                云芯智联网卡：
                improve 3SNIC 910/920/930 NIC driver https://gitee.com/openeuler/kernel/pulls/6048
                成都北中网芯：
                Add Chengdu BeiZhongWangXin Technology N5/N6 Series Network Card Driver https://gitee.com/openeuler/kernel/pulls/5752

内核编译专项：
                 新一轮config调整中，查漏补缺，已合入PR:
                arm64: enable CONFIG_ARM64_MPAM in openeuler_defconfig https://gitee.com/openeuler/kernel/pulls/6244
                OLK-tdx-guest-configs-6.6 https://gitee.com/openeuler/kernel/pulls/5813

bugfix：
                fix some issues for arm64 machine check safe https://gitee.com/openeuler/kernel/pulls/6105
                KVM: arm64: vgic-its: use vgic_get_irq_kref() before vgic_put_irq() https://gitee.com/openeuler/kernel/pulls/5869

KABI专项： closed
继承特性回合事项： closed

        最新tag 6.6.0-20.0.0
        openEuler-24.03-LTS ISO镜像下载链接：http://121.36.84.172/dailybuild/EBS-openEuler-24.03-LTS/

议题二：内核安全编程规范（倪琛）
内核函数的不安全使用经常会给内核带来潜在威胁，基于对内核api使用模式的统计汇总编写了内核安全编程规范，该规范汇总了近100个常用内核api的不规范使用方式，并给出了git commit实例，帮助提高新人内核代码质量，  安全编程规范已提交pr（https://gitee.com/openeuler/kernel-docs/pulls/20）。

议题三：openEuler-22.03-LTS-SP4需求评审（张伽琳）

调度：
https://gitee.com/openeuler/kernel/issues/I9GZAQ        [openEuler-22.03-LTS-SP4] 鲲鹏920支持自适应NUMA需求 结论：通过

安全：
https://gitee.com/openeuler/kernel/issues/I8TANP        OLK5.10支持地址随机化区域指定 结论：通过
https://gitee.com/openeuler/kernel/issues/I9GXST        【OLK-5.10】openeuler_defconfig开启CONFIG_BPF_LSM 结论：通过

内存：
https://gitee.com/openeuler/kernel/issues/I99G3O        【openEuler-22.03-LTS-SP4】【性能】L0内存管理 结论：通过
https://gitee.com/openeuler/kernel/issues/I9GSSR        [openEuler-22.03-LTS-SP4] alloc_page内存申请维测增强 结论：通过
https://gitee.com/openeuler/kernel/issues/I9GT87        [openEuler-22.03-LTS-SP4] 用户态容器内存支持主动回收、压缩、去重 结论：通过
https://gitee.com/openeuler/kernel/issues/I9GVYW        【openEuler-22.03-LTS-SP4】Add hugetlb MADV_DONTNEED support 结论：通过

x86:
https://gitee.com/openeuler/kernel/issues/I92HAJ        【OLK-5.10】Support Hygon QoS feature 结论：通过
https://gitee.com/openeuler/kernel/issues/I92NKS        【OLK-5.10】Some fixes for Hygon model 4h~6h processors 结论：通过
https://gitee.com/openeuler/kernel/issues/I92NM4        【OLK-5.10】Support Hygon family 18h model 6h L3 PMU 结论：通过
https://gitee.com/openeuler/kernel/issues/I92NMX        【OLK-5.10】Support Hygon family 18h model 5h HD-Audio 结论：通过

虚拟化：
https://gitee.com/openeuler/kernel/issues/I9BPVF        【OLK-5.10】Backporting Dirty ring feature 结论：不影响其他公共模块的情况下，以Virt sig意见为准
https://gitee.com/openeuler/kernel/issues/I9CC0X        【OLK-5.10】add support for arm virtcca vm 结论：不影响其他公共模块的情况下，以Virt sig意见为准
https://gitee.com/openeuler/intel-kernel/issues/I9HH9U    [openEuler-22.03-LTS-SP4] KVM TDP MMU new refactors 结论：代码改动较大，尽快提交PR，找相关领域committer review

驱动:
https://gitee.com/openeuler/kernel/issues/I8TFYM        Yunsilicon XSC RDMA驱动添加自动加载的udev规则
https://gitee.com/openeuler/kernel/issues/I9175D        [OLK-5.10] Driver for Zhaoxin AES and SHA algorithm
https://gitee.com/openeuler/kernel/issues/I977K1        [OLK-5.10]沐创千兆兆网卡驱动适配
https://gitee.com/openeuler/kernel/issues/I9ATOW        [OLK-5.10]沐创万兆网卡vf驱动适配
https://gitee.com/openeuler/kernel/issues/I9ATXX        [OLK-5.10]沐创千兆网卡vf驱动适配
https://gitee.com/openeuler/kernel/issues/I9BXF1        [OLK-5.10] Mont-TSSE驱动适配
https://gitee.com/openeuler/kernel/issues/I9F23X        SPxxx系列RAID卡驱动新增SG_RAW命令返回值
https://gitee.com/openeuler/kernel/issues/I9GYGB        【OLK-5.10】openeuler_defconfig中关闭CONFIG_YUSUR_K2
https://gitee.com/openeuler/kernel/issues/I9H643        【OLK-5.10】增加华为智能网卡RDMA驱动
结论：驱动为新增模块，对核心模块影响较小，通过


三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/4/3 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：曾昭荣->郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：张伽琳
会议链接：https://meeting.huaweicloud.com:36443/#/j/985365971
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&郑增凯）
近两周(2024.3.25 ~ 4.3)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-194.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-194.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.49.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.70.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.132.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-192.0.0 更新至 5.10.0-194.0.0, 回合补丁数326个
        git log 5.10.0-192.0.0..5.10.0-194.0.0 --oneline | wc -l
        326

        同步linux 5.10.y社区LTS补丁集2个: 5.10.199 - 5.10.200
        https://gitee.com/openeuler/kernel/pulls/5684 Backport 5.10.200 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/5499 Backport 5.10.199 LTS patches from upstream

        修复CVE 34个
        CVE-2023-52622
        https://gitee.com/openeuler/kernel/pulls/5580  CVE-2023-52622
        CVE-2024-26645
        https://gitee.com/openeuler/kernel/pulls/5566  tracing: Ensure visibility when inserting an element into tracing_map
        CVE-2023-52601
        https://gitee.com/openeuler/kernel/pulls/5473  jfs: fix array-index-out-of-bounds in dbAdjTree
        CVE-2023-52618
        https://gitee.com/openeuler/kernel/pulls/5431  block/rnbd-srv: Check for unlikely string overflow
        CVE-2024-26642
        https://gitee.com/openeuler/kernel/pulls/5537  netfilter: nf_tables: disallow anonymous set with timeout flag
        CVE-2024-26643
        https://gitee.com/openeuler/kernel/pulls/5527  netfilter: nf_tables: mark set as dead when unbinding anonymous set with timeout
        CVE-2024-23307
        https://gitee.com/openeuler/kernel/pulls/5521  md/raid5: fix atomicity violation in raid5_cache_count
        CVE-2023-52489
        https://gitee.com/openeuler/kernel/pulls/5494  mm/sparsemem: fix race in accessing memory_section->usage
        CVE-2023-52620
        https://gitee.com/openeuler/kernel/pulls/5516  netfilter: nf_tables: disallow timeout for anonymous sets
        CVE-2023-52610
        https://gitee.com/openeuler/kernel/pulls/5441  net/sched: act_ct: fix skb leak and crash on ooo frags
        CVE-2024-24855
        https://gitee.com/openeuler/kernel/pulls/5519  scsi: lpfc: Fix a possible data race in lpfc_unregister_fcf_rescan()
        CVE-2021-47094
        https://gitee.com/openeuler/kernel/pulls/5445  KVM: x86/mmu: Don't advance iterator after restart due to yielding
        CVE-2023-52493
        https://gitee.com/openeuler/kernel/pulls/5510  bus: mhi: host: Drop chan lock before queuing buffers
        CVE-2023-52594
        https://gitee.com/openeuler/kernel/pulls/5466  wifi: ath9k: Fix potential array-index-out-of-bounds read in ath9k_htc_txstatus()
        CVE-2024-26640
        https://gitee.com/openeuler/kernel/pulls/5491  CVE-2024-26640
        CVE-2024-26635
        https://gitee.com/openeuler/kernel/pulls/5495  llc: Drop support for ETH_P_TR_802_2.
        CVE-2024-26636
        https://gitee.com/openeuler/kernel/pulls/5496  llc: make llc_ui_sendmsg() more robust against bonding changes
        CVE-2024-26625
        https://gitee.com/openeuler/kernel/pulls/5266  llc: call sock_orphan() at release time
        CVE-2023-52619
        https://gitee.com/openeuler/kernel/pulls/5500  pstore/ram: Fix crash when setting number of cpus to an odd number
        CVE-2023-52616
        https://gitee.com/openeuler/kernel/pulls/5460 v2  crypto: lib/mpi - Fix unexpected pointer access in mpi_ec_init
        CVE-2023-52445
        https://gitee.com/openeuler/kernel/pulls/5368  media: pvrusb2: fix use after free on context disconnection
        CVE-2023-52514
        https://gitee.com/openeuler/kernel/pulls/5075  x86/reboot: VMCLEAR active VMCSes before emergency reboot
        CVE-2023-52530
        https://gitee.com/openeuler/kernel/pulls/5093  wifi: mac80211: fix potential key use-after-free
        CVE-2023-52603
        https://gitee.com/openeuler/kernel/pulls/5327  UBSAN: array-index-out-of-bounds in dtSplitRoot
        CVE-2023-52602
        https://gitee.com/openeuler/kernel/pulls/5322  jfs: fix slab-out-of-bounds Read in dtSearch
        CVE-2023-52604
        https://gitee.com/openeuler/kernel/pulls/5308  FS:JFS:UBSAN:array-index-out-of-bounds in dbAdjTree
        CVE-2023-52488
        https://gitee.com/openeuler/kernel/pulls/5286  serial: sc16is7xx: convert from _raw_ to _noinc_ regmap functions for FIFO
        CVE-2023-52600 CVE-2023-52599
        https://gitee.com/openeuler/kernel/pulls/5232  jfs: fix cve issue
        CVE-2023-52598
        https://gitee.com/openeuler/kernel/pulls/5348  s390/ptrace: handle setting of fpc register correctly
        CVE-2023-52597
        https://gitee.com/openeuler/kernel/pulls/5317  KVM: s390: fix setting of fpc register
        CVE-2024-26627​
        https://gitee.com/openeuler/kernel/pulls/5259  CVE-2024-26627​ 
        CVE-2023-52609
        https://gitee.com/openeuler/kernel/pulls/5339  binder: fix race between mmput() and do_exit()
        CVE-2024-26622
        https://gitee.com/openeuler/kernel/pulls/5253  tomoyo: fix UAF write bug in tomoyo_write_control()

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/5617 v4  Fix I/O high when memory almost met memcg limit
        https://gitee.com/openeuler/kernel/pulls/5518  dm: revert partial fix for redundant bio-based IO accounting
        https://gitee.com/openeuler/kernel/pulls/5493  arm64/mpam: Fix repeated enabling in mpam_enable()
        https://gitee.com/openeuler/kernel/pulls/5606  mm/mlock: return EINVAL for illegal user memory range in mlock
        https://gitee.com/openeuler/kernel/pulls/5553  mm: ksm: fix use-after-free kasan report in ksm_might_need_to_copy
        https://gitee.com/openeuler/kernel/pulls/5269  printk: avoid deadlock in panic
        https://gitee.com/openeuler/kernel/pulls/5316 v2  iomap: add support to track dirty state of sub pages
        https://gitee.com/openeuler/kernel/pulls/5385 v3  enable arm64_pbha by default

2024.3.22 ~ 4.3进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2403.4.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/
        openEuler-1.0-LTS从 4.19.90-2403.3.0 更新至 4.19.90-2403.4.0, 回合补丁数39个
        git log --no-merges 4.19.90-2403.3.0..4.19.90-2403.4.0 --oneline | wc -l
        39
        
        修复CVE 24个
        CVE-2021-47161
        https://gitee.com/openeuler/kernel/pulls/5539  spi: spi-fsl-dspi: Fix a resource leak in an error handling path
        CVE-2024-24855
        https://gitee.com/openeuler/kernel/pulls/5520  scsi: lpfc: Fix a possible data race in lpfc_unregister_fcf_rescan()
        CVE-2021-47110
        https://gitee.com/openeuler/kernel/pulls/5514  CVE-2021-47110
        CVE-2024-26635
        https://gitee.com/openeuler/kernel/pulls/5497  llc: Drop support for ETH_P_TR_802_2.
        CVE-2024-26636
        https://gitee.com/openeuler/kernel/pulls/5498  llc: make llc_ui_sendmsg() more robust against bonding changes
        CVE-2024-26640
        https://gitee.com/openeuler/kernel/pulls/5490  tcp: add sanity checks to rx zerocopy
        CVE-2023-52619
        https://gitee.com/openeuler/kernel/pulls/5502  pstore/ram: Fix crash when setting number of cpus to an odd number
        CVE-2021-47112
        https://gitee.com/openeuler/kernel/pulls/5477  Fixed CVE-2021-47112
        CVE-2023-52600
        https://gitee.com/openeuler/kernel/pulls/5479  jfs: fix cve-2023-52600
        CVE-2023-52599
        https://gitee.com/openeuler/kernel/pulls/5478  jfs: fix array-index-out-of-bounds in diNewExt
        CVE-2023-52594
        https://gitee.com/openeuler/kernel/pulls/5465  wifi: ath9k: Fix potential array-index-out-of-bounds read in ath9k_htc_txstatus()
        CVE-2021-47113
        https://gitee.com/openeuler/kernel/pulls/5361  btrfs: abort in rename_exchange if we fail to insert the second ref
        CVE-2024-26622
        https://gitee.com/openeuler/kernel/pulls/5254  tomoyo: fix UAF write bug in tomoyo_write_control()
        CVE-2023-52603
        https://gitee.com/openeuler/kernel/pulls/5321  UBSAN: array-index-out-of-bounds in dtSplitRoot
        CVE-2021-47114
        https://gitee.com/openeuler/kernel/pulls/5455  CVE-2021-47114
        CVE-2023-52602
        https://gitee.com/openeuler/kernel/pulls/5320  jfs: fix slab-out-of-bounds Read in dtSearch
        CVE-2023-52615
        https://gitee.com/openeuler/kernel/pulls/5374  hwrng: core - Fix page fault dead lock on mmap-ed hwrng
        CVE-2023-52597
        https://gitee.com/openeuler/kernel/pulls/5418  [sync] PR-5317:  KVM: s390: fix setting of fpc register
        CVE-2024-26615
        https://gitee.com/openeuler/kernel/pulls/5272  net/smc: fix illegal rmb_desc access in SMC-D connection dump
        CVE-2021-47086
        https://gitee.com/openeuler/kernel/pulls/5274  phonet/pep: refuse to enable an unbound pipe
        CVE-2021-47122
        https://gitee.com/openeuler/kernel/pulls/5359  CVE-2021-47121 and CVE-2021-47122
        CVE-2021-47121
        https://gitee.com/openeuler/kernel/pulls/5359  CVE-2021-47121 and CVE-2021-47122
        CVE-2023-52595
        https://gitee.com/openeuler/kernel/pulls/5358  v5  CVE-2023-52595
        CVE-2023-52609
        https://gitee.com/openeuler/kernel/pulls/5336  binder: fix race between mmput() and do_exit()
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/5542  round lts patches
        https://gitee.com/openeuler/kernel/pulls/5485  nfsd: fix use-after-free due to delegation race
        https://gitee.com/openeuler/kernel/pulls/5281  printk: avoid deadlock in panic
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20240403：
OLK-6.6进展同步：
继承特性回合事项：
新分支已合入PR 469个，补丁 7267个
         近两周(3.25-4.3)新合入特性PR：
         内存:
            Backport Introduce __mt_dup() to improve the performance of fork() https://gitee.com/openeuler/kernel/pulls/5492
            mm: backport rmap interface overhaul https://gitee.com/openeuler/kernel/pulls/5613
            Mitigate a vmap lock contention https://gitee.com/openeuler/kernel/pulls/5629
            userfaultfd: early return in dup_userfaultfd() https://gitee.com/openeuler/kernel/pulls/5641
            mm: backport fork/unmap/zap optimize https://gitee.com/openeuler/kernel/pulls/5656
            Introduce dynamic pool feature part 2 https://gitee.com/openeuler/kernel/pulls/5662
            arm64: transparent contiguous PTEs for user mappings https://gitee.com/openeuler/kernel/pulls/5663
            Optimize compaction https://gitee.com/openeuler/kernel/pulls/5688
KABI专项：  closed
处理器及板卡支持专项：
         新合入PR：
          intel: Intel: Backport QuickAssist Technology(QAT) in-tree driver https://gitee.com/openeuler/kernel/pulls/5526
          龙芯：loongson-exiointc timer simulation and cpucfg simulation https://gitee.com/openeuler/kernel/pulls/5547
                add steal time software breakpoint pv ipi support for loongarch kvm https://gitee.com/openeuler/kernel/pulls/5655
          云芯智联： SCSI: SSSRAID: Support 3SNIC 3S5XX serial RAID/HBA controllers https://gitee.com/openeuler/kernel/pulls/5513
          华为：SCSI: hisi_raid: support SPxxx serial RAID/HBA controllers https://gitee.com/openeuler/kernel/pulls/5578
               roh: backport roh driver feature support https://gitee.com/openeuler/kernel/pulls/5561
               Adding Huawei BMA driver https://gitee.com/openeuler/kernel/pulls/5609
内核编译专项：
          新一轮config调整中，查漏补缺，已合入PR:
          enable openeuler_defconfig HISI_ACC_VFIO_PCI=m https://gitee.com/openeuler/kernel/pulls/5523
          arch/powerpc: open BTF relevant configs in openuler defconfig https://gitee.com/openeuler/kernel/pulls/5529
          Open CONFIG_LZ4_COMPRESS option for x86_64 architecture https://gitee.com/openeuler/kernel/pulls/5582
          arm64: Enable hardware NMI for perf events NMI https://gitee.com/openeuler/kernel/pulls/5653
          configs: arm64: Enable CONFIG_ACPI_AGDI and CONFIG_ACPI_FFH https://gitee.com/openeuler/kernel/pulls/5667
          disable CONFIG_CMDLINE_FROM_BOOTLOADER CONFIG_INITRAMFS_PRESERVE_MTIME in 6.6 https://gitee.com/openeuler/kernel/pulls/5669
          openeuler_defconfig: Disable CONFIG_PREEMPT_DYNAMIC for x86 https://gitee.com/openeuler/kernel/pulls/5703
     
   最新tag 6.6.0-16.0.0 
   openEuler-24.03-LTS ISO镜像下载链接：http://121.36.84.172/dailybuild/EBS-openEuler-24.03-LTS/


议题二：Xu Yan、Yuan Xia、Liu Yonglong申请成为kernel contributors（飞腾 帅家坤）
https://gitee.com/openeuler/community/pulls/5440

会议结论：同意上述三人成为 contributors：
1)  由于加入到 contributors 名单中, 可以将 lgtm 转为 Review 签名，添加到 git log 中，有助于提升社区参与感。
2）contributors Review 信息供正式 Committer 参考，不具有实际的合入权限和决策权限。

参考：《社区角色说明》https://www.openeuler.org/zh/sig/role-description/
议题三：Mont-TSSE驱动适配22.03-SP4 5.10内核测试报告评审（澜起 蔡仲斐）

议题四：22.03-LTS-SP4需求收集（张伽琳）
SP4 release plan:
https://gitee.com/openeuler/release-management/blob/master/openEuler-22.03-LTS-SP4/release-plan.md

openEuler-22.03-LTS-SP4 kernel 需求收集截止日期： 2024 年 4 月 19 日星期五

openEuler-22.03-LTS-SP4 kernel 需求合入截止日期： 2024 年 5 月 29 日星期三

目前是需求收集阶段，如果您有合入 openEuler-22.03-LTS-SP4 kernel 的需求，请您尽快向 openEuler 社区 kernel sig 提交需求 issue

需求 issue 提交链接： https://gitee.com/openeuler/kernel/issues ， issue 类型选择需求， issue 标题以 [openEuler-22.03-LTS-SP4] 开头

我们将在 2024 年 4 月 19 日 的kernel sig 双周例会上集中讨论，采纳的需求将纳入里程碑规划


三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/3/22 Kernel SIG 双周例会】
轮值主持：郑增凯 【轮值主持顺序：曾昭荣->郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：桑力鹏
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/989029425
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&郑增凯）

SP4 release plan:
https://gitee.com/openeuler/release-management/blob/master/openEuler-22.03-LTS-SP4/release-plan.md

近两周(2024.3.11 ~ 3.22)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-192.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-192.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.47.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.68.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.130.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-190.0.0 更新至 5.10.0-192.0.0, 回合补丁数770个
        git log 5.10.0-190.0.0..5.10.0-192.0.0 --oneline | wc -l
        770

        同步linux 5.10.y社区LTS补丁集4个: 5.10.195 - 5.10.198
        https://gitee.com/openeuler/kernel/pulls/5188 Backport 5.10.198 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/5031 Backport 5.10.196 -5.10.197 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/4905 Backport 5.10.195 LTS patches from upstream

        修复CVE 32个
        CVE-2023-52447
        https://gitee.com/openeuler/kernel/pulls/5342  CVE-2023-52447
        CVE-2023-52452
        https://gitee.com/openeuler/kernel/pulls/5364 v2  CVE-2023-52452
        CVE-2023-52494
        https://gitee.com/openeuler/kernel/pulls/5313  bus: mhi: host: Add alignment check for event ring read pointer
        CVE-2023-52593
        https://gitee.com/openeuler/kernel/pulls/5355  CVE-2023-52593
        CVE-2023-52586
        https://gitee.com/openeuler/kernel/pulls/5307  drm/msm/dpu: Add mutex lock in control vblank irq
        CVE-2023-52606
        https://gitee.com/openeuler/kernel/pulls/5240  powerpc/lib: Validate size for vector operations
        CVE-2024-26624
        https://gitee.com/openeuler/kernel/pulls/5231  af_unix: fix lockdep positive in sk_diag_dump_icons()
        CVE-2023-52607
        https://gitee.com/openeuler/kernel/pulls/5222  powerpc/mm: Fix null-pointer dereference in pgtable_cache_add
        CVE-2023-52583
        https://gitee.com/openeuler/kernel/pulls/5245  ceph: fix deadlock or deadcode of misusing dget()
        CVE-2023-52492
        https://gitee.com/openeuler/kernel/pulls/5195  dmaengine: fix NULL pointer in channel unregistration function
        CVE-2023-52502
        https://gitee.com/openeuler/kernel/pulls/5171  net: nfc: fix races in nfc_llcp_sock_get() and nfc_llcp_sock_get_sn()
        CVE-2023-52486
        https://gitee.com/openeuler/kernel/pulls/5197  drm: Don't unref the same fb many times by mistake due to deadlock handling
        CVE-2023-52524
        https://gitee.com/openeuler/kernel/pulls/5178  net: nfc: llcp: Add lock when modifying device list
        CVE-2023-52507
        https://gitee.com/openeuler/kernel/pulls/5164  nfc: nci: assert requested protocol is valid
        CVE-2023-52515
        https://gitee.com/openeuler/kernel/pulls/5156  RDMA/srp: Do not call scsi_done() from srp_abort()
        CVE-2023-52527
        https://gitee.com/openeuler/kernel/pulls/5117  fix CVE-2023-52527\
        CVE-2023-52578
        https://gitee.com/openeuler/kernel/pulls/5113  fix CVE-2023-52578
        CVE-2023-52577
        https://gitee.com/openeuler/kernel/pulls/5063  dccp: fix dccp_v4_err()/dccp_v6_err() again
        CVE-2023-52574
        https://gitee.com/openeuler/kernel/pulls/5062  team: fix null-ptr-deref when team device type is changed
        CVE-2023-52525
        https://gitee.com/openeuler/kernel/pulls/5096  wifi: mwifiex: Fix oob check condition in mwifiex_process_rx_packet
        CVE-2021-47076
        https://gitee.com/openeuler/kernel/pulls/5078  RDMA/rxe: Return CQE error if invalid lkey was supplied
        CVE-2024-23851
        https://gitee.com/openeuler/kernel/pulls/5051  dm: limit the number of targets and parameter size area
        CVE-2023-52500
        https://gitee.com/openeuler/kernel/pulls/4933  scsi: pm80xx: Avoid leaking tags when processing OPC_INB_SET_CONTROLLER_CONFIG command
        CVE-2023-52573
        https://gitee.com/openeuler/kernel/pulls/5064  net: rds: Fix possible NULL-pointer dereference
        CVE-2023-52522
        https://gitee.com/openeuler/kernel/pulls/5058  net: fix possible store tearing in neigh_periodic_work()
        CVE-2021-47014
        https://gitee.com/openeuler/kernel/pulls/5032  net/sched: act_ct: fix wild memory access when clearing fragments
        CVE-2023-52566
        https://gitee.com/openeuler/kernel/pulls/5004  nilfs2: fix potential use after free in nilfs_gccache_submit_read_data()
        CVE-2023-52528
        https://gitee.com/openeuler/kernel/pulls/4987  net: usb: smsc75xx: Fix uninit-value access in __smsc75xx_read_reg
        CVE-2023-52568
        https://gitee.com/openeuler/kernel/pulls/4991  CVE-2023-52568
        CVE-2023-52510
        https://gitee.com/openeuler/kernel/pulls/4988  ieee802154: ca8210: Fix a potential UAF in ca8210_probe
        CVE-2021-47028
        https://gitee.com/openeuler/kernel/pulls/4979  CVE-2021-47028
        CVE-2024-23850
        https://gitee.com/openeuler/kernel/pulls/4925 v2  btrfs: do not ASSERT() if the newly created subvolume already got read

        Intel
        https://gitee.com/openeuler/kernel/pulls/4648 [OLK-5.10] Intel: backport TPMI RAPL driver for GNR/SRF
        https://gitee.com/openeuler/kernel/pulls/4842 Intel-sig: intel_idle: add Sierra Forest SoC support on 5.10
        https://gitee.com/openeuler/kernel/pulls/4261 [22.03-LTS-SP3] Fix crash on platfoms using legacy KVM MMU Notifier APIs

        AMD
        https://gitee.com/openeuler/kernel/pulls/5038 [OLK-5.10] Do not serialize MSR accesses on AMD

        yunsilicon
        https://gitee.com/openeuler/kernel/pulls/4632 [OLK-5.10] drivers: update yunsilicon drivers to version 1.1.0.375

        Mucse
        https://gitee.com/openeuler/kernel/pulls/3297 [OLK-5.10] Add drivers support for Mucse Network Adapter(N10/N400)

        Yusur
        https://gitee.com/openeuler/kernel/pulls/3308 [OLK-5.10] initial support for KPU FLEXFLOW-2100P driver from Yusur Technology

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/5242  Revert two stable patches to keep binary compatible
        https://gitee.com/openeuler/kernel/pulls/5229  iommu/arm-smmu-v3: Disable ECMDQ before reset
        https://gitee.com/openeuler/kernel/pulls/5152  arm64/mpam: Remove warning about no msc corresponding to the online cpu
        https://gitee.com/openeuler/kernel/pulls/5145  arm64/mpam: Expand the monitor number of the resctrl root
        https://gitee.com/openeuler/kernel/pulls/5144  arm64/mpam: Fix use-after-free when deleting resource groups
        https://gitee.com/openeuler/kernel/pulls/4994  mpam/mpam_ctrlmon: update monitor config with its parent's ctrl_val
        https://gitee.com/openeuler/kernel/pulls/5044  bugfix for pbha
        https://gitee.com/openeuler/kernel/pulls/4966 [sync] PR-4934:  arm64: head.S: always initialize PSTATE
        https://gitee.com/openeuler/kernel/pulls/4968  sched: migtate user interface from smart grid to sched bpf
        https://gitee.com/openeuler/kernel/pulls/5033 v3  Remove WQ_FLAG_BOOKMARK flag
        https://gitee.com/openeuler/kernel/pulls/4339 pmem: compile pmem legacy device while libnvdimm as a module

2024.3.11 ~ 3.22进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2403.3.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/

        openEuler-1.0-LTS从 4.19.90-2403.1.0 更新至 4.19.90-2403.3.0, 回合补丁数100个
        git log --no-merges 4.19.90-2402.5.0..4.19.90-2403.1.0 --oneline | wc -l
        100

        修复CVE 50个：
        CVE-2023-52598
        CVE-2023-52586
        CVE-2023-52604
        CVE-2024-26625
        CVE-2023-52583
        CVE-2023-52606
        CVE-2023-52607
        CVE-2022-48630
        CVE-2022-48629
        CVE-2023-52486
        CVE-2023-52524
        CVE-2023-52502
        CVE-2023-52507
        CVE-2023-52515
        CVE-2021-46952
        CVE-2021-46926
        CVE-2023-52578
        CVE-2023-52464
        CVE-2023-52478
        CVE-2023-52530
        CVE-2021-47063
        CVE-2021-47071
        CVE-2021-47076
        CVE-2021-47074
        CVE-2021-47078
        CVE-2023-52522
        CVE-2021-46933
        CVE-2021-46998
        CVE-2021-46984
        CVE-2023-52504
        CVE-2021-47020
        CVE-2021-47015
        CVE-2022-48627
        CVE-2021-47013
        CVE-2020-36783
        CVE-2023-52528
        CVE-2023-52566
        CVE-2021-46935
        CVE-2021-46990
        CVE-2020-36778
        CVE-2021-47077
        CVE-2021-47024
        CVE-2021-46924
        CVE-2023-52510
        CVE-2023-52476
        CVE-2021-47056
        CVE-2023-52500
        CVE-2021-46906
        CVE-2021-47040
        CVE-2023-52458

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/5306  FS:JFS:UBSAN:array-index-out-of-bounds in dbAdjTree
        https://gitee.com/openeuler/kernel/pulls/5347  s390/ptrace: handle setting of fpc register correctly
        https://gitee.com/openeuler/kernel/pulls/5309  drm/msm/dpu: Add mutex lock in control vblank irq
        https://gitee.com/openeuler/kernel/pulls/5267  llc: call sock_orphan() at release time
        https://gitee.com/openeuler/kernel/pulls/5241  powerpc/lib: Validate size for vector operations
        https://gitee.com/openeuler/kernel/pulls/5246  ceph: fix deadlock or deadcode of misusing dget()
        https://gitee.com/openeuler/kernel/pulls/5268  crypto: algif_aead - fix uninitialized ctx->init
        https://gitee.com/openeuler/kernel/pulls/5220  powerpc/mm: Fix null-pointer dereference in pgtable_cache_add
        https://gitee.com/openeuler/kernel/pulls/5196  drm: Don't unref the same fb many times by mistake due to deadlock handling
        https://gitee.com/openeuler/kernel/pulls/5210  v2  Fix CVE-2022-48629 and CVE-2022-48630
        https://gitee.com/openeuler/kernel/pulls/5175  arm64/mpam: Fix use-after-free when deleting resource groups
        https://gitee.com/openeuler/kernel/pulls/5163  nfc: nci: assert requested protocol is valid
        https://gitee.com/openeuler/kernel/pulls/5172  CVE-2023-52502 for openEuler-1.0-LTS
        https://gitee.com/openeuler/kernel/pulls/5177  net: nfc: llcp: Add lock when modifying device list
        https://gitee.com/openeuler/kernel/pulls/5157  RDMA/srp: Do not call scsi_done() from srp_abort()
        https://gitee.com/openeuler/kernel/pulls/5142  arm64/mpam: Expand the monitor number of the resctrl root
        https://gitee.com/openeuler/kernel/pulls/5133  CVE-2021-46926
        https://gitee.com/openeuler/kernel/pulls/5136  NFS: fs_context: validate UDP retrans to prevent shift out-of-bounds
        https://gitee.com/openeuler/kernel/pulls/5052  v3  Remove WQ_FLAG_BOOKMARK flag
        https://gitee.com/openeuler/kernel/pulls/5140  linux-4.19.y inclusion(4.19.305..4.19.307) part3
        https://gitee.com/openeuler/kernel/pulls/5114  fix CVE-2023-52578
        https://gitee.com/openeuler/kernel/pulls/5119  crypto: scomp - fix req->dst buffer overflow
        https://gitee.com/openeuler/kernel/pulls/5101  EDAC/thunderx: Fix possible out-of-bounds string access
        https://gitee.com/openeuler/kernel/pulls/5094  HID: logitech-hidpp: Fix kernel crash on receiver USB disconnect
        https://gitee.com/openeuler/kernel/pulls/5092  wifi: mac80211: fix potential key use-after-free
        https://gitee.com/openeuler/kernel/pulls/5095  linux-4.19.y inclusion(4.19.305..4.19.307) part 2
        https://gitee.com/openeuler/kernel/pulls/5090  drm: bridge/panel: Cleanup connector on bridge detach
        https://gitee.com/openeuler/kernel/pulls/5088  uio_hv_generic: Fix a memory leak in error handling paths
        https://gitee.com/openeuler/kernel/pulls/4952  scsi: qedf: Add pointer checks in qedf_update_link_speed()
        https://gitee.com/openeuler/kernel/pulls/5076  v3  CVE-2021-47074
        https://gitee.com/openeuler/kernel/pulls/5073  RDMA/rxe: Clear all QP fields if creation failed
        https://gitee.com/openeuler/kernel/pulls/5077  RDMA/rxe: Return CQE error if invalid lkey was supplied
        https://gitee.com/openeuler/kernel/pulls/5055  linux-4.19.y inclusion(4.19.305..4.19.307) part 1
        https://gitee.com/openeuler/kernel/pulls/5060  net: fix possible store tearing in neigh_periodic_work()
        https://gitee.com/openeuler/kernel/pulls/5046  usb: gadget: f_fs: Clear ffs_eventfd in ffs_data_clear.
        https://gitee.com/openeuler/kernel/pulls/4929  scsi: pm80xx: Avoid leaking tags when processing OPC_INB_SET_CONTROLLER_CONFIG command
        https://gitee.com/openeuler/kernel/pulls/4752  block: add check that partition length needs to be aligned with block size
        https://gitee.com/openeuler/kernel/pulls/4735  blk-mq: fix IO hang from sbitmap wakeup race
        https://gitee.com/openeuler/kernel/pulls/3864  nvme: sanitize metadata bounce buffer for reads
        https://gitee.com/openeuler/kernel/pulls/4946  NFC: st21nfca: Fix memory leak in device probe and remove
        https://gitee.com/openeuler/kernel/pulls/4999  CVE-2021-46984
        https://gitee.com/openeuler/kernel/pulls/4938  crypto: qat - ADF_STATUS_PF_RUNNING should be set after adf_dev_init
        https://gitee.com/openeuler/kernel/pulls/4990  vt: fix memory overlapping when deleting chars in the buffer
        https://gitee.com/openeuler/kernel/pulls/4978  nilfs2: fix potential use after free in nilfs_gccache_submit_read_data()
        https://gitee.com/openeuler/kernel/pulls/5018  ethernet:enic: Fix a use after free bug in enic_hard_start_xmit
        https://gitee.com/openeuler/kernel/pulls/4992  bnxt_en: Fix RX consumer index logic in the error path.
        https://gitee.com/openeuler/kernel/pulls/4997  Fixed CVE-2023-52504
        https://gitee.com/openeuler/kernel/pulls/4982  i2c: img-scb: fix reference leak when pm_runtime_get_sync fails
        https://gitee.com/openeuler/kernel/pulls/4983  net:emac/emac-mac: Fix a use after free in emac_mac_tx_buf_send
        https://gitee.com/openeuler/kernel/pulls/4995  mpam/mpam_ctrlmon: update monitor config with its parent's ctrl_val
        https://gitee.com/openeuler/kernel/pulls/4974  arm64/mpam: set default feedback of last_cmd_status interface as null string
        https://gitee.com/openeuler/kernel/pulls/4975  arm64/mpam: support resctrl fs to show mounting option
        https://gitee.com/openeuler/kernel/pulls/4973  arm64/mpam: Skip updates of unrelated ctrl type
        https://gitee.com/openeuler/kernel/pulls/4996  soundwire: stream: fix memory leak in stream config error path
        https://gitee.com/openeuler/kernel/pulls/4817  v2  io_uring: fix overflows checks in provide buffers
        https://gitee.com/openeuler/kernel/pulls/4969  CVE-2021-46990
        https://gitee.com/openeuler/kernel/pulls/4945  ieee802154: ca8210: Fix a potential UAF in ca8210_probe
        https://gitee.com/openeuler/kernel/pulls/4944  perf/x86/lbr: Filter vsyscall addresses
        https://gitee.com/openeuler/kernel/pulls/4967  i2c: xiic: fix reference leak when pm_runtime_get_sync fails
        https://gitee.com/openeuler/kernel/pulls/4970  binder: fix async_free_space accounting for empty parcels
        https://gitee.com/openeuler/kernel/pulls/4919  v2  HID: usbhid: fix info leak in hid_submit_ctrl
        https://gitee.com/openeuler/kernel/pulls/4980  net: usb: smsc75xx: Fix uninit-value access in __smsc75xx_read_reg
        https://gitee.com/openeuler/kernel/pulls/4949  CVE-2021-47024
        
20240322：
OLK-6.6进展同步：
继承特性回合事项：
新分支已合入PR 423个，补丁 6851个
         近两周(3.8-3.22)新合入特性PR：
         内存:
            mTHP anon support https://gitee.com/openeuler/kernel/pulls/5199
            etmem swapcache recalim feature https://gitee.com/openeuler/kernel/pulls/5047
         虚拟化：
            Introduce multiple LPI translation caches https://gitee.com/openeuler/kernel/pulls/5174
         安全：
            ima: Support modsig verify using trusted keys
         架构 & 驱动：
            RDMA/hns: Support hns RoCE Bonding https://gitee.com/openeuler/kernel/pulls/5180
            crypto: hisilicon support no-sva feature https://gitee.com/openeuler/kernel/pulls/5239
         6.6.8-6.6.22 LTS: 
            https://gitee.com/openeuler/kernel/pulls/5318
            https://gitee.com/openeuler/kernel/pulls/5369
        CVE:
            CVE-2023-52607
            CVE-2023-52583
            CVE-2024-26630
            CVE-2024-26616
            CVE-2023-52588
            CVE-2024-26627
            CVE-2023-52593
            CVE-2023-52606
            CVE-2024-26620
            CVE-2024-26632
            CVE-2024-26638
        编译问题:
            arm64: Delete macro in the scsnp feature https://gitee.com/openeuler/kernel/pulls/5451
KABI专项：
         1.KABI白名单已输出；
           https://gitee.com/src-openeuler/kernel/blob/master/Module.kabi_aarch64
           https://gitee.com/src-openeuler/kernel/blob/master/Module.kabi_x86_64
         2.已合入58个KABI预留PR， 预留工作已完成
处理器及板卡支持专项：
         新合入PR：
          intel: intel-sig: configs: enable PMT related configs for OLK6.6 https://gitee.com/openeuler/kernel/pulls/5150
                 intel-sig: configs: enable TPMI related configs for OLK6.6 https://gitee.com/openeuler/kernel/pulls/5151
          海光： Support PSPCCP/NTBCCP identification for Hygon 2th and 3th CPU https://gitee.com/openeuler/kernel/pulls/5212
          龙芯： modpost: Optimize symbol search from linear to binary search https://gitee.com/openeuler/kernel/pulls/5134
          沐创： Add drivers support for Mucse Network Adapter rnpm (N10/N400) https://gitee.com/openeuler/kernel/pulls/4782
                Add support for Mucse Network Adapter(N500/N210) https://gitee.com/openeuler/kernel/pulls/5037
内核编译专项：
          1.已合入config相关PR 34个，已完成
          2.最新tag 6.6.0-13.0.0

议题二:  将dirty-ring  backport至5.10内核(温志伟&卫少坤)

议题三：推选仉鹏为kernel sig committer（仉鹏）
主要贡献PR：
Backport 6.6.8~6.6.22 LTS 补丁
https://gitee.com/openeuler/kernel/pulls/5369
https://gitee.com/openeuler/kernel/pulls/5318
Backport numa balancing相关的folio conversation
https://gitee.com/openeuler/kernel/pulls/3018
Backport mlock支持large folio
https://gitee.com/openeuler/kernel/pulls/4199
支持userswap特性
https://gitee.com/openeuler/kernel/pulls/3352
Backport memcg维测特性：
https://gitee.com/openeuler/kernel/pulls/4154
日常CVE与bugfix

议题四：EEVDF算法分享讨论 （李华）
遗留问题：确认eevdf的latency_nice接口还没有开放，后续跟进社区回合

三、本期遗留问题

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/3/8 Kernel SIG 双周例会】
轮值主持：廖涛 【轮值主持顺序：曾昭荣->郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：郑增凯
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/989606341
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&郑增凯）

20240308：
OLK-6.6进展同步： --- 郑增凯
继承特性回合事项：
新分支已合入PR 375个，补丁 3876个
         近两周(2.26-3.8)新合入特性PR：
         虚拟化：
            Support PV-sched feature https://gitee.com/openeuler/kernel/pulls/4785
            Export vcpu stat via debugfs https://gitee.com/openeuler/kernel/pulls/4802
         架构 & 驱动：
            kabi/iommu: Backport patches from upstream and maintainer tree https://gitee.com/openeuler/kernel/pulls/4676
            merge upstream net-v6.7 all wangxun patches https://gitee.com/openeuler/kernel/pulls/4725
            RAS: Report ARM processor information to userspace https://gitee.com/openeuler/kernel/pulls/4727
            coresight: trbe: Enable ACPI based devices https://gitee.com/openeuler/kernel/pulls/4730
KABI专项：
         1.KABI白名单已输出；
           https://gitee.com/src-openeuler/kernel/blob/master/Module.kabi_aarch64
           https://gitee.com/src-openeuler/kernel/blob/master/Module.kabi_x86_64
         2.已合入55个KABI预留PR， 预留工作基本已完成
处理器支持专项：
         新合入PR：
          intel: Intel-sig: intel_idle: add Sierra Forest SoC support on 6.6 https://gitee.com/openeuler/kernel/pulls/4841
                 Intel: backport KVM LAM from v6.8 to OLK-6.6 https://gitee.com/openeuler/kernel/pulls/4807
          龙芯： Add loongarch kernel kvm support https://gitee.com/openeuler/kernel/pulls/4773
内核编译专项：
          1.已合入config相关PR 27个，已完成
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

2024.2.26 ~ 3.8进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2403.1.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/

        openEuler-1.0-LTS从 4.19.90-2402.5.0 更新至 4.19.90-2403.1.0, 回合补丁数50个
        git log --no-merges 4.19.90-2402.5.0..4.19.90-2403.1.0 --oneline | wc -l
        50

        修复CVE 40个：
        CVE-2021-47034
        CVE-2021-46934
        CVE-2024-26600
        CVE-2021-46909
        CVE-2020-36780
        CVE-2024-26597
        CVE-2021-47073
        CVE-2024-22099
        CVE-2020-36777
        CVE-2021-47061
        CVE-2021-46932
        CVE-2020-36784
        CVE-2021-47060
        CVE-2019-25162
        CVE-2021-47006
        CVE-2024-1151
        CVE-2021-46941
        CVE-2023-52475
        CVE-2023-52443
        CVE-2021-46989
        CVE-2021-47054
        CVE-2021-46955
        CVE-2021-47049
        CVE-2024-26602
        CVE-2020-36782
        CVE-2021-46928
        CVE-2023-52445
        CVE-2023-52451
        CVE-2023-52469
        CVE-2024-26606
        CVE-2024-26598
        CVE-2021-46904
        CVE-2023-52449
        CVE-2024-26595
        CVE-2024-26586
        CVE-2023-52435
        CVE-2023-52435
        CVE-2023-52444
        CVE-2023-52439
        CVE-2023-52436

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/4947  powerpc/64s: Fix pte update for kernel memory on radix
        https://gitee.com/openeuler/kernel/pulls/4932  phy: ti: phy-omap-usb2: Fix NULL pointer dereference for SRP
        https://gitee.com/openeuler/kernel/pulls/4874  v2  net: openvswitch: limit the number of recursions from action sets
        https://gitee.com/openeuler/kernel/pulls/4920  ARM: footbridge: remove personal server platform
        https://gitee.com/openeuler/kernel/pulls/4887  KVM: Destroy I/O bus devices on unregister failure _after_ sync'ing SRCU
        https://gitee.com/openeuler/kernel/pulls/4918  v3  usb: hub: Guard against accesses to uninitialized BOS descriptors
        https://gitee.com/openeuler/kernel/pulls/4936  i2c: validate user data in compat ioctl
        https://gitee.com/openeuler/kernel/pulls/4898  platform/x86: dell-smbios-wmi: Fix oops on rmmod dell_smbios
        https://gitee.com/openeuler/kernel/pulls/4879  KVM: Stop looking for coalesced MMIO zones if the bus is destroyed
        https://gitee.com/openeuler/kernel/pulls/4869  Fix CVE-2021-46941
        https://gitee.com/openeuler/kernel/pulls/4904  i2c: sprd: fix reference leak when pm_runtime_get_sync fails
        https://gitee.com/openeuler/kernel/pulls/4859  hfsplus: prevent corruption in shrinking truncate
        https://gitee.com/openeuler/kernel/pulls/4877  i2c: Fix a potential use after free
        https://gitee.com/openeuler/kernel/pulls/4888  v3  media: dvbdev: Fix memory leak in dvb_media_device_free()
        https://gitee.com/openeuler/kernel/pulls/4825  sched/membarrier: reduce the ability to hammer on sys_membarrier
        https://gitee.com/openeuler/kernel/pulls/4882  Input: appletouch - initialize work before device registration
        https://gitee.com/openeuler/kernel/pulls/4876  backport patch to fix CVE-2021-47077
        https://gitee.com/openeuler/kernel/pulls/4899  net: qualcomm: rmnet: fix global oob in rmnet_policy
        https://gitee.com/openeuler/kernel/pulls/4892  Bluetooth: rfcomm: Fix null-ptr-deref in rfcomm_check_security
        https://gitee.com/openeuler/kernel/pulls/4881  i2c: cadence: fix reference leak when pm_runtime_get_sync fails
        https://gitee.com/openeuler/kernel/pulls/4865  Input: powermate - fix use-after-free in powermate_config_complete
        https://gitee.com/openeuler/kernel/pulls/4860  apparmor: avoid crash when parsed profile name is empty
        https://gitee.com/openeuler/kernel/pulls/4856  bus: qcom: Put child node before return
        https://gitee.com/openeuler/kernel/pulls/4828  Drivers: hv: vmbus: Use after free in __vmbus_open()
        https://gitee.com/openeuler/kernel/pulls/4806  v2  media: pvrusb2: fix use after free on context disconnection
        https://gitee.com/openeuler/kernel/pulls/4777  drivers/amd/pm: fix a use-after-free in kv_parse_power_table
        https://gitee.com/openeuler/kernel/pulls/4819  v2  fix CVE-2020-36782
        https://gitee.com/openeuler/kernel/pulls/4833  openvswitch: fix stack OOB read while fragmenting IPv4 packets
        https://gitee.com/openeuler/kernel/pulls/4677  f2fs: fix to avoid dirent corruption
        https://gitee.com/openeuler/kernel/pulls/4804  CVE-2023-52451 backport to 4.19 v2
        https://gitee.com/openeuler/kernel/pulls/4778  v3  Revert "memcg: fix a UAF problem in drain_all_stock()"
        https://gitee.com/openeuler/kernel/pulls/4812  parisc: Clear stale IIR value on instruction access rights trap
        https://gitee.com/openeuler/kernel/pulls/4758  binder: signal epoll threads of self-work
        https://gitee.com/openeuler/kernel/pulls/4746  KVM: arm64: vgic-its: Avoid potential UAF in LPI translation cache
        https://gitee.com/openeuler/kernel/pulls/4751  [sync] PR-4623: i2c: Optimized the value setting of maxwrite limit to  fifo depth - 1
        https://gitee.com/openeuler/kernel/pulls/4707  mtd: Fix gluebi NULL pointer dereference caused by ftl notifier
        https://gitee.com/openeuler/kernel/pulls/4686  mlxsw: spectrum_acl_tcam: Fix stack corruption
        https://gitee.com/openeuler/kernel/pulls/4710  CVE-2021-46904 for openEuler1.0
        https://gitee.com/openeuler/kernel/pulls/4671  uio: Fix use-after-free in uio_open
        https://gitee.com/openeuler/kernel/pulls/4701  v2  mlxsw: spectrum_acl_tcam: Fix NULL pointer dereference in error path
        https://gitee.com/openeuler/kernel/pulls/4684  v3  CVE-2023-52435
        https://gitee.com/openeuler/kernel/pulls/4643  f2fs: explicitly null-terminate the xattr list

近两周(2024.2.26 ~ 3.8)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-190.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-190.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.45.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.66.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.128.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-188.0.0 更新至 5.10.0-190.0.0, 回合补丁数600个
        git log 5.10.0-188.0.0..5.10.0-190.0.0 --oneline | wc -l
        600

        同步linux 5.10.y社区LTS补丁集5个: 5.10.190 - 5.10.194
        https://gitee.com/openeuler/kernel/pulls/4674 Backport 5.10.193- 5.10.194 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/4663 Backport 5.10.191 - 5.10.192 LTS patches from upstream
        https://gitee.com/openeuler/kernel/pulls/4600 Backport 5.10.190 LTS patches from upstream

        修复CVE 29个
        CVE-2024-26607
        https://gitee.com/openeuler/kernel/pulls/4928  drm/bridge: sii902x: Fix probing race issue
        CVE-2024-26600
        https://gitee.com/openeuler/kernel/pulls/4931  phy: ti: phy-omap-usb2: Fix NULL pointer dereference for SRP
        CVE-2024-26581
        https://gitee.com/openeuler/kernel/pulls/4809  netfilter: nft_set_rbtree: skip end interval element from gc
        CVE-2023-52443
        https://gitee.com/openeuler/kernel/pulls/4940  apparmor: avoid crash when parsed profile name is empty
        CVE-2021-47036
        https://gitee.com/openeuler/kernel/pulls/4901  fix CVE-2021-47036        
        CVE-2024-1151
        https://gitee.com/openeuler/kernel/pulls/4868  net: openvswitch: limit the number of recursions from action sets
        CVE-2024-26601
        https://gitee.com/openeuler/kernel/pulls/4861  ext4: regenerate buddy after block freeing failed if under fc replay
        CVE-2023-52482
        https://gitee.com/openeuler/kernel/pulls/4857  x86/srso: Add SRSO mitigation for Hygon processors
        CVE-2023-52475
        https://gitee.com/openeuler/kernel/pulls/4902 [sync] PR-4865:  Input: powermate - fix use-after-free in powermate_config_complete
        CVE-2024-22099
        https://gitee.com/openeuler/kernel/pulls/4891  Bluetooth: rfcomm: Fix null-ptr-deref in rfcomm_check_security
        CVE-2021-46987
        https://gitee.com/openeuler/kernel/pulls/4847  btrfs: mainline backport
        CVE-2023-52444
        https://gitee.com/openeuler/kernel/pulls/4678  f2fs: fix to avoid dirent corruption
        CVE-2023-52458
        https://gitee.com/openeuler/kernel/pulls/4742  block: add check that partition length needs to be aligned with block size
        CVE-2023-52451
        https://gitee.com/openeuler/kernel/pulls/4805  CVE-2023-52451 backport to OLK-5.10 v2
        CVE-2024-26583
        https://gitee.com/openeuler/kernel/pulls/4803  CVE-2024-26583
        CVE-2024-26583
        https://gitee.com/openeuler/kernel/pulls/4794  serial: imx: fix tx statemachine deadlock
        CVE-2023-52463
        https://gitee.com/openeuler/kernel/pulls/4702  efivarfs: force RO when remounting if SetVariable is not supported
        CVE-2023-52448
        https://gitee.com/openeuler/kernel/pulls/4790 v2  gfs2: Fix kernel NULL pointer dereference in gfs2_rgrp_dump
        CVE-2024-26606
        https://gitee.com/openeuler/kernel/pulls/4764  binder: signal epoll threads of self-work
        CVE-2024-26598
        https://gitee.com/openeuler/kernel/pulls/4747  KVM: arm64: vgic-its: Avoid potential UAF in LPI translation cache
        CVE-2024-26603
        https://gitee.com/openeuler/kernel/pulls/4772  x86/fpu: Stop relying on userspace for info to fault in xsave buffer
        CVE-2023-52457
        https://gitee.com/openeuler/kernel/pulls/4729  serial: 8250: omap: Don't skip resource freeing if pm_runtime_resume_and_get() failed
        CVE-2024-26586
        https://gitee.com/openeuler/kernel/pulls/4690  CVE-2024-26586
        CVE-2023-52439
        https://gitee.com/openeuler/kernel/pulls/4672  uio: Fix use-after-free in uio_open
        CVE-2023-52449
        https://gitee.com/openeuler/kernel/pulls/4706  mtd: Fix gluebi NULL pointer dereference caused by ftl notifier
        CVE-2024-26595
        https://gitee.com/openeuler/kernel/pulls/4694 v2  mlxsw: spectrum_acl_tcam: Fix NULL pointer dereference in error path
        CVE-2023-52435
        https://gitee.com/openeuler/kernel/pulls/4662 v3  CVE-2023-52435
        CVE-2023-52438
        https://gitee.com/openeuler/kernel/pulls/4646  binder: fix use-after-free in shinker's callback
        CVE-2023-52436
        https://gitee.com/openeuler/kernel/pulls/4645  f2fs: explicitly null-terminate the xattr list

        Intel
        https://gitee.com/openeuler/kernel/pulls/4363 [OLK-5.10] add ACPI/EINJ CXL error types
        https://gitee.com/openeuler/kernel/pulls/4388 intel: backport Intel SST TPMI support
        https://gitee.com/openeuler/kernel/pulls/4387 intel: backport uncore freq control tpmi support for BHS platform
        https://gitee.com/openeuler/kernel/pulls/4202 Intel: Backport GNR/SRF pmu uncore support back to kernel 5.10
        https://gitee.com/openeuler/kernel/pulls/4273 Intel: Backport SRF/GRR perf cstate support back to kernel 5.10
        https://gitee.com/openeuler/kernel/pulls/4048 [OLK-5.10] Intel: Backport PEBS format 5 support to OLK-5.10 for GNR/SRF Timed PEBS enabling
        https://gitee.com/openeuler/kernel/pulls/4433 【OLK-5.10】Add PCH less Boot support on GNR/SRF
        https://gitee.com/openeuler/kernel/pulls/4230 [OLK-5.10] Intel: backport to support RAS EDAC feature on Granite Rapids(GNR) and Sierra Forest(SRF) server

        AMD
        https://gitee.com/openeuler/kernel/pulls/4657 perf/x86/amd/uncore: Fix memory leak for events array
        
        hisilicon
        https://gitee.com/openeuler/kernel/pulls/4529 crypto: hisilicon/qm - add bracket protection for macro parameters
        https://gitee.com/openeuler/kernel/pulls/4647 hisi_ptt: Move type check to the beginning of hisi_ptt_pmu_event_init()
        https://gitee.com/openeuler/kernel/pulls/4665 urma: fix some bugs of urma
        https://gitee.com/openeuler/kernel/pulls/4617 Fix the bug of tp negotiation concurrency
        https://gitee.com/openeuler/kernel/pulls/4623 i2c: Optimized the value setting of maxwrite limit to  fifo depth - 1
        https://gitee.com/openeuler/kernel/pulls/4220 backport some patches for kunpeng hccs

        沐创
        https://gitee.com/openeuler/kernel/pulls/3123 Add pcie acs and no-bus-reset quirk for mucse Nics

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/4737  blk-mq: fix IO hang from sbitmap wakeup race
        https://gitee.com/openeuler/kernel/pulls/4649  arm64/mpam: update reminder message about MBHDL option
        https://gitee.com/openeuler/kernel/pulls/4510  ubi: fastmap: Optimize ubi wl algorithm to improve flash service life


议题二：arm64 VCPU热插拔特性-- 李伟

议题三：openEuler 6.6 内存管理folio相关介绍 -- 孙南勇

三、本期遗留问题

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/2/23 Kernel SIG 双周例会】
轮值主持：张伽琳 【轮值主持顺序：郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：廖涛
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/980795271
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&郑增凯）
近两周(2024.1.29 ~ 2.23)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-188.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-188.0.0
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.43.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.64.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.126.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-185.0.0 更新至 5.10.0-188.0.0, 回合补丁数150个
        git log 5.10.0-185.0.0..5.10.0-188.0.0 --oneline | wc -l
        150

        修复CVE 8个
        CVE-2023-46838
        https://gitee.com/openeuler/kernel/pulls/4521  xen-netback: don't produce zero-size SKB frags
        CVE-2024-0841
        https://gitee.com/openeuler/kernel/pulls/4588  fs,hugetlb: fix NULL pointer dereference in hugetlbs_fill_super
        CVE-2023-52340
        https://gitee.com/openeuler/kernel/pulls/4431 v2  patchset for CVE-2023-52340
        CVE-2024-1086
        https://gitee.com/openeuler/kernel/pulls/4461  netfilter: nf_tables: reject QUEUE/DROP verdict parameters
        CVE-2023-6531
        https://gitee.com/openeuler/kernel/pulls/4321  io_uring/af_unix: disable sending io_uring over sockets
        CVE-2024-22705
        https://gitee.com/openeuler/kernel/pulls/4266  ksmbd: fix slab-out-of-bounds in smb_strndup_from_utf16()
        CVE-2023-51042
        https://gitee.com/openeuler/kernel/pulls/4262 [sync] PR-4255:  drm/amdgpu: Fix potential fence use-after-free v2
        CVE-2023-46343
        https://gitee.com/openeuler/kernel/pulls/4257  nfc: nci: fix possible NULL pointer dereference in send_acknowledge()

        Intel:
        https://gitee.com/openeuler/kernel/pulls/4032 intel: add TPMI base driver support for GNR
        https://gitee.com/openeuler/kernel/pulls/3372 Cluster scheduler support
        https://gitee.com/openeuler/kernel/pulls/3634 Intel: Backport Granite Rapids(GNR) core PMU support to OLK-5.10

        Shingroup:
        https://gitee.com/openeuler/kernel/pulls/4121 Init support for ppc64le

        WindRiver:
        https://gitee.com/openeuler/kernel/pulls/3228  net: txgbe: Fix memleak in txgbe_calc_eeprom_checksum()
        https://gitee.com/openeuler/kernel/pulls/3134  Add MODULE_FIRMWARE() for FIRMWARE_TG357766.
        https://gitee.com/openeuler/kernel/pulls/4015  drm/amdgpu: correct the amdgpu runtime dereference usage count
        https://gitee.com/openeuler/kernel/pulls/4014  drm/dp_mst: Fix NULL deref in get_mst_branch_device_by_guid_helper()
        https://gitee.com/openeuler/kernel/pulls/4013  drm/amdgpu: correct chunk_ptr to a pointer to chunk.
        https://gitee.com/openeuler/kernel/pulls/4012  drm/amdgpu: Fix a null pointer access when the smc_rreg pointer is NULL
        https://gitee.com/openeuler/kernel/pulls/4010  drm/amd/display: Exit idle optimizations before attempt to access PHY
        https://gitee.com/openeuler/kernel/pulls/3955  drm/radeon: possible buffer overflow

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/4524 fix spi: hisi-sfc-v3xx: Return IRQ_NONE if no interrupts were detected

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/4605  arm64/mpam: support resctrl fs to show mounting option
        https://gitee.com/openeuler/kernel/pulls/4604  arm64/mpam: Skip updates of unrelated ctrl type
        https://gitee.com/openeuler/kernel/pulls/4602  arm64/mpam: support MPAM v0.1 version
        https://gitee.com/openeuler/kernel/pulls/4531  fs:/dcache.c: fix negative dentry flag warning in dentry_free
        https://gitee.com/openeuler/kernel/pulls/4580  printk: fix double unlock issue in logbuf_lock
        https://gitee.com/openeuler/kernel/pulls/4562 v4  tracing: Backport bugfixes
        https://gitee.com/openeuler/kernel/pulls/4496 [sync] PR-4362:  ubifs: Queue up space reservation tasks if retrying many times
        https://gitee.com/openeuler/kernel/pulls/4484 v4  Using smmu IIDR registers
        https://gitee.com/openeuler/kernel/pulls/3861  nvme: sanitize metadata bounce buffer for reads
        https://gitee.com/openeuler/kernel/pulls/4256  scsi: core: Always send batch on reset or error handling command
        https://gitee.com/openeuler/kernel/pulls/4327 【OLK-5.10】cgroup_writeback: fix deadlock in cgroup1_writeback
        https://gitee.com/openeuler/kernel/pulls/4280 v2  fs:/dcache.c: fix negative dentry limit not complete problem
        https://gitee.com/openeuler/kernel/pulls/4290  net/rds: Fix UBSAN: array-index-out-of-bounds in rds_cmsg_recv
        https://gitee.com/openeuler/kernel/pulls/4268  linux Mainline ubifs Fix Patch bacnport to 5.10
        https://gitee.com/openeuler/kernel/pulls/4270  fix spinlock already unlocked in inet_csk_reqsk_queue_add' bug
        https://gitee.com/openeuler/kernel/pulls/4003  ext4: fix some ext4_lblk_t overflow issues
        https://gitee.com/openeuler/kernel/pulls/4149  block: remove precise_iostat
        https://gitee.com/openeuler/kernel/pulls/4213  netlink: fix potential sleeping issue in mqueue_flush_file
        https://gitee.com/openeuler/kernel/pulls/4203  mm/dynamic_hugetlb: skip unexpected migration
        https://gitee.com/openeuler/kernel/pulls/4167  sched/fair: Fix qos_timer deadlock when cpuhp offline

2024.1.29 ~ 2.23进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2402.5.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/

        openEuler-1.0-LTS从 4.19.90-2401.5.0 更新至 4.19.90-2402.5.0, 回合补丁数38个
        git log --no-merges 4.19.90-2401.5.0..4.19.90-2402.5.0 --oneline | wc -l
        38

        修复CVE 9个：
        CVE-2023-46838
        CVE-2023-52340
        CVE-2024-1086
        CVE-2023-51043
        CVE-2023-6531
        CVE-2024-23849
        CVE-2023-51042
        CVE-2023-46343
        CVE-2024-0639

        hisilicon：
        https://gitee.com/openeuler/kernel/pulls/4231  crypto: hisilicon/qm - drop unnecessary IS_ENABLE(CONFIG_NUMA) check
        https://gitee.com/openeuler/kernel/pulls/4583  net: hns3: fix a bug and modify the hns3 driver version
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/4137  sctp: fix potential deadlock on &net->sctp.addr_wq_lock
        https://gitee.com/openeuler/kernel/pulls/4166  sched/fair: Fix qos_timer deadlock when cpuhp offline
        https://gitee.com/openeuler/kernel/pulls/3942  efi/x86: Map the entire EFI vendor string before copying it
        https://gitee.com/openeuler/kernel/pulls/3943  timerqueue: Use rb_entry_safe() in timerqueue_getnext()
        https://gitee.com/openeuler/kernel/pulls/3944  time: Handle negative seconds correctly in timespec64_to_ns()
        https://gitee.com/openeuler/kernel/pulls/4212  netlink: fix potential sleeping issue in mqueue_flush_file
        https://gitee.com/openeuler/kernel/pulls/4209  dhugetlb: skip unexpected migration
        https://gitee.com/openeuler/kernel/pulls/4255  drm/amdgpu: Fix potential fence use-after-free v2
        https://gitee.com/openeuler/kernel/pulls/4235  nfc: nci: fix possible NULL pointer dereference in send_acknowledge()
        https://gitee.com/openeuler/kernel/pulls/4228  fix spinlock already unlocked in inet_csk_reqsk_queue_add' bug
        https://gitee.com/openeuler/kernel/pulls/4299  smb: client: fix NULL deref in asn1_ber_decoder()
        https://gitee.com/openeuler/kernel/pulls/4288  net/rds: Fix UBSAN: array-index-out-of-bounds in rds_cmsg_recv
        https://gitee.com/openeuler/kernel/pulls/4277  fs:/dcache.c: fix negative dentry limit not complete problem
        https://gitee.com/openeuler/kernel/pulls/4320  io_uring/af_unix: disable sending io_uring over sockets
        https://gitee.com/openeuler/kernel/pulls/4360  net/sched: sch_hfsc: upgrade 'rt' to 'sc' when it becomes a inner curve
        https://gitee.com/openeuler/kernel/pulls/4369  mm/filemap: avoid buffered read/write race to read inconsistent data
        https://gitee.com/openeuler/kernel/pulls/4392  linux-4.19.y inclusion
        https://gitee.com/openeuler/kernel/pulls/4399  net: dst: Optimized route gc
        https://gitee.com/openeuler/kernel/pulls/4412  v3  Save and restore msg_namelen in sock_sendmsg
        https://gitee.com/openeuler/kernel/pulls/4411  v2  drm/atomic: Fix potential use-after-free in nonblocking commits
        https://gitee.com/openeuler/kernel/pulls/4454  netfilter: nf_tables: reject QUEUE/DROP verdict parameters
        https://gitee.com/openeuler/kernel/pulls/4538  fix kprobe reenter bug
        https://gitee.com/openeuler/kernel/pulls/4526  v2  fs:/dcache.c: fix negative dentry flag warning in dentry_free
        https://gitee.com/openeuler/kernel/pulls/4552  v4  CVE-2023-52340
        https://gitee.com/openeuler/kernel/pulls/4601  v2  xen-netback: don't produce zero-size SKB frags

20240223：
OLK-6.6进展同步：
继承特性回合事项：
截至1月26日，新分支已合入PR 330个，补丁 3336个
         近两周新合入特性PR：
         内存：
             memory tiering: calculate abstract distance based on ACPI HMAT https://gitee.com/openeuler/kernel/pulls/4449
             change zswap's default allocator to zsmalloc https://gitee.com/openeuler/kernel/pulls/4450
         文件系统：
             ubi: fastmap: Optimize ubi wl algorithm to improve flash service life https://gitee.com/openeuler/kernel/pulls/4506
         架构 & 驱动：
            Add support for ecmdq https://gitee.com/openeuler/kernel/pulls/4576
            RDMA/hns: Support MR management https://gitee.com/openeuler/kernel/pulls/4546
KABI专项：
         1.KABI白名单已输出；
           https://gitee.com/src-openeuler/kernel/blob/master/Module.kabi_aarch64
           https://gitee.com/src-openeuler/kernel/blob/master/Module.kabi_x86_64
         2.已合入54个KABI预留PR， 预留工作基本已完成
处理器支持专项：
         新合入PR：
          AMD:  AMD: fix brstack event for AMD Zen CPU https://gitee.com/openeuler/kernel/pulls/4489
          申威：add sw64 architecture support https://gitee.com/openeuler/kernel/pulls/4545
          飞腾： Add iommu support for Phytium S2500 https://gitee.com/openeuler/kernel/pulls/4598
                Fix gic support for Phytium S2500 https://gitee.com/openeuler/kernel/pulls/4661
内核编译专项：
          1.已合入config相关PR 27个，已完成
          2.kernel rpm包构建， 合入tag到6.6.0-10.0.0 https://gitee.com/src-openeuler/kernel/pulls/1448

议题二：待合入24.03的TSSE driver产品介绍（澜起 蔡仲斐）

三、本期遗留问题

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/1/26 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：张伽琳
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/967727869
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&郑增凯）
近两周(2024.1.15 ~ 1.26)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2401.5.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/

        openEuler-1.0-LTS从 4.19.90-2401.3.0 更新至 4.19.90-2401.5.0, 回合补丁数12个
        git log --no-merges 4.19.90-2401.3.0..4.19.90-2401.5.0 --oneline | wc -l
        12

        修复CVE 5个：
        CVE-2024-0607
        CVE-2022-48619
        CVE-2024-0565
        CVE-2023-6040
        CVE-2024-0340

        phytium：
        https://gitee.com/openeuler/kernel/pulls/2954  spi: phytium: fix phytium_spi_irq panic on boot
        
        hisilicon：
        https://gitee.com/openeuler/kernel/pulls/4006  crypto: hisilicon/sec2: fix memory use-after-free issue
        https://gitee.com/openeuler/kernel/pulls/4025  crypto: hisilicon - replace 'smp_processor_id' with the raw version of the macro
        https://gitee.com/openeuler/kernel/pulls/4039  crypto: hisilicon/qm: fix several issues
        
        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/3923  net: bridge: multicast: fix UAF of net_bridge
        https://gitee.com/openeuler/kernel/pulls/3980  vhost: use kzalloc() instead of kmalloc() followed by memset()
        https://gitee.com/openeuler/kernel/pulls/4021  netfilter: nf_tables: Reject tables of unsupported family
        https://gitee.com/openeuler/kernel/pulls/4065  smb: client: fix OOB in receive_encrypted_standard()
        https://gitee.com/openeuler/kernel/pulls/4080  rtnetlink: Reject negative ifindexes in RTM_NEWLINK
        https://gitee.com/openeuler/kernel/pulls/4067  fix CVE-2022-48619
        https://gitee.com/openeuler/kernel/pulls/4101  netfilter: nf_tables: fix pointer math issue in nft_byteorder_eval()

近两周(2024.1.15 ~ 1.26)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-185.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-185.0.0，前两周冻结，本周开始陆续合入
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.40.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.61.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.123.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/
        以OLK-5.10为例:
        从 5.10.0-183.0.0 更新至 5.10.0-185.0.0, 回合补丁数117个
        git log 5.10.0-183.0.0..5.10.0-185.0.0 --oneline | wc -l
        117

        修复CVE 7个
        CVE-2024-0607
        https://gitee.com/openeuler/kernel/pulls/4100  netfilter: nf_tables: fix pointer math issue in nft_byteorder_eval()
        CVE-2023-6040
        https://gitee.com/openeuler/kernel/pulls/4022  netfilter: nf_tables: Reject tables of unsupported family
        CVE-2023-6915
        https://gitee.com/openeuler/kernel/pulls/4090  ida: Fix crash in ida_free when the bitmap is empty
        CVE-2024-0641
        https://gitee.com/openeuler/kernel/pulls/4069  tipc: fix a potential deadlock on &tx->lock
        CVE-2024-0565
        https://gitee.com/openeuler/kernel/pulls/4064  smb: client: fix OOB in receive_encrypted_standard()
        CVE-2024-0340
        https://gitee.com/openeuler/kernel/pulls/3981  vhost: use kzalloc() instead of kmalloc() followed by memset()
        CVE-2023-6121
        https://gitee.com/openeuler/kernel/pulls/3915  nvmet: nul-terminate the NQNs passed in the connect command

        Intel
        https://gitee.com/openeuler/kernel/pulls/3689 Intel: Backport Sierra Forest(SRF) core PMU support to OLK-5.10

        LoongArch
        https://gitee.com/openeuler/kernel/pulls/3418 [sync] PR-2918: fix some bugs in loongarch kvm

        hisilicon
        https://gitee.com/openeuler/kernel/pulls/4136 udma: change the way of query dfx resource
        https://gitee.com/openeuler/kernel/pulls/4024 udma: add mailbox description printing.
        https://gitee.com/openeuler/kernel/pulls/3940 net: hns3: fix the cmdq reset command times out when all VFs are enabled and the queue is full.
        https://gitee.com/openeuler/kernel/pulls/3925 udma: add capability of DWQE in RC mode

        KVM
        https://gitee.com/openeuler/kernel/pulls/4138 KVM: arm64: arch_timer: init ret for kvm_timer_enable

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/4134  fs:/dcache.c: fix negative dentry limit not complete problem
        https://gitee.com/openeuler/kernel/pulls/4054  ext4: correct return value of ext4_convert_meta_bg
        https://gitee.com/openeuler/kernel/pulls/4058  ext4: synchronize the casefold bugfix from the mainline.
        https://gitee.com/openeuler/kernel/pulls/3975  md/raid1-10: limit the number of plugged bio
        https://gitee.com/openeuler/kernel/pulls/3998  cpufreq: CPPC: Fix performance/frequency conversion
        https://gitee.com/openeuler/kernel/pulls/4091  x86/quirks: Add parameter to clear MSIs early
        https://gitee.com/openeuler/kernel/pulls/4019  mm/filemap: avoid buffered read/write race to read inconsistent data
        https://gitee.com/openeuler/kernel/pulls/3912  net: bridge: multicast: fix UAF of net_bridge
        https://gitee.com/openeuler/kernel/pulls/3982  ACPI: CPPC: Assume no transition latency if no PCCT
        https://gitee.com/openeuler/kernel/pulls/3972  arm64: make cma=0 as default for openeuler

        OLK-6.6进展同步：
继承特性回合事项：
截至1月26日，新分支已合入PR 188个，补丁 2773个
         近两周新合入特性PR：
         调度：可编程调度相关特性 https://gitee.com/openeuler/kernel/pulls/4053
               smart grid zone功耗相关特性 https://gitee.com/openeuler/kernel/pulls/4093
         内存：
             动态大页相关特性 https://gitee.com/openeuler/kernel/pulls/3976
             Backport etmem feature to OLK 6.6 https://gitee.com/openeuler/kernel/pulls/4070
             Support large folio for mlock https://gitee.com/openeuler/kernel/pulls/4199
             Add per-node vmstat info and memcg info https://gitee.com/openeuler/kernel/pulls/4154
             backport two page_owner patchsets https://gitee.com/openeuler/kernel/pulls/4087
         文件系统：
             使用epbf基于大数据场景进行读性能优化 https://gitee.com/openeuler/kernel/pulls/3895
             挂载文件系统的裸盘操作打印增强 https://gitee.com/openeuler/kernel/pulls/3963
        网络：
             drivers: hooks: add bonding driver vendor hooks https://gitee.com/openeuler/kernel/pulls/3964
         架构：
             arm64 mpam特性 https://gitee.com/openeuler/kernel/pulls/4120
             arm64 lse 启动参数开关 https://gitee.com/openeuler/kernel/pulls/4104
             arm64 MBIGEN中断控制器支持特性 https://gitee.com/openeuler/kernel/pulls/3974
             Intel RDT non-contiguous CBM support https://gitee.com/openeuler/kernel/pulls/4027
             iommufd dirty tracking from v6.7 https://gitee.com/openeuler/kernel/pulls/4159
KABI专项：
         1.KABI白名单正在输出；
         2.已提KABI预留PR 32个，1月26日开始统一合入，预计1月30日左右合入完，接下来开始测试KABI预留补丁的影响及查漏补缺
处理器支持专项：
         新合入PR：
          Intel: 
             Backport GNR/SRF PMU uncore support to kernel v6.6 https://gitee.com/openeuler/kernel/pulls/4116
             Backport In Field Scan(IFS) SAF & Array BIST support for GNR & SRF https://gitee.com/openeuler/kernel/pulls/4115
             Backport microcode restructuring  https://gitee.com/openeuler/kernel/pulls/4103
             Backport Sierra Forest(SRF) perf cstate support to kernel OLK-6.6 https://gitee.com/openeuler/kernel/pulls/4102
             Backport SRF LBR branch counter support to kernel v6.6 https://gitee.com/openeuler/kernel/pulls/4099
          兆芯：
             Add support for Zhaoxin Processors https://gitee.com/openeuler/kernel/pulls/3098
             x86/mce: Add Centaur MCA support https://gitee.com/openeuler/kernel/pulls/3102
             Add support for Zhaoxin HDAC and codec https://gitee.com/openeuler/kernel/pulls/3124
             Driver for Zhaoxin CPU core temperature monitoring https://gitee.com/openeuler/kernel/pulls/3131
             rtc: Fix set RTC time delay 500ms on some Zhaoxin SOCs https://gitee.com/openeuler/kernel/pulls/3170
             Add MWAIT Cx support for Zhaoxin CPUs https://gitee.com/openeuler/kernel/pulls/3177
             海光：
             Add support for Hygon model 4h CPU topology https://gitee.com/openeuler/kernel/pulls/3311
             Add support for Hygon model 5h CPU cache https://gitee.com/openeuler/kernel/pulls/3830
             Add support for Hygon model 4h IOAPIC https://gitee.com/openeuler/kernel/pulls/3834
             Add support for Hygon model 4h QoS https://gitee.com/openeuler/kernel/pulls/3836
          龙芯：
             LoongArch: add old BPI compatibility https://gitee.com/openeuler/kernel/pulls/3137
             LoongArch: add cpufreq and ls2k500 bmc support https://gitee.com/openeuler/kernel/pulls/3323
             LoongArch: fix some pci problems https://gitee.com/openeuler/kernel/pulls/3444
          飞腾： 3个Review中
内核编译专项：
          1.已合入config相关PR 15个，仍有15个在review中
          2.kernel rpm包构建， 合入tag到6.6.0-6.0.0 https://gitee.com/src-openeuler/kernel/pulls/1409

议题二：Intel LKP/0-Day Testing for openEuler Kernel Launched（曾昭荣）

议题三：24.03  RISC-V Kernel 合入方案讨论 （邢明政）

议题四：硬件驱动开源至社区内核流程变更 （刘彦泽）

议题五：soc下hccs驱动commiter申报 （李辉松）
drivers/soc/hisilicon/kunpeng_hccs
会议结论：通过

三、本期遗留问题

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

https://lore.kernel.org/oe-kbuild-all/202401191329.q4EWAhse-lkp@intel.com/

https://lore.kernel.org/oe-kbuild-all/202401181124.lY3ISI6l-lkp@intel.com/

https://lore.kernel.org/oe-kbuild-all/202401180440.MFTxugeQ-lkp@intel.com/

https://lore.kernel.org/oe-kbuild-all/202401180343.M6gjqR5d-lkp@intel.com/

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
【2024/1/12 Kernel SIG 双周例会】
轮值主持：郑增凯 【轮值主持顺序：郑增凯->桑力鹏->张伽琳->廖涛】
下次轮值主持：桑力鹏
会议链接：https://bmeeting.huaweicloud.com:36443/#/j/983665981
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一： 进展update（张伽琳 & 章昌仲&郑增凯）
近两周(2024.1.2 ~ 1.12)内进展同步:
        总体上OLK-5.10主干更新到tag 5.10.0-183.0.0
        openEuler-22.03-LTS-SP3分支，更新到tag 5.10.0-183.0.0
        前两周冻结，本周开始陆续合入
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP3/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3/update/
        openEuler-22.03-LTS-SP2分支，更新到tag 5.10.0-153.38.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP2/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP2/update/
        openEuler-22.03-LTS-SP1分支，更新到tag 5.10.0-136.59.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS-SP1/update/
        openEuler-22.03-LTS维护分支更新到tag 5.10.0-60.121.0，
        release ISO获取链接: https://repo.openeuler.org/openEuler-22.03-LTS/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-22.03-LTS/update/

        以OLK-5.10为例:
        从 5.10.0-182.0.0 更新至 5.10.0-183.0.0, 回合补丁数85个
        git log 5.10.0-182.0.0..5.10.0-183.0.0 --oneline | wc -l
        85

        修复CVE 10个
        CVE-2023-6546
        https://gitee.com/openeuler/kernel/pulls/3562  tty: n_gsm: fix the UAF caused by race condition in gsm_cleanup_mux
        CVE-2023-6606
        CVE-2023-6610
        https://gitee.com/openeuler/kernel/pulls/3694  Fix tow CVEs of CIFS
        CVE-2023-6931
        https://gitee.com/openeuler/kernel/pulls/3570  perf/core: Fix CVE-2023-6931
        CVE-2023-51780
        https://gitee.com/openeuler/kernel/pulls/3659  atm: Fix Use-After-Free in do_vcc_ioctl
        CVE-2023-51782
        https://gitee.com/openeuler/kernel/pulls/3668  net/rose: Fix Use-After-Free in rose_ioctl
        CVE-2023-51779
        https://gitee.com/openeuler/kernel/pulls/3686  Bluetooth: af_bluetooth: Fix Use-After-Free in bt_sock_recvmsg
        CVE-2023-35827
        https://gitee.com/openeuler/kernel/pulls/3594  CVE-2023-35827 patchset
        CVE-2023-51781
        https://gitee.com/openeuler/kernel/pulls/3715  appletalk: Fix Use-After-Free in atalk_ioctl
        CVE-2023-6817
        https://gitee.com/openeuler/kernel/pulls/3617  netfilter: nft_set_pipapo: skip inactive elements during set walk

        Intel:
        https://gitee.com/openeuler/kernel/pulls/3848 [22.03-LTS-SP3] Bug fix for KVM MMU

        jingdong:
        https://gitee.com/openeuler/kernel/pulls/3459 reset idlest_cpu if not meet the conditions for preferred CPU

        hisilicon:
        https://gitee.com/openeuler/kernel/pulls/3810 Some cleanup and bugfix for HNS3
        https://gitee.com/openeuler/kernel/pulls/3804 MAINTAINERS: Update maintainers of HiSilicon RoCE
        https://gitee.com/openeuler/kernel/pulls/3811 drivers: net: ub: dev: network_mgmt: Modified OLK5.10 ub compilation missing header files.
        https://gitee.com/openeuler/kernel/pulls/3480 drivers: net: ub: dev: network_mgmt: ip_notify: ip_notify: Merge the openEuler modification  suggestions.

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/3776  Revert "sched: clear credit count in error branch"
        https://gitee.com/openeuler/kernel/pulls/3746  smart_grid: make sure hot zone have the highest priority
        https://gitee.com/openeuler/kernel/pulls/3756  md: mainline backport
        https://gitee.com/openeuler/kernel/pulls/3822  ext4: fix kernel BUG in 'ext4_write_inline_data_end()'
        https://gitee.com/openeuler/kernel/pulls/3793  cppc_cpufreq: use policy->cpu in cppc_set_perf()
        https://gitee.com/openeuler/kernel/pulls/3769  tls: suppress wakeups unless we have a full record
        https://gitee.com/openeuler/kernel/pulls/3771  ext4: fix uninitialized ratelimit_state->lock access in __ext4_fill_super()
        https://gitee.com/openeuler/kernel/pulls/3552  block: warn once for each partition in bio_check_ro()
        https://gitee.com/openeuler/kernel/pulls/3466  livepatch/core: Disable support for replacing
        https://gitee.com/openeuler/kernel/pulls/3637  jbd2: fix soft lockup in journal_finish_inode_data_buffers()
        https://gitee.com/openeuler/kernel/pulls/3272  x86/kprobes: Fix the error judgment for debug exceptions
        https://gitee.com/openeuler/kernel/pulls/3447  dm: add error handling support for add_disk()
        https://gitee.com/openeuler/kernel/pulls/3420  md: protect md_thread with rcu
        https://gitee.com/openeuler/kernel/pulls/3379  md: do not return existing mddevs from mddev_find_or_alloc

近两周(2024.1.1 ~ 1.12)内进展同步:
        总体上openEuler-1.0-LTS更新到tag 4.19.90-2401.3.0
        openEuler-20.03-LTS-SP1分支
        release ISO获取链接: https://repo.openeuler.org/openEuler-20.03-LTS-SP1/ISO/
                对应update rpm包下载地址:
                https://repo.openeuler.org/openEuler-20.03-LTS-SP1/update/

        openEuler-1.0-LTS从 4.19.90-2312.6.0 更新至 4.19.90-2401.3.0, 回合补丁数42个
        git log --no-merges 4.19.90-2312.6.0..4.19.90-2401.3.0 --oneline | wc -l
        42

        修复CVE 11个：
        CVE-2023-51781        
        CVE-2023-51782        
        CVE-2023-6121
        CVE-2023-7192
        CVE-2021-33630
        CVE-2021-33631
        CVE-2023-35827
        CVE-2023-51779
        CVE-2023-51780
        CVE-2023-6606
        CVE-2023-6610

        社区问题修复以及上游社区bugfix补丁回合：
        https://gitee.com/openeuler/kernel/pulls/3449  Fix data-races around
        https://gitee.com/openeuler/kernel/pulls/3592  CVE-2023-35827 patchset
        https://gitee.com/openeuler/kernel/pulls/3555  net: check vlan filter feature in vlan_vids_add_by_dev() and vlan_vids_del_by_dev()
        https://gitee.com/openeuler/kernel/pulls/3189  fs: don't audit the capability check in simple_xattr_list()
        https://gitee.com/openeuler/kernel/pulls/3627  jbd2: fix soft lockup in journal_finish_inode_data_buffers()
        https://gitee.com/openeuler/kernel/pulls/3671  smb: client: fix OOB in smbCalcSize()
        https://gitee.com/openeuler/kernel/pulls/3672  smb: client: fix potential OOB in smb2_dump_detail()
        https://gitee.com/openeuler/kernel/pulls/3687  Bluetooth: af_bluetooth: Fix Use-After-Free in bt_sock_recvmsg
        https://gitee.com/openeuler/kernel/pulls/3660  atm: Fix Use-After-Free in do_vcc_ioctl
        https://gitee.com/openeuler/kernel/pulls/3667  net/rose: Fix Use-After-Free in rose_ioctl
        https://gitee.com/openeuler/kernel/pulls/3716  appletalk: Fix Use-After-Free in atalk_ioctl
        https://gitee.com/openeuler/kernel/pulls/3757  Fix bugs from LTS patches
        https://gitee.com/openeuler/kernel/pulls/3770  ext4: fix uninitialized ratelimit_state->lock access in __ext4_fill_super()
        https://gitee.com/openeuler/kernel/pulls/3803  net/sched: cbs: Fix not adding cbs instance to list
        https://gitee.com/openeuler/kernel/pulls/3823  [sync] PR-3822:  ext4: fix kernel BUG in 'ext4_write_inline_data_end()'
        https://gitee.com/openeuler/kernel/pulls/3862  linux-4.19.y inclusion(4.19.299..4.19.303) part1
        https://gitee.com/openeuler/kernel/pulls/3863  linux-4.19.y inclusion(4.19.299..4.19.303) part2
        https://gitee.com/openeuler/kernel/pulls/3847  nvmet: nul-terminate the NQNs passed in the connect command
        https://gitee.com/openeuler/kernel/pulls/3845  netfilter: ctnetlink: fix possible refcount leak in ctnetlink_create_conntrack()
        https://gitee.com/openeuler/kernel/pulls/3768  iomap: add support to track dirty state of sub pages

OLK-6.6:
20240112：
OLK-6.6进展同步：
继承特性回合事项：
         截至1月12日，新分支已合入PR 133个，补丁 2356个
         已合入特性PR：
         调度：QOS SCHED特性 https://gitee.com/openeuler/kernel/pulls/3383
              steal task特性 https://gitee.com/openeuler/kernel/pulls/3712
              潮汐affinity特性 https://gitee.com/openeuler/kernel/pulls/3573
              qos smt expeller相关特性 https://gitee.com/openeuler/kernel/pulls/3734 & https://gitee.com/openeuler/kernel/pulls/3747
         内存：内存可靠性分级 https://gitee.com/openeuler/kernel/pulls/3921
              userswap特性 https://gitee.com/openeuler/kernel
              
              
              /pulls/3352
              machine check safe特性 https://gitee.com/openeuler/kernel/pulls/3280
              Per-memcg swap control https://gitee.com/openeuler/kernel/pulls/3894
              add memmap interface to reserved memory https://gitee.com/openeuler/kernel/pulls/3722
              MEMCG QOS特性 https://gitee.com/openeuler/kernel/pulls/3638
              Cgroup统计内存文件具体占用信息特性 https://gitee.com/openeuler/kernel/pulls/3528
              Add support for page cache limit https://gitee.com/openeuler/kernel/pulls/3722
              kfence增强特性 https://gitee.com/openeuler/kernel/pulls/3897
         网络：TCP压缩特性 https://gitee.com/openeuler/kernel/pulls/3732
         文件系统：
              打印脏页特性 https://gitee.com/openeuler/kernel/pulls/3899
         安全：arm32/ppc64 kaslr https://gitee.com/openeuler/kernel/pulls/3525 & https://gitee.com/openeuler/kernel/pulls/3475
         CGROUP:file cgroup支持特性 https://gitee.com/openeuler/kernel/pulls/3588
                memcg reclaim and cgroup kill https://gitee.com/openeuler/kernel/pulls/3431
                psi: support psi under cgroup v1 https://gitee.com/openeuler/kernel/pulls/3785
         调测：arm32/arm64/ppc32/ppc64/x86 livepatch支持 https://gitee.com/openeuler/kernel/pulls/3542
         ......
KABI专项：
         1.KABI白名单初稿正在输出；
         2.已提KABI预留PR：
         kabi: mm: add kabi reserve for mm structure https://gitee.com/openeuler/kernel/pulls/3959
         kabi: net: reserve space for net https://gitee.com/openeuler/kernel/pulls/3500
         x86: Add x86 related kabi reservations https://gitee.com/openeuler/kernel/pulls/3695
         kabi: Reserve space for perf subsystem related structures https://gitee.com/openeuler/kernel/pulls/3903
         kabi: reserve space for bpf related structures https://gitee.com/openeuler/kernel/pulls/3877
         kabi reserve for memcg and cgroup_bpf https://gitee.com/openeuler/kernel/pulls/3856
         KABI reservation for IMA and crypto https://gitee.com/openeuler/kernel/pulls/3669
处理器支持专项：
         处理器支持PR统计: 兆芯 27个，龙芯3个，飞腾1个，海光11个，合芯1个，RISCV 1个；
         兆芯：
         Add support for Zhaoxin Processors https://gitee.com/openeuler/kernel/pulls/3098
         x86/mce: Add Centaur MCA support https://gitee.com/openeuler/kernel/pulls/3102
         Add support for Zhaoxin HDAC and codec https://gitee.com/openeuler/kernel/pulls/3124
         Driver for Zhaoxin Serial ATA IDE https://gitee.com/openeuler/kernel/pulls/3125
         Driver for Zhaoxin HW Random Number Generator https://gitee.com/openeuler/kernel/pulls/3126
         Driver for Zhaoxin AES and SHA algorithm https://gitee.com/openeuler/kernel/pulls/3129
         Driver for Zhaoxin CPU core temperature monitoring https://gitee.com/openeuler/kernel/pulls/3131
         USB:Fix kernel NULL pointer when unbind UHCI form vfio-pci https://gitee.com/openeuler/kernel/pulls/3132
         iommu/vt-d:Add support for detecting ACPI device in RMRR https://gitee.com/openeuler/kernel/pulls/3133
         ......
         龙芯：
         LoongArch: add old BPI compatibility https://gitee.com/openeuler/kernel/pulls/3137
         LoongArch: add cpufreq and ls2k500 bmc support https://gitee.com/openeuler/kernel/pulls/3323
         LoongArch: fix some pci problems https://gitee.com/openeuler/kernel/pulls/3444
         飞腾：
         Add Phytium support for S2500 https://gitee.com/openeuler/kernel/pulls/3133
         海光：
         Add support for Hygon model 5h CPU cache https://gitee.com/openeuler/kernel/pulls/3830
         Add support for loading Hygon microcode https://gitee.com/openeuler/kernel/pulls/3831
         Add support for Hygon model 4h IOAPIC https://gitee.com/openeuler/kernel/pulls/3834
         Add support for Hygon model 6h L3 PMU https://gitee.com/openeuler/kernel/pulls/3835
         Add support for Hygon model 4h QoS https://gitee.com/openeuler/kernel/pulls/3836
         Add support for Hygon model 4h northbridge https://gitee.com/openeuler/kernel/pulls/3837
         Add support for Hygon model 4h EDAC https://gitee.com/openeuler/kernel/pulls/3838
         Add support for Hygon model 4h k10temp https://gitee.com/openeuler/kernel/pulls/3839
         Remove Hygon SMBus IMC detecting https://gitee.com/openeuler/kernel/pulls/3840
         Add support for Hygon family 18h model 5h HD-Audio https://gitee.com/openeuler/kernel/pulls/3841
         合芯：
         arch/powerpc: add ppc little endian openuler defconfig https://gitee.com/openeuler/kernel/pulls/3742
         RISCV:
         Add initial openeuler_defconfig for riscv64 https://gitee.com/openeuler/kernel/pulls/3670
         review过程中发现共性问题，针对这些问题提出如下建议：
         1.不要把所有模块的补丁都提到一个PR中，建议一个模块创建一个issue，对应提交一个PR，PR功能验证情况填到issue中作为合入条件之一；
         2.处理器支持的PR做好侵入式修改管控，避免影响其他处理器平台；
内核编译专项：
         1.config相关PR:
         Add initial openeuler_defconfig for arm64 and x86 https://gitee.com/openeuler/kernel/pulls/2900
         openeuler_defconfig: enable some mm https://gitee.com/openeuler/kernel/pulls/3111
         openeuler_defconfig: enable CONFIG_EROFS_FS_ONDEMAND for x86 and arm64 https://gitee.com/openeuler/kernel/pulls/3619
         openeuler_defconfig: enable CONFIG_UNICODE for x86 and arm64 https://gitee.com/openeuler/kernel/pulls/3605
         enable ARM64/X86 CONFIG_XDP_SOCKET、CONFIG_XDP_SOCKETS_DIAG config https://gitee.com/openeuler/kernel/pulls/3696
         enable ARM64/X86 CONFIG_BPF_LSM config https://gitee.com/openeuler/kernel/pulls/3697
         enable ARM64/X86_64 CONFIG_MPTCP/CONFIG_MPTCP_IPV6 config https://gitee.com/openeuler/kernel/pulls/3698
         Enable CONFIG_IOMMUFD and CONFIG_VFIO_DEVICE_CDEV in x86/arm64 defconfig https://gitee.com/openeuler/kernel/pulls/3699
         openeuler_defconfig: set CONFIG_NODES_SHIFT to 8 for both x86_64/ARM64 https://gitee.com/openeuler/kernel/pulls/3886
         2. kernel rpm包构建， 合入tag到6.6.0-2.0.0

议题二：待申报
Yunsilicon XSC RDMA驱动添加自动加载的udev规则 · Issue #I8TFYM · openEuler/kernel - Gitee.com

三、本期遗留问题

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
