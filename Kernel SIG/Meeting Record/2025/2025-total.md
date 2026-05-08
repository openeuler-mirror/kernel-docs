```
【2025/12/19 Kernel SIG 双周例会】
轮值主持：廖涛【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：李楠
会议链接：https://meeting.huaweicloud.com:36443/#/j/962719880
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-295.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-293.0.0 更新至 5.10.0-295.0.0, 回合补丁数78个
        git log 5.10.0-293.0.0..5.10.0-295.0.0 --oneline --no-merges | wc -l
CVE: (40)
CVE-2025-37776  https://gitee.com/openeuler/kernel/pulls/19450 
CVE-2025-38561  https://gitee.com/openeuler/kernel/pulls/19449 
CVE-2025-40271  https://gitee.com/openeuler/kernel/pulls/19539 
CVE-2025-40322  https://gitee.com/openeuler/kernel/pulls/19645 
CVE-2024-57907  https://gitee.com/openeuler/kernel/pulls/19315 
CVE-2024-58034  https://gitee.com/openeuler/kernel/pulls/19445 
CVE-2025-38729  https://gitee.com/openeuler/kernel/pulls/18648 
CVE-2023-53254  https://gitee.com/openeuler/kernel/pulls/19651 
CVE-2025-38618  https://gitee.com/openeuler/kernel/pulls/19567 
CVE-2025-39851  https://gitee.com/openeuler/kernel/pulls/19522 
CVE-2025-37927  https://gitee.com/openeuler/kernel/pulls/19418 
CVE-2023-53466  https://gitee.com/openeuler/kernel/pulls/19606 
CVE-2025-38572  https://gitee.com/openeuler/kernel/pulls/19565 
CVE-2025-38706  https://gitee.com/openeuler/kernel/pulls/19003 
CVE-2025-38664  https://gitee.com/openeuler/kernel/pulls/19566 
CVE-2025-40105  https://gitee.com/openeuler/kernel/pulls/19540 
CVE-2025-22039  https://gitee.com/openeuler/kernel/pulls/19384 
CVE-2025-37789  https://gitee.com/openeuler/kernel/pulls/19425 
CVE-2025-38734  https://gitee.com/openeuler/kernel/pulls/19572 
CVE-2022-49196  https://gitee.com/openeuler/kernel/pulls/19542 
CVE-2025-39756  https://gitee.com/openeuler/kernel/pulls/19538 
CVE-2023-53520  https://gitee.com/openeuler/kernel/pulls/19573 
CVE-2025-38250  https://gitee.com/openeuler/kernel/pulls/19428 
CVE-2025-40102  https://gitee.com/openeuler/kernel/pulls/19523 
CVE-2025-38201  https://gitee.com/openeuler/kernel/pulls/19427 
CVE-2025-40190  https://gitee.com/openeuler/kernel/pulls/19537 
CVE-2025-39901  https://gitee.com/openeuler/kernel/pulls/19571 
CVE-2025-38617  https://gitee.com/openeuler/kernel/pulls/19569 
CVE-2023-53491  https://gitee.com/openeuler/kernel/pulls/19583 
CVE-2024-57911  https://gitee.com/openeuler/kernel/pulls/19534 
CVE-2025-40018  https://gitee.com/openeuler/kernel/pulls/19570 
CVE-2025-21905  https://gitee.com/openeuler/kernel/pulls/19308 
CVE-2025-22020  https://gitee.com/openeuler/kernel/pulls/19431 
CVE-2025-37749  https://gitee.com/openeuler/kernel/pulls/19424 
CVE-2025-22083  https://gitee.com/openeuler/kernel/pulls/19420 
CVE-2025-23158  https://gitee.com/openeuler/kernel/pulls/19419 
CVE-2025-22022  https://gitee.com/openeuler/kernel/pulls/19443 
CVE-2023-53673  https://gitee.com/openeuler/kernel/pulls/19574 
CVE-2025-21968  https://gitee.com/openeuler/kernel/pulls/19543 
CVE-2025-38022  https://gitee.com/openeuler/kernel/pulls/19426 
Bugfix:
mainline patch backport
                https://gitee.com/openeuler/kernel/pulls/19498 
net:don't dump stack on queue timeout
                https://gitee.com/openeuler/kernel/pulls/19349 
Bluetooth: MGMT: Fix deadlock in mgmt_pending_lock
                https://gitee.com/openeuler/kernel/pulls/19664 
smb: client: fix mid_q_entry memleak leak with per-mid locking
                https://gitee.com/openeuler/kernel/pulls/19399 
net/oenetcls: Prioritize oenetcls hooks over rps
                https://gitee.com/openeuler/kernel/pulls/19578 
arm64: kdump: Skip kmemleak scan reserved memory for kdump
                https://gitee.com/openeuler/kernel/pulls/19461 
Bugfix for three issues
                https://gitee.com/openeuler/kernel/pulls/19575 
iommu/arm-smmu-v3-sva: Fix mm use-after-free
                https://gitee.com/openeuler/kernel/pulls/19681 
海思：
RDMA/hns: Fix a memory issue in roce bonding
                https://gitee.com/openeuler/kernel/pulls/19436 
兆芯：
[OLK-5.10] Add platform-specific quirks for ZX-200 device
                https://gitee.com/openeuler/kernel/pulls/19065 
[OLK-5.10] ata: zhaoxin: update for rename symbols
                https://gitee.com/openeuler/kernel/pulls/18979 
海光：
[OLK-5.10] Backport upstream bugfix or cleanup patches for SEV{-ES} - part1
                https://gitee.com/openeuler/kernel/pulls/19075 
[OLK-5.10] Backport the patch that allows guest access to the EFI confidential computing secret area
                https://gitee.com/openeuler/kernel/pulls/19046 

OLK-6.6进展同步
    tag更新到6.6.0-130.0.0
        ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数1054个
    git log 6.6.0-120.0.0..6.6.0-130.0.0 --oneline --no-merges | wc -l
CVE(131)
        CVE-2025-40134    https://gitee.com/openeuler/kernel/pulls/19119 
        CVE-2025-39677    https://gitee.com/openeuler/kernel/pulls/19368 
        CVE-2025-37892    https://gitee.com/openeuler/kernel/pulls/18029 
        CVE-2025-40206    https://gitee.com/openeuler/kernel/pulls/19274 
        CVE-2025-40082    https://gitee.com/openeuler/kernel/pulls/19133 
        CVE-2025-40074    https://gitee.com/openeuler/kernel/pulls/19306 
        CVE-2025-22022    https://gitee.com/openeuler/kernel/pulls/19442 
        CVE-2025-40049    https://gitee.com/openeuler/kernel/pulls/19271 
        CVE-2025-40167    https://gitee.com/openeuler/kernel/pulls/19136 
        CVE-2025-40088    https://gitee.com/openeuler/kernel/pulls/19117 
        CVE-2025-40194    https://gitee.com/openeuler/kernel/pulls/19030 
        CVE-2025-38234    https://gitee.com/openeuler/kernel/pulls/19293 
        CVE-2025-37861    https://gitee.com/openeuler/kernel/pulls/19263 
        CVE-2025-38100    https://gitee.com/openeuler/kernel/pulls/19179 
        CVE-2025-40035    https://gitee.com/openeuler/kernel/pulls/19209 
        CVE-2025-40125    https://gitee.com/openeuler/kernel/pulls/19057 
        CVE-2025-38666    https://gitee.com/openeuler/kernel/pulls/19175 
        CVE-2025-38729    https://gitee.com/openeuler/kernel/pulls/18647 
        CVE-2017-13694    https://gitee.com/openeuler/kernel/pulls/19177 
        CVE-2025-38664    https://gitee.com/openeuler/kernel/pulls/19598 
        CVE-2025-39801    https://gitee.com/openeuler/kernel/pulls/18794 
        CVE-2025-40183    https://gitee.com/openeuler/kernel/pulls/19224 
        CVE-2025-38214    https://gitee.com/openeuler/kernel/pulls/19178 
        CVE-2025-38231    https://gitee.com/openeuler/kernel/pulls/19248 
        CVE-2025-40322    https://gitee.com/openeuler/kernel/pulls/19647 
        CVE-2025-38058    https://gitee.com/openeuler/kernel/pulls/19266 
        CVE-2025-40204    https://gitee.com/openeuler/kernel/pulls/19222 
        CVE-2025-38084    https://gitee.com/openeuler/kernel/pulls/19282 
        CVE-2024-58095    https://gitee.com/openeuler/kernel/pulls/18704 
        CVE-2025-23133    https://gitee.com/openeuler/kernel/pulls/19377 
        CVE-2025-39940    https://gitee.com/openeuler/kernel/pulls/19294 
        CVE-2025-38614    https://gitee.com/openeuler/kernel/pulls/19268 
        CVE-2025-39710    https://gitee.com/openeuler/kernel/pulls/19269 
        CVE-2025-39881    https://gitee.com/openeuler/kernel/pulls/19416 
        CVE-2025-40164    https://gitee.com/openeuler/kernel/pulls/19291 
        CVE-2025-39994    https://gitee.com/openeuler/kernel/pulls/19410 
        CVE-2025-39911    https://gitee.com/openeuler/kernel/pulls/19366 
        CVE-2025-37972    https://gitee.com/openeuler/kernel/pulls/19252 
        CVE-2025-40190    https://gitee.com/openeuler/kernel/pulls/19137 
        CVE-2025-39810    https://gitee.com/openeuler/kernel/pulls/19152 
        CVE-2025-38501    https://gitee.com/openeuler/kernel/pulls/18760 
        CVE-2025-38717    https://gitee.com/openeuler/kernel/pulls/18644 
        CVE-2025-37822    https://gitee.com/openeuler/kernel/pulls/19354 
        CVE-2025-38636    https://gitee.com/openeuler/kernel/pulls/19441 
        CVE-2025-39839    https://gitee.com/openeuler/kernel/pulls/19048 
        CVE-2025-22026    https://gitee.com/openeuler/kernel/pulls/19323 
        CVE-2025-40202    https://gitee.com/openeuler/kernel/pulls/19203 
        CVE-2025-40139    https://gitee.com/openeuler/kernel/pulls/19409 
        CVE-2025-39827    https://gitee.com/openeuler/kernel/pulls/19072 
        CVE-2025-38220    https://gitee.com/openeuler/kernel/pulls/19212 
        CVE-2025-38331    https://gitee.com/openeuler/kernel/pulls/18797 
        CVE-2025-40192    https://gitee.com/openeuler/kernel/pulls/19190 
        CVE-2025-40104    https://gitee.com/openeuler/kernel/pulls/19364 
        CVE-2025-40200    https://gitee.com/openeuler/kernel/pulls/19191 
        CVE-2025-38282    https://gitee.com/openeuler/kernel/pulls/19267 
        CVE-2025-40012    https://gitee.com/openeuler/kernel/pulls/19131 
        CVE-2025-22039    https://gitee.com/openeuler/kernel/pulls/18664 
        CVE-2025-38713    https://gitee.com/openeuler/kernel/pulls/18613 
        CVE-2025-40110    https://gitee.com/openeuler/kernel/pulls/19167 
        CVE-2025-40198    https://gitee.com/openeuler/kernel/pulls/19110 
        CVE-2025-38581    https://gitee.com/openeuler/kernel/pulls/19176 
        CVE-2025-40040    https://gitee.com/openeuler/kernel/pulls/19316 
        CVE-2025-39992    https://gitee.com/openeuler/kernel/pulls/18830 
        CVE-2025-37899    https://gitee.com/openeuler/kernel/pulls/19374 
        CVE-2025-38706    https://gitee.com/openeuler/kernel/pulls/18634 
        CVE-2025-39931    https://gitee.com/openeuler/kernel/pulls/19193 
        CVE-2025-38005    https://gitee.com/openeuler/kernel/pulls/19247 
        CVE-2025-40061    https://gitee.com/openeuler/kernel/pulls/19371 
        CVE-2025-40176    https://gitee.com/openeuler/kernel/pulls/19272 
        CVE-2025-38588    https://gitee.com/openeuler/kernel/pulls/19597 
        CVE-2025-40129    https://gitee.com/openeuler/kernel/pulls/19226 
        CVE-2025-39684    https://gitee.com/openeuler/kernel/pulls/19156 
        CVE-2025-39866    https://gitee.com/openeuler/kernel/pulls/19310 
        CVE-2025-40111    https://gitee.com/openeuler/kernel/pulls/19230 
        CVE-2025-39692    https://gitee.com/openeuler/kernel/pulls/19125 
        CVE-2025-39736    https://gitee.com/openeuler/kernel/pulls/18791 
        CVE-2025-40178    https://gitee.com/openeuler/kernel/pulls/19303 
        CVE-2025-40266    https://gitee.com/openeuler/kernel/pulls/19552 
        CVE-2025-38477    https://gitee.com/openeuler/kernel/pulls/19367 
        CVE-2025-39694    https://gitee.com/openeuler/kernel/pulls/19124 
        CVE-2025-38436    https://gitee.com/openeuler/kernel/pulls/19438 
        CVE-2025-22107    https://gitee.com/openeuler/kernel/pulls/18496 
        CVE-2025-39996    https://gitee.com/openeuler/kernel/pulls/19361 
        CVE-2025-38663    https://gitee.com/openeuler/kernel/pulls/18345 
        CVE-2025-39947    https://gitee.com/openeuler/kernel/pulls/19365 
        CVE-2025-40052    https://gitee.com/openeuler/kernel/pulls/19401 
        CVE-2025-39790    https://gitee.com/openeuler/kernel/pulls/18661 
        CVE-2025-40043    https://gitee.com/openeuler/kernel/pulls/19111 
        CVE-2025-37994    https://gitee.com/openeuler/kernel/pulls/19393 
        CVE-2025-39817    https://gitee.com/openeuler/kernel/pulls/19256 
        CVE-2025-37956    https://gitee.com/openeuler/kernel/pulls/19251 
        CVE-2025-38617    https://gitee.com/openeuler/kernel/pulls/19601 
        CVE-2025-39675    https://gitee.com/openeuler/kernel/pulls/19157 
        CVE-2025-39737    https://gitee.com/openeuler/kernel/pulls/18615 
        CVE-2025-39732    https://gitee.com/openeuler/kernel/pulls/19205 
        CVE-2025-39901    https://gitee.com/openeuler/kernel/pulls/19696 
        CVE-2025-39825    https://gitee.com/openeuler/kernel/pulls/19415 
        CVE-2025-38714    https://gitee.com/openeuler/kernel/pulls/18632 
        CVE-2025-40171    https://gitee.com/openeuler/kernel/pulls/19115 
        CVE-2025-38109    https://gitee.com/openeuler/kernel/pulls/19446 
        CVE-2025-40140    https://gitee.com/openeuler/kernel/pulls/19207 
        CVE-2025-38566    https://gitee.com/openeuler/kernel/pulls/19412 
        CVE-2025-38105    https://gitee.com/openeuler/kernel/pulls/18948 
        CVE-2025-40016    https://gitee.com/openeuler/kernel/pulls/19358 
        CVE-2025-38443    https://gitee.com/openeuler/kernel/pulls/19311 
        CVE-2025-37891    https://gitee.com/openeuler/kernel/pulls/19182 
        CVE-2025-37997    https://gitee.com/openeuler/kernel/pulls/18837 
        CVE-2025-38705    https://gitee.com/openeuler/kernel/pulls/18653 
        CVE-2025-39751    https://gitee.com/openeuler/kernel/pulls/18636 
        CVE-2025-40084    https://gitee.com/openeuler/kernel/pulls/19114 
        CVE-2025-39766    https://gitee.com/openeuler/kernel/pulls/18867 
        CVE-2025-38071    https://gitee.com/openeuler/kernel/pulls/19386 
        CVE-2025-38457    https://gitee.com/openeuler/kernel/pulls/19429 
        CVE-2025-37973    https://gitee.com/openeuler/kernel/pulls/19253 
        CVE-2025-40120    https://gitee.com/openeuler/kernel/pulls/19216 
        CVE-2025-39697    https://gitee.com/openeuler/kernel/pulls/19411 
        CVE-2025-39938    https://gitee.com/openeuler/kernel/pulls/19113 
        CVE-2025-40053    https://gitee.com/openeuler/kernel/pulls/19206 
        CVE-2025-39964    https://gitee.com/openeuler/kernel/pulls/19213 
        CVE-2025-40173    https://gitee.com/openeuler/kernel/pulls/19273 
        CVE-2025-40211    https://gitee.com/openeuler/kernel/pulls/19211 
        CVE-2025-39703    https://gitee.com/openeuler/kernel/pulls/19118 
        CVE-2025-38688    https://gitee.com/openeuler/kernel/pulls/19620 
        CVE-2025-38712    https://gitee.com/openeuler/kernel/pulls/18780 
        CVE-2025-40187    https://gitee.com/openeuler/kernel/pulls/19223 
        CVE-2025-38361    https://gitee.com/openeuler/kernel/pulls/19355 
        CVE-2025-40141    https://gitee.com/openeuler/kernel/pulls/19134 
        CVE-2025-40055    https://gitee.com/openeuler/kernel/pulls/19151 
        CVE-2025-38697    https://gitee.com/openeuler/kernel/pulls/18861 
        CVE-2025-37777    https://gitee.com/openeuler/kernel/pulls/17888 
        CVE-2025-40048    https://gitee.com/openeuler/kernel/pulls/19007 

Bugfix(55)
init/Kconfig: Move ARCH_SUPPORTS_SCHED_SOFT_QUOTA to drop CGROUPS dependency
        https://gitee.com/openeuler/kernel/pulls/19257 
[OLK-6.6] backport important bugfix for Broadcom NIC driver from upstream linux-6.6.y
        https://gitee.com/openeuler/kernel/pulls/19383 
RDMA/bnxt_re: Fix budget handling of notification queue
        https://gitee.com/openeuler/kernel/pulls/18451 
v3  xsched: add xsched_{set,get}attr syscall
        https://gitee.com/openeuler/kernel/pulls/19390 
scsi: mpi3mr: Fetch correct device dev handle for status reply descriptor
        https://gitee.com/openeuler/kernel/pulls/19086 
NFSv4: Fix deadlock during the running of state manager
        https://gitee.com/openeuler/kernel/pulls/19220 
bpf: Avoid RCU context warning when unpinning htab with internal structs
        https://gitee.com/openeuler/kernel/pulls/19227 
[OLK-6.6] Fix CVE-2025-40082
        https://gitee.com/openeuler/kernel/pulls/19133 
[OLK-6.6][linux-6.6.y sync] Backport 6.6.88-6.6.89 LTS Patches
        https://gitee.com/openeuler/kernel/pulls/19143 
mm: try skipping pinned page before unmapping in migration
        https://gitee.com/openeuler/kernel/pulls/19709 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.68-6.6.69 LTS Conflicts Patches
        https://gitee.com/openeuler/kernel/pulls/17056 
sched: Fix race between yield_to() and try_to_wake_up()
        https://gitee.com/openeuler/kernel/pulls/19346 
mm/numa_remote: fix wild-memory-access in numa_remote_hugetlb_nowatermark
        https://gitee.com/openeuler/kernel/pulls/19526 
scsi: mpi3mr: Split off bus_reset function from host_reset
        https://gitee.com/openeuler/kernel/pulls/19078 
iommu/vt-d: debugfs: Fix legacy mode page table dump logic
        https://gitee.com/openeuler/kernel/pulls/19195 
XSched: List Corruption
        https://gitee.com/openeuler/kernel/pulls/19702 
scsi: mpi3mr: Add support for status reply descriptor
        https://gitee.com/openeuler/kernel/pulls/19085 
[OLK-6.6][linux-6.6.y sync] Backport 6.6.87-6.6.88 LTS Patches
        https://gitee.com/openeuler/kernel/pulls/18978 
scsi: mpi3mr: Replace deprecated strncpy() with assignments
        https://gitee.com/openeuler/kernel/pulls/19092 
arm64/mpam: Add build dependencies for CONFIG_RESCTRL_IOMMU
        https://gitee.com/openeuler/kernel/pulls/19052 
zcopy: Fix context switch within RCU read-side
        https://gitee.com/openeuler/kernel/pulls/19339 
scsi: mpi3mr: Set MPI request flags appropriately
        https://gitee.com/openeuler/kernel/pulls/19095 
smb: client: fix mid_q_entry memleak leak with per-mid locking
        https://gitee.com/openeuler/kernel/pulls/19400 
bpf: Sync pending IRQ work before freeing ring buffer
        https://gitee.com/openeuler/kernel/pulls/19334 
[OLK-6.6][linux-6.6.y sync] Backport 6.6.89-6.6.90 LTS Patches
        https://gitee.com/openeuler/kernel/pulls/19166 
Bugfix for two issues
        https://gitee.com/openeuler/kernel/pulls/19576 
v2  bugfix for xcall2.0
        https://gitee.com/openeuler/kernel/pulls/19398 
xsched: prevent linked list corruption in RT priority updates
        https://gitee.com/openeuler/kernel/pulls/19683 
Fix UAF issue for mfs
        https://gitee.com/openeuler/kernel/pulls/19557 
xsched: XCU Partition
        https://gitee.com/openeuler/kernel/pulls/19624 
xsched: move xsched types to user-accessible headers
        https://gitee.com/openeuler/kernel/pulls/19738 
task_work: Fix NMI race condition
        https://gitee.com/openeuler/kernel/pulls/19475 
scsi: mpi3mr: Clear ioctl blocking flag for an unresponsive controller
        https://gitee.com/openeuler/kernel/pulls/19097 
xsched: XCU Partition
        https://gitee.com/openeuler/kernel/pulls/19285 
[OLK-6.6] xhci: fix memory leak regression when freeing xhci vdev devices depth first
        https://gitee.com/openeuler/kernel/pulls/18479 
Fix some memory policy bugfix
        https://gitee.com/openeuler/kernel/pulls/19507 
Fixes and cleanup of page cache limit
        https://gitee.com/openeuler/kernel/pulls/19392 
[OLK-6.6] Fix CVE-2025-38105
        https://gitee.com/openeuler/kernel/pulls/18948 
xsched: fix compile error when CONFIG_XCU_SCHEDULER is disabled
        https://gitee.com/openeuler/kernel/pulls/19414 
Fix unexpected behavior in resctrl mounting
        https://gitee.com/openeuler/kernel/pulls/19530 
crash: fix crashkernel resource shrink
        https://gitee.com/openeuler/kernel/pulls/19141 
zcopy: fix two issues
        https://gitee.com/openeuler/kernel/pulls/19513 
v7  bugfix for xcall2.0
        https://gitee.com/openeuler/kernel/pulls/19341 
sched: Fix incorrect cluster mask
        https://gitee.com/openeuler/kernel/pulls/19402 
ASoC: Intel: bytcr_rt5651: Fix invalid quirk input mapping
        https://gitee.com/openeuler/kernel/pulls/19194 
xsched: XCU Partition
        https://gitee.com/openeuler/kernel/pulls/19460 
xsched: simplify logging macros by removing redundant pr_fmt usage
        https://gitee.com/openeuler/kernel/pulls/19657 
arm64/mpam: Reset mbwu_state while creating new monitor group
        https://gitee.com/openeuler/kernel/pulls/19519 
Some bugfixes for interference
        https://gitee.com/openeuler/kernel/pulls/19636 
blk-ioinf: accumulate total latency properly across sampling periods
        https://gitee.com/openeuler/kernel/pulls/19292 
[sync] PR-19363:  Revert "scsi: libsas: Fix exp-attached device scan after probe failure scanned in again after probe failed"
        https://gitee.com/openeuler/kernel/pulls/19388 
kvm: Only enable shadow mode for ioeventfd and Align the lifecycle of …
        https://gitee.com/openeuler/kernel/pulls/17661 
Add Support for Disabling Hugetlb in soft_offline_page
        https://gitee.com/openeuler/kernel/pulls/19300 
nfsd: provide locking for v4_end_grace
        https://gitee.com/openeuler/kernel/pulls/19237 
gmem: fix several issues
        https://gitee.com/openeuler/kernel/pulls/19517 

海光
[OLK-6.6] fix possible crash caused by null pointer when hct get page.
        https://gitee.com/openeuler/kernel/pulls/19486 

龙芯
LoongArch: Mask all interrupts during kexec/kdump
        https://gitee.com/openeuler/kernel/pulls/19680 
Loongarch: Enable CONFIG_RANDOMIZE_BASE default
        https://gitee.com/openeuler/kernel/pulls/19682 

申威
[OLK-6.6]:update patches for sw64 architecture
        https://gitee.com/openeuler/kernel/pulls/19405 

飞腾
[OLK-6.6] PCI: phytium: Add hotplug and hotreset workaround patch for phytium SoCs
        https://gitee.com/openeuler/kernel/pulls/18003 

兆芯
[OLK-6.6] Add platform-specific quirks for ZX-200 device
        https://gitee.com/openeuler/kernel/pulls/18481 
[OLK-6.6] ALSA: HDA: Add Zhaoxin HDMI Controller and Codec support
        https://gitee.com/openeuler/kernel/pulls/18453 
[OLK-6.6] x86/hpet: Set dynamic IRQ feature for HPET for KH-50000
        https://gitee.com/openeuler/kernel/pulls/18483 

海思
hisi_acc_vfio_pci: adapt to new migration configuration
        https://gitee.com/openeuler/kernel/pulls/19329 
crypto: hisilicon/qm - fix incorrect judgment in qm_get_complete_eqe_num()
        https://gitee.com/openeuler/kernel/pulls/19435 
drm/hisilicon/hibmc: fix PCIe 64-bit bar support
        https://gitee.com/openeuler/kernel/pulls/19714 
ub: hisi-ubus: Fix ub memory decoder create
        https://gitee.com/openeuler/kernel/pulls/19359 
net: hns3: remove VF multi-TC compat bit
        https://gitee.com/openeuler/kernel/pulls/19447 
ub: ubase: Remove useless character '+'
        https://gitee.com/openeuler/kernel/pulls/19317 
net: unic: Add support for uboe and ethernet related tools
        https://gitee.com/openeuler/kernel/pulls/19287 
crypto: hisilicon - some bugfix
        https://gitee.com/openeuler/kernel/pulls/19634 
urma: bugfix ubagg drivers refent error
        https://gitee.com/openeuler/kernel/pulls/19433 
ub:hisi-ubus: Adding compatibility Interfaces for ub memory
        https://gitee.com/openeuler/kernel/pulls/19328 
perf arm-spe: Add support for SPE Data Source packet on HiSilicon HIP12
        https://gitee.com/openeuler/kernel/pulls/19553 
ubcore: fix route_list when no full match.
        https://gitee.com/openeuler/kernel/pulls/19659 
uvb: change dir name
        https://gitee.com/openeuler/kernel/pulls/19521 
urma: Bugfix for ubcore_get_route_list implement
        https://gitee.com/openeuler/kernel/pulls/19468 
ubios_uvb: add msleep in poll thread
        https://gitee.com/openeuler/kernel/pulls/19357 
ub: ub_fwctl: add ub_fwctl driver-api documentation description
        https://gitee.com/openeuler/kernel/pulls/19327 
uburma: add tp_type in urma ioctl operation.
        https://gitee.com/openeuler/kernel/pulls/19161 
crypto: hisilicon - add reference counting to queues for tfm kernel reuse
        https://gitee.com/openeuler/kernel/pulls/19494 
net: hns3: add VLAN id validation before using
        https://gitee.com/openeuler/kernel/pulls/19532 
ub:ubfi: Fix UBFI memory leak issue
        https://gitee.com/openeuler/kernel/pulls/19628 
ubcore: fix query route list by eid pair.
        https://gitee.com/openeuler/kernel/pulls/19353 
ub: udma: Bugfix related to crq event unregister.
        https://gitee.com/openeuler/kernel/pulls/19687 
Documentation: Add opensource document for ubase&unic&ubl
        https://gitee.com/openeuler/kernel/pulls/19165 
crypto: hisilicon/trng - Fix the issue where TRNG cannot be used by multiple threads.
        https://gitee.com/openeuler/kernel/pulls/19585 
ub: ubase&unic: Fix some bug finding in running the driver
        https://gitee.com/openeuler/kernel/pulls/19616 
ub: libcdma: add eid upi update response
        https://gitee.com/openeuler/kernel/pulls/19677 
ub:ubus: add active_mutex in ub_entity
        https://gitee.com/openeuler/kernel/pulls/19589 
ub:hisi-ubus: fix MUE unreg msg rsp time
        https://gitee.com/openeuler/kernel/pulls/19641 
iommu/ummu: Add UMMU documentation description
        https://gitee.com/openeuler/kernel/pulls/19330 
Handling Kunpeng Chip ARM Spectre-BHB (CVE-2022-23960) Issue
        https://gitee.com/openeuler/kernel/pulls/19617 
urma: fixed process exiting uburma driver's private memory UAF
        https://gitee.com/openeuler/kernel/pulls/19609 
ub: ubase: Fix spell error of month
        https://gitee.com/openeuler/kernel/pulls/19639 
ub: ub_fwctl: Modify TP/TA/SCC register query process.
        https://gitee.com/openeuler/kernel/pulls/19608 
iommu/ummu: Fix UMMU documentation error
        https://gitee.com/openeuler/kernel/pulls/19338 
ub:ubus: Add ubus and ubfi opensource document
        https://gitee.com/openeuler/kernel/pulls/19305 
ub: udma: bugfix related to print location.
        https://gitee.com/openeuler/kernel/pulls/19637 
urma: added functions for getting and setting TP attribute fields.
        https://gitee.com/openeuler/kernel/pulls/19320 
ub: ub_fwctl: Modify the problem of incorret data when querying entry
        https://gitee.com/openeuler/kernel/pulls/19508 
iommu/ummu: Fix the issue of uninitialized resources in logic_ummu_viommu
        https://gitee.com/openeuler/kernel/pulls/19623 
ub: ubase: Improve performance and fix some bug
        https://gitee.com/openeuler/kernel/pulls/19278 
ub: udma: recent bugfix for udma.
        https://gitee.com/openeuler/kernel/pulls/19214 
ub: udma: add requirement about document and tp attr.
        https://gitee.com/openeuler/kernel/pulls/19332 
ub: bugfix of port, decoder and vfio
        https://gitee.com/openeuler/kernel/pulls/19555 
ub: cdma: add CDMA userspace-api documentation description
        https://gitee.com/openeuler/kernel/pulls/19264 
hisi_acc_vfio_pci: adapt to new migration configuration
urma: bugfix the issue of urma stream generation failure
        https://gitee.com/openeuler/kernel/pulls/19290 
Revert "RDMA/hns: Fix mismatch exception rollback"
        https://gitee.com/openeuler/kernel/pulls/19607 
ub: ubase: CtrlQ retry message uses the same seq
        https://gitee.com/openeuler/kernel/pulls/19688 
Revert "net: hns3: add support for queue bonding mode of flow director"
        https://gitee.com/openeuler/kernel/pulls/19243 
urma: fixing ubcore hash table initialization failure.
        https://gitee.com/openeuler/kernel/pulls/19391 
ub: udma: bugfix related to init xa flags.
        https://gitee.com/openeuler/kernel/pulls/19520 
ub: cdma: fix the timing issue during flow-based deregistration.
        https://gitee.com/openeuler/kernel/pulls/19563 
ub: udma: Support retrieving the migr field.
        https://gitee.com/openeuler/kernel/pulls/19337 
ub:ubus: bugfix port reset in cluster mode
        https://gitee.com/openeuler/kernel/pulls/19638 
ubagg: fix mismatched spin unlock.
        https://gitee.com/openeuler/kernel/pulls/19621 
KVM: arm64: ipiv: change declaration argument
        https://gitee.com/openeuler/kernel/pulls/19189 
Packet throughput decreases with multiple jetty streams
        https://gitee.com/openeuler/kernel/pulls/19661 
perf: Fix lastup for multi-CPU PG
        https://gitee.com/openeuler/kernel/pulls/19610 
add check ack msg and do sleep
        https://gitee.com/openeuler/kernel/pulls/19735 
IPIV: fix bug in live migration
        https://gitee.com/openeuler/kernel/pulls/19132 
add check ack_dono flag for reboot event
        https://gitee.com/openeuler/kernel/pulls/19551 
obmm: fix granu checking in mmap
        https://gitee.com/openeuler/kernel/pulls/19561 
obmm: sync obmm default params value to sysfs.
        https://gitee.com/openeuler/kernel/pulls/19558 
obmm: Race condition fix, mmap rollback fix and export_user flag check.
        https://gitee.com/openeuler/kernel/pulls/19717 
obmm: bugfixes of log and race condition
        https://gitee.com/openeuler/kernel/pulls/19674 
obmm: suppport unaligned PMD mapping
        https://gitee.com/openeuler/kernel/pulls/19644 
obmm: remove redundant code and fix log issues
        https://gitee.com/openeuler/kernel/pulls/19439 
net: fix the compile problem introduced by AF_UB
        https://gitee.com/openeuler/kernel/pulls/19045 
obmm: Ownership Based Memory Management framework
        https://gitee.com/openeuler/kernel/pulls/19100 
obmm: set MAX Numa Distance to 255
        https://gitee.com/openeuler/kernel/pulls/19560 
net: hibmcge: add support for pagepool on rx
        https://gitee.com/openeuler/kernel/pulls/19378 
[OLK-6.6] virtcca: fix incorrect use of the percpu declare
        https://gitee.com/openeuler/kernel/pulls/19562 
add sentry kmod
        https://gitee.com/openeuler/kernel/pulls/18870 
Fix incorrect use of cpuhp_remove_multi_state parameter
        https://gitee.com/openeuler/kernel/pulls/19592 
Fix SPI registration failure logging level
        https://gitee.com/openeuler/kernel/pulls/19116 


议题二： 申请更换loongarch领域committer (高巨鑫）
更换loongarch架构领域committer（从@Hongchen_Zhang更改为@robinorg) 

结论：通过。待办：1. 门禁修改（吴腾达）；2. 提交人员变更PR（吴腾达）；3. 提供新committer的信息 (高巨鑫）
新committer的信息: wangming01@loongson.cn
删除旧committer：Hongchen_Zhang

议题三：openEuler特性合入规范评审 - 吴腾达

结论：同意实施。后续提交PR至kernel-docs仓库，各kernel maintaner检视完成后合入。


议题四：sched_ext 特性支持评审并申请成为对应模块committer（车烈权、屈子程）
可编程调度sched_ext落入openEuler-26.09创新分支
https://gitee.com/openeuler/kernel/issues/IDE61A
https://gitee.com/openeuler/kernel/issues/IDE61D
https://gitee.com/openeuler/kernel/issues/ID7HLY

结论：同意接纳该特性，并同意新增申请committer，同时需得到调度模块相关负责人加分。


议题五：sched_ext 新建用户态策略库仓库（吴长冶/杨宸）

结论：同意。

三、遗留问题

-------------------------------------------------------------------------------------------------------------------------------------
【2025/12/5 Kernel SIG 双周例会】
轮值主持：吴腾达【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/964469206
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-293.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-291.0.0 更新至 5.10.0-293.0.0, 回合补丁数121个
        git log 5.10.0-291.0.0..5.10.0-293.0.0 --oneline --no-merges | wc -l
CVE: (31)
CVE-2025-40049  https://gitee.com/openeuler/kernel/pulls/19186 
CVE-2025-37997  https://gitee.com/openeuler/kernel/pulls/18836 
CVE-2025-40200  https://gitee.com/openeuler/kernel/pulls/19309 
CVE-2025-38005  https://gitee.com/openeuler/kernel/pulls/19246 
CVE-2025-40183  https://gitee.com/openeuler/kernel/pulls/19225 
CVE-2025-40178  https://gitee.com/openeuler/kernel/pulls/19299 
CVE-2025-40139  https://gitee.com/openeuler/kernel/pulls/19408 
CVE-2025-39994  https://gitee.com/openeuler/kernel/pulls/19413 
CVE-2025-22121  https://gitee.com/openeuler/kernel/pulls/18816 
CVE-2022-49470  https://gitee.com/openeuler/kernel/pulls/19396 
CVE-2025-37899  https://gitee.com/openeuler/kernel/pulls/19375 
CVE-2025-40074  https://gitee.com/openeuler/kernel/pulls/19307 
CVE-2025-37786  https://gitee.com/openeuler/kernel/pulls/19407 
CVE-2025-39817  https://gitee.com/openeuler/kernel/pulls/19255 
CVE-2025-39766  https://gitee.com/openeuler/kernel/pulls/18866 
CVE-2025-40204  https://gitee.com/openeuler/kernel/pulls/19406 
CVE-2025-39751  https://gitee.com/openeuler/kernel/pulls/19004 
CVE-2021-47653  https://gitee.com/openeuler/kernel/pulls/19283 
CVE-2025-40019  https://gitee.com/openeuler/kernel/pulls/19169 
CVE-2023-53510  https://gitee.com/openeuler/kernel/pulls/19259 
CVE-2025-21945  https://gitee.com/openeuler/kernel/pulls/19387 
CVE-2025-40111  https://gitee.com/openeuler/kernel/pulls/19232 
CVE-2025-40168  https://gitee.com/openeuler/kernel/pulls/19241 
CVE-2025-40194  https://gitee.com/openeuler/kernel/pulls/19164 
CVE-2025-37994  https://gitee.com/openeuler/kernel/pulls/19394 
CVE-2025-22107  https://gitee.com/openeuler/kernel/pulls/19380 
CVE-2024-58007  https://gitee.com/openeuler/kernel/pulls/19395 
CVE-2023-53282  https://gitee.com/openeuler/kernel/pulls/19295 
CVE-2025-40211  https://gitee.com/openeuler/kernel/pulls/19210 
CVE-2022-49267  https://gitee.com/openeuler/kernel/pulls/19379 
CVE-2025-38477  https://gitee.com/openeuler/kernel/pulls/19369 
Bugfix:
fuse: fix compile warning when CONFIG_FUSE_FASTPATH=y
                https://gitee.com/openeuler/kernel/pulls/19351 
Fixes of page cache limit
                https://gitee.com/openeuler/kernel/pulls/19347 
drm/omap: fix misleading indentation in pixinc()
                https://gitee.com/openeuler/kernel/pulls/19335 
[OLK-5.10] PCI/MSI: Set device flag indicating only 32-bit MSI support
                https://gitee.com/openeuler/kernel/pulls/15328 
sched: Fix incorrect cluster mask
                https://gitee.com/openeuler/kernel/pulls/19296 
[OLK-5.10] x86/cpu: Remove pointless evaluation of x86_coreid_bits
                https://gitee.com/openeuler/kernel/pulls/9148 
sbitmap: fix infinite loop caused by negative wait_cnt
                https://gitee.com/openeuler/kernel/pulls/19217 
Revert "PCI/MSI: Set device flag indicating only 32-bit MSI support"
                https://gitee.com/openeuler/kernel/pulls/19432 
NFSv4: Fix deadlock during the running of state manager
                https://gitee.com/openeuler/kernel/pulls/19221 
mm: proc: fix compile warning when CONFIG_NUMA=n
                https://gitee.com/openeuler/kernel/pulls/19340 
sched: Fix race between yield_to() and try_to_wake_up()
                https://gitee.com/openeuler/kernel/pulls/19345 
bpf: Sync pending IRQ work before freeing ring buffer
                https://gitee.com/openeuler/kernel/pulls/19333 
兆芯：
[OLK-5.10] Optimize Zhaoxin CPU Temp Monitoring During Suspend/Resume
                https://gitee.com/openeuler/kernel/pulls/19036 
[OLK-5.10] Revert "xhci: Adjust the UHCI Controllers bit value"
                https://gitee.com/openeuler/kernel/pulls/8955 
[OLK-5.10] Turning off Zhaoxin ahci controller runtime pm
                https://gitee.com/openeuler/kernel/pulls/8971 
[OLK-5.10] ata: libata: disabling PhyRdy Change Interrupt based on actual LPM capability
                https://gitee.com/openeuler/kernel/pulls/19008 
[OLK-5.10] hwrng: add Zhaoxin rng driver base on rep_xstore instruction
                https://gitee.com/openeuler/kernel/pulls/9134 
[OLK-5.10] USB: hcd-pci: Avoid modifying UHCI driver_data when bound to non-native drivers
                https://gitee.com/openeuler/kernel/pulls/18985 
[OLK-5.10] USB: Fix ehci infinite suspend-resume loop issue in zhaoxin
                https://gitee.com/openeuler/kernel/pulls/18986 
[OLK-5.10] Driver for Zhaoxin I2C controller
                https://gitee.com/openeuler/kernel/pulls/8973 
[OLK-5.10] x86/acpi/cstate: Add MWAIT Cx support for Zhaoxin CPUs
                https://gitee.com/openeuler/kernel/pulls/8972 
[OLK-5.10] Update cputemp driver with using the same MSR uniformly
                https://gitee.com/openeuler/kernel/pulls/9110 
[OLK-5.10] perf/zhaoxin/core: Tailor FMS for KH-50000
                https://gitee.com/openeuler/kernel/pulls/19059 
[OLK-5.10] x86/mce: Set bios_cmci_threshold for CMCI threshold
                https://gitee.com/openeuler/kernel/pulls/9152 
Add Support for Disabling Hugetlb in soft_offline_page
                https://gitee.com/openeuler/kernel/pulls/19304 
openeuler_defconfig: enable CONFIG_PAGE_CACHE_LIMIT for x86/arm64
                https://gitee.com/openeuler/kernel/pulls/19029 
Revert "scsi: libsas: Fix exp-attached device scan after probe failure scanned in again after probe failed"
                https://gitee.com/openeuler/kernel/pulls/19363 
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/18818 
[OLK-5.10] x86/hpet: Set dynamic IRQ feature for HPET for KH-50000
                https://gitee.com/openeuler/kernel/pulls/19084 
[OLK-5.10] crypto: zhaoxin - Update Kconfig dependencies and defaults
                https://gitee.com/openeuler/kernel/pulls/18982 
[OLK-5.10] cpufreq: acpi-cpufreq: Zhaoxin: fix incorrect max-freq issue
                https://gitee.com/openeuler/kernel/pulls/13848 
[OLK-5.10] KVM: x86: allow CPUID 0xC000_0000 to proceed on Zhaoxin CPUs
                https://gitee.com/openeuler/kernel/pulls/19040 
海光：
[Hygon][5.10][EDAC] The width of hash value is 2 bits for Hygon family 18h model 6h processors
                https://gitee.com/openeuler/kernel/pulls/18720 
[Hygon][5.10][Bugfix] Bug fix for EDAC address translation on hygon family 18h model 4h
                https://gitee.com/openeuler/kernel/pulls/18586 
[OLK-5.10] force use dma api when AMD SEV is actived
                https://gitee.com/openeuler/kernel/pulls/18967 
海思：
drivers:misc:sdma-dae: add channel depth info in debugfs
                https://gitee.com/openeuler/kernel/pulls/19370 


议题二：申请OBMM和UMMU-CORE领域committer（高超）
新增灵衢下OBMM子模块，增加（@TrueAI，@kazero00）为Committer
现有灵衢下UMMU子模块，增加（@gongleihuawei） 为Committer

结论：通过

议题三: openEuler kernel 合入特性规范讨论 - 谢秀奇
纪要：根据会上讨论内容，吴腾达、李楠帮忙起草一下，下次会议讨论。


议题X：征集中，可直接在此申报（请备注汇报人）


三、遗留问题


------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/11/21 Kernel SIG 双周例会】
轮值主持：桑力鹏【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：李楠
会议链接：https://meeting.huaweicloud.com:36443/#/j/987186410
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-6.6进展同步
    tag更新到6.6.0-120.0.0
        ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数1085个
    git log 6.6.0-114.0.0..6.6.0-120.0.0 --oneline --no-merges | wc -l
CVE(106)
CVE-2025-38132        https://gitee.com/openeuler/kernel/pulls/18309 
CVE-2025-38286        https://gitee.com/openeuler/kernel/pulls/18672 
CVE-2025-38164        https://gitee.com/openeuler/kernel/pulls/18381 
CVE-2025-38275        https://gitee.com/openeuler/kernel/pulls/18793 
CVE-2025-40109        https://gitee.com/openeuler/kernel/pulls/19122 
CVE-2025-39693        https://gitee.com/openeuler/kernel/pulls/18501 
CVE-2025-39916        https://gitee.com/openeuler/kernel/pulls/18492 
CVE-2025-39949        https://gitee.com/openeuler/kernel/pulls/18683 
CVE-2025-38274        https://gitee.com/openeuler/kernel/pulls/18789 
CVE-2024-56591        https://gitee.com/openeuler/kernel/pulls/18711 
CVE-2025-39970        https://gitee.com/openeuler/kernel/pulls/18681 
CVE-2025-39832        https://gitee.com/openeuler/kernel/pulls/18267 
CVE-2025-38349        https://gitee.com/openeuler/kernel/pulls/18244 
CVE-2025-39794        https://gitee.com/openeuler/kernel/pulls/18954 
CVE-2025-38293        https://gitee.com/openeuler/kernel/pulls/18778 
CVE-2025-22073        https://gitee.com/openeuler/kernel/pulls/17926 
CVE-2025-38640        https://gitee.com/openeuler/kernel/pulls/18504 
CVE-2025-38203        https://gitee.com/openeuler/kernel/pulls/18438 
CVE-2025-38230        https://gitee.com/openeuler/kernel/pulls/18944 
CVE-2025-39719        https://gitee.com/openeuler/kernel/pulls/18518 
CVE-2025-39711        https://gitee.com/openeuler/kernel/pulls/18519 
CVE-2025-38107        https://gitee.com/openeuler/kernel/pulls/18949 
CVE-2025-40044        https://gitee.com/openeuler/kernel/pulls/18739 
CVE-2025-38576        https://gitee.com/openeuler/kernel/pulls/18215 
CVE-2025-40126        https://gitee.com/openeuler/kernel/pulls/19024 
CVE-2025-38347        https://gitee.com/openeuler/kernel/pulls/18243 
CVE-2025-38155        https://gitee.com/openeuler/kernel/pulls/18321 
CVE-2025-37781        https://gitee.com/openeuler/kernel/pulls/18902 
CVE-2025-38059        https://gitee.com/openeuler/kernel/pulls/18398 
CVE-2025-38204        https://gitee.com/openeuler/kernel/pulls/18674 
CVE-2025-40038        https://gitee.com/openeuler/kernel/pulls/18960 
CVE-2025-39742        https://gitee.com/openeuler/kernel/pulls/18268 
CVE-2025-39975        https://gitee.com/openeuler/kernel/pulls/18807 
CVE-2025-38217        https://gitee.com/openeuler/kernel/pulls/18945 
CVE-2025-37998        https://gitee.com/openeuler/kernel/pulls/18668 
CVE-2025-40172        https://gitee.com/openeuler/kernel/pulls/19026 
CVE-2025-38295        https://gitee.com/openeuler/kernel/pulls/18781 
CVE-2025-38138        https://gitee.com/openeuler/kernel/pulls/18370 
CVE-2025-38258        https://gitee.com/openeuler/kernel/pulls/18404 
CVE-2025-38718        https://gitee.com/openeuler/kernel/pulls/18005 
CVE-2025-38290        https://gitee.com/openeuler/kernel/pulls/18690 
CVE-2025-38206        https://gitee.com/openeuler/kernel/pulls/18812 
CVE-2025-38191        https://gitee.com/openeuler/kernel/pulls/18435 
CVE-2025-38348        https://gitee.com/openeuler/kernel/pulls/18245 
CVE-2025-40157        https://gitee.com/openeuler/kernel/pulls/19043 
CVE-2025-39847        https://gitee.com/openeuler/kernel/pulls/18273 
CVE-2025-38300        https://gitee.com/openeuler/kernel/pulls/18786 
CVE-2025-39973        https://gitee.com/openeuler/kernel/pulls/18699 
CVE-2025-39767        https://gitee.com/openeuler/kernel/pulls/18502 
CVE-2025-39685        https://gitee.com/openeuler/kernel/pulls/18363 
CVE-2025-39861        https://gitee.com/openeuler/kernel/pulls/18955 
CVE-2025-38715        https://gitee.com/openeuler/kernel/pulls/18633 
CVE-2025-38259        https://gitee.com/openeuler/kernel/pulls/18432 
CVE-2025-38328        https://gitee.com/openeuler/kernel/pulls/18242 
CVE-2025-39889        https://gitee.com/openeuler/kernel/pulls/18272 
CVE-2025-40057        https://gitee.com/openeuler/kernel/pulls/18659 
CVE-2025-40042        https://gitee.com/openeuler/kernel/pulls/18646 
CVE-2025-38326        https://gitee.com/openeuler/kernel/pulls/18246 
CVE-2025-39701        https://gitee.com/openeuler/kernel/pulls/18486 
CVE-2025-40102        https://gitee.com/openeuler/kernel/pulls/18735 
CVE-2025-40026        https://gitee.com/openeuler/kernel/pulls/18802 
CVE-2025-39716        https://gitee.com/openeuler/kernel/pulls/18503 
CVE-2025-38011        https://gitee.com/openeuler/kernel/pulls/18876 
CVE-2025-38292        https://gitee.com/openeuler/kernel/pulls/18777 
CVE-2025-38126        https://gitee.com/openeuler/kernel/pulls/18947 
CVE-2025-39969        https://gitee.com/openeuler/kernel/pulls/18682 
CVE-2025-39909        https://gitee.com/openeuler/kernel/pulls/18494 
CVE-2025-38336        https://gitee.com/openeuler/kernel/pulls/18799 
CVE-2025-39945        https://gitee.com/openeuler/kernel/pulls/18679 
CVE-2025-38077        https://gitee.com/openeuler/kernel/pulls/18393 
CVE-2025-39934        https://gitee.com/openeuler/kernel/pulls/18493 
CVE-2025-39880        https://gitee.com/openeuler/kernel/pulls/18271 
CVE-2025-40207        https://gitee.com/openeuler/kernel/pulls/19019 
CVE-2025-39781        https://gitee.com/openeuler/kernel/pulls/18506 
CVE-2025-38262        https://gitee.com/openeuler/kernel/pulls/18434 
CVE-2025-39863        https://gitee.com/openeuler/kernel/pulls/18953 
CVE-2025-39952        https://gitee.com/openeuler/kernel/pulls/18497 
CVE-2025-38136        https://gitee.com/openeuler/kernel/pulls/18369 
CVE-2025-39808        https://gitee.com/openeuler/kernel/pulls/18040 
CVE-2025-39977        https://gitee.com/openeuler/kernel/pulls/18680 
CVE-2025-39782        https://gitee.com/openeuler/kernel/pulls/18316 
CVE-2025-39951        https://gitee.com/openeuler/kernel/pulls/18910 
CVE-2025-38153        https://gitee.com/openeuler/kernel/pulls/18310 
CVE-2025-40080        https://gitee.com/openeuler/kernel/pulls/18758 
CVE-2025-38335        https://gitee.com/openeuler/kernel/pulls/18798 
CVE-2025-38027        https://gitee.com/openeuler/kernel/pulls/18389 
CVE-2025-38185        https://gitee.com/openeuler/kernel/pulls/18813 
CVE-2025-39846        https://gitee.com/openeuler/kernel/pulls/18957 
CVE-2025-38698        https://gitee.com/openeuler/kernel/pulls/18631 
CVE-2025-38218        https://gitee.com/openeuler/kernel/pulls/18946 
CVE-2025-38734        https://gitee.com/openeuler/kernel/pulls/17988 
CVE-2025-38696        https://gitee.com/openeuler/kernel/pulls/18505 
CVE-2025-40153        https://gitee.com/openeuler/kernel/pulls/19069 
CVE-2025-39972        https://gitee.com/openeuler/kernel/pulls/18702 
CVE-2025-38323        https://gitee.com/openeuler/kernel/pulls/17950 
CVE-2025-39842        https://gitee.com/openeuler/kernel/pulls/18956 
CVE-2025-38225        https://gitee.com/openeuler/kernel/pulls/18814 
CVE-2025-39860        https://gitee.com/openeuler/kernel/pulls/18270 
CVE-2025-38167        https://gitee.com/openeuler/kernel/pulls/18388 
CVE-2025-38160        https://gitee.com/openeuler/kernel/pulls/18367 
CVE-2025-40071        https://gitee.com/openeuler/kernel/pulls/18649 
CVE-2025-40021        https://gitee.com/openeuler/kernel/pulls/18630 
CVE-2025-38199        https://gitee.com/openeuler/kernel/pulls/18675 
CVE-2025-39726        https://gitee.com/openeuler/kernel/pulls/18515 
CVE-2025-40123        https://gitee.com/openeuler/kernel/pulls/19103 
CVE-2025-40169        https://gitee.com/openeuler/kernel/pulls/18995 

Bugfix（53）
coresight: fix indentation error in cscfg_remove_owned_csdev_configs()
                https://gitee.com/openeuler/kernel/pulls/18309 
v2  Fix bugs
                https://gitee.com/openeuler/kernel/pulls/19087 
mm/slab: make __free(kfree) accept error pointers
                https://gitee.com/openeuler/kernel/pulls/19028 
RDMA/bnxt_re: Fix error recovery sequence
                https://gitee.com/openeuler/kernel/pulls/18447 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.82-6.6.83 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/18500 
some minor bugfix about zcopy
                https://gitee.com/openeuler/kernel/pulls/19093 
smb: client: validate change notify buffer before copy
                https://gitee.com/openeuler/kernel/pulls/18943 
arm64/mpam: Add quirk to retrigger L3 CSU monitor
                https://gitee.com/openeuler/kernel/pulls/18803 
ext4: disambiguate the return value of ext4_dio_write_end_io()
                https://gitee.com/openeuler/kernel/pulls/18423 
mm: introduce memalloc_flags_{save,restore}
                https://gitee.com/openeuler/kernel/pulls/18874 
bnxt_en: Fix ethtool -d byte order for 32-bit values
                https://gitee.com/openeuler/kernel/pulls/18448 
KVM: x86: use array_index_nospec with indices that come from guest
                https://gitee.com/openeuler/kernel/pulls/18917 
fs/resctrl: Fix the L3 CMAX conversion mechanism
                https://gitee.com/openeuler/kernel/pulls/18845 
PCI: Run quirk_huawei_pcie_sva() before arm_smmu_probe_device()
                https://gitee.com/openeuler/kernel/pulls/18695 
rtc: rx8025: fix incorrect register reference
                https://gitee.com/openeuler/kernel/pulls/18942 
mm: fix compilation error due to MAX_PAGE_ORDER isn't declared
                https://gitee.com/openeuler/kernel/pulls/18705 
misc: pci_endpoint_test: Avoid issue of interrupts remaining after request_irq error
                https://gitee.com/openeuler/kernel/pulls/18914 
scsi: ufs: mcq: Add NULL check in ufshcd_mcq_abort()
                https://gitee.com/openeuler/kernel/pulls/18915 
mm: add nr_free_highatomic in show_free_areas
                https://gitee.com/openeuler/kernel/pulls/18927 
rseq: Protect event mask against membarrier IPI
                https://gitee.com/openeuler/kernel/pulls/18839 
v2  mm: Fix shmem build and numa fault counting errors
                https://gitee.com/openeuler/kernel/pulls/19009 
btf: Avoid weak external references
                https://gitee.com/openeuler/kernel/pulls/18484 
[OLK-6.6][linux-6.6.y sync] Backport 6.6.86-6.6.87 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/18940 
*** Mainline PATCH backport ***
                https://gitee.com/openeuler/kernel/pulls/18745 
arch_numa: make node_reclaim_distance_setup static
                https://gitee.com/openeuler/kernel/pulls/19066 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.85-6.6.86 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/18842 
KVM: arm64: Fix access_actlr() build warning
                https://gitee.com/openeuler/kernel/pulls/19120 
net: usb: aqc111: debug info before sanitation
                https://gitee.com/openeuler/kernel/pulls/18310 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.84-6.6.85 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/18421 
regulator: max20086: Fix refcount leak in max20086_parse_regulators_dt()
                https://gitee.com/openeuler/kernel/pulls/18389 
arm64/mpam: Add quirk to shrink MATA PMG range
                https://gitee.com/openeuler/kernel/pulls/18969 
[OLK-6.6] backport important bugfix for lpfc driver from upstream linux-6.6.y
                https://gitee.com/openeuler/kernel/pulls/18820 
some bugfixes for NUMA.remote
                https://gitee.com/openeuler/kernel/pulls/18894 
padata: Reset next CPU when reorder sequence wraps around
                https://gitee.com/openeuler/kernel/pulls/18784 
bnxt_en: Fix DCB ETS validation
                https://gitee.com/openeuler/kernel/pulls/18452 
[OLK-6.6] backport important bugfix for mpt3sas driver from upstream linux-6.6.y
                https://gitee.com/openeuler/kernel/pulls/18817 
bpf-rvi: block: fix memleak issue in bpf_show_partitions_start()
                https://gitee.com/openeuler/kernel/pulls/18666 
software node: Correct a OOB check in software_node_get_reference_args()
                https://gitee.com/openeuler/kernel/pulls/18916 
CCA: Fix soft lockup bug while destroy realm
                https://gitee.com/openeuler/kernel/pulls/18892 
perf: Fix tt_core mismatch over PG CPU
                https://gitee.com/openeuler/kernel/pulls/18920 
iommu/ummu:  Bugfix of ummu
                https://gitee.com/openeuler/kernel/pulls/19064 
mm: do not install PMD mappings when handling a COW fault
                https://gitee.com/openeuler/kernel/pulls/18855 
sched/fair: remove qos_reweight logic under non-SMP scenario
                https://gitee.com/openeuler/kernel/pulls/18372 
KVM: arm64: Deactivate the spurious vtimer interrupt
                https://gitee.com/openeuler/kernel/pulls/18859 
kvm: add struct kvm if only CONFIG_KVM enabled
                https://gitee.com/openeuler/kernel/pulls/18896 
perf: fix ddrc redundant value set
                https://gitee.com/openeuler/kernel/pulls/18806 
mm: migrate: Fix the compilation error caused by redundant semicolons
                https://gitee.com/openeuler/kernel/pulls/18977 
mm/thp: Add a new sysfs knob for zero COW
                https://gitee.com/openeuler/kernel/pulls/18934 
gmem: fix some warnings
                https://gitee.com/openeuler/kernel/pulls/18928 
v2:mm/swap: get the swap device offset directly
                https://gitee.com/openeuler/kernel/pulls/18929 
blk-ioinf: fix default weight being reset to 0 for non-root cgroups
                https://gitee.com/openeuler/kernel/pulls/19053 
blk-ioinf: fix division by zero caused by inflight overflow in ioinf_qos_write()
                https://gitee.com/openeuler/kernel/pulls/18992 
[Backport] mm/hugetlb: declare hugetlbfs_pagecache_present() non-static
                https://gitee.com/openeuler/kernel/pulls/18908 

feature
kvm: supports hugepages POD when migrate vm
                https://gitee.com/openeuler/kernel/pulls/18968 
kvm: supports hugepages reclaime notify
                https://gitee.com/openeuler/kernel/pulls/18963 
GMEM: General Memory Management
                https://gitee.com/openeuler/kernel/pulls/18723 
Backport PLR (Power Limit Reasons) TPMI driver for 6.6
                https://gitee.com/openeuler/kernel/pulls/18857 
xsched: XCU Partition
                https://gitee.com/openeuler/kernel/pulls/19070 
v6  fuse:io_uring: support fuse over io_uring
                https://gitee.com/openeuler/kernel/pulls/19031 
v2  Add MFS Support
                https://gitee.com/openeuler/kernel/pulls/18906 
mm: add huge pfnmap support for remap_pfn_range()
                https://gitee.com/openeuler/kernel/pulls/18961 
zcopy: A zero-copy data transfer mechanism
                https://gitee.com/openeuler/kernel/pulls/18988 
v2  Backport some memory policy feature and bugfix from mainline
                https://gitee.com/openeuler/kernel/pulls/18840 
wakeup kswapd during node_reclaim
                https://gitee.com/openeuler/kernel/pulls/18966 
v11  Add xcall 2.0 support
                https://gitee.com/openeuler/kernel/pulls/19027 
blk-ioinf: introduce inflight-based IO QoS controller
                https://gitee.com/openeuler/kernel/pulls/18921 

intel
Intel: Backport PMU support for Intel Clearwater Forest platform
                https://gitee.com/openeuler/kernel/pulls/18348 

网讯
net: wangxun: ngbe: add support for wangxun 1G
                https://gitee.com/openeuler/kernel/pulls/18376 
[OLK-6.6] fix txgbe link fec issues and  enhance hot reset mechanism
                https://gitee.com/openeuler/kernel/pulls/18328 

星云智联
net:nebula-matrix:fix compile err
                https://gitee.com/openeuler/kernel/pulls/18848 
net:nebula-matrix:fix compile err
                https://gitee.com/openeuler/kernel/pulls/19071 

麒麟
[OLK-6.6] [Bugfix] Bug fix for min_free_kbytes warning storms
                https://gitee.com/openeuler/kernel/pulls/18051 

兆芯
[OLK-6.6] ACPI: processor: idle: Set timer broadcast state on C3 for KH-50000
                https://gitee.com/openeuler/kernel/pulls/18482 
[OLK-6.6] Enhance SM3 SM4 drivers with optimizations and compatibility fixes
                https://gitee.com/openeuler/kernel/pulls/18467 
[OLK-6.6] i2c: zhaoxin: Enhancements and Modifications to SMBus Driver
                https://gitee.com/openeuler/kernel/pulls/18450 
[OLK-6.6] hwmon: zhaoxin-cputemp: Update for KH-50000
                https://gitee.com/openeuler/kernel/pulls/18478 
[OLK-6.6] pinctrl: Zhaoxin: Add KH-50000 support
                https://gitee.com/openeuler/kernel/pulls/18440 
[OLK-6.6] perf/zhaoxin/core: Tailor FMS for KH-50000
                https://gitee.com/openeuler/kernel/pulls/18477 
[OLK-6.6] Optimize Zhaoxin CPU Temp Monitoring During Suspend/Resume
                https://gitee.com/openeuler/kernel/pulls/18449 

海光
Add ccp-mdev feature into hygon ccp driver
                https://gitee.com/openeuler/kernel/pulls/18428 
mm: add auxillary functions for folios and hugetlb
                https://gitee.com/openeuler/kernel/pulls/18841 

龙芯
LoongArch: fix nvme/megaraid/stmmac/uprobe/rtc/kdump problems
                https://gitee.com/openeuler/kernel/pulls/17268 

海思
arm64/watchdog_hld: Add a cpufreq notifier for update watchdog thresh
                https://gitee.com/openeuler/kernel/pulls/18598 
net: hibmcge: fix the inappropriate netif_device_detach()
                https://gitee.com/openeuler/kernel/pulls/18662 
net: hns3: the multi-tcs VF can be configured only when the interface is down
                https://gitee.com/openeuler/kernel/pulls/18761 
drivers/perf: hisi: Add support for HiSilicon MN PMU driver
                https://gitee.com/openeuler/kernel/pulls/18863 
drivers/perf: hisi: Support UMMU pmu
                https://gitee.com/openeuler/kernel/pulls/18804 
misc: uacce - fix a null pointer access issue when poweroff
                https://gitee.com/openeuler/kernel/pulls/18980 
net: hibmcge: support pagepool for rx
                https://gitee.com/openeuler/kernel/pulls/18800 
KVM: arm64: ipiv: Fix compilation warning
                https://gitee.com/openeuler/kernel/pulls/19080 
ub: ub_fwctl: Release rpc_out when kernel state return error
                https://gitee.com/openeuler/kernel/pulls/19091 
ub: ubase: Fix some compile warnings&fix pages free problem
                https://gitee.com/openeuler/kernel/pulls/18885 
ub:ubus: call ub_host_probe inside register_ub_manage_subsystem_ops
                https://gitee.com/openeuler/kernel/pulls/19082 
ub: udma: Support udma basic transaction operations and advanced features.
                https://gitee.com/openeuler/kernel/pulls/19123 
ub: ubfi: Support ummu node in ubfi
                https://gitee.com/openeuler/kernel/pulls/18748 
ub: add cdma driver code
                https://gitee.com/openeuler/kernel/pulls/18964 
ub: Support new features for UBUS
                https://gitee.com/openeuler/kernel/pulls/18788 
ub: ubase: Support debugs functions
                https://gitee.com/openeuler/kernel/pulls/18858 
ub: ubase: support for advanced functions
                https://gitee.com/openeuler/kernel/pulls/18810 
vfio:ubus: Support Virtual Function I/O  of UBUS
                https://gitee.com/openeuler/kernel/pulls/18852 
net: unic: Support advanced functions of unic driver
                https://gitee.com/openeuler/kernel/pulls/18970 
ubcore: implement memory and netlink features.
                https://gitee.com/openeuler/kernel/pulls/18952 
urma: introduce ubcore main module.
                https://gitee.com/openeuler/kernel/pulls/18849 
ub: ub_fwctl:Add the ub_fwctl driver
                https://gitee.com/openeuler/kernel/pulls/18684 
ub:ubus: Add ummu_map attribute in sysfs
                https://gitee.com/openeuler/kernel/pulls/19033 
net:Add a new protocol family definition AF_UB to support UB Memory based Socket(UMS)
                https://gitee.com/openeuler/kernel/pulls/18407 
ub: add cdma driver code
                https://gitee.com/openeuler/kernel/pulls/18685 
ub: ubase: Add support of base driver for ub network
                https://gitee.com/openeuler/kernel/pulls/18710 
ubcore: implement device registration and jetty management
                https://gitee.com/openeuler/kernel/pulls/18930 
ub: ubase: Do some bugfix about cmdq/ctrlq message and debugfs
                https://gitee.com/openeuler/kernel/pulls/19121 
iommu: Enabling Broadcast TLB Maintenance (BTM) for UMMU on ARM64
                https://gitee.com/openeuler/kernel/pulls/18713 
iommu/ummu: Implement IOMMU ops and advanced capabilities.
                https://gitee.com/openeuler/kernel/pulls/18877 
ub:hisi-ubus: Support HISI-UBUS driver framework
                https://gitee.com/openeuler/kernel/pulls/18901 
net: unic: add support of unic driver for ub network
                https://gitee.com/openeuler/kernel/pulls/18853 
ub: udma: Support loading and unloading driver.
                https://gitee.com/openeuler/kernel/pulls/18703 
ub: ubase: Fix CTRLQ init process
                https://gitee.com/openeuler/kernel/pulls/19139 
iommu/ummu: Add ummu driver basic capabilities.
                https://gitee.com/openeuler/kernel/pulls/18750 
uburma: implement jetty linking features.
                https://gitee.com/openeuler/kernel/pulls/18998 
urma: implement ubcore sysfs interface and device management
                https://gitee.com/openeuler/kernel/pulls/18887 
ubagg: implement ubagg module with ioctl interface and topology management
                https://gitee.com/openeuler/kernel/pulls/18976 
urma: implement netlink and memory management features.
                https://gitee.com/openeuler/kernel/pulls/18950 
net: ubl: add depend to ARM64 and remove config in x86
                https://gitee.com/openeuler/kernel/pulls/18605 
ubios_uvb: support uvb driver
                https://gitee.com/openeuler/kernel/pulls/18701 
ub: add UBUS and UBFI driver framework
                https://gitee.com/openeuler/kernel/pulls/18525 
ub:ubus: Fix X86 build error
                https://gitee.com/openeuler/kernel/pulls/19081 
iommu/ummu-core: Add ummu-core framework.
                https://gitee.com/openeuler/kernel/pulls/18597 
ub:ubus: Bugfix of ubus and ubfi
                https://gitee.com/openeuler/kernel/pulls/19006 
dma-mapping: benchmark: add support for UB devices
                https://gitee.com/openeuler/kernel/pulls/18938 
ub: udma: udma driver TA layer resource control operation.
                https://gitee.com/openeuler/kernel/pulls/19058 
                
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-291.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-287.0.0 更新至 5.10.0-291.0.0, 回合补丁数141个
        git log 5.10.0-287.0.0..5.10.0-291.0.0 --oneline --no-merges | wc -l
CVE: (14)
CVE-2025-39757  https://gitee.com/openeuler/kernel/pulls/19017 
CVE-2023-53034  https://gitee.com/openeuler/kernel/pulls/18890 
CVE-2025-40021  https://gitee.com/openeuler/kernel/pulls/18628 
CVE-2025-40081  https://gitee.com/openeuler/kernel/pulls/18729 
CVE-2025-21914  https://gitee.com/openeuler/kernel/pulls/18883 
CVE-2025-39973  https://gitee.com/openeuler/kernel/pulls/18728 
CVE-2025-40157  https://gitee.com/openeuler/kernel/pulls/19042 
CVE-2025-38415  https://gitee.com/openeuler/kernel/pulls/17396 
CVE-2024-57929  https://gitee.com/openeuler/kernel/pulls/18722 
CVE-2025-37810  https://gitee.com/openeuler/kernel/pulls/19002 
CVE-2025-40123  https://gitee.com/openeuler/kernel/pulls/19102 
CVE-2025-40042  https://gitee.com/openeuler/kernel/pulls/18686 
CVE-2025-40044  https://gitee.com/openeuler/kernel/pulls/18738 
CVE-2025-39993  https://gitee.com/openeuler/kernel/pulls/18617 
Bugfix:
KVM: arm64: Deactivate the spurious vtimer interrupt
                https://gitee.com/openeuler/kernel/pulls/18860 
[OLK-5.10]RNPVF: NET: Fix os crash while enable sriov for rnp
                https://gitee.com/openeuler/kernel/pulls/9490 
[OLK-5.10] openeuler_defconfig: clean up invalid kernel configurations
                https://gitee.com/openeuler/kernel/pulls/13242 
sched/fair: remove qos_reweight logic under non-SMP scenario
                https://gitee.com/openeuler/kernel/pulls/18378 
Rate-limit the logging of dirty-page and SPECTRE_V2 messages
                https://gitee.com/openeuler/kernel/pulls/18018 
mm: introduce memalloc_flags_{save,restore}
                https://gitee.com/openeuler/kernel/pulls/18873 
mainline patch backport
                https://gitee.com/openeuler/kernel/pulls/18746 
padata: Reset next CPU when reorder sequence wraps around
                https://gitee.com/openeuler/kernel/pulls/18783 
perf test bpf: Address error about non-null argument for epoll_pwait 2nd arg
                https://gitee.com/openeuler/kernel/pulls/18663 
net/oenetcls: work around l0 cache
                https://gitee.com/openeuler/kernel/pulls/18864 
v2  net/oenetcls: Balancing softirq to improve performance
                https://gitee.com/openeuler/kernel/pulls/18687 
[OLK-5.10] Fix repeated VM vcpu hotplug causing Qemu to abort
                https://gitee.com/openeuler/kernel/pulls/18665 
Feature:
net/oenetcls: Add mode 2 for rps numa affinity
                https://gitee.com/openeuler/kernel/pulls/18808 
zcopy: A zero-copy data transfer mechanism
                https://gitee.com/openeuler/kernel/pulls/18989 
zcopy: Remove the dump_pagetable interface
                https://gitee.com/openeuler/kernel/pulls/19094 
wakeup kswapd during node_reclaim
                https://gitee.com/openeuler/kernel/pulls/18878 
e1000e: Add support for the next LOM generation
                https://gitee.com/openeuler/kernel/pulls/2934 
mm: proc: use per_vma mmap_lock for vma traversal.
                https://gitee.com/openeuler/kernel/pulls/19062 
Intel:
[Intel-SIG] CWF PMU legacy support including core/uncore/event and their fixes
                https://gitee.com/openeuler/kernel/pulls/18430 
Add EDAC basic support and RRL enhancement for CWF/SRF/GNR/GNR-D for 5.10
                https://gitee.com/openeuler/kernel/pulls/18392 
海光：
[OLK-5.10]Support request attestation report from CSV guest
                https://gitee.com/openeuler/kernel/pulls/18365 
[OLK-5.10] Support Trusted computing(TC) feature for hygon CPU
                https://gitee.com/openeuler/kernel/pulls/19001 
[OLK-5.10] : Backport the upstream SEV-ES 32-bit boot path support and other updates
                https://gitee.com/openeuler/kernel/pulls/19011 
飞腾：
IXIC:add phytium ixic d2000 driver
                https://gitee.com/openeuler/kernel/pulls/14672 
net :stmmac add support for Phytium GMAC controller
                https://gitee.com/openeuler/kernel/pulls/14859 
海思：
Backport kunpeng920G to OLK-5.10
                https://gitee.com/openeuler/kernel/pulls/18951 
风河：
[OLK-5.10] backport important bugfix for lpfc driver from upstream linux-5.10.y
                https://gitee.com/openeuler/kernel/pulls/18743 
[OLK-5.10] backport important bugfix for mpt3sas driver from upstream linux-5.10.y
                https://gitee.com/openeuler/kernel/pulls/18737 

议题二：openEuler Kernel SIG 运作章程评审 - 谢秀奇
议题内容：
https://gitee.com/openeuler/kernel-docs/pulls/44
会议纪要：所有Maintainer评审加分后合入生效。

议题三：openEuler 26.09 创新版本启动 - 谢秀奇
议题内容：
https://e.gitee.com/open_euler/projects/711615/versions/292965?issue=ID7AYM

会议纪要：
1. 基于最新的 OLK-6.6 拉出 openEuler-26.09 分支，如后续 Release 正式版本号有变化，随之修改。
2. 李楠暂时负责该创新版本，并组建该创新版本开发维护团队。
3. 创新版本需求/特性，试行先评审接纳，后合入PR。试行后，推广其他分支版本。

议题四：申请linqu 底软开源commiter人员评审-林运生
新增junlong-zheng、rock_hw、shu-shengming、hongwu-wang、chenjunxin1992、fanghaiqinghw、caixu-blue 、Tankll2021、fangfeng123和mufengyan为灵衢UDEV、UDMA、CDMA、UNIC、ub_fwctl、UMMU模块的committer
会议结论：通过


三、遗留问题


------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/10/31 Kernel SIG 双周例会】
轮值主持：曾昭荣【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：桑力鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/985774693
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）

！！24.03 SP3 特性需要在11.19日之前合入完毕

        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-287.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-285.0.0 更新至 5.10.0-287.0.0, 回合补丁数52个
        git log 5.10.0-285.0.0..5.10.0-287.0.0 --oneline --no-merges | wc -l
CVE: (11)
CVE-2025-38700  https://gitee.com/openeuler/kernel/pulls/18007
CVE-2023-53292  https://gitee.com/openeuler/kernel/pulls/18202
CVE-2025-39971  https://gitee.com/openeuler/kernel/pulls/18549
CVE-2025-39697  https://gitee.com/openeuler/kernel/pulls/17991
CVE-2025-39998  https://gitee.com/openeuler/kernel/pulls/18397
CVE-2025-39795  https://gitee.com/openeuler/kernel/pulls/18200
CVE-2023-53728  https://gitee.com/openeuler/kernel/pulls/18537
CVE-2025-38709  https://gitee.com/openeuler/kernel/pulls/18197
CVE-2025-39898  https://gitee.com/openeuler/kernel/pulls/18470
CVE-2024-57904  https://gitee.com/openeuler/kernel/pulls/18512
CVE-2022-50306  https://gitee.com/openeuler/kernel/pulls/18150

Bugfix: (8)
scsi/hifc: Fix rport dev loss tmo flag and function parameter check err
                https://gitee.com/openeuler/kernel/pulls/18463
fscrypt: Don't use problematic non-inline crypto engines
                https://gitee.com/openeuler/kernel/pulls/17400
net/oenetcls: Fix memleak when clean flow table
                https://gitee.com/openeuler/kernel/pulls/18353
umount performance fix
                https://gitee.com/openeuler/kernel/pulls/18361
Fix kfree mismatch reported by cocci
                https://gitee.com/openeuler/kernel/pulls/15216
fs: quota: create dedicated workqueue for quota_release_work
                https://gitee.com/openeuler/kernel/pulls/18314
tracing: probes: Fix a possible race in trace_probe_log APIs
                https://gitee.com/openeuler/kernel/pulls/18514
KVM: arm64: vgic-v4: Restore pending state on host userspace write
                https://gitee.com/openeuler/kernel/pulls/18480

海思:
net/hinic3: Modify driver version
                https://gitee.com/openeuler/kernel/pulls/18424
RDMA/hns: Fix more wrong WQE data cases when QP wraps around
                https://gitee.com/openeuler/kernel/pulls/18487
drivers:misc:sdma-dae: optimize kernel code
                https://gitee.com/openeuler/kernel/pulls/18530
hisi: l0: update device name from hisi_l0 to hisi_soc_cache_mgmt
                https://gitee.com/openeuler/kernel/pulls/18584
v2  Add some bugfix for l0.
                https://gitee.com/openeuler/kernel/pulls/18490

申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/18534

OLK-6.6进展同步
    tag更新到6.6.0-114.0.0
        ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数311个
    git log 6.6.0-112.0.0..6.6.0-114.0.0 --oneline --no-merges | wc -l

CVE（42）
        CVE-2025-21801        https://gitee.com/openeuler/kernel/pulls/17611 
        CVE-2025-39691        https://gitee.com/openeuler/kernel/pulls/18152 
        CVE-2025-39989        https://gitee.com/openeuler/kernel/pulls/18425 
        CVE-2025-37917        https://gitee.com/openeuler/kernel/pulls/18037 
        CVE-2025-37987        https://gitee.com/openeuler/kernel/pulls/18028 
        CVE-2025-37983        https://gitee.com/openeuler/kernel/pulls/18027 
        CVE-2025-39920        https://gitee.com/openeuler/kernel/pulls/18406 
        CVE-2025-38709        https://gitee.com/openeuler/kernel/pulls/18131 
        CVE-2025-39679        https://gitee.com/openeuler/kernel/pulls/18513 
        CVE-2025-39967        https://gitee.com/openeuler/kernel/pulls/18495 
        CVE-2025-38333        https://gitee.com/openeuler/kernel/pulls/17859 
        CVE-2025-39898        https://gitee.com/openeuler/kernel/pulls/18385 
        CVE-2025-40019        https://gitee.com/openeuler/kernel/pulls/18593 
        CVE-2025-39795        https://gitee.com/openeuler/kernel/pulls/18199 
        CVE-2025-37931        https://gitee.com/openeuler/kernel/pulls/18034 
        CVE-2025-39724        https://gitee.com/openeuler/kernel/pulls/18498 
        CVE-2025-39787        https://gitee.com/openeuler/kernel/pulls/18357 
        CVE-2025-38630        https://gitee.com/openeuler/kernel/pulls/17908 
        CVE-2025-38615        https://gitee.com/openeuler/kernel/pulls/17877 
        CVE-2025-38245        https://gitee.com/openeuler/kernel/pulls/17354 
        CVE-2025-37922        https://gitee.com/openeuler/kernel/pulls/18036 
        CVE-2025-39923        https://gitee.com/openeuler/kernel/pulls/18433 
        CVE-2025-37935        https://gitee.com/openeuler/kernel/pulls/18035 
        CVE-2025-37792        https://gitee.com/openeuler/kernel/pulls/18401 
        CVE-2025-38700        https://gitee.com/openeuler/kernel/pulls/18006 
        CVE-2025-39998        https://gitee.com/openeuler/kernel/pulls/18395 
        CVE-2025-38555        https://gitee.com/openeuler/kernel/pulls/17909 
        CVE-2025-39806        https://gitee.com/openeuler/kernel/pulls/18545 
        CVE-2025-37897        https://gitee.com/openeuler/kernel/pulls/18032 
        CVE-2025-38701        https://gitee.com/openeuler/kernel/pulls/18151 
        CVE-2025-37901        https://gitee.com/openeuler/kernel/pulls/18033 
        CVE-2025-39971        https://gitee.com/openeuler/kernel/pulls/18427 
        CVE-2025-39993        https://gitee.com/openeuler/kernel/pulls/18517 
        CVE-2025-38577        https://gitee.com/openeuler/kernel/pulls/17872 
        CVE-2025-39982        https://gitee.com/openeuler/kernel/pulls/18638 
        CVE-2025-38626        https://gitee.com/openeuler/kernel/pulls/17871 
        CVE-2025-38313        https://gitee.com/openeuler/kernel/pulls/17928 
        CVE-2025-38414        https://gitee.com/openeuler/kernel/pulls/17760 
        CVE-2025-37914        https://gitee.com/openeuler/kernel/pulls/18030 
        CVE-2025-38668        https://gitee.com/openeuler/kernel/pulls/18579 
        CVE-2025-38624        https://gitee.com/openeuler/kernel/pulls/18224 
        CVE-2025-39968        https://gitee.com/openeuler/kernel/pulls/18464 

Bugfix
fs: quota: create dedicated workqueue for quota_release_work
                https://gitee.com/openeuler/kernel/pulls/18313 
sched/core: Add sched_change_qos_group() in sched_cgroup_fork()
                https://gitee.com/openeuler/kernel/pulls/18419 
ext4: preserve SB_I_VERSION on remount
                https://gitee.com/openeuler/kernel/pulls/18312 
perf vendor events arm64: Add N2, V2, N3, V3 events/metrics
                https://gitee.com/openeuler/kernel/pulls/16738 
KVM: arm64: vgic-v4: Restore pending state on host userspace write
                https://gitee.com/openeuler/kernel/pulls/18455 
fscrypt: Don't use problematic non-inline crypto engines
                https://gitee.com/openeuler/kernel/pulls/17401 
fs/resctrl: Re-allocate rmid for the monitor when migrating across control groups
                https://gitee.com/openeuler/kernel/pulls/18544 
perf: arm_spe: Prevent overflow in PERF_IDX2OFF()
                https://gitee.com/openeuler/kernel/pulls/18564 
arm64/mpam: Fix L2 MBWU monitor multiplexing issue
                https://gitee.com/openeuler/kernel/pulls/18563 
locking/qspinlock: Fix CNA NUMA node setup before numa_store_cpu_info()
                https://gitee.com/openeuler/kernel/pulls/18374 
ext4: fix an off-by-one issue during moving extents
                https://gitee.com/openeuler/kernel/pulls/18311 
arm64/mpam: Fix MBWU monitor overflow handling
                https://gitee.com/openeuler/kernel/pulls/18559 
sdei_watchdog: Add CPU_PM_ENTER_FAILED handling in sdei_watchdog_pm_notifier
                https://gitee.com/openeuler/kernel/pulls/18415 
arm/syscalls: mark syscall invocation as likely in
                https://gitee.com/openeuler/kernel/pulls/18531 
mm: fix __count_zid_vm_events when CONFIG_ZONE_EXTMEM is enabled
                https://gitee.com/openeuler/kernel/pulls/18608 
arm64/cpufeatures/kvm: Add ARMv8.9 FEAT_ECBHB bits in ID_AA64MMFR1 register
                https://gitee.com/openeuler/kernel/pulls/11635 
cpu/SMT: recover global num_threads after disable smt switch fail
                https://gitee.com/openeuler/kernel/pulls/18550 
ras: ACPI: HED: Always initialize before evged
                https://gitee.com/openeuler/kernel/pulls/18241 
umount performance fix
                https://gitee.com/openeuler/kernel/pulls/18362 
kernel/sys.c: fix the racy usage of task_lock(tsk->group_leader) in sys_prlimit64() paths
                https://gitee.com/openeuler/kernel/pulls/18402 
arm64: Enable vmalloc-huge with ptdump
                https://gitee.com/openeuler/kernel/pulls/18324 
Expand scope of khugepaged anonymous collapse
                https://gitee.com/openeuler/kernel/pulls/18289 

feature
fuse: support sysfs api for flush and
                https://gitee.com/openeuler/kernel/pulls/18237 

星云智联
Net: nebula_matrix: set nebula_matrix driver to a newer state
                https://gitee.com/openeuler/kernel/pulls/18130 

AMD
[OLK-6.6] Backported patches of Transient Scheduler Attacks (TSA)
                https://gitee.com/openeuler/kernel/pulls/17676 

麒麟
enfs: add new path state PM_STATE_UNSTABLE
                https://gitee.com/openeuler/kernel/pulls/18249 

Intel
Add EDAC basic support and RRL enhancement for CWF/SRF/GNR/GNR-D
                https://gitee.com/openeuler/kernel/pulls/18256 
Add IFS support for ClearWater Forest
                https://gitee.com/openeuler/kernel/pulls/18254 

沐创
RNPGBE: NET: Fix dmesg 'unknow speed' show when 1000M
                https://gitee.com/openeuler/kernel/pulls/16777 

申威
[OLK-6.6]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/18533 

海光
[OLK-6.6] Support Hygon TKM (Trusted Key Management) Guest live migration
                https://gitee.com/openeuler/kernel/pulls/18326 

海思
RDMA/hns: Fix wrong WQE data when QP wraps around
                https://gitee.com/openeuler/kernel/pulls/18488 
net: ubl: add CONFIG_UB_UBL definition and UBL interface
                https://gitee.com/openeuler/kernel/pulls/18327 
arm64: add cnp verification on Hisilicon erratum 162100125
                https://gitee.com/openeuler/kernel/pulls/18457 
net/hinic3: Modify driver version
                https://gitee.com/openeuler/kernel/pulls/18422 
crypto: hisilicon - support for new ZIP features
                https://gitee.com/openeuler/kernel/pulls/18409 
arm64: Add support for HIP09 Spectre-BHB mitigation
                https://gitee.com/openeuler/kernel/pulls/18516 
net: hns3: fix null pointer in debugfs issue
                https://gitee.com/openeuler/kernel/pulls/18639 
Fix add define COMPAT_ELF_HWCAP3
                https://gitee.com/openeuler/kernel/pulls/18414 
v3  Errata management for VM Live migration
                https://gitee.com/openeuler/kernel/pulls/18640 
arm-smmu-v3: add 'HIP10C' for 162100602 errata
                https://gitee.com/openeuler/kernel/pulls/18536 
Make ID reg writable
                https://gitee.com/openeuler/kernel/pulls/18592 
Add workaround for HIP09/HIP10/HIP10C/HIP12 erratum 162100803/162200807/162400807/165010802
                https://gitee.com/openeuler/kernel/pulls/17807 
net: hibmcge: support pci_driver.shutdown()
                https://gitee.com/openeuler/kernel/pulls/18589 
Fix wrong CPU aff3 conversion between  MPIDR and SYS_LSUDVMBM_EL2
                https://gitee.com/openeuler/kernel/pulls/18507 
perf: arm_pmuv3: Factor out PMCCNTR_EL0 use conditions and Don't use PMCCNTR_EL0 on SMT cores
                https://gitee.com/openeuler/kernel/pulls/18258 
tools headers arm64: Sync arm64's cputype.h with the kernel sources
                https://gitee.com/openeuler/kernel/pulls/18624 
add memory ras feature support
                https://gitee.com/openeuler/kernel/pulls/18588 
support mempool feature
                https://gitee.com/openeuler/kernel/pulls/18622 
support NUMA.remote feature
                https://gitee.com/openeuler/kernel/pulls/18568 

龙芯：
btf: Avoid weak external references
https://gitee.com/openeuler/kernel/pulls/18484
LoongArch: fix nvme/megaraid/stmmac/uprobe/rtc/kdump problems
https://gitee.com/openeuler/kernel/pulls/17268


议题二：AF_UB协议族预埋openEuler2403 LTS SP3合入  --议题申报人：田震松
结论：通过

议题三：Bug Fix: 海光EDAC驱动address translation问题 --议题申报人:  施爱春
https://gitee.com/openeuler/kernel/pulls/18586



三、遗留问题


------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2025/10/17 Kernel SIG 双周例会】
轮值主持：关文涛【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：曾昭荣
会议链接：https://meeting.huaweicloud.com:36443/#/j/963829636
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表
议题一：进展update（李楠&吴腾达）
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-285.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-283.0.0 更新至 5.10.0-285.0.0, 回合补丁数71个
        git log 5.10.0-283.0.0..5.10.0-285.0.0 --oneline --no-merges | wc -l
CVE: (15)
CVE-2025-38615  https://gitee.com/openeuler/kernel/pulls/17876 
CVE-2022-49234  https://gitee.com/openeuler/kernel/pulls/18262 
CVE-2025-39850  https://gitee.com/openeuler/kernel/pulls/18305 
CVE-2023-53241  https://gitee.com/openeuler/kernel/pulls/18122 
CVE-2025-21801  https://gitee.com/openeuler/kernel/pulls/17610 
CVE-2022-50410  https://gitee.com/openeuler/kernel/pulls/18067 
CVE-2025-39883  https://gitee.com/openeuler/kernel/pulls/18251 
CVE-2025-38313  https://gitee.com/openeuler/kernel/pulls/17929 
CVE-2025-39865  https://gitee.com/openeuler/kernel/pulls/18112 
CVE-2025-39866  https://gitee.com/openeuler/kernel/pulls/18070 
CVE-2022-50350  https://gitee.com/openeuler/kernel/pulls/18126 
CVE-2023-53438  https://gitee.com/openeuler/kernel/pulls/18162 
CVE-2025-38086  https://gitee.com/openeuler/kernel/pulls/18229 
CVE-2023-53259  https://gitee.com/openeuler/kernel/pulls/18138 
CVE-2025-22073  https://gitee.com/openeuler/kernel/pulls/17927 
Feature:
[OLK-5.10] Add SEV-ES hypervisor support
                https://gitee.com/openeuler/kernel/pulls/18043 
Bugfix:
sched/dynamic_affinity: Calculate cpu capacity in real time when realtime tasks are running on this cpu
                https://gitee.com/openeuler/kernel/pulls/18278 
ARM: rockchip: fix kernel hang during smp initialization
                https://gitee.com/openeuler/kernel/pulls/18155 
perf: backport community patches
                https://gitee.com/openeuler/kernel/pulls/17990 
fix oenetcls bugs
                https://gitee.com/openeuler/kernel/pulls/18052 
nfsd: replace wait_on_bit by wait_on_bit_acquire in nfsd_file_acquire
                https://gitee.com/openeuler/kernel/pulls/18099 
x86/paravirt: Fix build due to __text_gen_insn() backport
                https://gitee.com/openeuler/kernel/pulls/18335
RDMA/hns: Fix wrong WQE data when QP wraps around
                https://gitee.com/openeuler/kernel/pulls/18283 


OLK-6.6进展同步
    tag更新到6.6.0-112.0.0
        ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP2
    期间合入补丁数164个
    git log 6.6.0-111.0.0..6.6.0-112.0.0 --oneline --no-merges | wc -l

CVE（24）
        CVE-2025-39865  https://gitee.com/openeuler/kernel/pulls/18114 
        CVE-2025-22081  https://gitee.com/openeuler/kernel/pulls/17957 
        CVE-2025-38497  https://gitee.com/openeuler/kernel/pulls/17961 
        CVE-2025-22005  https://gitee.com/openeuler/kernel/pulls/18231 
        CVE-2025-38395  https://gitee.com/openeuler/kernel/pulls/17953 
        CVE-2025-39824  https://gitee.com/openeuler/kernel/pulls/18073 
        CVE-2025-39715  https://gitee.com/openeuler/kernel/pulls/18322 
        CVE-2025-39886  https://gitee.com/openeuler/kernel/pulls/18293 
        CVE-2025-39883  https://gitee.com/openeuler/kernel/pulls/18250 
        CVE-2025-39844  https://gitee.com/openeuler/kernel/pulls/18291 
        CVE-2025-38377  https://gitee.com/openeuler/kernel/pulls/17952 
        CVE-2024-56591  https://gitee.com/openeuler/kernel/pulls/18179 
        CVE-2025-37741  https://gitee.com/openeuler/kernel/pulls/17958 
        CVE-2025-39853  https://gitee.com/openeuler/kernel/pulls/18227 
        CVE-2025-39851  https://gitee.com/openeuler/kernel/pulls/18290 
        CVE-2025-39850  https://gitee.com/openeuler/kernel/pulls/18306 
        CVE-2025-38725  https://gitee.com/openeuler/kernel/pulls/18183 
        CVE-2025-39914  https://gitee.com/openeuler/kernel/pulls/18342 
        CVE-2025-38319  https://gitee.com/openeuler/kernel/pulls/17960 
        CVE-2025-38363  https://gitee.com/openeuler/kernel/pulls/17956 
        CVE-2025-39739  https://gitee.com/openeuler/kernel/pulls/18133 
        CVE-2025-38086  https://gitee.com/openeuler/kernel/pulls/18230 
        CVE-2025-39819  https://gitee.com/openeuler/kernel/pulls/18041 
        CVE-2025-38384  https://gitee.com/openeuler/kernel/pulls/17954 

Bugfix（21）
samples/bpf: fix cpuinfo_arm64 prog load issue
                https://gitee.com/openeuler/kernel/pulls/18280 
arm64/mpam: Add quirk for hisi cpbm_wd field
                https://gitee.com/openeuler/kernel/pulls/18123 
net/oenetcls: Fix memleak when clean flow table
                https://gitee.com/openeuler/kernel/pulls/18352 
samples/bpf: Fix print issue in dump_partitions()
                https://gitee.com/openeuler/kernel/pulls/18234 
use refcount+RCU method to implement lockless slab shrink
                https://gitee.com/openeuler/kernel/pulls/15977 
ARM: rockchip: fix kernel hang during smp initialization
                https://gitee.com/openeuler/kernel/pulls/18156 
usb: core: config: Prevent OOB read in SS endpoint companion parsing
                https://gitee.com/openeuler/kernel/pulls/18173 
memory tiers: use default_dram_perf_ref_source in log message
                https://gitee.com/openeuler/kernel/pulls/18264 
v3  arm64: Do not enable hardware xcall/xint in guest temporarily
                https://gitee.com/openeuler/kernel/pulls/18038 
Backport fs/pipe performance optimization patches
                https://gitee.com/openeuler/kernel/pulls/18144 
v2: shmem cleanup
                https://gitee.com/openeuler/kernel/pulls/18282 
cpufreq: Initialize cpufreq-based invariance before subsys
                https://gitee.com/openeuler/kernel/pulls/18330 
perf: backport community patches
                https://gitee.com/openeuler/kernel/pulls/17994 
ACPI/IORT: Fix memory leak in iort_rmr_alloc_sids()
                https://gitee.com/openeuler/kernel/pulls/18331 
Introduce fwctl subystem framework
                https://gitee.com/openeuler/kernel/pulls/18031 
workqueue: Fix kabi broken of enum WORK_OFFQ_POOL_SHIFT
                https://gitee.com/openeuler/kernel/pulls/18320 
samples/bpf: Fix print issue in bpf_rvi_diskstats
                https://gitee.com/openeuler/kernel/pulls/18253 
arm64/mpam: Update MB hardlimit and priority default value forcely
                https://gitee.com/openeuler/kernel/pulls/18195 
cgroup: split cgroup_destroy_wq into 3 workqueues
                https://gitee.com/openeuler/kernel/pulls/18259 
samples/bpf: Fix print issue in dump_swaps()
                https://gitee.com/openeuler/kernel/pulls/18118 
mm: shmem: fix the strategy for the tmpfs 'huge=' options
                https://gitee.com/openeuler/kernel/pulls/18286 

intel
[OLK-6.6] [Intel-SIG] Enable FLR for IDXD halt
                https://gitee.com/openeuler/kernel/pulls/17858 
[OLK-6.6] [Intel-SIG] crypto: iaa - Remove potential infinite loop in check_completion()
                https://gitee.com/openeuler/kernel/pulls/17636 

麒麟
enfs: recreate shard info when re-adding enfs module
                https://gitee.com/openeuler/kernel/pulls/17973 

海光
[OLK-6.6] Optimized the kernel driver of HYGON trusted functions
                https://gitee.com/openeuler/kernel/pulls/18275 

海思
soc: hisilicon: kunpeng_hccs: Fix incorrect log information
                https://gitee.com/openeuler/kernel/pulls/18129 
Updates of HiSilicon Uncore L3C PMU
                https://gitee.com/openeuler/kernel/pulls/18166 
crypto: hisilicon - some bugfix
                https://gitee.com/openeuler/kernel/pulls/17949 
soc cache: support L3 cache lock in framework
                https://gitee.com/openeuler/kernel/pulls/18336 


议题二：
星云：
 Kernel完整支持星云智联板卡M18000网卡驱动
https://gitee.com/openeuler/kernel/pulls/18130

议题三：
多级内存管理项目TieredMMS，考虑贡献社区。 --议题申报人：魏松

议题四：
virtCCA机密虚机热迁移特性补丁推送openEuler 24.03 LTS SP3。 --议题申报人：朱轶凡
https://www.openeuler.org/zh/download/#openEuler%2025.09 25.09已经合入Arm CCA host/guest 特性

三、遗留问题


------------------------------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------
【2025/9/26 Kernel SIG 双周例会】
轮值主持：陈玮【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：关文涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/981549586
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪


二、议题列表

议题一：进展update（李楠&吴腾达）
OLK-6.6进展同步
​    tag更新到6.6.0-111.0.0
​        ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
​    期间合入补丁数87个
​    git log 6.6.0-109.0.0..6.6.0-111.0.0 --oneline --no-merges | wc -l

CVE（19）
        CVE-2025-38724        https://gitee.com/openeuler/kernel/pulls/17919 
        CVE-2025-38147        https://gitee.com/openeuler/kernel/pulls/17941 
        CVE-2025-38680        https://gitee.com/openeuler/kernel/pulls/18016 
        CVE-2025-38710        https://gitee.com/openeuler/kernel/pulls/18000 
        CVE-2025-38637        https://gitee.com/openeuler/kernel/pulls/17887 
        CVE-2025-38723        https://gitee.com/openeuler/kernel/pulls/17976 
        CVE-2025-38194        https://gitee.com/openeuler/kernel/pulls/17861 
        CVE-2025-38173        https://gitee.com/openeuler/kernel/pulls/17850 
        CVE-2025-38694        https://gitee.com/openeuler/kernel/pulls/18071 
        CVE-2025-38516        https://gitee.com/openeuler/kernel/pulls/17939 
        CVE-2025-38683        https://gitee.com/openeuler/kernel/pulls/17997 
        CVE-2025-39773        https://gitee.com/openeuler/kernel/pulls/18061 
        CVE-2025-38018        https://gitee.com/openeuler/kernel/pulls/17940 
        CVE-2025-38143        https://gitee.com/openeuler/kernel/pulls/17854 
        CVE-2025-39718        https://gitee.com/openeuler/kernel/pulls/18026 
        CVE-2025-37840        https://gitee.com/openeuler/kernel/pulls/17889 
        CVE-2025-37838        https://gitee.com/openeuler/kernel/pulls/17839 
        CVE-2025-38691        https://gitee.com/openeuler/kernel/pulls/18017 
        CVE-2025-38693        https://gitee.com/openeuler/kernel/pulls/17977 


bugfix（11）
sched: Fix sched_numa_find_nth_cpu() if mask offline
        https://gitee.com/openeuler/kernel/pulls/17967 
fix oenetcls bugs
        https://gitee.com/openeuler/kernel/pulls/17983 
trace/fgraph: Fix error handling
        https://gitee.com/openeuler/kernel/pulls/18024 
net/oenetcls: Fix crash when removing module
        https://gitee.com/openeuler/kernel/pulls/18088 
mm/shmem, swap: bugfix and improvement of mTHP swap in
        https://gitee.com/openeuler/kernel/pulls/17946 
arm64/mpam: Add quirk for L3 CSU counters
        https://gitee.com/openeuler/kernel/pulls/17972 
arm64/mpam: Add quirk for cmax and cmin
        https://gitee.com/openeuler/kernel/pulls/17969 
Do not shatter hugezeropage on wp-fault
        https://gitee.com/openeuler/kernel/pulls/16579 
iommu: Fix the incorrect exception process of the failed memory allocation
        https://gitee.com/openeuler/kernel/pulls/17974 
virtCCA CoDA: Prevent secure PFs/VFs load or probe native drivers.
        https://gitee.com/openeuler/kernel/pulls/17987 
arm64: RME: handle RIPAS changes before kvm_rec_enter
        https://gitee.com/openeuler/kernel/pulls/17955 

feature
tools/mpam: Add MPAM dynamic adjustment and sampling scripts
        https://gitee.com/openeuler/kernel/pulls/17962 
virtCCA: Improve cvm performance.
        https://gitee.com/openeuler/kernel/pulls/17792 
arm64 kvm: On the Adaptation of CCA and virtCCA.
        https://gitee.com/openeuler/kernel/pulls/18054 
arm64: cca_base: On the Adaptation of CCA and virtCCA.
        https://gitee.com/openeuler/kernel/pulls/18015 

飞腾
[OLK-6.6] drm/phytium: Fix make allmodconfig build fail
        https://gitee.com/openeuler/kernel/pulls/17602 

麒麟
enfs: fix some bugs and optimize performance
        https://gitee.com/openeuler/kernel/pulls/17898 

intel
[Intel-SIG] backporting KVM: x86: Advertise AVX10.1 CPUID to userspace
        https://gitee.com/openeuler/kernel/pulls/17468 
platform/x86: ISST: Add Clearwater Forest to support list
        https://gitee.com/openeuler/kernel/pulls/17663 
cpufreq: intel_pstate: Support Clearwater Forest OOB mode
        https://gitee.com/openeuler/kernel/pulls/17665 
cpufreq: intel_pstate: Add Granite Rapids support in no-HWP mode
        https://gitee.com/openeuler/kernel/pulls/17668 
[OLK-6.6] Intel-SIG: Add new Intel CPU# definition
        https://gitee.com/openeuler/kernel/pulls/17571 
cpufreq: intel_pstate: Update Balance-performance EPP for Granite Rapids
        https://gitee.com/openeuler/kernel/pulls/17681 

海光
[OLK-6.6]Backport upstream CC Measurement support in the efi libstub
        https://gitee.com/openeuler/kernel/pulls/17869 
[OLK-6.6]Hygon: Support RTMR and Attestation that includes RTMR for Hygon CSV3 VM
        https://gitee.com/openeuler/kernel/pulls/17862 

网讯
[OLK-6.6] add support for WangXun 10G/25G/40G
        https://gitee.com/openeuler/kernel/pulls/17932 

海思
Updates of HiSilicon Uncore L3C PMU
        https://gitee.com/openeuler/kernel/pulls/17985 
migration/hisilicon: some bugfix
        https://gitee.com/openeuler/kernel/pulls/17947 

OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-283.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-281.0.0 更新至 5.10.0-283.0.0, 回合补丁数9个
        git log 5.10.0-281.0.0..5.10.0-283.0.0 --oneline --no-merges | wc -l
CVE: (5)
CVE-2025-38693  https://gitee.com/openeuler/kernel/pulls/17995
CVE-2025-39773  https://gitee.com/openeuler/kernel/pulls/18068
CVE-2022-50255  https://gitee.com/openeuler/kernel/pulls/18100
CVE-2025-38724  https://gitee.com/openeuler/kernel/pulls/17970
CVE-2025-38710  https://gitee.com/openeuler/kernel/pulls/17999
Bugfix:
trace/fgraph: Fix error handling
                https://gitee.com/openeuler/kernel/pulls/18025
bpf: Fix memleak due to fentry attach failure
                https://gitee.com/openeuler/kernel/pulls/18102

议题二：征集中（可直接在此填报，需备注汇报人）

三、遗留问题
CVE汇报小组汇报

------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2025/9/12 Kernel SIG 双周例会】
轮值主持：郑增凯【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：陈玮
会议链接：https://meeting.huaweicloud.com:36443/#/j/966528928
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪

二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-281.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-279.0.0 更新至 5.10.0-281.0.0, 回合补丁数82个
        git log 5.10.0-279.0.0..5.10.0-281.0.0 --oneline --no-merges | wc -l
CVE: (20)
CVE-2025-38645  https://gitee.com/openeuler/kernel/pulls/17912 
CVE-2025-37834  https://gitee.com/openeuler/kernel/pulls/17759 
CVE-2024-56602  https://gitee.com/openeuler/kernel/pulls/17686 
CVE-2025-38611  https://gitee.com/openeuler/kernel/pulls/17817 
CVE-2025-38119  https://gitee.com/openeuler/kernel/pulls/17867 
CVE-2025-21759  https://gitee.com/openeuler/kernel/pulls/17791 
CVE-2025-38632  https://gitee.com/openeuler/kernel/pulls/17806 
CVE-2022-49622  https://gitee.com/openeuler/kernel/pulls/17688 
CVE-2025-38563  https://gitee.com/openeuler/kernel/pulls/17795 
CVE-2025-22056  https://gitee.com/openeuler/kernel/pulls/17698 
CVE-2025-38174  https://gitee.com/openeuler/kernel/pulls/17773 
CVE-2025-38652  https://gitee.com/openeuler/kernel/pulls/17805 
CVE-2025-38399  https://gitee.com/openeuler/kernel/pulls/17443 
CVE-2025-38085  https://gitee.com/openeuler/kernel/pulls/17749 
CVE-2025-37911  https://gitee.com/openeuler/kernel/pulls/17710 
CVE-2024-54458  https://gitee.com/openeuler/kernel/pulls/17793 
CVE-2025-38671  https://gitee.com/openeuler/kernel/pulls/17743 
CVE-2025-38502  https://gitee.com/openeuler/kernel/pulls/17933 
CVE-2024-56558  https://gitee.com/openeuler/kernel/pulls/17738 
CVE-2025-38602  https://gitee.com/openeuler/kernel/pulls/17799 

Bugfix:
mm/smaps: fix race between smaps_hugetlb_range and migration
                https://gitee.com/openeuler/kernel/pulls/17765 
mm/hugetlb: fix surplus pages in dissolve_free_huge_page()
                https://gitee.com/openeuler/kernel/pulls/17820 
cpufreq: Init policy->rwsem before it may be possibly used
                https://gitee.com/openeuler/kernel/pulls/17852 
Fix trace may OOB when trace_get_user failed
                https://gitee.com/openeuler/kernel/pulls/17740 
page_pool: Fix use-after-free in page_pool_recycle_in_ring
                https://gitee.com/openeuler/kernel/pulls/17801 

intel:
Add TPMI RAPL PMU support for GNR/CWF and later Intel Xeon machines
                https://gitee.com/openeuler/kernel/pulls/17682 
cpufreq: intel_pstate: Add Granite Rapids support in no-HWP mode
                https://gitee.com/openeuler/kernel/pulls/17667 
intel_pstate support OOB mode for EMR/GNR/SRF/CWF
                https://gitee.com/openeuler/kernel/pulls/17664 
Add Model specific EPP adjustment support for EMR/SPR/GNR
                https://gitee.com/openeuler/kernel/pulls/17680 
platform/x86: ISST: Add Clearwater Forest to support list
                https://gitee.com/openeuler/kernel/pulls/17662 
申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/17849 
飞腾：
[OLK-5.10] dma: phytium: Add PSWIOTLB mechanism to improve DMA performance
                https://gitee.com/openeuler/kernel/pulls/16636 
兆芯：
[OLK-5.5] perf/zhaoxin/uncore: Enhance uncore support and fix related bugs
                https://gitee.com/openeuler/kernel/pulls/17904 
海思：
RDMA/hns: Fix bond not cleared when the configuration becomes invalid
                https://gitee.com/openeuler/kernel/pulls/17767 
ROH: Add crc_err_cnt and retry_cnt mib statistics
                https://gitee.com/openeuler/kernel/pulls/17573 
风河：
[OLK-5.10] backport the follow important bugfix for nvme driver from upstream linux-5.10.y
                https://gitee.com/openeuler/kernel/pulls/17316 
[OLK-5.10] backport important bugfix for lpfc driver from upstream linux-5.10.y
                https://gitee.com/openeuler/kernel/pulls/17885 

OLK-6.6进展同步
​    tag更新到6.6.0-109.0.0
​        ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP2
​    期间合入补丁数223个
​    git log 6.6.0-107.0.0..6.6.0-109.0.0 --oneline --no-merges | wc -l

CVE（83）
        CVE-2025-38312        https://gitee.com/openeuler/kernel/pulls/17836 
        CVE-2025-38351        https://gitee.com/openeuler/kernel/pulls/17470 
        CVE-2025-37959        https://gitee.com/openeuler/kernel/pulls/17707 
        CVE-2025-38022        https://gitee.com/openeuler/kernel/pulls/17780 
        CVE-2025-38102        https://gitee.com/openeuler/kernel/pulls/17846 
        CVE-2025-38645        https://gitee.com/openeuler/kernel/pulls/17813 
        CVE-2025-37829        https://gitee.com/openeuler/kernel/pulls/17834 
        CVE-2025-38621        https://gitee.com/openeuler/kernel/pulls/17866 
        CVE-2025-38087        https://gitee.com/openeuler/kernel/pulls/17783 
        CVE-2025-22086        https://gitee.com/openeuler/kernel/pulls/17694 
        CVE-2025-21746        https://gitee.com/openeuler/kernel/pulls/17818 
        CVE-2025-22021        https://gitee.com/openeuler/kernel/pulls/17699 
        CVE-2025-37879        https://gitee.com/openeuler/kernel/pulls/17703 
        CVE-2025-22056        https://gitee.com/openeuler/kernel/pulls/17697 
        CVE-2025-21678        https://gitee.com/openeuler/kernel/pulls/17685 
        CVE-2025-38420        https://gitee.com/openeuler/kernel/pulls/17590 
        CVE-2025-22057        https://gitee.com/openeuler/kernel/pulls/17696 
        CVE-2025-38410        https://gitee.com/openeuler/kernel/pulls/17584 
        CVE-2025-38687        https://gitee.com/openeuler/kernel/pulls/17945 
        CVE-2025-38574        https://gitee.com/openeuler/kernel/pulls/17892 
        CVE-2025-38097        https://gitee.com/openeuler/kernel/pulls/17786 
        CVE-2025-38584        https://gitee.com/openeuler/kernel/pulls/17936 
        CVE-2025-38408        https://gitee.com/openeuler/kernel/pulls/17585 
        CVE-2025-38590        https://gitee.com/openeuler/kernel/pulls/17883 
        CVE-2025-38020        https://gitee.com/openeuler/kernel/pulls/17782 
        CVE-2025-38019        https://gitee.com/openeuler/kernel/pulls/17781 
        CVE-2025-38399        https://gitee.com/openeuler/kernel/pulls/17442 
        CVE-2025-38201        https://gitee.com/openeuler/kernel/pulls/17788 
        CVE-2025-37912        https://gitee.com/openeuler/kernel/pulls/17718 
        CVE-2025-38042        https://gitee.com/openeuler/kernel/pulls/17776 
        CVE-2025-22063        https://gitee.com/openeuler/kernel/pulls/17715 
        CVE-2025-38671        https://gitee.com/openeuler/kernel/pulls/17742 
        CVE-2025-38502        https://gitee.com/openeuler/kernel/pulls/17882 
        CVE-2025-38635        https://gitee.com/openeuler/kernel/pulls/17937 
        CVE-2025-37794        https://gitee.com/openeuler/kernel/pulls/17700 
        CVE-2025-37909        https://gitee.com/openeuler/kernel/pulls/17711 
        CVE-2025-38593        https://gitee.com/openeuler/kernel/pulls/17913 
        CVE-2025-38057        https://gitee.com/openeuler/kernel/pulls/17775 
        CVE-2025-37961        https://gitee.com/openeuler/kernel/pulls/17717 
        CVE-2025-38409        https://gitee.com/openeuler/kernel/pulls/17586 
        CVE-2025-38425        https://gitee.com/openeuler/kernel/pulls/17594 
        CVE-2025-38467        https://gitee.com/openeuler/kernel/pulls/17583 
        CVE-2025-38334        https://gitee.com/openeuler/kernel/pulls/17922 
        CVE-2025-38039        https://gitee.com/openeuler/kernel/pulls/17777 
        CVE-2025-37875        https://gitee.com/openeuler/kernel/pulls/17705 
        CVE-2025-38166        https://gitee.com/openeuler/kernel/pulls/17785 
        CVE-2025-37990        https://gitee.com/openeuler/kernel/pulls/17712 
        CVE-2025-37945        https://gitee.com/openeuler/kernel/pulls/17708 
        CVE-2025-38227        https://gitee.com/openeuler/kernel/pulls/17923 
        CVE-2025-38611        https://gitee.com/openeuler/kernel/pulls/17816 
        CVE-2025-22089        https://gitee.com/openeuler/kernel/pulls/17693 
        CVE-2025-37911        https://gitee.com/openeuler/kernel/pulls/17709 
        CVE-2025-38569        https://gitee.com/openeuler/kernel/pulls/17798 
        CVE-2025-37859        https://gitee.com/openeuler/kernel/pulls/17704 
        CVE-2025-38010        https://gitee.com/openeuler/kernel/pulls/17778 
        CVE-2025-38563        https://gitee.com/openeuler/kernel/pulls/17794 
        CVE-2025-38024        https://gitee.com/openeuler/kernel/pulls/17779 
        CVE-2025-38448        https://gitee.com/openeuler/kernel/pulls/17596 
        CVE-2025-37752        https://gitee.com/openeuler/kernel/pulls/17844 
        CVE-2025-38305        https://gitee.com/openeuler/kernel/pulls/17911 
        CVE-2025-38044        https://gitee.com/openeuler/kernel/pulls/17679 
        CVE-2025-21864        https://gitee.com/openeuler/kernel/pulls/17689 
        CVE-2025-38406        https://gitee.com/openeuler/kernel/pulls/17587 
        CVE-2025-38154        https://gitee.com/openeuler/kernel/pulls/17789 
        CVE-2025-22106        https://gitee.com/openeuler/kernel/pulls/17692 
        CVE-2025-37989        https://gitee.com/openeuler/kernel/pulls/17713 
        CVE-2025-37789        https://gitee.com/openeuler/kernel/pulls/17701 
        CVE-2025-22007        https://gitee.com/openeuler/kernel/pulls/17690 
        CVE-2025-38066        https://gitee.com/openeuler/kernel/pulls/17678 
        CVE-2025-37772        https://gitee.com/openeuler/kernel/pulls/17706 
        CVE-2025-38003        https://gitee.com/openeuler/kernel/pulls/17714 
        CVE-2025-38004        https://gitee.com/openeuler/kernel/pulls/17774 
        CVE-2025-38632        https://gitee.com/openeuler/kernel/pulls/17804 
        CVE-2025-38500        https://gitee.com/openeuler/kernel/pulls/17845 
        CVE-2025-38165        https://gitee.com/openeuler/kernel/pulls/17784 
        CVE-2025-38119        https://gitee.com/openeuler/kernel/pulls/17865 
        CVE-2025-38422        https://gitee.com/openeuler/kernel/pulls/17593 
        CVE-2025-38540        https://gitee.com/openeuler/kernel/pulls/17772 
        CVE-2025-38416        https://gitee.com/openeuler/kernel/pulls/17582 
        CVE-2025-22064        https://gitee.com/openeuler/kernel/pulls/17695 
        CVE-2025-37749        https://gitee.com/openeuler/kernel/pulls/17702 
        CVE-2025-38428        https://gitee.com/openeuler/kernel/pulls/17595 
        CVE-2025-37924        https://gitee.com/openeuler/kernel/pulls/17842 

bugfix（23）
fs/resctrl: Fix max_threshold_occupancy write operation
                https://gitee.com/openeuler/kernel/pulls/17841 
v3  arm64: Fix actlr_el1 can not set problem in guest
                https://gitee.com/openeuler/kernel/pulls/17853 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.64-6.6.66 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/17337 
tracing/probes: Avoid using params uninitialized in parse_btf_arg()
                https://gitee.com/openeuler/kernel/pulls/17824 
arm64/mpam: Fix the logic that determines whether an MPAM MSC should initialize
                https://gitee.com/openeuler/kernel/pulls/17823 
arm64/mpam: Half the number of RMIDs for all resources under CDP mode
                https://gitee.com/openeuler/kernel/pulls/17915 
[backport]KVM: arm64: Select default PMU in KVM_ARM_VCPU_INIT handler
                https://gitee.com/openeuler/kernel/pulls/17924 
[OLK-6.6] backport important bugfix for lpfc driver from upstream linux-6.6.y
                https://gitee.com/openeuler/kernel/pulls/17880 
mm/hugetlb: fix surplus pages in dissolve_free_huge_page()
                https://gitee.com/openeuler/kernel/pulls/17821 
page_pool: Fix use-after-free in page_pool_recycle_in_ring
                https://gitee.com/openeuler/kernel/pulls/17790 
arm64/mpam: Fix num_rmids when enable CDP mode
                https://gitee.com/openeuler/kernel/pulls/17840 
scsi: Remove scsi device no_start_on_resume flag
                https://gitee.com/openeuler/kernel/pulls/17868 
[OLK-6.6] backport important bugfix for lpfc driver from upstream linux-6.6.y
                https://gitee.com/openeuler/kernel/pulls/17294 
mm/hugetlb: fix set_max_huge_pages() when there are surplus pages
                https://gitee.com/openeuler/kernel/pulls/17838 
v2  perf/aux: Fix pending disable flow when the AUX ring buffer overruns
                https://gitee.com/openeuler/kernel/pulls/17835 
proc: use the same treatment to check proc_lseek as ones for proc_read_iter et.al
                https://gitee.com/openeuler/kernel/pulls/17733 
sdei_watchdog: add percpu flag to fix sdei watchdog state in lpi mode
                https://gitee.com/openeuler/kernel/pulls/17856 
mm/smaps: fix race between smaps_hugetlb_range and migration
                https://gitee.com/openeuler/kernel/pulls/17763 
Fix trace may OOB when trace_get_user failed
                https://gitee.com/openeuler/kernel/pulls/17741 
v3  HiSock Redirect Framework
                https://gitee.com/openeuler/kernel/pulls/17797 
[OLK-6.6] Fix CVE-2025-37924
                https://gitee.com/openeuler/kernel/pulls/17842 
Fix netns reference count issue
                https://gitee.com/openeuler/kernel/pulls/17244 
sched: apply custom cpu range for idle cpu
                https://gitee.com/openeuler/kernel/pulls/17879 
virtCCA CoDA: Expose I/O hook interfaces.
                https://gitee.com/openeuler/kernel/pulls/17914 

特性
arm64/mpam: Add mb_only boot option
        https://gitee.com/openeuler/kernel/pulls/17731 
v2  sched: More flexible use of CPU quota when CPU is idle
        https://gitee.com/openeuler/kernel/pulls/17659 
mm: madvise: use per_vma lock for MADV_FREE
        https://gitee.com/openeuler/kernel/pulls/17635 
网络多路径功能
        https://gitee.com/openeuler/kernel/pulls/17768 
ext4 文件系统块分配干扰隔离增强
        https://gitee.com/openeuler/kernel/pulls/17815 

北京纵存
LeapIOraid: fix strscpy size argument
        https://gitee.com/openeuler/kernel/pulls/17890 

申威
[OLK-6.6]:update patches for sw64 architecture
        https://gitee.com/openeuler/kernel/pulls/17848 

海光
Provide host-side administrators/users with real-time access to the usage status of CSV3 CMA memory.
        https://gitee.com/openeuler/kernel/pulls/17756 

兆新
[OLK-6.6] i2c/zhaoxin: I2C controller driver enhancement and optimization
        https://gitee.com/openeuler/kernel/pulls/9218 
[OLK-6.6] perf/zhaoxin/uncore: Enhance uncore support and fix related bugs
        https://gitee.com/openeuler/kernel/pulls/17902 

海思
fix bug in hdbss
        https://gitee.com/openeuler/kernel/pulls/17748 
RDMA/hns: Fix bond not cleared when the configuration becomes invalid
        https://gitee.com/openeuler/kernel/pulls/17766 
arm64: perf: Add support for HIP12 hw metric
        https://gitee.com/openeuler/kernel/pulls/17755 
gic: increase the arch_timer
        https://gitee.com/openeuler/kernel/pulls/17800 
cpufreq: Exit governor when failed to start old governor
        https://gitee.com/openeuler/kernel/pulls/17609 
ROH: Add crc_err_cnt and retry_cnt mib statistics
        https://gitee.com/openeuler/kernel/pulls/17574 


议题二：committer覆盖范围列表刷新评审（吴腾达）
为支持PR通知精准推送到各个committer，现对现有committer覆盖范围进行审视和更新，具体如下：
https://gitee.com/openeuler/community/pulls/6801
会议结论：
1、列表内容评审通过；
2、体系结构里面，原本的Jackie Liu、增凯为最早期人员参与不足时的占位，现在已有专门体系结构committer，Jackie Liu、增凯可去掉；
3、补充爱春邮箱变更。shiaichun@hygon.cn


议题三：使用 22.03-LTS-SP4 的 5.10.0-279.0.0 内核版本在AMD、海光服务器上进行Unixbench跑分低问题讨论（苟超）
在AMD 3代、海光3、4代CPU服务器 + 5.10.0-279.0.0内核的环境中使用Unixbench跑分，发现跑分结果相较2203 LTS SP3的5.10.0-196.0.0内核下降明显（单核跑分下降38%、多核跑分下降8%），从跑分的结果来看，在吞吐类的跑分项分数较低。有对比SP4的其他版本，发现在版本从22.03-LTS-SP4 的 5.10.0-220.0.0 升级为 5.10.0-221.0.0开始出现该问题。
》转issue跟进

议题四：征集中（可直接在此填报，需备注汇报人）

三、遗留问题


-------------------------------------------------------------------------------------------------------------------------------------
【2025/8/29 Kernel SIG 双周例会】
轮值主持：吴腾达【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：郑增凯
会议链接：https://meeting.huaweicloud.com:36443/#/j/960874149
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪
1. CVE 协作小组创建 —— 李楠
【Done】已开始运作
2. 历史遗留PR跟进 —— 李楠、吴腾达
【Done】
3. issue清理策略待讨论 ——郑增凯
【Done】先小范围运作，王炼、陈玮、增凯


二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-279.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-277.0.0 更新至 5.10.0-279.0.0, 回合补丁数75个
        git log 5.10.0-277.0.0..5.10.0-279.0.0 --oneline --no-merges | wc -l
CVE: (34)
CVE-2022-49377  https://gitee.com/openeuler/kernel/pulls/17452 
CVE-2025-38529  https://gitee.com/openeuler/kernel/pulls/17568 
CVE-2025-38464  https://gitee.com/openeuler/kernel/pulls/17619 
CVE-2025-21772  https://gitee.com/openeuler/kernel/pulls/15618 
CVE-2025-37992  https://gitee.com/openeuler/kernel/pulls/17376 
CVE-2025-38124  https://gitee.com/openeuler/kernel/pulls/17617 
CVE-2025-37796  https://gitee.com/openeuler/kernel/pulls/17539 
CVE-2025-38495  https://gitee.com/openeuler/kernel/pulls/17480 
CVE-2024-53214  https://gitee.com/openeuler/kernel/pulls/17612 
CVE-2025-22075  https://gitee.com/openeuler/kernel/pulls/17624 
CVE-2025-38539  https://gitee.com/openeuler/kernel/pulls/17581 
CVE-2025-38465  https://gitee.com/openeuler/kernel/pulls/17727 
CVE-2024-58093  https://gitee.com/openeuler/kernel/pulls/17527 
CVE-2025-38052  https://gitee.com/openeuler/kernel/pulls/17621 
CVE-2025-38184  https://gitee.com/openeuler/kernel/pulls/17622 
CVE-2022-49390  https://gitee.com/openeuler/kernel/pulls/17613 
CVE-2024-57906  https://gitee.com/openeuler/kernel/pulls/17580 
CVE-2024-56678  https://gitee.com/openeuler/kernel/pulls/17579 
CVE-2025-22018  https://gitee.com/openeuler/kernel/pulls/17616 
CVE-2025-37915  https://gitee.com/openeuler/kernel/pulls/17545 
CVE-2025-37780  https://gitee.com/openeuler/kernel/pulls/17626 
CVE-2024-57982  https://gitee.com/openeuler/kernel/pulls/17614 
CVE-2025-38445  https://gitee.com/openeuler/kernel/pulls/17454 
CVE-2024-58069  https://gitee.com/openeuler/kernel/pulls/17627 
CVE-2025-37890  https://gitee.com/openeuler/kernel/pulls/17576 
CVE-2025-38323  https://gitee.com/openeuler/kernel/pulls/17522 
CVE-2025-22058  https://gitee.com/openeuler/kernel/pulls/17615 
CVE-2025-38565  https://gitee.com/openeuler/kernel/pulls/17631 
CVE-2025-37798  https://gitee.com/openeuler/kernel/pulls/17543 
CVE-2025-38115  https://gitee.com/openeuler/kernel/pulls/17618 
CVE-2025-37797  https://gitee.com/openeuler/kernel/pulls/17623 
CVE-2025-37913  https://gitee.com/openeuler/kernel/pulls/17544 
CVE-2022-49623  https://gitee.com/openeuler/kernel/pulls/17525 
CVE-2025-38192  https://gitee.com/openeuler/kernel/pulls/17620 
Bugfix:
ftrace: Also allocate and copy hash for reading of filter files
                https://gitee.com/openeuler/kernel/pulls/17675 
hugelb: do not sleep during spinlock hugetlb_lock
                https://gitee.com/openeuler/kernel/pulls/17566 
two bugfix for arm64 support HVO
                https://gitee.com/openeuler/kernel/pulls/17603 
ftrace: Fix potential warning in trace_printk_seq during ftrace_dump
                https://gitee.com/openeuler/kernel/pulls/17670 
net: vlan: fix VLAN 0 refcount imbalance of toggling filtering during runtime
                https://gitee.com/openeuler/kernel/pulls/17536 
selftests/bpf: Add remaining ASSERT_xxx() variants
                https://gitee.com/openeuler/kernel/pulls/17657 
arm64: mm: fix EFI_BUFFER_TOO_SMALL problem for MemoryOnChipMode
                https://gitee.com/openeuler/kernel/pulls/17554 
arm64: mm: Update PBHA related variable name
                https://gitee.com/openeuler/kernel/pulls/15064 
perf/core: Don't leak AUX buffer refcount on allocation failure
                https://gitee.com/openeuler/kernel/pulls/17726 
sched: Fix sched tunable parameter range overflow
                https://gitee.com/openeuler/kernel/pulls/17532 
trace/fgraph: Fix the warning caused by missing unregister notifier
                https://gitee.com/openeuler/kernel/pulls/1774
mm/dpool: mark dpool hugetlb page as dirty in free_huge_page()
                https://gitee.com/openeuler/kernel/pulls/17723 
RDMA/hns: Fix dip entries leak on devices newer than hip09
                https://gitee.com/openeuler/kernel/pulls/17531 
Feature:
v2  kernfs performance optimization
                https://gitee.com/openeuler/kernel/pulls/17494 

OLK-6.6进展同步
    tag更新到6.6.0-107.0.0
        ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数186个
    git log 6.6.0-105.0.0..6.6.0-107.0.0 --oneline --no-merges | wc -l

CVE（45）
        CVE-2025-37801        https://gitee.com/openeuler/kernel/pulls/17719 
        CVE-2025-38456        https://gitee.com/openeuler/kernel/pulls/17687 
        CVE-2025-38441        https://gitee.com/openeuler/kernel/pulls/17637 
        CVE-2025-38445        https://gitee.com/openeuler/kernel/pulls/17453 
        CVE-2025-21839        https://gitee.com/openeuler/kernel/pulls/17649 
        CVE-2025-38310        https://gitee.com/openeuler/kernel/pulls/17640 
        CVE-2025-37913        https://gitee.com/openeuler/kernel/pulls/17546 
        CVE-2025-37796        https://gitee.com/openeuler/kernel/pulls/17538 
        CVE-2025-38495        https://gitee.com/openeuler/kernel/pulls/17481 
        CVE-2025-37767        https://gitee.com/openeuler/kernel/pulls/17629 
        CVE-2025-38526        https://gitee.com/openeuler/kernel/pulls/17592 
        CVE-2025-38013        https://gitee.com/openeuler/kernel/pulls/17652 
        CVE-2025-38248        https://gitee.com/openeuler/kernel/pulls/17644 
        CVE-2025-38465        https://gitee.com/openeuler/kernel/pulls/17645 
        CVE-2025-22097        https://gitee.com/openeuler/kernel/pulls/17569 
        CVE-2025-37780        https://gitee.com/openeuler/kernel/pulls/17628 
        CVE-2025-38528        https://gitee.com/openeuler/kernel/pulls/17564 
        CVE-2025-38464        https://gitee.com/openeuler/kernel/pulls/17639 
        CVE-2025-38068        https://gitee.com/openeuler/kernel/pulls/17720 
        CVE-2025-37890        https://gitee.com/openeuler/kernel/pulls/17575 
        CVE-2025-22102        https://gitee.com/openeuler/kernel/pulls/17747 
        CVE-2025-38565        https://gitee.com/openeuler/kernel/pulls/17632 
        CVE-2025-38211        https://gitee.com/openeuler/kernel/pulls/17523 
        CVE-2025-38089        https://gitee.com/openeuler/kernel/pulls/17646 
        CVE-2025-38184        https://gitee.com/openeuler/kernel/pulls/17642 
        CVE-2025-37798        https://gitee.com/openeuler/kernel/pulls/17542 
        CVE-2025-38369        https://gitee.com/openeuler/kernel/pulls/17633 
        CVE-2025-38112        https://gitee.com/openeuler/kernel/pulls/17643 
        CVE-2025-38251        https://gitee.com/openeuler/kernel/pulls/17517 
        CVE-2025-38009        https://gitee.com/openeuler/kernel/pulls/17651 
        CVE-2025-38192        https://gitee.com/openeuler/kernel/pulls/17641 
        CVE-2025-38670        https://gitee.com/openeuler/kernel/pulls/17730 
        CVE-2025-38515        https://gitee.com/openeuler/kernel/pulls/17606 
        CVE-2025-38444        https://gitee.com/openeuler/kernel/pulls/17455 
        CVE-2025-38239        https://gitee.com/openeuler/kernel/pulls/17307 
        CVE-2025-38045        https://gitee.com/openeuler/kernel/pulls/17653 
        CVE-2025-37819        https://gitee.com/openeuler/kernel/pulls/17309 
        CVE-2025-38539        https://gitee.com/openeuler/kernel/pulls/17570 
        CVE-2025-38006        https://gitee.com/openeuler/kernel/pulls/17728 
        CVE-2025-38473        https://gitee.com/openeuler/kernel/pulls/17519 
        CVE-2025-37915        https://gitee.com/openeuler/kernel/pulls/17547 
        CVE-2025-38463        https://gitee.com/openeuler/kernel/pulls/17638 
        CVE-2025-38052        https://gitee.com/openeuler/kernel/pulls/17647 
        CVE-2025-38375        https://gitee.com/openeuler/kernel/pulls/17524 
        CVE-2025-37920        https://gitee.com/openeuler/kernel/pulls/17648 

Bugfix（20）
ftrace: Also allocate and copy hash for reading of filter files
                https://gitee.com/openeuler/kernel/pulls/17674 
bpf-rvi: pidns: fix null-pointer-derefence in pidns_update_load_tasks
                https://gitee.com/openeuler/kernel/pulls/17671 
hrtimers: Update new CPU's next event in hrtimers_cpu_dying()
                https://gitee.com/openeuler/kernel/pulls/17716 
trace/fgraph: Fix the warning caused by missing unregister notifier
                https://gitee.com/openeuler/kernel/pulls/17744 
two bugfix for arm64 support HVO
                https://gitee.com/openeuler/kernel/pulls/17600 
gpiolib: Get rid of never false gpio_is_valid() calls
                https://gitee.com/openeuler/kernel/pulls/17515 
v2  mm/mem_sampling: preserve kernel subsystem SPE state across perf sampling
                https://gitee.com/openeuler/kernel/pulls/17495 
v2  Fix for bpf samples and selftests
                https://gitee.com/openeuler/kernel/pulls/17683 
net: vlan: fix VLAN 0 refcount imbalance of toggling filtering during runtime
                https://gitee.com/openeuler/kernel/pulls/17537 
HID: pidff: Fix null pointer dereference in pidff_find_fields
                https://gitee.com/openeuler/kernel/pulls/17634 
ftrace: Fix potential warning in trace_printk_seq during ftrace_dump
                https://gitee.com/openeuler/kernel/pulls/17669 
mm/util: make memdup_user_nul() similar to memdup_user()
                https://gitee.com/openeuler/kernel/pulls/17608 
perf/core: Don't leak AUX buffer refcount on allocation failure
                https://gitee.com/openeuler/kernel/pulls/17725 
[OLK-6.6] backport important bugfix for Broadcom BCM57414 nic driver from upstream linux-6.6.y
                https://gitee.com/openeuler/kernel/pulls/17293 
sched/psi: change permissions of /proc/pressure/stat
                https://gitee.com/openeuler/kernel/pulls/17530 
v2  Fix static check warning reported by coccinelle
                https://gitee.com/openeuler/kernel/pulls/17677 
filemap: move prefaulting out of hot write path
                https://gitee.com/openeuler/kernel/pulls/17556 
KVM: arm64: fix memory leak in TLBI
                https://gitee.com/openeuler/kernel/pulls/16545 
iBMA: Fix veth soft lockup by adding DMA-pre-readl sync
                https://gitee.com/openeuler/kernel/pulls/17751 
mm/dpool: mark dpool hugetlb page as dirty in free_huge_folio()
                https://gitee.com/openeuler/kernel/pulls/17724 

性能优化
mm: optimize mremap() by PTE batching
                https://gitee.com/openeuler/kernel/pulls/17529 
Enhance soft hwpoison handling and injection
                https://gitee.com/openeuler/kernel/pulls/17565 

特性
cgroup/cpuset: Support dynamic affinity feature
                https://gitee.com/openeuler/kernel/pulls/17660 
高性能容器资源视图
                https://gitee.com/openeuler/kernel/pulls/17526 

麒麟
fix some bugs of enfs
                https://gitee.com/openeuler/kernel/pulls/17479 

申威
[OLK-6.6]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/17438 

飞腾
Delete PHYTIUM_CPU_PART_FTC862 macro
                https://gitee.com/openeuler/kernel/pulls/17597 
[OLK-6.6] dma: phytium: Add PSWIOTLB mechanism to improve DMA performance
                https://gitee.com/openeuler/kernel/pulls/16528 

海思
RDMA/hns: Fix dip entries leak on devices newer than hip09
                https://gitee.com/openeuler/kernel/pulls/17553 
soc cache: Fix incorrect error path of ioctl
                https://gitee.com/openeuler/kernel/pulls/17737 
PM / devfreq: Add HiSilicon uncore frequency scaling driver
                https://gitee.com/openeuler/kernel/pulls/17510 
net: phy: motorcomm: Add support for PHY LEDs on YT8521
                https://gitee.com/openeuler/kernel/pulls/17650 



议题二：讨论一个cpuinfo_x86结构的kABI修复问题 - 曾昭荣(Intel)
   PR: https://gitee.com/openeuler/kernel/pulls/17571
   回合 6.6.y stable的如下commit会导致break kABI: 
       cb3491e875f6 x86/cpu/vfm: Add/initialize x86_vfm field to struct cpuinfo_x86
   修复方法讨论：
       https://gitee.com/openeuler/intel-kernel/commit/b4af8e893995f7d6699f81389c1b2d08af553cd8
会议结论：通过

议题三：PR 跟踪和通知机制讨论 - 谢秀奇
https://gitee.com/api/v5/swagger#/getV5UsersUsername 根据pr所有者的username获取用户信息（包含email）

议题三：征集中（可直接在此填报，需备注汇报人）

三、遗留问题


-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/8/15 Kernel SIG 双周例会】
轮值主持：廖涛【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯->陈玮->关文涛】
下次轮值主持：吴腾达
会议链接：https://meeting.huaweicloud.com:36443/#/j/963670522
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪

1. 关闭历史遗留的issue和pr —— 郑增凯
已关闭ci-robot自动提交的状态是冲突的PR 893个


二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-277.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-275.0.0 更新至 5.10.0-277.0.0, 回合补丁数88个
        git log 5.10.0-275.0.0..5.10.0-277.0.0 --oneline --no-merges | wc -l
CVE: (28)
CVE-2025-38439  https://gitee.com/openeuler/kernel/pulls/17379
CVE-2025-38332  https://gitee.com/openeuler/kernel/pulls/17350
CVE-2025-38125  https://gitee.com/openeuler/kernel/pulls/17425
CVE-2025-38362  https://gitee.com/openeuler/kernel/pulls/17373
CVE-2025-38063  https://gitee.com/openeuler/kernel/pulls/16940
CVE-2025-38222  https://gitee.com/openeuler/kernel/pulls/17370
CVE-2025-37823  https://gitee.com/openeuler/kernel/pulls/17504
CVE-2025-38386  https://gitee.com/openeuler/kernel/pulls/17433
CVE-2025-21920  https://gitee.com/openeuler/kernel/pulls/17485
CVE-2025-38371  https://gitee.com/openeuler/kernel/pulls/17429
CVE-2025-38263  https://gitee.com/openeuler/kernel/pulls/17424
CVE-2024-56616  https://gitee.com/openeuler/kernel/pulls/17417
CVE-2025-23142  https://gitee.com/openeuler/kernel/pulls/17503
CVE-2025-38474  https://gitee.com/openeuler/kernel/pulls/17407
CVE-2025-38459  https://gitee.com/openeuler/kernel/pulls/17365
CVE-2022-49183  https://gitee.com/openeuler/kernel/pulls/17383
CVE-2025-21891  https://gitee.com/openeuler/kernel/pulls/17388
CVE-2022-49420  https://gitee.com/openeuler/kernel/pulls/17382
CVE-2025-21692  https://gitee.com/openeuler/kernel/pulls/17377
CVE-2025-22004  https://gitee.com/openeuler/kernel/pulls/17486
CVE-2024-57798  https://gitee.com/openeuler/kernel/pulls/17418
CVE-2024-58237  https://gitee.com/openeuler/kernel/pulls/17505
CVE-2025-38352  https://gitee.com/openeuler/kernel/pulls/17457
CVE-2025-38387  https://gitee.com/openeuler/kernel/pulls/17374
CVE-2025-21700  https://gitee.com/openeuler/kernel/pulls/17381
CVE-2025-38181  https://gitee.com/openeuler/kernel/pulls/17347
CVE-2025-21926  https://gitee.com/openeuler/kernel/pulls/17484
CVE-2025-21702  https://gitee.com/openeuler/kernel/pulls/17389
Bugfix:
ovl: fix general protection fault in security_inode_getattr
                https://gitee.com/openeuler/kernel/pulls/17315
selftests/tracing: Fix false failure of subsystem event test
                https://gitee.com/openeuler/kernel/pulls/17394
v2  eventpoll: Fix return fixed cpu bug in set_prefetch_numa_cpu()
                https://gitee.com/openeuler/kernel/pulls/17344
arm-smmu-v3: adjust ecmdq log level
                https://gitee.com/openeuler/kernel/pulls/17466
drivers:misc:sdma-dae: fix incorrect debugfs print
                https://gitee.com/openeuler/kernel/pulls/17461
ROH: fix variable type inconsistency issue
                https://gitee.com/openeuler/kernel/pulls/17506
AMD:
[OLK 5.10] AMD HSMP driver support patches backport
                https://gitee.com/openeuler/kernel/pulls/17359
[OLK 5.10] AMD Turin and auto IBRS patches backport
                https://gitee.com/openeuler/kernel/pulls/17292
申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/17437


20250815
OLK-6.6进展同步
​    tag更新到6.6.0-105.0.0
​    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
​    期间合入补丁数208个
​    git log 6.6.0-103.0.0..6.6.0-105.0.0 --oneline --no-merges | wc -l

CVE（50）
        CVE-2024-58237        https://gitee.com/openeuler/kernel/pulls/17198 
        CVE-2025-38324        https://gitee.com/openeuler/kernel/pulls/17259 
        CVE-2025-38075        https://gitee.com/openeuler/kernel/pulls/16958 
        CVE-2025-38117        https://gitee.com/openeuler/kernel/pulls/17148 
        CVE-2025-38015        https://gitee.com/openeuler/kernel/pulls/17299 
        CVE-2025-38115        https://gitee.com/openeuler/kernel/pulls/17215 
        CVE-2025-38226        https://gitee.com/openeuler/kernel/pulls/17154 
        CVE-2025-22103        https://gitee.com/openeuler/kernel/pulls/17181 
        CVE-2025-38337        https://gitee.com/openeuler/kernel/pulls/17101 
        CVE-2025-38190        https://gitee.com/openeuler/kernel/pulls/17273 
        CVE-2025-37786        https://gitee.com/openeuler/kernel/pulls/17179 
        CVE-2025-22060        https://gitee.com/openeuler/kernel/pulls/17185 
        CVE-2025-37757        https://gitee.com/openeuler/kernel/pulls/17194 
        CVE-2025-21997        https://gitee.com/openeuler/kernel/pulls/17172 
        CVE-2025-37824        https://gitee.com/openeuler/kernel/pulls/17199 
        CVE-2025-21961        https://gitee.com/openeuler/kernel/pulls/17170 
        CVE-2025-37865        https://gitee.com/openeuler/kernel/pulls/17175 
        CVE-2025-38103        https://gitee.com/openeuler/kernel/pulls/17150 
        CVE-2025-38219        https://gitee.com/openeuler/kernel/pulls/17153 
        CVE-2024-56658        https://gitee.com/openeuler/kernel/pulls/17238 
        CVE-2025-37797        https://gitee.com/openeuler/kernel/pulls/17177 
        CVE-2025-22062        https://gitee.com/openeuler/kernel/pulls/17184 
        CVE-2025-38391        https://gitee.com/openeuler/kernel/pulls/17310 
        CVE-2025-22058        https://gitee.com/openeuler/kernel/pulls/17186 
        CVE-2025-23145        https://gitee.com/openeuler/kernel/pulls/17196 
        CVE-2025-38220        https://gitee.com/openeuler/kernel/pulls/17074 
        CVE-2025-37820        https://gitee.com/openeuler/kernel/pulls/17200 
        CVE-2025-37823        https://gitee.com/openeuler/kernel/pulls/17176 
        CVE-2025-22054        https://gitee.com/openeuler/kernel/pulls/17188 
        CVE-2025-23155        https://gitee.com/openeuler/kernel/pulls/17197 
        CVE-2025-38157        https://gitee.com/openeuler/kernel/pulls/16951 
        CVE-2025-37787        https://gitee.com/openeuler/kernel/pulls/17193 
        CVE-2025-22004        https://gitee.com/openeuler/kernel/pulls/17171 
        CVE-2025-37864        https://gitee.com/openeuler/kernel/pulls/17174 
        CVE-2025-22053        https://gitee.com/openeuler/kernel/pulls/17189 
        CVE-2025-38264        https://gitee.com/openeuler/kernel/pulls/17305 
        CVE-2025-22055        https://gitee.com/openeuler/kernel/pulls/17187 
        CVE-2025-22111        https://gitee.com/openeuler/kernel/pulls/17182 
        CVE-2025-38127        https://gitee.com/openeuler/kernel/pulls/17212 
        CVE-2025-38061        https://gitee.com/openeuler/kernel/pulls/17207 
        CVE-2025-38079        https://gitee.com/openeuler/kernel/pulls/17124 
        CVE-2025-38124        https://gitee.com/openeuler/kernel/pulls/17213 
        CVE-2025-38120        https://gitee.com/openeuler/kernel/pulls/17214 
        CVE-2025-38198        https://gitee.com/openeuler/kernel/pulls/17032 
        CVE-2025-37790        https://gitee.com/openeuler/kernel/pulls/17191 
        CVE-2025-38200        https://gitee.com/openeuler/kernel/pulls/17287 
        CVE-2025-38035        https://gitee.com/openeuler/kernel/pulls/17296 
        CVE-2025-23142        https://gitee.com/openeuler/kernel/pulls/17178 
        CVE-2025-37788        https://gitee.com/openeuler/kernel/pulls/17192 
        CVE-2025-22050        https://gitee.com/openeuler/kernel/pulls/17190 

Bugfix（18）
v2  ifs: Defer cgroup ifs enable
                https://gitee.com/openeuler/kernel/pulls/17262 
smb: client: fix use-after-free in cifs_oplock_break
                https://gitee.com/openeuler/kernel/pulls/17102 
smb: client: fix use-after-free in crypt_message when using async crypto
                https://gitee.com/openeuler/kernel/pulls/17076 
inspector: hold module refcnt when cpu inspector is running
                https://gitee.com/openeuler/kernel/pulls/17255 
fs/resctrl: Enqueue mon_event_count() forcefully for MPAM
                https://gitee.com/openeuler/kernel/pulls/17336 
arm64: Fix guest app segment fault when disable_sdei_nmi_watchdog
                https://gitee.com/openeuler/kernel/pulls/17308 
some fix for spe hotcold
                https://gitee.com/openeuler/kernel/pulls/17240 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.72-6.6.75 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/17159 
mm: fix uprobe pte be overwritten when expanding vma
                https://gitee.com/openeuler/kernel/pulls/17253 
arm64/mpam: Fix incorrect CPU-to-partid binding under CDP mode
                https://gitee.com/openeuler/kernel/pulls/17250 
driver core: Use kasprintf() instead of fixed buffer formatting
                https://gitee.com/openeuler/kernel/pulls/17206 
fs: export anon_inode_make_secure_inode() and fix secretmem LSM bypass
                https://gitee.com/openeuler/kernel/pulls/17275 
libbpf: Fix null pointer dereference in btf_dump__free on allocation failure
                https://gitee.com/openeuler/kernel/pulls/17291 
efi: efi_get_memory_map -- increase map headroom
                https://gitee.com/openeuler/kernel/pulls/17109 
[OLK-6.6] Backport TDX HLT/SAFE-HLT fix
                https://gitee.com/openeuler/kernel/pulls/16850 
sched/fair: Only increment deadline once on yield
                https://gitee.com/openeuler/kernel/pulls/17303 
【OLK-6.6】修复psp_mutex_lock_timeout超时触发soft lockup警告的问题
                https://gitee.com/openeuler/kernel/pulls/16797 
olk-6.6-backport-bugfix-for-dynamic-affinity
                https://gitee.com/openeuler/kernel/pulls/17161 

feature
v7  arm64: Add hardware xcall framework support
                https://gitee.com/openeuler/kernel/pulls/17341 
v2  Cgroup-Based Interference Statistics followup
                https://gitee.com/openeuler/kernel/pulls/17140 
v3:add perpcu stock for kmem
                https://gitee.com/openeuler/kernel/pulls/17156 

麒麟
MPTCP UPTREAM PART25
                https://gitee.com/openeuler/kernel/pulls/17246 
unify log function usage of enfs
                https://gitee.com/openeuler/kernel/pulls/17266 

申威
[OLK-6.6]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/17016 

海光
【OLK-6.6】修复虚拟机下使用海光TKM功能可能返回TKM_UNSUPPORTED_CMD错误
                https://gitee.com/openeuler/kernel/pulls/16602 

海思
net: hns3: reduce stack usage in hclge_dbg_dump_tm_pri()
                https://gitee.com/openeuler/kernel/pulls/17201 
RDMA/hns: Fix HW configurations not cleared in error flow
                https://gitee.com/openeuler/kernel/pulls/17237 
ROH: fix security issues and eliminate redundancies
                https://gitee.com/openeuler/kernel/pulls/17335 
net: hns3: fix spelling mistake "reg_um" -&gt; "reg_num"
                https://gitee.com/openeuler/kernel/pulls/17229 
[olk 6.6] net: hibmcge: backport some feature patches
                https://gitee.com/openeuler/kernel/pulls/17137 
Fixed the wrong debugfs node name in hisi_spi debugfs initialization
                https://gitee.com/openeuler/kernel/pulls/17261 


议题二：征集中（可直接在此填报，需备注汇报人）


三、遗留问题
1. CVE 协作小组创建 —— 李楠
2. 历史遗留PR跟进 —— 李楠、吴腾达
3. issue清理策略待讨论 ——郑增凯


-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/8/1 Kernel SIG 双周例会】
轮值主持：李楠【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达->郑增凯】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/948491968
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-275.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-273.0.0 更新至 5.10.0-275.0.0, 回合补丁数83个
        git log 5.10.0-273.0.0..5.10.0-275.0.0 --oneline --no-merges | wc -l
CVE: (15)
CVE-2025-38074  https://gitee.com/openeuler/kernel/pulls/16809
CVE-2025-38117  https://gitee.com/openeuler/kernel/pulls/17149
CVE-2022-49535  https://gitee.com/openeuler/kernel/pulls/15469
CVE-2022-50098  https://gitee.com/openeuler/kernel/pulls/17297
CVE-2025-38015  https://gitee.com/openeuler/kernel/pulls/17298
CVE-2022-49961  https://gitee.com/openeuler/kernel/pulls/17204
CVE-2025-38337  https://gitee.com/openeuler/kernel/pulls/17146
CVE-2025-38245  https://gitee.com/openeuler/kernel/pulls/17306
CVE-2025-38298  https://gitee.com/openeuler/kernel/pulls/17125
CVE-2025-38079  https://gitee.com/openeuler/kernel/pulls/17123
CVE-2025-38324  https://gitee.com/openeuler/kernel/pulls/17258
CVE-2025-38391  https://gitee.com/openeuler/kernel/pulls/17311
CVE-2024-58095  https://gitee.com/openeuler/kernel/pulls/17300
CVE-2025-38157  https://gitee.com/openeuler/kernel/pulls/17173
CVE-2025-38466  https://gitee.com/openeuler/kernel/pulls/17327

Bugfix:
gpiolib: Get rid of ARCH_NR_GPIOS
                https://gitee.com/openeuler/kernel/pulls/17241
fs/writeback: bail out if there is no more inodes for IO and queued once
                https://gitee.com/openeuler/kernel/pulls/17283
smb: client: fix use-after-free in cifs_oplock_break
                https://gitee.com/openeuler/kernel/pulls/17077
ima: prevent concurrent list operations in ima_lsm_update_rules
                https://gitee.com/openeuler/kernel/pulls/17242
smb: client: fix use-after-free in crypt_message when using async crypto
                https://gitee.com/openeuler/kernel/pulls/17195
fs: Backport two namespace fix patches
                https://gitee.com/openeuler/kernel/pulls/16885
arm64/mpam: Use an IPI instead of task_work_add() to update MPAM sysreg
                https://gitee.com/openeuler/kernel/pulls/17158
perf: Fix sample vs do_exit()
                https://gitee.com/openeuler/kernel/pulls/17010
v5  Fix x2apic enablement and allow more CPUs, clean up I/OAPIC and MSI bitfields
                https://gitee.com/openeuler/kernel/pulls/16386
libbpf: Fix null pointer dereference in btf_dump__free on allocation failure
                https://gitee.com/openeuler/kernel/pulls/17285
hugeltb: Fix null ptr exception during drain movable pcp
                https://gitee.com/openeuler/kernel/pulls/17233
ext4: fix slab-out-of-bounds in ext4_mb_find_good_group_avg_frag_lists()
                https://gitee.com/openeuler/kernel/pulls/16942
modify xcall xint proc file permissions
                https://gitee.com/openeuler/kernel/pulls/17131

海思：
soc: hisilicon: kunpeng_hccs: Fix incorrect log information
                https://gitee.com/openeuler/kernel/pulls/17232
ROH:fix security issues and eliminate redundancies
                https://gitee.com/openeuler/kernel/pulls/17252
RDMA/hns: Support querying DIP SCC context
                https://gitee.com/openeuler/kernel/pulls/17288
RDMA/hns: Remove MW support
                https://gitee.com/openeuler/kernel/pulls/17279
Fixed the wrong debugfs node name in hisi_spi debugfs initialization
                https://gitee.com/openeuler/kernel/pulls/17256
【OLK 5.10】some bugfixes and cleanups for hns3 driver
                https://gitee.com/openeuler/kernel/pulls/17239

风河：
[OLK-5.10] backport important bugfix for nvme driver from upstream linux-5.10.y
                https://gitee.com/openeuler/kernel/pulls/16746

20250801
OLK-6.6进展同步
​    tag更新到6.6.0-103.0.0
​    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
​    期间合入补丁数164个
​    git log 6.6.0-101.0.0..6.6.0-103.0.0 --oneline --no-merges | wc -l

CVE（50）
        CVE-2024-58237        https://gitee.com/openeuler/kernel/pulls/17198 
        CVE-2025-38324        https://gitee.com/openeuler/kernel/pulls/17259 
        CVE-2025-38075        https://gitee.com/openeuler/kernel/pulls/16958 
        CVE-2025-38117        https://gitee.com/openeuler/kernel/pulls/17148 
        CVE-2025-38015        https://gitee.com/openeuler/kernel/pulls/17299 
        CVE-2025-38115        https://gitee.com/openeuler/kernel/pulls/17215 
        CVE-2025-38226        https://gitee.com/openeuler/kernel/pulls/17154 
        CVE-2025-22103        https://gitee.com/openeuler/kernel/pulls/17181 
        CVE-2025-38337        https://gitee.com/openeuler/kernel/pulls/17101 
        CVE-2025-38190        https://gitee.com/openeuler/kernel/pulls/17273 
        CVE-2025-37786        https://gitee.com/openeuler/kernel/pulls/17179 
        CVE-2025-22060        https://gitee.com/openeuler/kernel/pulls/17185 
        CVE-2025-37757        https://gitee.com/openeuler/kernel/pulls/17194 
        CVE-2025-21997        https://gitee.com/openeuler/kernel/pulls/17172 
        CVE-2025-37824        https://gitee.com/openeuler/kernel/pulls/17199 
        CVE-2025-21961        https://gitee.com/openeuler/kernel/pulls/17170 
        CVE-2025-37865        https://gitee.com/openeuler/kernel/pulls/17175 
        CVE-2025-38103        https://gitee.com/openeuler/kernel/pulls/17150 
        CVE-2025-38219        https://gitee.com/openeuler/kernel/pulls/17153 
        CVE-2024-56658        https://gitee.com/openeuler/kernel/pulls/17238 
        CVE-2025-37797        https://gitee.com/openeuler/kernel/pulls/17177 
        CVE-2025-22062        https://gitee.com/openeuler/kernel/pulls/17184 
        CVE-2025-38391        https://gitee.com/openeuler/kernel/pulls/17310 
        CVE-2025-22058        https://gitee.com/openeuler/kernel/pulls/17186 
        CVE-2025-23145        https://gitee.com/openeuler/kernel/pulls/17196 
        CVE-2025-38220        https://gitee.com/openeuler/kernel/pulls/17074 
        CVE-2025-37820        https://gitee.com/openeuler/kernel/pulls/17200 
        CVE-2025-37823        https://gitee.com/openeuler/kernel/pulls/17176 
        CVE-2025-22054        https://gitee.com/openeuler/kernel/pulls/17188 
        CVE-2025-23155        https://gitee.com/openeuler/kernel/pulls/17197 
        CVE-2025-38157        https://gitee.com/openeuler/kernel/pulls/16951 
        CVE-2025-37787        https://gitee.com/openeuler/kernel/pulls/17193 
        CVE-2025-22004        https://gitee.com/openeuler/kernel/pulls/17171 
        CVE-2025-37864        https://gitee.com/openeuler/kernel/pulls/17174 
        CVE-2025-22053        https://gitee.com/openeuler/kernel/pulls/17189 
        CVE-2025-38264        https://gitee.com/openeuler/kernel/pulls/17305 
        CVE-2025-22055        https://gitee.com/openeuler/kernel/pulls/17187 
        CVE-2025-22111        https://gitee.com/openeuler/kernel/pulls/17182 
        CVE-2025-38127        https://gitee.com/openeuler/kernel/pulls/17212 
        CVE-2025-38061        https://gitee.com/openeuler/kernel/pulls/17207 
        CVE-2025-38079        https://gitee.com/openeuler/kernel/pulls/17124 
        CVE-2025-38124        https://gitee.com/openeuler/kernel/pulls/17213 
        CVE-2025-38120        https://gitee.com/openeuler/kernel/pulls/17214 
        CVE-2025-38198        https://gitee.com/openeuler/kernel/pulls/17032 
        CVE-2025-37790        https://gitee.com/openeuler/kernel/pulls/17191 
        CVE-2025-38200        https://gitee.com/openeuler/kernel/pulls/17287 
        CVE-2025-38035        https://gitee.com/openeuler/kernel/pulls/17296 
        CVE-2025-23142        https://gitee.com/openeuler/kernel/pulls/17178 
        CVE-2025-37788        https://gitee.com/openeuler/kernel/pulls/17192 
        CVE-2025-22050        https://gitee.com/openeuler/kernel/pulls/17190 

Bugfix（18）
v2  ifs: Defer cgroup ifs enable
                https://gitee.com/openeuler/kernel/pulls/17262 
smb: client: fix use-after-free in cifs_oplock_break
                https://gitee.com/openeuler/kernel/pulls/17102 
smb: client: fix use-after-free in crypt_message when using async crypto
                https://gitee.com/openeuler/kernel/pulls/17076 
inspector: hold module refcnt when cpu inspector is running
                https://gitee.com/openeuler/kernel/pulls/17255 
fs/resctrl: Enqueue mon_event_count() forcefully for MPAM
                https://gitee.com/openeuler/kernel/pulls/17336 
arm64: Fix guest app segment fault when disable_sdei_nmi_watchdog
                https://gitee.com/openeuler/kernel/pulls/17308 
some fix for spe hotcold
                https://gitee.com/openeuler/kernel/pulls/17240 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.72-6.6.75 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/17159 
mm: fix uprobe pte be overwritten when expanding vma
                https://gitee.com/openeuler/kernel/pulls/17253 
arm64/mpam: Fix incorrect CPU-to-partid binding under CDP mode
                https://gitee.com/openeuler/kernel/pulls/17250 
driver core: Use kasprintf() instead of fixed buffer formatting
                https://gitee.com/openeuler/kernel/pulls/17206 
fs: export anon_inode_make_secure_inode() and fix secretmem LSM bypass
                https://gitee.com/openeuler/kernel/pulls/17275 
libbpf: Fix null pointer dereference in btf_dump__free on allocation failure
                https://gitee.com/openeuler/kernel/pulls/17291 
olk-6.6-backport-bugfix-for-dynamic-affinity
                https://gitee.com/openeuler/kernel/pulls/17161 
sched/fair: Only increment deadline once on yield
                https://gitee.com/openeuler/kernel/pulls/17303 
[OLK-6.6] Backport TDX HLT/SAFE-HLT fix
                https://gitee.com/openeuler/kernel/pulls/16850 
unify log function usage of enfs
                https://gitee.com/openeuler/kernel/pulls/17266 
efi: efi_get_memory_map -- increase map headroom
                https://gitee.com/openeuler/kernel/pulls/17109 

feature
v7  arm64: Add hardware xcall framework support
        https://gitee.com/openeuler/kernel/pulls/17341 
v2  Cgroup-Based Interference Statistics followup
        https://gitee.com/openeuler/kernel/pulls/17140 
v3:add perpcu stock for kmem
        https://gitee.com/openeuler/kernel/pulls/17156 

申威
[OLK-6.6]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/17016 

海光
【OLK-6.6】修复虚拟机下使用海光TKM功能可能返回TKM_UNSUPPORTED_CMD错误
                https://gitee.com/openeuler/kernel/pulls/16602 
【OLK-6.6】修复psp_mutex_lock_timeout超时触发soft lockup警告的问题
                https://gitee.com/openeuler/kernel/pulls/16797 

麒麟
MPTCP UPTREAM PART25
                https://gitee.com/openeuler/kernel/pulls/17246 

海思
net: hns3: fix spelling mistake "reg_um" -&gt; "reg_num"
                https://gitee.com/openeuler/kernel/pulls/17229 
Fixed the wrong debugfs node name in hisi_spi debugfs initialization
                https://gitee.com/openeuler/kernel/pulls/17261 
net: hns3: reduce stack usage in hclge_dbg_dump_tm_pri()
                https://gitee.com/openeuler/kernel/pulls/17201 
RDMA/hns: Fix HW configurations not cleared in error flow
                https://gitee.com/openeuler/kernel/pulls/17237 
ROH: fix security issues and eliminate redundancies
                https://gitee.com/openeuler/kernel/pulls/17335 
[olk 6.6] net: hibmcge: backport some feature patches
                https://gitee.com/openeuler/kernel/pulls/17137 


议题二：Maintainer 变更申请（杨颖梁 -> 郭寒军）： 谢秀奇

由于杨颖梁工作调整，原有 Maintainer 相关工作交接给郭寒军。

郭寒军，openEuler 社区组织和筹备者之一，曾担任首届TC委员、Kernel SIG Maintainer，长期担任 Kernel SIG ACPI/ARM 子系统 Committer。在上游社区长期担任 ACPI 子系统 Maintainer。长期带领团队参与和贡献openEuler社区，并负责 ACPI、ARM 子系统补丁合入和 Review。
会议结论：通过

议题三：LoongArch: 添加 TPM/SM3/SM4/EDAC支持 (龙芯-赵群钦)

https://gitee.com/openeuler/kernel/pulls/17265
会议结论：检视后合入

议题四: 新增commiter 关文涛(统信软件)
关文涛，目前已经给openeuler  kernel提交合入20余pr，主要负责lts和cve的维护工作，同时是deepin-community/kernel的维护者，也在上游社区有做贡献。
会议结论：通过

议题五：新增ARM架构新committer 帅家坤（飞腾）
帅家坤是飞腾在开源社区的技术生态负责人，有多年ARM架构内核及开源社区相关经验，本人在openEuler社区提交PR 10余项，组织飞腾其他技术人员在openEuler提交PR 数十项。
申请将飞腾相关新增特性添加毛泓博、帅家坤作为committer以进行review工作。
会议结论：通过
同时申请合入以下PR：
[OLK-6.6] spi: qspi: Add Phytium spi/qspi controller support
https://gitee.com/openeuler/kernel/pulls/17029
[OLK-6.6]Add Phytium GPIO driver
https://gitee.com/openeuler/kernel/pulls/16014
[OLK-6.6]i2c: add Phytium i2c driver
https://gitee.com/openeuler/kernel/pulls/15944
会议结论：检视后合入


三、遗留问题
1. CVE 协作小组创建 —— 李楠
2. 历史遗留PR跟进 —— 李楠
3. 关闭历史遗留的issue和pr —— 郑增凯

-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/7/18 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达】
下次轮值主持：李楠
会议链接：https://meeting.huaweicloud.com:36443/#/j/986249346
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-273.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-270.0.0 更新至 5.10.0-273.0.0, 回合补丁数82个
        git log 5.10.0-270.0.0..5.10.0-273.0.0 --oneline --no-merges | wc -l
CVE: (12)
CVE-2025-38229  https://gitee.com/openeuler/kernel/pulls/17058 
CVE-2025-38095  https://gitee.com/openeuler/kernel/pulls/16965 
CVE-2025-38170  https://gitee.com/openeuler/kernel/pulls/16970 
CVE-2024-57931  https://gitee.com/openeuler/kernel/pulls/16992 
CVE-2025-21855  https://gitee.com/openeuler/kernel/pulls/16429 
CVE-2025-38146  https://gitee.com/openeuler/kernel/pulls/16966 
CVE-2025-38320  https://gitee.com/openeuler/kernel/pulls/17105 
CVE-2025-38072  https://gitee.com/openeuler/kernel/pulls/16899 
CVE-2025-38108  https://gitee.com/openeuler/kernel/pulls/17002 
CVE-2025-38023  https://gitee.com/openeuler/kernel/pulls/16752 
CVE-2025-37968  https://gitee.com/openeuler/kernel/pulls/17037 
CVE-2024-58002  https://gitee.com/openeuler/kernel/pulls/16949 
Bugfix:
nfs: Clean up /proc/net/rpc/nfs when nfs_fs_proc_net_init() fails.
                https://gitee.com/openeuler/kernel/pulls/16927 
uprobes: check anon before compound when unregister
                https://gitee.com/openeuler/kernel/pulls/16901 
net: fix slab-use-after-free read in decode_session6
                https://gitee.com/openeuler/kernel/pulls/16914 
Backport mainline patches
                https://gitee.com/openeuler/kernel/pulls/16916 
cifs: fix mount deadlock by avoiding super block iteration in DFS reconnect
                https://gitee.com/openeuler/kernel/pulls/16761 
xhci: Limit time spent with xHC interrupts disabled during bus resume
                https://gitee.com/openeuler/kernel/pulls/16944 
cachefiles: Fix the potential ABBA deadlock issue
                https://gitee.com/openeuler/kernel/pulls/16776 
mm/hugetlb: fix incorrect gfp flag for mempolicy MPOL_PREFERRED_MANY
                https://gitee.com/openeuler/kernel/pulls/16909 
KVM: x86/mmu: Treat NX as a valid SPTE bit for NPT
                https://gitee.com/openeuler/kernel/pulls/16943 
Feature:
hugetlb: drain pcp for movable zone before alloc
                https://gitee.com/openeuler/kernel/pulls/17104 
arm64: Fix a typo in xcall_init_task()
                https://gitee.com/openeuler/kernel/pulls/17045 
arm64: exec: add mcs support for prepare_binprm
                https://gitee.com/openeuler/kernel/pulls/17099 
[OLK-5.10] io_uring: Support forcing sq thread to be idle and woken up by hrtimer
                https://gitee.com/openeuler/kernel/pulls/16918 
申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/17015 
[OLK-5.10]:sw64: perf unwind: Do not put libunwind-sw_64 in FEATURE_TESTS_BASIC
                https://gitee.com/openeuler/kernel/pulls/16937 
兆芯：
[OLK-5.10] iommu: Add support for ACPI device direct mapping
                https://gitee.com/openeuler/kernel/pulls/16751 
海光：
[OLK-5.10] perf/x86/uncore: Add DF PMU support for Hygon family 18h model 8h
                https://gitee.com/openeuler/kernel/pulls/15658 
Get the correct instance id calculation for Hygon family 18h model 6h~10h
                https://gitee.com/openeuler/kernel/pulls/15236 
correct address translation for Hygon family 18h model 4h~10h
                https://gitee.com/openeuler/kernel/pulls/15235 
[OLK-5.10] Print secure features when running on Hygon CPUs
                https://gitee.com/openeuler/kernel/pulls/16795 
EDAC/amd64: Fix the check build warning info in hygon_umc_normaddr_to_sysaddr()
                https://gitee.com/openeuler/kernel/pulls/17050 
Add set_guest_pat_wb parameter to enhance performance for non-passthrough application scenarios
                https://gitee.com/openeuler/kernel/pulls/15224 
海思：
net: hns3: fix kernel crash when uninstalling driver
                https://gitee.com/openeuler/kernel/pulls/16881 
RDMA/hns: Stability and Security Fixes and Improvements
                https://gitee.com/openeuler/kernel/pulls/17048 
ptp: hisi: the print of element in ptp need protected by lock
                https://gitee.com/openeuler/kernel/pulls/16855 
net: hns3: fix a use of uninitialized variable problem
                https://gitee.com/openeuler/kernel/pulls/16852 
Add gpio-hisi softdepend
                https://gitee.com/openeuler/kernel/pulls/16839 
[OLK-5.10] Add gpio-hisi softdepend
                https://gitee.com/openeuler/kernel/pulls/16935 
Add the spidev.ko to OLK-5.10
                https://gitee.com/openeuler/kernel/pulls/12159 
[OLK-5.10] PCIe Synchronous OLK-6.6 modified to OLK-6.6
                https://gitee.com/openeuler/kernel/pulls/16934 


202507018
OLK-6.6进展同步
    tag更新到6.6.0-101.0.0
    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数322个
    git log 6.6.0-99.0.0..6.6.0-101.0.0 --oneline --no-merges | wc -l
 
CVE（39）
            CVE-2025-37817  https://gitee.com/openeuler/kernel/pulls/17068 
            CVE-2025-38229  https://gitee.com/openeuler/kernel/pulls/17059 
            CVE-2025-38170  https://gitee.com/openeuler/kernel/pulls/16969 
            CVE-2025-23141  https://gitee.com/openeuler/kernel/pulls/16982 
            CVE-2025-37842  https://gitee.com/openeuler/kernel/pulls/17026 
            CVE-2025-37810  https://gitee.com/openeuler/kernel/pulls/17071 
            CVE-2025-22101  https://gitee.com/openeuler/kernel/pulls/16462 
            CVE-2025-37991  https://gitee.com/openeuler/kernel/pulls/17036 
            CVE-2025-38195  https://gitee.com/openeuler/kernel/pulls/17033 
            CVE-2025-38163  https://gitee.com/openeuler/kernel/pulls/16957 
            CVE-2025-38159  https://gitee.com/openeuler/kernel/pulls/16996 
            CVE-2025-38320  https://gitee.com/openeuler/kernel/pulls/17106 
            CVE-2025-37739  https://gitee.com/openeuler/kernel/pulls/16995 
            CVE-2025-37951  https://gitee.com/openeuler/kernel/pulls/16896 
            CVE-2025-37808  https://gitee.com/openeuler/kernel/pulls/17013 
            CVE-2025-38182  https://gitee.com/openeuler/kernel/pulls/17001 
            CVE-2025-38146  https://gitee.com/openeuler/kernel/pulls/16967 
            CVE-2025-22108  https://gitee.com/openeuler/kernel/pulls/17062 
            CVE-2025-38298  https://gitee.com/openeuler/kernel/pulls/17126 
            CVE-2025-37984  https://gitee.com/openeuler/kernel/pulls/16983 
            CVE-2025-37854  https://gitee.com/openeuler/kernel/pulls/17035 
            CVE-2025-38202  https://gitee.com/openeuler/kernel/pulls/17023 
            CVE-2025-38197  https://gitee.com/openeuler/kernel/pulls/17049 
            CVE-2025-38108  https://gitee.com/openeuler/kernel/pulls/17003 
            CVE-2025-38067  https://gitee.com/openeuler/kernel/pulls/16906 
            CVE-2025-37968  https://gitee.com/openeuler/kernel/pulls/17039 
            CVE-2025-37887  https://gitee.com/openeuler/kernel/pulls/16237 
            CVE-2025-38072  https://gitee.com/openeuler/kernel/pulls/16898 
            CVE-2025-38094  https://gitee.com/openeuler/kernel/pulls/16994 
            CVE-2025-37933  https://gitee.com/openeuler/kernel/pulls/16999 
            CVE-2025-38142  https://gitee.com/openeuler/kernel/pulls/16991 
            CVE-2025-38099  https://gitee.com/openeuler/kernel/pulls/17014 
            CVE-2025-38095  https://gitee.com/openeuler/kernel/pulls/16964 
            CVE-2025-38090  https://gitee.com/openeuler/kernel/pulls/17006 
            CVE-2025-38023  https://gitee.com/openeuler/kernel/pulls/16753 
            CVE-2025-38322  https://gitee.com/openeuler/kernel/pulls/17107 
            CVE-2025-38118  https://gitee.com/openeuler/kernel/pulls/17034 
            CVE-2025-37784  https://gitee.com/openeuler/kernel/pulls/16897 
            CVE-2025-38081  https://gitee.com/openeuler/kernel/pulls/17022 

Bugfix（23）
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.83-6.6.84 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/16603 
fs: Backport four namespace fix patches
                https://gitee.com/openeuler/kernel/pulls/16884 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.70-6.6.72 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/17041 
nfs: Clean up /proc/net/rpc/nfs when nfs_fs_proc_net_init() fails.
                https://gitee.com/openeuler/kernel/pulls/16926 
bpf verifier fixes
                https://gitee.com/openeuler/kernel/pulls/17054 
drm/amd/display: Fix && vs || typos
                https://gitee.com/openeuler/kernel/pulls/17092 
[OLK-6.6] backport important bugfix for nvme driver from upstream linux-6.6.y
                https://gitee.com/openeuler/kernel/pulls/16565 
arm64/mpam: Fix L2 monitor issue under CDP mode
                https://gitee.com/openeuler/kernel/pulls/16998 
config: Set TSM_REPORTS=m and ARM_CCA_GUEST=m
                https://gitee.com/openeuler/kernel/pulls/17094 
cachefiles: Fix the incorrect return value in cachefiles_ondemand_fd_write_iter()
                https://gitee.com/openeuler/kernel/pulls/16902 
v2  irqchip/gic-v3: Fix xint sleeping function called from invalid context
                https://gitee.com/openeuler/kernel/pulls/16922 
[OLK-6.6] Fix patches for X2avic to backport for OLK-6.6
                https://gitee.com/openeuler/kernel/pulls/16947 
xcall xint 644
                https://gitee.com/openeuler/kernel/pulls/17136 
Backport mainline patches
                https://gitee.com/openeuler/kernel/pulls/16919 
v2  mm: respect mmap hint address when aligning for THP
                https://gitee.com/openeuler/kernel/pulls/17000 
Fix compile problem for psi_grained
                https://gitee.com/openeuler/kernel/pulls/16988 
v4  mm/mem_sampling: fix some mem sampling issues
                https://gitee.com/openeuler/kernel/pulls/16781 
some optimization patches for inet_diag dump
                https://gitee.com/openeuler/kernel/pulls/16903 
[OLK-6.6] backport important bugfix for lpfc driver from upstream linux-6.6.y
                https://gitee.com/openeuler/kernel/pulls/16743 
bpf lts backport
                https://gitee.com/openeuler/kernel/pulls/17055 
fix some build errors of enfs
                https://gitee.com/openeuler/kernel/pulls/16891 
mm: batched unmap lazyfree large folios
                https://gitee.com/openeuler/kernel/pulls/17120 
arm64/mpam: Add quirk for MPAM MSMON_MBWU monitor NRDY bit
                https://gitee.com/openeuler/kernel/pulls/17070 

feature
mm/mem_sampling: add trace event for spe based damon record
                https://gitee.com/openeuler/kernel/pulls/16780 
OLK-6.6 Bperf
                https://gitee.com/openeuler/kernel/pulls/16908 
Support CCA Guest
                https://gitee.com/openeuler/kernel/pulls/16792 
                https://gitee.com/openeuler/kernel/pulls/16956 

申威
[OLK-6.6]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/16567 

龙芯
LoongArch: Fix bugs in huge_pte_offset/__alloc_pages_slowpath/iommu
                https://gitee.com/openeuler/kernel/pulls/16747 
drm/virtio: implement virtio_gpu_shutdown
                https://gitee.com/openeuler/kernel/pulls/16467 

兆新
[OLK-6.6] PCI/P2PDMA: Add Zhaoxin Zhaoxin bridges to the whitelist
                https://gitee.com/openeuler/kernel/pulls/16557 

海思
perf: Add support for SPE Data Source packet on HiSilicon HIP12
                https://gitee.com/openeuler/kernel/pulls/16950 
Supports virtCCA
                https://gitee.com/openeuler/kernel/pulls/16895 
                https://gitee.com/openeuler/kernel/pulls/16912 

议题二：openeuler创新分支25.09即将拉出，基于OLK 6.6内核，需求收集截止7.30  ——李楠
https://gitee.com/openeuler/release-management/blob/master/openEuler-25.09/release-plan.md

议题三：议题征集中（请备注汇报人）


三、遗留问题

-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/7/4 Kernel SIG 双周例会】
轮值主持：曾昭荣 【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达】
下次轮值主持：桑力鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/960953892
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪
李楠：committer相关门禁刷新
【Done】

二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-270.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-268.0.0 更新至 5.10.0-270.0.0, 回合补丁数112个
        git log 5.10.0-268.0.0..5.10.0-270.0.0 --oneline --no-merges | wc -l
CVE: (9)
CVE-2024-26798  https://gitee.com/openeuler/kernel/pulls/16816
CVE-2022-50230  https://gitee.com/openeuler/kernel/pulls/16786
CVE-2025-37738  https://gitee.com/openeuler/kernel/pulls/16578
CVE-2022-50057  https://gitee.com/openeuler/kernel/pulls/16826
CVE-2022-50167  https://gitee.com/openeuler/kernel/pulls/16887
CVE-2025-38078  https://gitee.com/openeuler/kernel/pulls/16785
CVE-2025-22026  https://gitee.com/openeuler/kernel/pulls/16819
CVE-2025-37937  https://gitee.com/openeuler/kernel/pulls/16758
CVE-2025-21927  https://gitee.com/openeuler/kernel/pulls/16872
Bugfix:
locking/qspinlock: Micro-optimize pending state waiting for unlock
                https://gitee.com/openeuler/kernel/pulls/16406
[OLK-5.10] bcache: allow allocator to invalidate bucket in gc
                https://gitee.com/openeuler/kernel/pulls/11994
eventpoll: Fix soft lockup in xcall_read()
                https://gitee.com/openeuler/kernel/pulls/16794
ftrace: Fix UAF when lookup kallsym after ftrace disabled
                https://gitee.com/openeuler/kernel/pulls/16841
[22.03-LTS-SP3] bcache: call force_wake_up_gc() if necessary in check_should_bypass()
                https://gitee.com/openeuler/kernel/pulls/11993
arm64: kaslr: fix nokaslr cmdline parsing
                https://gitee.com/openeuler/kernel/pulls/16860
bpf: Fix prog_array_map_poke_run map poke update
                https://gitee.com/openeuler/kernel/pulls/16774
A small fix for ftrace preemption count
                https://gitee.com/openeuler/kernel/pulls/16840
arm64: xcall: Fix GPR touch as the original step
                https://gitee.com/openeuler/kernel/pulls/16749
Feature:
v2  add-exec-ebpf-v3
                https://gitee.com/openeuler/kernel/pulls/16750
v4  Introduce soft domain v4
                https://gitee.com/openeuler/kernel/pulls/16849
v4  add soft quota
                https://gitee.com/openeuler/kernel/pulls/16801
net/oenetcls: Support cluster sched
                https://gitee.com/openeuler/kernel/pulls/16847
v5  HiSock Redirect Framework
                https://gitee.com/openeuler/kernel/pulls/16892
OLK-5.10 Bperf
                https://gitee.com/openeuler/kernel/pulls/16706
申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/16735
海光：
Add support edac for hygon family 18h model 10h
                https://gitee.com/openeuler/kernel/pulls/15234
Add IOAPIC support for Hygon family 18h model 10h
                https://gitee.com/openeuler/kernel/pulls/15239
Add LS and IF mce types for Hygon family 18h model 7h
                https://gitee.com/openeuler/kernel/pulls/15238
Add GM Driver Support for Hygon platform（Cryptographic Coprocessor，OLK-5.10)
                https://gitee.com/openeuler/kernel/pulls/16798
海思：
RDMA/hns: Get messgae length of ack_req from FW
                https://gitee.com/openeuler/kernel/pulls/16768


20250704
OLK-6.6进展同步
​    tag更新到6.6.0-99.0.0
​    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
​    期间合入补丁数114个
​    git log 6.6.0-98.0.0..6.6.0-99.0.0 --oneline --no-merges | wc -l

CVE（12）
        CVE-2025-37948  https://gitee.com/openeuler/kernel/pulls/16652 
        CVE-2025-37937  https://gitee.com/openeuler/kernel/pulls/16757 
        CVE-2025-38060  https://gitee.com/openeuler/kernel/pulls/16803 
        CVE-2025-38065  https://gitee.com/openeuler/kernel/pulls/16828 
        CVE-2025-40014  https://gitee.com/openeuler/kernel/pulls/16426 
        CVE-2025-21996  https://gitee.com/openeuler/kernel/pulls/16778 
        CVE-2025-38034  https://gitee.com/openeuler/kernel/pulls/16827 
        CVE-2025-38080  https://gitee.com/openeuler/kernel/pulls/16851 
        CVE-2025-38074  https://gitee.com/openeuler/kernel/pulls/16806 
        CVE-2025-38007  https://gitee.com/openeuler/kernel/pulls/16804 
        CVE-2025-37930  https://gitee.com/openeuler/kernel/pulls/16656 
        CVE-2025-38078  https://gitee.com/openeuler/kernel/pulls/16791 
        CVE-2025-37948  https://gitee.com/openeuler/kernel/pulls/16652 

bugfix（17）
pci:vga fix race condition in vga_arb_write
        https://gitee.com/openeuler/kernel/pulls/16865 
arm64: xcall: Fix GPR touch as the original step
        https://gitee.com/openeuler/kernel/pulls/16748 
SELinux: Add check for the user data passed to kcalloc in hashtab_init
        https://gitee.com/openeuler/kernel/pulls/16617 
mm: mincore: use pte_batch_hint() to batch process large folios
        https://gitee.com/openeuler/kernel/pulls/16559 
arm64: kaslr: fix nokaslr cmdline parsing
        https://gitee.com/openeuler/kernel/pulls/16861 
tracing: probes: Fix a possible race in trace_probe_log APIs
        https://gitee.com/openeuler/kernel/pulls/16848 
mm:userswap: change VM_USWAP_BIT to bit 61
        https://gitee.com/openeuler/kernel/pulls/16773 
bpf: Avoid __bpf_prog_ret0_warn when jit fails
        https://gitee.com/openeuler/kernel/pulls/16845 
v2  Fix some smmu bugs
        https://gitee.com/openeuler/kernel/pulls/16820 
ftrace: Fix UAF when lookup kallsym after ftrace disabled
        https://gitee.com/openeuler/kernel/pulls/16842 
ftrace: Fix preemption accounting for stacktrace filter command
        https://gitee.com/openeuler/kernel/pulls/16837 
mm: pcp: increase pcp->free_count threshold to trigger free_high
        https://gitee.com/openeuler/kernel/pulls/16756 
perf/x86/intel: Only check the group flag for X86 leader
        https://gitee.com/openeuler/kernel/pulls/16512 
perf hisi-ptt: Fix memory leak in lseek failure handling
        https://gitee.com/openeuler/kernel/pulls/16812 
v2  mempolicy: optimize queue_folios_pte_range by PTE batching
        https://gitee.com/openeuler/kernel/pulls/16866 
Backport 6.6.64-6.6.72 LTS
        https://gitee.com/openeuler/kernel/pulls/16573 
[OLK-6.6]fix enfs bug
        https://gitee.com/openeuler/kernel/pulls/16775 

Feature
mm/madvise: batch tlb flushes for MADV_DONTNEED and MADV_FREE
        https://gitee.com/openeuler/kernel/pulls/16689
add virtcca capability and kae vf interface
        https://gitee.com/openeuler/kernel/pulls/16601 

intel
[OLK-6.6] Intel: Backport to fix QuickAssist Technology(QAT) in-tree driver from v6.10 to v6.16
        https://gitee.com/openeuler/kernel/pulls/16770 

兆新
[OLK-6.6] PCI: Supplement ACS quirk for more Zhaoxin Root Ports
        https://gitee.com/openeuler/kernel/pulls/16556 

海思
[OLK-6.6]Arm64:KVM: Auto get the virtual_dev irq bypass's devid
        https://gitee.com/openeuler/kernel/pulls/14552 

议题二：新增AMD架构新committer 舒明（AMD 王文宽）
舒明有着多年kernel开发经验
【结论】通过 gitee：sming56_admin 邮箱： "Shu, Ming" <ming.shu@amd.com>

议题二：征集中，可直接填报到此处（需要备注汇报人及单位）


三、遗留问题

-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/6/20 Kernel SIG 双周例会】
轮值主持：吴腾达 【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达】
下次轮值主持：曾昭荣
会议链接：https://meeting.huaweicloud.com:36443/#/j/962662667
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪
李楠：committer相关门禁刷新

二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-268.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-266.0.0 更新至 5.10.0-268.0.0, 回合补丁数207个
        git log 5.10.0-266.0.0..5.10.0-268.0.0 --oneline --no-merges | wc -l
CVE: (9)
CVE-2025-23156  https://gitee.com/openeuler/kernel/pulls/16552
CVE-2025-37995  https://gitee.com/openeuler/kernel/pulls/16581
CVE-2023-53082  https://gitee.com/openeuler/kernel/pulls/16568
CVE-2025-21704  https://gitee.com/openeuler/kernel/pulls/16713
CVE-2025-37923  https://gitee.com/openeuler/kernel/pulls/16584
CVE-2025-23148  https://gitee.com/openeuler/kernel/pulls/16551
CVE-2024-58083  https://gitee.com/openeuler/kernel/pulls/16676
CVE-2023-53039  https://gitee.com/openeuler/kernel/pulls/16681
CVE-2022-21546  https://gitee.com/openeuler/kernel/pulls/16539

Bugfix:
mm: slub: add __GFP_NOWARN when allocations with GFP_NOWAIT
                https://gitee.com/openeuler/kernel/pulls/16677
pci:vga fix race condition in vga_arb_write
                https://gitee.com/openeuler/kernel/pulls/16615
IMA: use real_inode to get the i_version
                https://gitee.com/openeuler/kernel/pulls/16640
cgroup/cpuset-v1: Add missing support for cpuset_v2_mode
                https://gitee.com/openeuler/kernel/pulls/16575
arm64: uaccess: avoid blocking within critical sections
                https://gitee.com/openeuler/kernel/pulls/16693
SELinux: Add check for the user data passed to kcalloc in hashtab_init
                https://gitee.com/openeuler/kernel/pulls/16618
ipc: fix to protect IPCS lookups using RCU
                https://gitee.com/openeuler/kernel/pulls/16589
Fix watchdog false positive problem
                https://gitee.com/openeuler/kernel/pulls/16664
mm:fix return handling of cow_user_page
                https://gitee.com/openeuler/kernel/pulls/16197

Feature:
sched: Support NUMA parallel scheduling for multiple processes
                https://gitee.com/openeuler/kernel/pulls/16572
Backport SMC-D feature
                https://gitee.com/openeuler/kernel/pulls/16625
v10  arm64: Support xcall prefetch
                https://gitee.com/openeuler/kernel/pulls/16710
net/oenetcls: introduce oenetcls for network optimization
                https://gitee.com/openeuler/kernel/pulls/16553

申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/16566
飞腾：
iommu: smmuv3: Not print information of SMMU 0x10 event
                https://gitee.com/openeuler/kernel/pulls/16647
海思：
drivers:misc:sdma-dae: sdma fix uncorrect sleep time
                https://gitee.com/openeuler/kernel/pulls/16687
兆芯：
[OLK-5.10] PCI: Supplement ACS quirk for more Zhaoxin Root Ports
                https://gitee.com/openeuler/kernel/pulls/16555
[OLK-5.10] PCI/P2PDMA: Add Zhaoxin Zhaoxin bridges to the whitelist
                https://gitee.com/openeuler/kernel/pulls/16558
[OLK-5.10] iommu: Fix RMRR and ACPI direct mappings by using pci_dev instead of pn_dev
                https://gitee.com/openeuler/kernel/pulls/16468
intel：
platform/x86/intel-uncore-freq: Add efficiency latency control and other fix for 5.10
                https://gitee.com/openeuler/kernel/pulls/16561
云脉芯联
drivers: update Yunsilicon drivers to version 2412GA
                https://gitee.com/openeuler/kernel/pulls/16340
海光：
[OLK-5.10] Add HGSC_CERT_IMPORT ioctl interface for Hygon CPUs.
                https://gitee.com/openeuler/kernel/pulls/16715
Add support for Hygon family 18h model 8h
                https://gitee.com/openeuler/kernel/pulls/15244
【OLK-5.10】Support PSPCCP/NTBCCP identification for Hygon 2th、C86-3G and C86-4G
                https://gitee.com/openeuler/kernel/pulls/16659


20250620
OLK-6.6进展同步
    tag更新到6.6.0-98.0.0
    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数106个
    git log 6.6.0-95.0.0..6.6.0-98.0.0 --oneline --no-merges | wc -l

CVE（14）
        CVE-2025-21966  https://gitee.com/openeuler/kernel/pulls/16580 
        CVE-2024-58100  https://gitee.com/openeuler/kernel/pulls/16606 
        CVE-2025-37995  https://gitee.com/openeuler/kernel/pulls/16582 
        CVE-2025-37923  https://gitee.com/openeuler/kernel/pulls/16585 
        CVE-2025-37916  https://gitee.com/openeuler/kernel/pulls/16604 
        CVE-2025-37926  https://gitee.com/openeuler/kernel/pulls/16434 
        CVE-2025-22126  https://gitee.com/openeuler/kernel/pulls/16537 
        CVE-2025-37857  https://gitee.com/openeuler/kernel/pulls/16494 
        CVE-2025-23156  https://gitee.com/openeuler/kernel/pulls/16550 
        CVE-2025-23148  https://gitee.com/openeuler/kernel/pulls/16549 
        CVE-2025-37969  https://gitee.com/openeuler/kernel/pulls/16605 
        CVE-2025-37921  https://gitee.com/openeuler/kernel/pulls/16593 
        CVE-2025-40325  https://gitee.com/openeuler/kernel/pulls/16538 
        CVE-2025-23131  https://gitee.com/openeuler/kernel/pulls/16586 

bugfix（23）
fix move_pages return value
        https://gitee.com/openeuler/kernel/pulls/16627 
ftrace: Fix preemption accounting for stacktrace trigger command
        https://gitee.com/openeuler/kernel/pulls/16600 
arm64: Fix unmet direct dependencies for DEBUG_FEATURE_BYPASS
        https://gitee.com/openeuler/kernel/pulls/16729 
fs/resctrl: Fix return value in rdtgroup_pseudo_locked_in_hierarchy()
        https://gitee.com/openeuler/kernel/pulls/16705 
ipc: fix to protect IPCS lookups using RCU
        https://gitee.com/openeuler/kernel/pulls/16588 
arm64/watchdog: fix watchdog failure in low power scenarios
        https://gitee.com/openeuler/kernel/pulls/16492 
cgroup/cpuset-v1: Add missing support for cpuset_v2_mode
        https://gitee.com/openeuler/kernel/pulls/16574 
v2  Fix file content inconsistency issue and incorporate subsequent fix patches
        https://gitee.com/openeuler/kernel/pulls/16714 
mm/mm_spe.c: remove redundant checks and debug prints in mm_spe probe
        https://gitee.com/openeuler/kernel/pulls/16670 
close_files(): don't bother with xchg()
        https://gitee.com/openeuler/kernel/pulls/16620 
fs/resctrl: L2_MON does not support the limbo mechanism
        https://gitee.com/openeuler/kernel/pulls/16679 
iommu/arm-smmu-v3: Fix global-out-of-bounds access in arm_smmu_group_get_mpam()
        https://gitee.com/openeuler/kernel/pulls/16651 
Fix issues of nfs mounting
        https://gitee.com/openeuler/kernel/pulls/16717 
Remove useless file
        https://gitee.com/openeuler/kernel/pulls/16668 
af_unix: Read 0 bytes with MSG_PEEK loops if last skb is OOB
        https://gitee.com/openeuler/kernel/pulls/16711 
mm: provide vm_normal_(page|folio)_pmd() with CONFIG_PGTABLE_HAS_HUGE_LEAVES
        https://gitee.com/openeuler/kernel/pulls/16699 
v2  Soft domain improves and bugfixes
        https://gitee.com/openeuler/kernel/pulls/16686 
Fix the problem of NFS client mount read/write permission failure
        https://gitee.com/openeuler/kernel/pulls/16680 
powerpc/crash: Fix non-smp kexec preparation
        https://gitee.com/openeuler/kernel/pulls/16596 
Fix watchdog false positive problem
        https://gitee.com/openeuler/kernel/pulls/16662 
Fix erofs fid overflow
        https://gitee.com/openeuler/kernel/pulls/16571 
arm64/mpam: Add MPAM manual
        https://gitee.com/openeuler/kernel/pulls/16639 
v3  Rewrite smt interference account logic
        https://gitee.com/openeuler/kernel/pulls/16691 

飞腾
[OLK-6.6]drm/phytium: Fix some Bugs in Phytium Display Engine
        https://gitee.com/openeuler/kernel/pulls/15819 

兆新
[OLK-6.6] Revert "USB: xHCI: fix resume issue of some ZHAOXIN hosts"
        https://gitee.com/openeuler/kernel/pulls/16653 

intel
platform/x86/intel-uncore-freq: Add efficiency latency control and other fix for 6.6
        https://gitee.com/openeuler/kernel/pulls/16562

海思
KVM: arm64: check if IPIV is enabled in BIOS
        https://gitee.com/openeuler/kernel/pulls/16740 
migration: update status after RAS error
        https://gitee.com/openeuler/kernel/pulls/16609 
drivers/perf: hisi: Clarifying event names and fix event ID for pa_pmu
        https://gitee.com/openeuler/kernel/pulls/16724 
uacce: removal of the Shared Memory Feature for Queues
        https://gitee.com/openeuler/kernel/pulls/16730 
KVM: arm64: Check whether GICv4.0 is enabled
        https://gitee.com/openeuler/kernel/pulls/16696 
Update the watchdog period according to real CPU frequency
        https://gitee.com/openeuler/kernel/pulls/16287 
drivers/perf: hisi: Add events and rename event "cycle" for pa_pmu
        https://gitee.com/openeuler/kernel/pulls/16737 
perf iostat: hisi: Fix port range retrival
        https://gitee.com/openeuler/kernel/pulls/16723 
perf: Remove unstable events for uncore L3C PMU
        https://gitee.com/openeuler/kernel/pulls/16727 
cpufreq: CPPC: Don't warn on failing to read perf counters on offline cpus
        https://gitee.com/openeuler/kernel/pulls/16721 
Add HiSilicon uncore frequency scaling driver
        https://gitee.com/openeuler/kernel/pulls/16701 
crypto: hisilicon - support algorithm fallback v2
        https://gitee.com/openeuler/kernel/pulls/16712 
RDMA/hns: Fix double destruction of rsv_qp
        https://gitee.com/openeuler/kernel/pulls/16694 
drivers/perf: hisi: Add cacheable option for L3C PMU
        https://gitee.com/openeuler/kernel/pulls/16728 
drivers/perf: hisi: Fixes the incorrect bitmask limit for the CPA event sysfs interface
        https://gitee.com/openeuler/kernel/pulls/16732 



议题二：征集中，可直接填报到此处（备注汇报人）
“qemu kvm龙芯架构相关uapi变更”
【背景】：
龙芯虚拟化功能不断完善，陆续推送到上游社区，当前PR是龙芯中断控制器在kvm中仿真patch的修改，因为中断控制器仿真patch提交到openEuler社区的时间要早于提交到上游社区，patch在提交到上游社区的时候发生了更改变化，导致uapi和提交到openEuler的uapi发生了不一致，为了以后更好的兼容上游社区，防止以后的兼容问题，现在将上游中断控制器相关的uapi同步到openEuler社区。
涉及PR：
https://gitee.com/openeuler/qemu/pulls/1492
https://gitee.com/openeuler/kernel/pulls/16467
汇报人: 龙芯虚拟化--李香来
会议结论：同意。由对应committer加分后合入。


三、遗留问题

-------------------------------------------------------------------------------------------------------------------------------------
【2025/6/6 Kernel SIG 双周例会】
轮值主持：廖涛 【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛->吴腾达】
下次轮值主持：吴腾达
会议链接：https://meeting.huaweicloud.com:36443/#/j/963059184
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）
OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-266.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-264.0.0 更新至 5.10.0-266.0.0, 回合补丁数110个
        git log 5.10.0-264.0.0..5.10.0-266.0.0 --oneline --no-merges | wc -l
CVE: (9)
CVE-2025-37925  https://gitee.com/openeuler/kernel/pulls/16397
CVE-2025-37782  https://gitee.com/openeuler/kernel/pulls/16318
CVE-2025-37858  https://gitee.com/openeuler/kernel/pulls/16457
CVE-2022-3238  https://gitee.com/openeuler/kernel/pulls/16258
CVE-2022-49647  https://gitee.com/openeuler/kernel/pulls/16535
CVE-2025-37940  https://gitee.com/openeuler/kernel/pulls/16370
CVE-2024-57876  https://gitee.com/openeuler/kernel/pulls/16424
CVE-2024-58097  https://gitee.com/openeuler/kernel/pulls/16403
CVE-2025-37773  https://gitee.com/openeuler/kernel/pulls/16292

Bugfix: (10)
padata: do not leak refcount in reorder_work
                https://gitee.com/openeuler/kernel/pulls/16498
powercap: intel_rapl_tpmi: backport 2 rapl tpmi update and fix from upstream6.12
                https://gitee.com/openeuler/kernel/pulls/16444
[OLK-5.10]scsi: hisi_sas: Fixed failure to issue vendor specific commands
                https://gitee.com/openeuler/kernel/pulls/16345
xfs: read only mounts with fsopen mount API are busted
                https://gitee.com/openeuler/kernel/pulls/16452
sched/dynamic_affinity: fix preffered_cpu offline problem
                https://gitee.com/openeuler/kernel/pulls/16502
cachefiles: Fix non-taking of sb_writers around set/removexattr
                https://gitee.com/openeuler/kernel/pulls/16219
[OLK-5.10] scsi: libsas: Abort all in-flight requests when device is gone
                https://gitee.com/openeuler/kernel/pulls/16305
sched/fair: Fix the bug in dynamic smt when getting physical core load
                https://gitee.com/openeuler/kernel/pulls/16299
memcg: always call cond_resched() after fn()
                https://gitee.com/openeuler/kernel/pulls/16533
[OLK-5.10] Fix sxe compile errors without CONFIG_PM_SLEEP
                https://gitee.com/openeuler/kernel/pulls/16360

Feature:
Intel: Intel_idle add GNRD and CWF platform support for 5.10
                https://gitee.com/openeuler/kernel/pulls/16446
v4  io_uring patches backport
                https://gitee.com/openeuler/kernel/pulls/16442
[OLK-5.10]Arm64:KVM: Auto get the virtual_dev irq bypass's devid
                https://gitee.com/openeuler/kernel/pulls/14483

海思：
drivers:misc:sdma-dae: fix incorrect kmalloc flag
                https://gitee.com/openeuler/kernel/pulls/16493
drivers:misc:sdma-dae: sdma fix PUAF problem fork risk
                https://gitee.com/openeuler/kernel/pulls/16439

申威：
[OLK-5.10]:sw64: perf: fix compilation error with undeclared EM_SW_64
                https://gitee.com/openeuler/kernel/pulls/16373
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/16357

20250606
OLK-6.6进展同步
​    tag更新到6.6.0-95.0.0
​    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
​    期间合入补丁数423个
​    git log 6.6.0-92.0.0..6.6.0-95.0.0 --oneline --no-merges | wc -l

CVE
        CVE-2025-37867        https://gitee.com/openeuler/kernel/pulls/16428 
        CVE-2025-37943        https://gitee.com/openeuler/kernel/pulls/16479 
        CVE-2025-37952        https://gitee.com/openeuler/kernel/pulls/16372 
        CVE-2025-37940        https://gitee.com/openeuler/kernel/pulls/16369 
        CVE-2025-37765        https://gitee.com/openeuler/kernel/pulls/16414 
        CVE-2025-37782        https://gitee.com/openeuler/kernel/pulls/16317 
        CVE-2025-22127        https://gitee.com/openeuler/kernel/pulls/16209 
        CVE-2025-37738        https://gitee.com/openeuler/kernel/pulls/16371 
        CVE-2025-23151        https://gitee.com/openeuler/kernel/pulls/16413 
        CVE-2025-37851        https://gitee.com/openeuler/kernel/pulls/16496 
        CVE-2024-58096        https://gitee.com/openeuler/kernel/pulls/16404 
        CVE-2025-37936        https://gitee.com/openeuler/kernel/pulls/16453 
        CVE-2025-37925        https://gitee.com/openeuler/kernel/pulls/16399 
        CVE-2025-37970        https://gitee.com/openeuler/kernel/pulls/16394 
        CVE-2025-22104        https://gitee.com/openeuler/kernel/pulls/16207 
        CVE-2025-37747        https://gitee.com/openeuler/kernel/pulls/16542 
        CVE-2024-50140        https://gitee.com/openeuler/kernel/pulls/16477 
        CVE-2025-37773        https://gitee.com/openeuler/kernel/pulls/16291 
        CVE-2025-37886        https://gitee.com/openeuler/kernel/pulls/16478 
        CVE-2025-21972        https://gitee.com/openeuler/kernel/pulls/16433 
        CVE-2025-37903        https://gitee.com/openeuler/kernel/pulls/16521 
        CVE-2025-37836        https://gitee.com/openeuler/kernel/pulls/16313 
        CVE-2025-37858        https://gitee.com/openeuler/kernel/pulls/16459 
        CVE-2025-37852        https://gitee.com/openeuler/kernel/pulls/16408 
        CVE-2025-22109        https://gitee.com/openeuler/kernel/pulls/16210 
        CVE-2025-22028        https://gitee.com/openeuler/kernel/pulls/16211 
        CVE-2025-37988        https://gitee.com/openeuler/kernel/pulls/16435 
        CVE-2025-37754        https://gitee.com/openeuler/kernel/pulls/16476 
        CVE-2025-23161        https://gitee.com/openeuler/kernel/pulls/16395 
        CVE-2024-58097        https://gitee.com/openeuler/kernel/pulls/16432 
        CVE-2024-27079        https://gitee.com/openeuler/kernel/pulls/16524 

bugfix
ASoC: qcom: Fix sc7280 lpass potential buffer overflow
                https://gitee.com/openeuler/kernel/pulls/16515 
init/Kconfig: Add SMP to the dependencies of QOS_SCHED
                https://gitee.com/openeuler/kernel/pulls/16085 
memcg: always call cond_resched() after fn()
                https://gitee.com/openeuler/kernel/pulls/16532 
[OLK-6.6][Bugfix]hugetlb: Fix NULL pointer dereference BUG
                https://gitee.com/openeuler/kernel/pulls/16445 
padata: do not leak refcount in reorder_work
                https://gitee.com/openeuler/kernel/pulls/16499 
v2  arm64: entry: Fix ACTLR_XCALL_XINT not set build problem
                https://gitee.com/openeuler/kernel/pulls/16523 
net: tcp: scale connect() under pressure
                https://gitee.com/openeuler/kernel/pulls/16481 
bcache: call force_wake_up_gc() if necessary in check_should_bypass()
                https://gitee.com/openeuler/kernel/pulls/15903 
Backport 6.6.55-6.6.60 LTS
                https://gitee.com/openeuler/kernel/pulls/16366 
gfp: include __GFP_NOWARN in GFP_NOWAIT
                https://gitee.com/openeuler/kernel/pulls/16364 
tracing: Fix filter string testing
                https://gitee.com/openeuler/kernel/pulls/16564 
cachefiles: Parse the "secctx" immediately
                https://gitee.com/openeuler/kernel/pulls/16398 
Some random fixes and cleanup to shmem
                https://gitee.com/openeuler/kernel/pulls/16563 
LTS Conflicts Backport
                https://gitee.com/openeuler/kernel/pulls/16374 
kernel: Remove signal hacks for vhost_tasks
                https://gitee.com/openeuler/kernel/pulls/16311 
cgroup: Eliminate the need for cgroup_mutex in proc_cgroup_show()
                https://gitee.com/openeuler/kernel/pulls/16388 
Add CFTYPE_NOT_ON_ROOT for qos_level
                https://gitee.com/openeuler/kernel/pulls/16365 
backport mainline mm bugfix
                https://gitee.com/openeuler/kernel/pulls/16246 
mm: fix VMA heap bounds checking
                https://gitee.com/openeuler/kernel/pulls/16421 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.69-6.6.70 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/16482 
v2  some fix about ifs
                https://gitee.com/openeuler/kernel/pulls/16527 
[OLK-6.6]riscv: fix kprobe crash due to broken patch_text() API
                https://gitee.com/openeuler/kernel/pulls/16448 
vdpa:Adding compilation macro to decouple the vdpa and iommufd modules
                https://gitee.com/openeuler/kernel/pulls/16378 

特性
kvm:Optimize the processing performance of multiple eventfd and irqfd
                https://gitee.com/openeuler/kernel/pulls/16100 
v3  fuse: Backport Anolis Features and Performance patches
                https://gitee.com/openeuler/kernel/pulls/16422 
v7  Add FUSE Passthrough Support
                https://gitee.com/openeuler/kernel/pulls/16401 
[OLK-6.6][eNFS]add nfs feature to support multipath
                https://gitee.com/openeuler/kernel/pulls/16028 
v5  xfs: support log grant track bytes
                https://gitee.com/openeuler/kernel/pulls/16456 
arm64/mpam: Update QoS partition default value
                https://gitee.com/openeuler/kernel/pulls/16423 
sched: fair: Use rq_clock_task to account rq->idle_avg
                https://gitee.com/openeuler/kernel/pulls/16536 
ext4: better scalability for ext4 block allocation
                https://gitee.com/openeuler/kernel/pulls/16441 
v5  Cgroup-Based Interference Statistics
                https://gitee.com/openeuler/kernel/pulls/16489 
mm: remove unnecessary calls to lru_add_drain
                https://gitee.com/openeuler/kernel/pulls/16389 
v5: ucounts: rlimit scalability issues
                https://gitee.com/openeuler/kernel/pulls/16484 
v2  Support thp policy control per process
                https://gitee.com/openeuler/kernel/pulls/16509 
v3  arm64: idle: Handle idle state for xcall/xint
                https://gitee.com/openeuler/kernel/pulls/16458 
v5  Support soft domain
                https://gitee.com/openeuler/kernel/pulls/16510 
v10  High Performance Container Resource View Isolation
                https://gitee.com/openeuler/kernel/pulls/16486 
fs/resctrl: Restore default settings for all resctrl_res_level
                https://gitee.com/openeuler/kernel/pulls/16513 

裕泰微
yt6801: Add Motorcomm yt6801 PCIe driver
                https://gitee.com/openeuler/kernel/pulls/16346 

申威
[OLK-6.6]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/16363 

海光
Add  hygon_set_guest_pat_wb parameter  to  enhance performance for non-passthrough application scenarios
                https://gitee.com/openeuler/kernel/pulls/15148 
[OLK-6.6] perf/x86/uncore: Add DF PMU support for Hygon family 18h model 8h
                https://gitee.com/openeuler/kernel/pulls/15657 
Get the correct  instance id  calculation for Hygon family 18h model 6h~10h
                https://gitee.com/openeuler/kernel/pulls/15153 
Add IOAPIC  support for Hygon family 18h model 10h
                https://gitee.com/openeuler/kernel/pulls/15156 
[OLK-6.6] 移除vpsp运行时对CSV功能的依赖
                https://gitee.com/openeuler/kernel/pulls/16427 
[OLK-6.6]Hygon: Support to dec and enc userspace pages
                https://gitee.com/openeuler/kernel/pulls/16449 
[OLK-6.6] 支持用户态通过hygon_psp_resource2设备节点mmap PSP设备的mmio内存
                https://gitee.com/openeuler/kernel/pulls/16041 
correct address translation  for Hygon family 18h model 4h~10h
                https://gitee.com/openeuler/kernel/pulls/15150 

intel
Intel: Intel_idle add GNRD and CWF platform support for 6.6
                https://gitee.com/openeuler/kernel/pulls/16447 

海思
RDMA/hns: Trace support and bugfixes
                https://gitee.com/openeuler/kernel/pulls/16473 
hisi_sas: Misc patches and cleanups
                https://gitee.com/openeuler/kernel/pulls/16487 
drm/hisilicon/hibmc: add HPD, getting EDID, colorbar features in DP function
                https://gitee.com/openeuler/kernel/pulls/16488 
bugfix for hisilicon accelerator driver
                https://gitee.com/openeuler/kernel/pulls/16483 
net: hns3: add set_loopback interface to realtek phy driver
                https://gitee.com/openeuler/kernel/pulls/16461 
v5  IPIV-BUGFIX for HIP12
                https://gitee.com/openeuler/kernel/pulls/16431 
irqchip/gic: remove useless printing in pv sgi
                https://gitee.com/openeuler/kernel/pulls/16541 
【olk 6.6】backport two bugfixes for hibmcge driver
                https://gitee.com/openeuler/kernel/pulls/16392 


议题二：征集中，可直接填报到此处（备注汇报人）

1.申威架构特有文件committer申报 （申威-顾子滔）
申威架构相关的文件主要包括arch/sw_64目录、drivers下部分驱动、tools下部分文件，这些文件名中均带有sw64或者sunway关键字，或者在sw_64目录下，现申请成为这些文件的committer，负责相关review工作。
arch/sw_64/*
drivers/clocksource/timer-sw64.c
drivers/cpufreq/sunway-cpufreq.c
drivers/firmware/efi/sunway-init.c
drivers/firmware/efi/sunway-runtime.c
drivers/gpio/gpio-sunway.c
drivers/hwmon/sw64_pvt.c
drivers/i2c/busses/i2c-sunway.c
drivers/iommu/sw64/Kconfig
drivers/iommu/sw64/Makefile
drivers/iommu/sw64/iommu.c
[6.6] drivers/iommu/sw64/iommu.h
drivers/iommu/sw64/iommu_v2.c
[5.10] drivers/iommu/sw64/sunway_iommu.h
drivers/irqchip/irq-sunway-cpu.c
drivers/irqchip/irq-sunway-lpc-intc.c
drivers/irqchip/irq-sunway-msi-v2.c
drivers/irqchip/irq-sunway-msi-vt.c
drivers/irqchip/irq-sunway-msi.c
drivers/irqchip/irq-sunway-pci-intx.c
drivers/irqchip/irq-sunway-pintc.c
drivers/mfd/lpc_sunway.c
drivers/mfd/sunway_ast2400.c
drivers/misc/sunway-ged.c
drivers/pci/controller/pci-sunway.c
drivers/pci/hotplug/sunway_pciehp.h
drivers/pci/hotplug/sunway_pciehp_core.c
drivers/pci/hotplug/sunway_pciehp_ctrl.c
drivers/pci/hotplug/sunway_pciehp_hpc.c
drivers/pci/hotplug/sunway_pciehp_pci.c
drivers/platform/sw64/Makefile
[5.10] drivers/platform/sw64/legacy_junzhang.c
[5.10] drivers/platform/sw64/legacy_xuelang.c
drivers/platform/sw64/misc-platform.c
drivers/platform/sw64/powercap.c
drivers/rtc/rtc-sw64-guest.c
drivers/rtc/rtc-sw64-virt-platform.c
drivers/rtc/rtc-sw64-virt.c
drivers/spi/spi-sunway-mmio.c
drivers/spi/spi-sunway.c
drivers/spi/spi-sunway.h
drivers/tty/serial/8250/8250_sunway.c
include/acpi/pdc_sw64.h
include/linux/platform_data/gpio-sunway.h
tools/arch/sw_64/include/asm/barrier.h
tools/arch/sw_64/include/uapi/asm/bitsperlong.h
tools/arch/sw_64/include/uapi/asm/bpf_perf_event.h
tools/arch/sw_64/include/uapi/asm/errno.h
tools/arch/sw_64/include/uapi/asm/mman.h
tools/arch/sw_64/include/uapi/asm/perf_regs.h
tools/build/feature/test-libunwind-sw_64.c
tools/perf/arch/sw_64/Build
tools/perf/arch/sw_64/Makefile
tools/perf/arch/sw_64/include/arch-tests.h
tools/perf/arch/sw_64/include/dwarf-regs-table.h
tools/perf/arch/sw_64/include/perf_regs.h
tools/perf/arch/sw_64/tests/Build
tools/perf/arch/sw_64/tests/arch-tests.c
tools/perf/arch/sw_64/tests/dwarf-unwind.c
tools/perf/arch/sw_64/tests/regs_load.S
tools/perf/arch/sw_64/util/Build
tools/perf/arch/sw_64/util/dwarf-regs.c
tools/perf/arch/sw_64/util/perf_regs.c
tools/perf/arch/sw_64/util/unwind-libdw.c
tools/perf/arch/sw_64/util/unwind-libunwind.c
tools/perf/util/libunwind/sw64.c
[6.6] tools/perf/util/perf-regs-arch/perf_regs_sw64.c

会上结论：同意。

2. arch/x86/mm/pat/enc_dec_user_memory.c文件committer申报（海光-韩里洋）
arch/x86/mm/pat/enc_dec_user_memory.c文件在PR：https://gitee.com/openeuler/kernel/pulls/16449 中引入。该文件为非通用功能，是为海光的gpu定制的内核接口。由于要调用kernel内部模块的api，无法从内核中剥离开来，所以单独出来成文件。申请将arch/x86/mm/pat/enc_dec_user_memory.c的committer改为海光-韩里洋（hanliyang@hygon.cn）

会上结论：同意。


三、遗留问题

李楠：committer相关门禁刷新

-----------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2025/5/23 Kernel SIG 双周例会】
轮值主持：李楠 【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/981717757
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetingscom

一、上期遗留问题跟踪


二、议题列表
议题一：进展update（李楠&吴腾达）
20250523
OLK-6.6进展同步
    tag更新到6.6.0-92.0.0
    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数361个
    git log 6.6.0-88.0.0..6.6.0-92.0.0 --oneline --no-merges | wc -l
CVE(34)
        CVE-2025-23146  https://gitee.com/openeuler/kernel/pulls/16326 
        CVE-2025-37818  https://gitee.com/openeuler/kernel/pulls/16231 
        CVE-2025-37860  https://gitee.com/openeuler/kernel/pulls/16208 
        CVE-2025-37742  https://gitee.com/openeuler/kernel/pulls/16189 
        CVE-2025-37811  https://gitee.com/openeuler/kernel/pulls/16233 
        CVE-2025-22014  https://gitee.com/openeuler/kernel/pulls/15908 
        CVE-2025-22095  https://gitee.com/openeuler/kernel/pulls/16117 
        CVE-2025-22045  https://gitee.com/openeuler/kernel/pulls/16074 
        CVE-2025-23144  https://gitee.com/openeuler/kernel/pulls/16224 
        CVE-2025-21635  https://gitee.com/openeuler/kernel/pulls/16066 
        CVE-2025-22121  https://gitee.com/openeuler/kernel/pulls/16023 
        CVE-2025-37799  https://gitee.com/openeuler/kernel/pulls/16165 
        CVE-2025-22113  https://gitee.com/openeuler/kernel/pulls/15931 
        CVE-2025-22044  https://gitee.com/openeuler/kernel/pulls/16073 
        CVE-2025-22040  https://gitee.com/openeuler/kernel/pulls/16094 
        CVE-2025-37807  https://gitee.com/openeuler/kernel/pulls/16218 
        CVE-2025-21979  https://gitee.com/openeuler/kernel/pulls/16087 
        CVE-2025-37830  https://gitee.com/openeuler/kernel/pulls/16198 
        CVE-2025-37884  https://gitee.com/openeuler/kernel/pulls/16217 
        CVE-2025-37755  https://gitee.com/openeuler/kernel/pulls/16193 
        CVE-2024-58094  https://gitee.com/openeuler/kernel/pulls/16053 
        CVE-2025-37870  https://gitee.com/openeuler/kernel/pulls/16328 
        CVE-2025-22041  https://gitee.com/openeuler/kernel/pulls/15994 
        CVE-2025-21950  https://gitee.com/openeuler/kernel/pulls/16257 
        CVE-2025-22027  https://gitee.com/openeuler/kernel/pulls/16086 
        CVE-2025-21957  https://gitee.com/openeuler/kernel/pulls/16101 
        CVE-2025-21916  https://gitee.com/openeuler/kernel/pulls/16256 
        CVE-2025-22125  https://gitee.com/openeuler/kernel/pulls/16103 
        CVE-2025-22048  https://gitee.com/openeuler/kernel/pulls/15962 
        CVE-2025-22072  https://gitee.com/openeuler/kernel/pulls/16116 
        CVE-2024-58093  https://gitee.com/openeuler/kernel/pulls/16080 
        CVE-2025-22079  https://gitee.com/openeuler/kernel/pulls/16310 
        CVE-2025-37878  https://gitee.com/openeuler/kernel/pulls/16325 
        CVE-2024-58098  https://gitee.com/openeuler/kernel/pulls/16298 

Bugfix（27）
scsi: sg: fix refcount underflow in
        https://gitee.com/openeuler/kernel/pulls/16367 
mm: zswap: handle incorrect attempts to load large folios
        https://gitee.com/openeuler/kernel/pulls/16108 
mpage: fix softlockup in mpage_readahead()
        https://gitee.com/openeuler/kernel/pulls/16075 
ext4: fix the logic to determine whether buffered IO can use iomap
        https://gitee.com/openeuler/kernel/pulls/16037 
xhci: Limit time spent with xHC interrupts disabled during bus resume
        https://gitee.com/openeuler/kernel/pulls/16183 
irqchip/mbigen: add check before deference 'mgn_chip'
        https://gitee.com/openeuler/kernel/pulls/16045 
kvm: x86: fix infinite loop in kvm_guest_time_update when tsc is 0
        https://gitee.com/openeuler/kernel/pulls/16271 
[OLK-6.6] 从上游linux-6.6.y回合nvme驱动重要bugfix
        https://gitee.com/openeuler/kernel/pulls/15918 
mailbox: pcc: Always clear the platform ack interrupt first
        https://gitee.com/openeuler/kernel/pulls/16055 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.63-6.6.64 LTS Conflicts Patches
        https://gitee.com/openeuler/kernel/pulls/15384 
mm/huge_memory: drop beyond-EOF folios with the right number of refs
        https://gitee.com/openeuler/kernel/pulls/15948 
Sync from 6.6 for the sam kabi
        https://gitee.com/openeuler/kernel/pulls/16284 
v2  tracing: Verify event formats that have "%*p.."
        https://gitee.com/openeuler/kernel/pulls/16079 
Two backport bugfix patches
        https://gitee.com/openeuler/kernel/pulls/15897 
Revert "tmpfs: fault in smaller chunks if large folio allocation not allowed"
        https://gitee.com/openeuler/kernel/pulls/16143 
[OLK-6.6] backport important bugfix for nvme driver from upstream linux-6.6.y
        https://gitee.com/openeuler/kernel/pulls/16344 
Backport PRM update and bugfixes up to v6.14.
        https://gitee.com/openeuler/kernel/pulls/15434 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.82-6.6.83 LTS Patches
        https://gitee.com/openeuler/kernel/pulls/16349 
md/raid1: fix memleak and double free in
        https://gitee.com/openeuler/kernel/pulls/15937 
bpf: Fix WARN() in get_bpf_raw_tp_regs
        https://gitee.com/openeuler/kernel/pulls/16323 
[OLK-6.6]Backport some mm related commits from Linux upstream
        https://gitee.com/openeuler/kernel/pulls/16020 
PINCTRL:ENABLE_CONFIG_PINCTRL for resolve Intel notebook touchpad issue;  fw, net: wireless: Add RTW88 driver and compressed firmware support
        https://gitee.com/openeuler/kernel/pulls/16180 
V3:mm: shmem: skip swapcache for swapin of synchronous swap device
        https://gitee.com/openeuler/kernel/pulls/16102 
swap-in support large folio
        https://gitee.com/openeuler/kernel/pulls/16034 

Feature
v5  Memory access profiler(SPE) driven NUMA balancing and damon
        https://gitee.com/openeuler/kernel/pulls/16342 
arm64/mpam: Expanding MPAM's QoS capability
        https://gitee.com/openeuler/kernel/pulls/16062 
fs/resctrl: Create l2 cache monitors
        https://gitee.com/openeuler/kernel/pulls/16099 
IMA: support virtcca extend assigned register
        https://gitee.com/openeuler/kernel/pulls/16302 
vdpa/iommufd: Support taking over vDPA devices' iommu groups through the iommufd API
        https://gitee.com/openeuler/kernel/pulls/15719 

龙芯
Add Loongson PWM controller support
        https://gitee.com/openeuler/kernel/pulls/16280 
Revert "LoongArch: Set hugetlb mmap base address aligned with pmd size"
        https://gitee.com/openeuler/kernel/pulls/16081 
[OLK-6.6] fix bug：compiler error on loongarch64 for mucse rnpm driver
        https://gitee.com/openeuler/kernel/pulls/12616 
LoongArch: sync internal repository 20250414
        https://gitee.com/openeuler/kernel/pulls/15887 
crypto: loongson: add wst se chip support
        https://gitee.com/openeuler/kernel/pulls/16279 
drm: LoongArch: fix rx550/gfx6/gfx7/gfx8 error
        https://gitee.com/openeuler/kernel/pulls/16278 
LoongArch: add PCA953X/2K3000 GMAC/IGC netcard/NR_CPUS=2048/SCHED_MC support
        https://gitee.com/openeuler/kernel/pulls/16324 
Fixed multiple vfio devices not working properly
        https://gitee.com/openeuler/kernel/pulls/14328 
drivers/iommu: Enhance the robustness of the iommu module
        https://gitee.com/openeuler/kernel/pulls/16229 

沐创
[OLK-6.6] mucse: rnpm ocp nic support hotplug and show sub-zero temperature
        https://gitee.com/openeuler/kernel/pulls/14100 
[OLK-6.6] Fix rnpvf compile errors without CONFIG_MXGBEVF_FIX_VF_QUEUE
        https://gitee.com/openeuler/kernel/pulls/12573 
[OLK-6.6] Fix os crash when cat some sys interface when net down
        https://gitee.com/openeuler/kernel/pulls/14174 
[OLK-6.6] Fix rnp errors dmesg show in hygon
        https://gitee.com/openeuler/kernel/pulls/14169 

云脉芯联
drivers/yunsilicon: fix query/modify pkt_dst_info return error
        https://gitee.com/openeuler/kernel/pulls/16192 
[openEuler-24.03-LTS-SP2] drivers: update Yunsilicon drivers to 2412GA
        https://gitee.com/openeuler/kernel/pulls/16144 

intel
[Intel-SIG]dmaengine: idxd: Add a new DSA device ID for Granite Rapids-D platform
        https://gitee.com/openeuler/kernel/pulls/15291 

海光
【OLK-6.6】新增海光psp/ccp device id以及优化海光可信功能内核驱动
                https://gitee.com/openeuler/kernel/pulls/16281 
[OLK-6.6][bugfix]Hygon: Remove HYDCU fixup header driver from kernel source code
                https://gitee.com/openeuler/kernel/pulls/16024 
[OLK-6.6] 优化海光密钥管理虚拟化场景的性能
                https://gitee.com/openeuler/kernel/pulls/16039 
[OLK-6.6]Hygon: Address boot failures of CSV1/CSV2 VMs on Hygon 2g and C86-3g CPUs with firmware build ID below 1878 and 1810.
                https://gitee.com/openeuler/kernel/pulls/16350 
[OLK-6.6]Hygon: In a CSV3 VM, the hypercall should notify real page enc/dec status
                https://gitee.com/openeuler/kernel/pulls/16026 
Add support for Hygon family 18h model 8h
                https://gitee.com/openeuler/kernel/pulls/15158 
[OLK-6.6][bugfix]Hygon：Avoid concurrent pinning shared pages at both KVM side and vfio side when passthrough device to CSV3 VM
                https://gitee.com/openeuler/kernel/pulls/16025 
Add LS and IF mce types for Hygon family 18h model 7h
                https://gitee.com/openeuler/kernel/pulls/15155 
[OLK-6.6][bugfix]Hygon: Return 0 at the beginning of csv_guest_hygon_coco_extension() for non-CSV3 VMs
                https://gitee.com/openeuler/kernel/pulls/16019 
Add support edac for hygon family 18h model 10h
                https://gitee.com/openeuler/kernel/pulls/15157 

灵达
[OLK-6.6] Ethernet: Supports Linkdata ethernet Controllers
                https://gitee.com/openeuler/kernel/pulls/15589 
[OLK-6.6] Fix sxe compile errors without CONFIG_PM_SLEEP
                https://gitee.com/openeuler/kernel/pulls/16352 

海思
【olk 6.6】net: hns3: backport some bugfixes
                https://gitee.com/openeuler/kernel/pulls/16186 
【olk 6.6】 add two bugfixes for ptp_hisi driver
                https://gitee.com/openeuler/kernel/pulls/16300 
net/hinic3: Synchronize new NIC features and bug fixes
                https://gitee.com/openeuler/kernel/pulls/16196 
net: hns3: some bugfixes for hns3 driver
                https://gitee.com/openeuler/kernel/pulls/16359 
RDMA/hns: Fix the compatibility between the kernel mode and user mode
                https://gitee.com/openeuler/kernel/pulls/15986 
arm64: Add support for FEAT_{LS64, LS64_V}.
                https://gitee.com/openeuler/kernel/pulls/16286 
Revert DP HPD module to fix the problem
                https://gitee.com/openeuler/kernel/pulls/16277
Add gpio-hisi softdepend
                https://gitee.com/openeuler/kernel/pulls/16174 

OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-264.0.0
        ISO镜像和update rpm包获取链接: 
                https://repo.openeuler.org/openEuler-22.03-LTS-SP3
                https://repo.openeuler.org/openEuler-22.03-LTS-SP4
        从 5.10.0-262.0.0 更新至 5.10.0-264.0.0, 回合补丁数215个
        git log 5.10.0-262.0.0..5.10.0-264.0.0 --oneline --no-merges | wc -l

CVE: (62)
CVE-2025-21863  https://gitee.com/openeuler/kernel/pulls/15595 
CVE-2025-21763  https://gitee.com/openeuler/kernel/pulls/16127 
CVE-2025-21816  https://gitee.com/openeuler/kernel/pulls/15701 
CVE-2025-37785  https://gitee.com/openeuler/kernel/pulls/16343 
CVE-2024-58009  https://gitee.com/openeuler/kernel/pulls/15397 
CVE-2025-21887  https://gitee.com/openeuler/kernel/pulls/15671 
CVE-2025-21943  https://gitee.com/openeuler/kernel/pulls/15769 
CVE-2024-57980  https://gitee.com/openeuler/kernel/pulls/15717 
CVE-2022-49246  https://gitee.com/openeuler/kernel/pulls/15378 
CVE-2025-21764  https://gitee.com/openeuler/kernel/pulls/16063 
CVE-2025-21756  https://gitee.com/openeuler/kernel/pulls/15413 
CVE-2025-21761  https://gitee.com/openeuler/kernel/pulls/16128 
CVE-2025-23144  https://gitee.com/openeuler/kernel/pulls/16225 
CVE-2025-21877  https://gitee.com/openeuler/kernel/pulls/15791 
CVE-2022-49553  https://gitee.com/openeuler/kernel/pulls/15630 
CVE-2024-58001  https://gitee.com/openeuler/kernel/pulls/15422 
CVE-2025-21935  https://gitee.com/openeuler/kernel/pulls/15811 
CVE-2025-21881  https://gitee.com/openeuler/kernel/pulls/15760 
CVE-2022-49443  https://gitee.com/openeuler/kernel/pulls/15679 
CVE-2025-21762  https://gitee.com/openeuler/kernel/pulls/16129 
CVE-2023-53010  https://gitee.com/openeuler/kernel/pulls/15892 
CVE-2022-49513  https://gitee.com/openeuler/kernel/pulls/15716 
CVE-2025-21719  https://gitee.com/openeuler/kernel/pulls/15403 
CVE-2025-21779  https://gitee.com/openeuler/kernel/pulls/15373 
CVE-2025-23150  https://gitee.com/openeuler/kernel/pulls/16204 
CVE-2025-21858  https://gitee.com/openeuler/kernel/pulls/15837 
CVE-2024-57947  https://gitee.com/openeuler/kernel/pulls/15295 
CVE-2025-21718  https://gitee.com/openeuler/kernel/pulls/15690 
CVE-2022-49096  https://gitee.com/openeuler/kernel/pulls/15307 
CVE-2022-49444  https://gitee.com/openeuler/kernel/pulls/15501 
CVE-2025-21823  https://gitee.com/openeuler/kernel/pulls/15728 
CVE-2021-47660  https://gitee.com/openeuler/kernel/pulls/15627 
CVE-2025-21816  https://gitee.com/openeuler/kernel/pulls/15510 
CVE-2023-53091  https://gitee.com/openeuler/kernel/pulls/16206 
CVE-2024-56642  https://gitee.com/openeuler/kernel/pulls/15765 
CVE-2025-21804  https://gitee.com/openeuler/kernel/pulls/15480 
CVE-2025-21727  https://gitee.com/openeuler/kernel/pulls/15683 
CVE-2025-21760  https://gitee.com/openeuler/kernel/pulls/16125 
CVE-2025-21791  https://gitee.com/openeuler/kernel/pulls/15449 
CVE-2025-22079  https://gitee.com/openeuler/kernel/pulls/16309 
CVE-2025-21928  https://gitee.com/openeuler/kernel/pulls/15841 
CVE-2025-21727  https://gitee.com/openeuler/kernel/pulls/15682 
CVE-2022-49711  https://gitee.com/openeuler/kernel/pulls/15379 
CVE-2023-53001  https://gitee.com/openeuler/kernel/pulls/15773 
CVE-2025-37807  https://gitee.com/openeuler/kernel/pulls/16316 
CVE-2022-49651  https://gitee.com/openeuler/kernel/pulls/15382 
CVE-2025-37839  https://gitee.com/openeuler/kernel/pulls/16220 
CVE-2022-49564  https://gitee.com/openeuler/kernel/pulls/15387 
CVE-2025-21993  https://gitee.com/openeuler/kernel/pulls/15959 
CVE-2024-54680  https://gitee.com/openeuler/kernel/pulls/15232 
CVE-2025-21780  https://gitee.com/openeuler/kernel/pulls/15956 
CVE-2025-21722  https://gitee.com/openeuler/kernel/pulls/15646 
CVE-2024-56664  https://gitee.com/openeuler/kernel/pulls/15766 
CVE-2025-21715  https://gitee.com/openeuler/kernel/pulls/15409 
CVE-2024-58094  https://gitee.com/openeuler/kernel/pulls/16088 
CVE-2025-21735  https://gitee.com/openeuler/kernel/pulls/15419 
CVE-2023-53093  https://gitee.com/openeuler/kernel/pulls/16164 
CVE-2025-23146  https://gitee.com/openeuler/kernel/pulls/16327 
CVE-2025-21999  https://gitee.com/openeuler/kernel/pulls/16036 
CVE-2022-49328  https://gitee.com/openeuler/kernel/pulls/15828 
CVE-2025-21785  https://gitee.com/openeuler/kernel/pulls/15675 
CVE-2024-57951  https://gitee.com/openeuler/kernel/pulls/15802 

Bugfix: (48)
soc: hisilicon: Serialize the online and onfline the acpi devices
                https://gitee.com/openeuler/kernel/pulls/15867 
block: fix bugs in blk_register_queue()
                https://gitee.com/openeuler/kernel/pulls/15840 
uffd: Fix bug of cannot set mode in userfaultfd_copy
                https://gitee.com/openeuler/kernel/pulls/16215 
orangefs: fix a oob in orangefs_debug_write
                https://gitee.com/openeuler/kernel/pulls/15389 
Fix kmemleak false positive
                https://gitee.com/openeuler/kernel/pulls/15759 
cifs: Fix an infinite loop in cifsd caused by a failed mount attempt on port 139
                https://gitee.com/openeuler/kernel/pulls/15498 
fs/dcache: fix bad unlock balance in shrink_dentry_list()
                https://gitee.com/openeuler/kernel/pulls/15696 
md/raid1: fix bitmap update when all write requests fail
                https://gitee.com/openeuler/kernel/pulls/15940 
md: bypass block throttle for superblock update
                https://gitee.com/openeuler/kernel/pulls/15938 
mpage: fix softlockup in mpage_readahead()
                https://gitee.com/openeuler/kernel/pulls/16076 
block: fix UAF in blk_mq_has_sqsched()
                https://gitee.com/openeuler/kernel/pulls/15941 
try to backport "block: fix rq-qos breakage from skipping rq_qos_done_bio"
                https://gitee.com/openeuler/kernel/pulls/15053 
Fix instance dir use-after-free in tracefs
                https://gitee.com/openeuler/kernel/pulls/15606 
intel: backport intel_pstate driver update from 6.11
                https://gitee.com/openeuler/kernel/pulls/13916 
powerpc: Fix save r13 on kprobe/ftrace entry
                https://gitee.com/openeuler/kernel/pulls/15756 
v3  CVE-2025-21816
                https://gitee.com/openeuler/kernel/pulls/15510 
[OLK-5.10] backport important bugfix from the kernel-5.10.y
                https://gitee.com/openeuler/kernel/pulls/14918 
[OLK-5.10] backport important bugfix for nvme driver from the kernel-5.10.y
                https://gitee.com/openeuler/kernel/pulls/15888 
kvm: x86: fix infinite loop in kvm_guest_time_update when tsc is 0
                https://gitee.com/openeuler/kernel/pulls/16274 
Backport the perf fix patch
                https://gitee.com/openeuler/kernel/pulls/15990 
x86/dumpstack: Fix inaccurate unwinding from exception stacks due to misplaced assignment
                https://gitee.com/openeuler/kernel/pulls/15753 
Backport mainline patches to avoid crash caused by rsize being 0
                https://gitee.com/openeuler/kernel/pulls/15899 
[OLK-5.10] backport important bugfix from the kernel-5.10.y
                https://gitee.com/openeuler/kernel/pulls/14905 
ftrace: Avoid potential division by zero in function_stat_show()
                https://gitee.com/openeuler/kernel/pulls/15894 
Push 2 self-developed patches to OLK-5.10
                https://gitee.com/openeuler/kernel/pulls/15699 
[OLK-5.10] iommu/vt-d: Set No Execute Enable bit in PASID table entry
                https://gitee.com/openeuler/kernel/pulls/16048 
ubi: fastmap: wl: Schedule fm_work if wear-leveling pool is empty
                https://gitee.com/openeuler/kernel/pulls/15428 
v2  iommu/arm-smmu-v3: Fix the extra atc tlb flush
                https://gitee.com/openeuler/kernel/pulls/15883 
backport mainline bugfix patch
                https://gitee.com/openeuler/kernel/pulls/15391 
mailbox: pcc: Always clear the platform ack interrupt first
                https://gitee.com/openeuler/kernel/pulls/16057 
Revert "arm64: mm: add mc support for __buffer_migrate_page"
                https://gitee.com/openeuler/kernel/pulls/15794 
[OLK-5.10] new bugfix from mainline for Turin
                https://gitee.com/openeuler/kernel/pulls/15776 
tracing: Fix use-after-free in print_graph_function_flags during tracer switching
                https://gitee.com/openeuler/kernel/pulls/15733 
RDMA/hns: Fix mbox timing out by adding retry mechanism
                https://gitee.com/openeuler/kernel/pulls/15454 
md/raid1: fix memory leak in raid1_run() if no active rdev
                https://gitee.com/openeuler/kernel/pulls/15939 
bpf: Fix WARN() in get_bpf_raw_tp_regs
                https://gitee.com/openeuler/kernel/pulls/16322 
net: hns3: some bugfixes for hns3 driver
                https://gitee.com/openeuler/kernel/pulls/15300 
bugfixes for fuse fastpath and fast_ipc
                https://gitee.com/openeuler/kernel/pulls/16356 
KVM: arm64: pvsched bugfix and module param
                https://gitee.com/openeuler/kernel/pulls/15241 
【olk 5.10】revert and backport a bugfix
                https://gitee.com/openeuler/kernel/pulls/15591 
Some bug fix patches for RDMA/hns to olk-5.10
                https://gitee.com/openeuler/kernel/pulls/15447 
Mainline Patch
                https://gitee.com/openeuler/kernel/pulls/15348 
mailbox: pcc: Fix the possible race in updation of chan_in_use flag
                https://gitee.com/openeuler/kernel/pulls/15429 
[22.03-LTS-SP3]Solve the problem that a virtual machine cannot identify the GPU by passthrough
                https://gitee.com/openeuler/kernel/pulls/8014 
v2  soc: hisilicon: Add checks against NULL pointer reference
                https://gitee.com/openeuler/kernel/pulls/15460 
smb: client: Fix netns refcount imbalance
                https://gitee.com/openeuler/kernel/pulls/15232 
net/hinic3: Synchronize new NIC features and bug fixes
                https://gitee.com/openeuler/kernel/pulls/16184 
Some bug fix patches for OLK-5.10 hns RoCE
                https://gitee.com/openeuler/kernel/pulls/15426 
soc: hisilicon: Fix one printing issue and simplify some printing
                https://gitee.com/openeuler/kernel/pulls/15456 

Feature:
[Intel-SIG]dmaengine: idxd: Add a new DSA device ID for Granite Rapids-D platform
                https://gitee.com/openeuler/kernel/pulls/15296 
arm64: mm: add mc support for __buffer_migrate_page
                https://gitee.com/openeuler/kernel/pulls/15669 
sched/fair: Optimize the dynamic smt
                https://gitee.com/openeuler/kernel/pulls/15676 
[Intel-SIG] 5.10-x86/cpu: Clearwater Forest new model and ISAs support.
                https://gitee.com/openeuler/kernel/pulls/15272 
fuse: support fastpath
                https://gitee.com/openeuler/kernel/pulls/16242 
perf: Configure BRBE correctly on VHE host
                https://gitee.com/openeuler/kernel/pulls/15816 
igc: add default intel igc driver module support
                https://gitee.com/openeuler/kernel/pulls/2893 

海思：
drivers:misc:sdma-dae: sync code to openEuler
                https://gitee.com/openeuler/kernel/pulls/15643 
sdma-dae: modify ttl_processes reduce logic
                https://gitee.com/openeuler/kernel/pulls/15782 

飞腾：
mm/init: Add quirk for phytium ps23064 SoC
                https://gitee.com/openeuler/kernel/pulls/15365 

申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/15709 
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/15279 
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/15330 

海光：
Add device HID for Hygon GPIO controller
                https://gitee.com/openeuler/kernel/pulls/15217 
Fix northbridge init warning in guest for Hygon family 18h model 4h
                https://gitee.com/openeuler/kernel/pulls/15226 

灵达：
[OLK-5.10] Ethernet: Supports Linkdata ethernet Controllers
                https://gitee.com/openeuler/kernel/pulls/15220 

议题二：征集中，可直接填报到此处（备注汇报人

1、新增裕太微YT6801 以太网驱动，YT6801  committer申报（Frank.Sae@motor-comm.com）--（裕太微-孙华）
   https://gitee.com/openeuler/kernel/pulls/16346
会议结论：review后合入

  裕太微 phy 驱动模块committer申报 （Frank.Sae@motor-comm.com)
  文件路径：drivers/net/phy/motorcomm.c  该驱动的linux开源就是由Frank.Sae@motor-comm.com完成的。
会议结论：通过


2、将committer转给关文涛 -- （统信-苟浩）
https://gitee.com/openeuler/kernel/pulls/16207、16209、16210、16211

3、调度模块committer申报 （zhangqiao22@huawei.com 华为-张乔（替换华为-郑祖程））
①、多年欧拉内核开发经验，贡献过调度优先级混部等调度特性到欧拉社区，https://e.gitee.com/open_euler/repos/openeuler/kernel/pulls/1940
②、长期参与欧拉社区调度模块补丁检视工作.
https://gitee.com/zqiao216
会议结论：通过

4、新增吴腾达为kernel sig committer
 * 多年Linux开发经验，专长perf、trace等领域；
 * 相关工作已熟悉1个多月，已负责review 5.10补丁60+个；
 * 申请为5.10分支的branch-keeper。
 会议结论：通过

三、本期遗留问题



-------------------------------------------------------------------------------------------------------------------------------------
【2025/5/9 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：曾昭荣->桑力鹏->李楠->廖涛】
下次轮值主持：李楠
会议链接：https://meeting.huaweicloud.com:36443/#/j/964960259
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪


二、议题列表

议题一：进展update（李楠&吴腾达）
20250509
24.03-SP2的需求、特性、硬件支持需要在5.27之前合入完成
OLK-6.6进展同步
    tag更新到6.6.0-88.0.0
    ISO镜像和update rpm包获取链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1
    期间合入补丁数873个
    git log 6.6.0-84.0.0..6.6.0-88.0.0 --oneline --no-merges | wc -l

CVE（55）
        CVE-2025-21949        https://gitee.com/openeuler/kernel/pulls/15821 
        CVE-2025-21899        https://gitee.com/openeuler/kernel/pulls/15748 
        CVE-2025-21856        https://gitee.com/openeuler/kernel/pulls/15620 
        CVE-2025-21784        https://gitee.com/openeuler/kernel/pulls/15277 
        CVE-2025-21870        https://gitee.com/openeuler/kernel/pulls/15786 
        CVE-2025-21978        https://gitee.com/openeuler/kernel/pulls/15950 
        CVE-2025-21715        https://gitee.com/openeuler/kernel/pulls/15410 
        CVE-2025-21772        https://gitee.com/openeuler/kernel/pulls/15338 
        CVE-2025-21885        https://gitee.com/openeuler/kernel/pulls/15974 
        CVE-2024-57795        https://gitee.com/openeuler/kernel/pulls/15871 
        CVE-2025-21892        https://gitee.com/openeuler/kernel/pulls/15793 
        CVE-2025-37893        https://gitee.com/openeuler/kernel/pulls/15981 
        CVE-2024-57857        https://gitee.com/openeuler/kernel/pulls/15775 
        CVE-2025-22038        https://gitee.com/openeuler/kernel/pulls/15952 
        CVE-2025-21888        https://gitee.com/openeuler/kernel/pulls/15807 
        CVE-2023-53034        https://gitee.com/openeuler/kernel/pulls/15980 
        CVE-2025-21878        https://gitee.com/openeuler/kernel/pulls/15787 
        CVE-2025-21928        https://gitee.com/openeuler/kernel/pulls/15785 
        CVE-2025-21744        https://gitee.com/openeuler/kernel/pulls/15408 
        CVE-2025-21883        https://gitee.com/openeuler/kernel/pulls/15813 
        CVE-2025-21873        https://gitee.com/openeuler/kernel/pulls/15762 
        CVE-2025-21927        https://gitee.com/openeuler/kernel/pulls/15826 
        CVE-2025-21816        https://gitee.com/openeuler/kernel/pulls/15488 
        CVE-2024-57999        https://gitee.com/openeuler/kernel/pulls/15396 
        CVE-2025-21832        https://gitee.com/openeuler/kernel/pulls/15641 
        CVE-2025-21910        https://gitee.com/openeuler/kernel/pulls/15788 
        CVE-2025-21887        https://gitee.com/openeuler/kernel/pulls/15672 
        CVE-2024-57952        https://gitee.com/openeuler/kernel/pulls/15613 
        CVE-2025-22008        https://gitee.com/openeuler/kernel/pulls/15845 
        CVE-2025-21993        https://gitee.com/openeuler/kernel/pulls/15960 
        CVE-2025-21739        https://gitee.com/openeuler/kernel/pulls/15680 
        CVE-2024-52560        https://gitee.com/openeuler/kernel/pulls/15724 
        CVE-2025-21846        https://gitee.com/openeuler/kernel/pulls/15622 
        CVE-2024-58079        https://gitee.com/openeuler/kernel/pulls/15515 
        CVE-2025-21844        https://gitee.com/openeuler/kernel/pulls/15581 
        CVE-2025-38240        https://gitee.com/openeuler/kernel/pulls/15961 
        CVE-2025-21914        https://gitee.com/openeuler/kernel/pulls/15789 
        CVE-2025-22013        https://gitee.com/openeuler/kernel/pulls/15852 
        CVE-2025-21881        https://gitee.com/openeuler/kernel/pulls/15743 
        CVE-2025-21994        https://gitee.com/openeuler/kernel/pulls/15799 
        CVE-2025-21722        https://gitee.com/openeuler/kernel/pulls/15645 
        CVE-2025-21964        https://gitee.com/openeuler/kernel/pulls/15749 
        CVE-2025-21734        https://gitee.com/openeuler/kernel/pulls/15621 
        CVE-2025-21943        https://gitee.com/openeuler/kernel/pulls/15768 
        CVE-2025-21946        https://gitee.com/openeuler/kernel/pulls/15798 
        CVE-2025-21935        https://gitee.com/openeuler/kernel/pulls/15812 
        CVE-2025-21889        https://gitee.com/openeuler/kernel/pulls/15704 
        CVE-2025-21738        https://gitee.com/openeuler/kernel/pulls/15644 
        CVE-2025-21948        https://gitee.com/openeuler/kernel/pulls/15935 
        CVE-2025-21709        https://gitee.com/openeuler/kernel/pulls/15681 
        CVE-2025-22049        https://gitee.com/openeuler/kernel/pulls/15916 
        CVE-2025-21863        https://gitee.com/openeuler/kernel/pulls/15593 
        CVE-2025-21976        https://gitee.com/openeuler/kernel/pulls/15790 
        CVE-2025-23136        https://gitee.com/openeuler/kernel/pulls/15979 
        CVE-2025-21941        https://gitee.com/openeuler/kernel/pulls/15795 

Bugfix（27）
perf/x86: Fix open counting event error
                https://gitee.com/openeuler/kernel/pulls/15975 
v3  Backport mainline patches to avoid crash caused by rsize being 0
                https://gitee.com/openeuler/kernel/pulls/15968 
proc: fix UAF in proc_get_inode()
                https://gitee.com/openeuler/kernel/pulls/15800 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.80-6.6.81 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15783 
block: fix resource leak in blk_register_queue() error path
                https://gitee.com/openeuler/kernel/pulls/15913 
tracing: Fix use-after-free in print_graph_function_flags during tracer switching
                https://gitee.com/openeuler/kernel/pulls/15705 
ext4: Some zeroing fixes
                https://gitee.com/openeuler/kernel/pulls/15839 
fs/dcache: fix bad unlock balance in shrink_dentry_list()
                https://gitee.com/openeuler/kernel/pulls/15697 
Fix kmemleak false positive
                https://gitee.com/openeuler/kernel/pulls/15757 
ftrace: Avoid potential division by zero in function_stat_show()
                https://gitee.com/openeuler/kernel/pulls/15739 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.79-6.6.80 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15729 
mm/vmscan: drop checking if _deferred_list is empty before using TTU_SYNC
                https://gitee.com/openeuler/kernel/pulls/15924 
Some mainline patches merged into drivers/hwmon
                https://gitee.com/openeuler/kernel/pulls/15731 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.76-6.6.78 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15686 
ASoC: imx-card: Add NULL check in imx_card_probe()
                https://gitee.com/openeuler/kernel/pulls/15936 
x86/dumpstack: Fix inaccurate unwinding from exception stacks due to misplaced assignment
                https://gitee.com/openeuler/kernel/pulls/15755 
cpufreq: governor: Fix negative 'idle_time' handling in dbs_update()
                https://gitee.com/openeuler/kernel/pulls/15958 
perf/core: Fix pmus_lock vs. pmus_srcu ordering
                https://gitee.com/openeuler/kernel/pulls/15750 
printk: Fix signed integer overflow when defining LOG_BUF_LEN_MAX
                https://gitee.com/openeuler/kernel/pulls/15321 
mm: shmem: fix potential data corruption during shmem swapin
                https://gitee.com/openeuler/kernel/pulls/15922 
v2  PCI: AER: fix deadlock in do_recovery
                https://gitee.com/openeuler/kernel/pulls/15904 
bpf: Add tracepoints with null-able arguments
                https://gitee.com/openeuler/kernel/pulls/15771 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.78-6.6.79 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15706 
tracing/osnoise: Fix possible recursive locking for cpus_read_lock()
                https://gitee.com/openeuler/kernel/pulls/15772 
erofs/cachefiles: Change the unmark inuse sequence in erofs ondemand mode
                https://gitee.com/openeuler/kernel/pulls/15970 
Minimize xa_node allocation during xarry split
                https://gitee.com/openeuler/kernel/pulls/15611
Some trivial cleanups for shmem
                https://gitee.com/openeuler/kernel/pulls/15612 

feature
fs/resctrl: Fix configuration to wrong control group when CDP is enabled
                https://gitee.com/openeuler/kernel/pulls/15988 
arm_mpam: Add SMMU support for MPAM
                https://gitee.com/openeuler/kernel/pulls/15929 
Some mainline patches merged into olk-6.6: drivers/hwmon
                https://gitee.com/openeuler/kernel/pulls/15863 
v3  Support the FEAT_HDBSS introduced in Armv9.5
                https://gitee.com/openeuler/kernel/pulls/15754

灵达
[OLK-6.6] SCSI: Support Linkdata HBA/RAID Controllers
                https://gitee.com/openeuler/kernel/pulls/14287 

海思
PCI/DPC: Ignore Surprise Down error on hot removal
                https://gitee.com/openeuler/kernel/pulls/15650 
v2  soc cache: Add support for HiSilicon L3 cache
                https://gitee.com/openeuler/kernel/pulls/15910 
Some bug fix patches for RDMA/hns to olk-6.6
                https://gitee.com/openeuler/kernel/pulls/15711 
Kunpeng Accelerator Enables New Features
                https://gitee.com/openeuler/kernel/pulls/15636 
perf arm-spe: Add support for SPE Data Source packet on HiSilicon HIP12
                https://gitee.com/openeuler/kernel/pulls/15854 
Updates for HiSilicon L3C PMU driver
                https://gitee.com/openeuler/kernel/pulls/15882 
RDMA/hns :Add some mainline patches to OLK-6.6
                https://gitee.com/openeuler/kernel/pulls/15923 
General updates of HiSilicon PMU drivers
                https://gitee.com/openeuler/kernel/pulls/15838 
hisilicon: ACC Live Migration DFX Replacement Mainline Solution
                https://gitee.com/openeuler/kernel/pulls/15072 
[OLK-6.6] drm/hisilicon/hibmc: some bugfixes for hibmc-drm driver
                https://gitee.com/openeuler/kernel/pulls/15906 
Support SMT control on arm64.
                https://gitee.com/openeuler/kernel/pulls/15921 
v2  add support DVMBM in HIP12
                https://gitee.com/openeuler/kernel/pulls/15660 
【olk 6.6】backport some bugfixes for hibmcge driver
                https://gitee.com/openeuler/kernel/pulls/15872 
perf stat: Enable iostat mode for HiSilicon PCIe PMU
                https://gitee.com/openeuler/kernel/pulls/15827 
coresight: tmc: Don't change the buffer size if it's in use
                https://gitee.com/openeuler/kernel/pulls/15909 
migration: adapt to new migration configuration
                https://gitee.com/openeuler/kernel/pulls/15851 
uacce: fix for the numa distance calculation
                https://gitee.com/openeuler/kernel/pulls/15834 
crypto: hisilicon - some bugfix
                https://gitee.com/openeuler/kernel/pulls/15945 
compile error: implicit declaration of
                https://gitee.com/openeuler/kernel/pulls/16007 
Add HPD, getting EDID, colorbar features in DP function
                https://gitee.com/openeuler/kernel/pulls/15886 
v12  Add support for IPIv
                https://gitee.com/openeuler/kernel/pulls/15987

OLK-5.10进展同步：
        OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-262.0.0
        ISO镜像和update rpm包获取链接: 
            https://repo.openeuler.org/openEuler-22.03-LTS-SP3
            https://repo.openeuler.org/openEuler-22.03-LTS-SP4
       从 5.10.0-257.0.0 更新至 5.10.0-262.0.0, 回合补丁数242个
       git log 5.10.0-254.0.0..5.10.0-257.0.0 --oneline --no-merges | wc -l

CVE: (39)
CVE-2025-21863  https://gitee.com/openeuler/kernel/pulls/15595
CVE-2025-21763  https://gitee.com/openeuler/kernel/pulls/16127
CVE-2024-58055  https://gitee.com/openeuler/kernel/pulls/15701
CVE-2025-21887  https://gitee.com/openeuler/kernel/pulls/15671
CVE-2025-21943  https://gitee.com/openeuler/kernel/pulls/15769
CVE-2024-57980  https://gitee.com/openeuler/kernel/pulls/15717
CVE-2022-49246  https://gitee.com/openeuler/kernel/pulls/15378
CVE-2025-21764  https://gitee.com/openeuler/kernel/pulls/16063
CVE-2025-21761  https://gitee.com/openeuler/kernel/pulls/16128
CVE-2025-21877  https://gitee.com/openeuler/kernel/pulls/15791
CVE-2022-49553  https://gitee.com/openeuler/kernel/pulls/15630
CVE-2025-21935  https://gitee.com/openeuler/kernel/pulls/15811
CVE-2025-21881  https://gitee.com/openeuler/kernel/pulls/15760
CVE-2022-49443  https://gitee.com/openeuler/kernel/pulls/15679
CVE-2025-21762  https://gitee.com/openeuler/kernel/pulls/16129
CVE-2023-53010  https://gitee.com/openeuler/kernel/pulls/15892
CVE-2022-49513  https://gitee.com/openeuler/kernel/pulls/15716
CVE-2025-21858  https://gitee.com/openeuler/kernel/pulls/15837
CVE-2025-21718  https://gitee.com/openeuler/kernel/pulls/15690
CVE-2025-21823  https://gitee.com/openeuler/kernel/pulls/15728
CVE-2021-47660  https://gitee.com/openeuler/kernel/pulls/15627
CVE-2025-21816  https://gitee.com/openeuler/kernel/pulls/15510
CVE-2024-56642  https://gitee.com/openeuler/kernel/pulls/15765
CVE-2025-21804  https://gitee.com/openeuler/kernel/pulls/15480
CVE-2025-21727  https://gitee.com/openeuler/kernel/pulls/15683
CVE-2025-21760  https://gitee.com/openeuler/kernel/pulls/16125
CVE-2025-21791  https://gitee.com/openeuler/kernel/pulls/15449
CVE-2025-21928  https://gitee.com/openeuler/kernel/pulls/15841
CVE-2025-21727  https://gitee.com/openeuler/kernel/pulls/15682
CVE-2023-53001  https://gitee.com/openeuler/kernel/pulls/15773
CVE-2025-21993  https://gitee.com/openeuler/kernel/pulls/15959
CVE-2025-21780  https://gitee.com/openeuler/kernel/pulls/15956
CVE-2025-21722  https://gitee.com/openeuler/kernel/pulls/15646
CVE-2024-56664  https://gitee.com/openeuler/kernel/pulls/15766
CVE-2025-21715  https://gitee.com/openeuler/kernel/pulls/15409
CVE-2024-58094  https://gitee.com/openeuler/kernel/pulls/16088
CVE-2022-49328  https://gitee.com/openeuler/kernel/pulls/15828
CVE-2025-21785  https://gitee.com/openeuler/kernel/pulls/15675
CVE-2024-57951  https://gitee.com/openeuler/kernel/pulls/15802

Bugfix:
md/raid1: fix memory leak in raid1_run() if no active rdev
                https://gitee.com/openeuler/kernel/pulls/15939
block: fix bugs in blk_register_queue()
                https://gitee.com/openeuler/kernel/pulls/15840
Fix kmemleak false positive
                https://gitee.com/openeuler/kernel/pulls/15759
fs/dcache: fix bad unlock balance in shrink_dentry_list()
                https://gitee.com/openeuler/kernel/pulls/15696
md/raid1: fix bitmap update when all write requests fail
                https://gitee.com/openeuler/kernel/pulls/15940
md: bypass block throttle for superblock update
                https://gitee.com/openeuler/kernel/pulls/15938
mpage: fix softlockup in mpage_readahead()
                https://gitee.com/openeuler/kernel/pulls/16076
block: fix UAF in blk_mq_has_sqsched()
                https://gitee.com/openeuler/kernel/pulls/15941
powerpc: Fix save r13 on kprobe/ftrace entry
                https://gitee.com/openeuler/kernel/pulls/15756
Backport the perf fix patch
                https://gitee.com/openeuler/kernel/pulls/15990
x86/dumpstack: Fix inaccurate unwinding from exception stacks due to misplaced assignment
                https://gitee.com/openeuler/kernel/pulls/15753
ftrace: Avoid potential division by zero in function_stat_show()
                https://gitee.com/openeuler/kernel/pulls/15894
Push 2 self-developed patches to OLK-5.10
                https://gitee.com/openeuler/kernel/pulls/15699
v2  iommu/arm-smmu-v3: Fix the extra atc tlb flush
                https://gitee.com/openeuler/kernel/pulls/15883
mailbox: pcc: Always clear the platform ack interrupt first
                https://gitee.com/openeuler/kernel/pulls/16057
Revert "arm64: mm: add mc support for __buffer_migrate_page"
                https://gitee.com/openeuler/kernel/pulls/15794
                arm64: mm: add mc support for __buffer_migrate_page
                https://gitee.com/openeuler/kernel/pulls/15669
tracing: Fix use-after-free in print_graph_function_flags during tracer switching
                https://gitee.com/openeuler/kernel/pulls/15733

特性：
sched/fair: Optimize the dynamic smt
                https://gitee.com/openeuler/kernel/pulls/15676

海思：
soc: hisilicon: Serialize the online and onfline the acpi devices
                https://gitee.com/openeuler/kernel/pulls/15867
perf: Configure BRBE correctly on VHE host
                https://gitee.com/openeuler/kernel/pulls/15816
sdma-dae: modify ttl_processes reduce logic
                https://gitee.com/openeuler/kernel/pulls/15782
飞腾：
mm/init: Add quirk for phytium ps23064 SoC
                https://gitee.com/openeuler/kernel/pulls/15365
申威：
[OLK-5.10]:update patches for sw64 architecture
                https://gitee.com/openeuler/kernel/pulls/15330
AMD：
[OLK-5.10] new bugfix from mainline for Turin
                https://gitee.com/openeuler/kernel/pulls/15776
灵达：
[OLK-5.10] Ethernet: Supports Linkdata ethernet Controllers
                https://gitee.com/openeuler/kernel/pulls/15220
风河：
[OLK-5.10] backport important bugfix for nvme driver from the kernel-5.10.y
                https://gitee.com/openeuler/kernel/pulls/15888


议题二：kernel sig committer
新增吴腾达为kernel sig committer
1、多年Linux开发经验，专长perf、trace等领域；
2、已经负责review 5.10各类分支30+个；
3、申请为5.10分支的branch-keeper。
结论：先熟悉一段时间工作，下次kernel sig再申请

议题三：6.6分支的branch-keeper变更为李楠
结论：通过

议题四：openEuler 26年 LTS 内核选型 --- 汇报人： 谢秀奇
拟选择 6.6 内核继续支撑 openEuler LTS 版本。

结论：同意选择6.6版本，并在社区公示，公示完成后去TC正式决策。


议题五：OLK-6.6 PR review —— 韩里洋（海光）
https://gitee.com/openeuler/kernel/pulls/16019
https://gitee.com/openeuler/kernel/pulls/16020
https://gitee.com/openeuler/kernel/pulls/16024
https://gitee.com/openeuler/kernel/pulls/16025
https://gitee.com/openeuler/kernel/pulls/16026
结论：committer加分后合入

三、本期遗留问题

-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/4/18 Kernel SIG 双周例会】
轮值主持：仉鹏 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：桑力鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/987901819
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪


二、议题列表

议题一：进展update（李楠&仉鹏）


议题二：征集中，可直接填报到此处（备注汇报人）
1、CVE-2022-49647: 评审合入。 社区补丁修复影响KABI，由于4.19没有预留KABI，适配方案评审。影响：cgroup.type接口不能设置为threaded.   --（华为-陈日东）
https://gitee.com/openeuler/kernel/pulls/15810

议题三：cpufreq、cpuidle、thermal、devdreq、hwmon驱动committer申报--（华为-詹捷）
drivers/cpufreq
drivers/cpuidle
drivers/thermal
drivers/devdreq
drivers/hwmon
功耗驱动之前没有commiter，目前詹捷是cpufreq、cpuidle、thermal、devdreq、hwmon中的maintainer，现申请成为openEuler这些模块的committer，参与这些模块的review工作

议题四：
1、YT6801 以太网驱动committer申报--（裕太微-孙华）
https://gitee.com/openeuler/kernel/pulls/15824


三、本期遗留问题

-------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2025/3/28 Kernel SIG 双周例会】
轮值主持：曾昭荣 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：仉鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/964258324
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

当前会输出类似 kernel(__ipv6_addr_type) = 0x0d542439 kmod(ac.ko) 这样的 Provides，希望评估使用场景，是否有必要把这一特性backport到 24.03 LTS 分支中 -- 仉鹏、Funda Wang

二、议题列表

议题一：进展update（李楠&仉鹏）
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20250328：
OLK-6.6进展同步：

新分支已合入PR 32个，commit 543个
近两周(3.15-3.28)新合入特性PR：

特性(1):
VirtCCA Feature: cvm support UEFI boot
                https://gitee.com/openeuler/kernel/pulls/15333

处理器及板卡支持专项(5)：
龙芯(1):
LoongArch: fix cacheinfo/unaligned/rtc/s3/hda/usb issues
                https://gitee.com/openeuler/kernel/pulls/15271
海思(4)：
Add dp module in hibmc driver
                https://gitee.com/openeuler/kernel/pulls/15492
Mainline patch merged into OLK-6.6
                https://gitee.com/openeuler/kernel/pulls/15603
perf: Configure BRBE correctly on VHE host
                https://gitee.com/openeuler/kernel/pulls/15459
[olk 6.6] some features for hibmcge driver
                https://gitee.com/openeuler/kernel/pulls/15568

LTS补丁回合(2):
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.75-6.6.76 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15625
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.72-6.6.75 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15464

Bugfix(7):
mm: shmem: remove unnecessary warning in shmem_writepage()
                https://gitee.com/openeuler/kernel/pulls/15516
[OLK-6.6] [Backport] upstream fix for driver nvme
                https://gitee.com/openeuler/kernel/pulls/15421
perf/core: Order the PMU list to fix warning about unordered pmu_ctx_list
                https://gitee.com/openeuler/kernel/pulls/15608
cpufreq: Fix some boost errors related to CPU online and offline
                https://gitee.com/openeuler/kernel/pulls/15430
bnxt_en: Fix possible memory leak when hwrm_req_replace fails
                https://gitee.com/openeuler/kernel/pulls/15414
two bugfixs
                https://gitee.com/openeuler/kernel/pulls/15580
mm: Backport some mm patchs
                https://gitee.com/openeuler/kernel/pulls/15047

CVE(16):
CVE-2024-57997
                https://gitee.com/openeuler/kernel/pulls/15475
CVE-2024-58069
                https://gitee.com/openeuler/kernel/pulls/15483
CVE-2025-21738
                https://gitee.com/openeuler/kernel/pulls/15644
CVE-2025-21853
                https://gitee.com/openeuler/kernel/pulls/15597
CVE-2025-21804
                https://gitee.com/openeuler/kernel/pulls/15477
CVE-2025-21745
                https://gitee.com/openeuler/kernel/pulls/15357
CVE-2025-21803
                https://gitee.com/openeuler/kernel/pulls/15476
CVE-2024-57998
                https://gitee.com/openeuler/kernel/pulls/15474
CVE-2024-57834
                https://gitee.com/openeuler/kernel/pulls/15369
CVE-2025-21863
                https://gitee.com/openeuler/kernel/pulls/15593
CVE-2024-58006
                https://gitee.com/openeuler/kernel/pulls/15472
CVE-2024-58080
                https://gitee.com/openeuler/kernel/pulls/15395
CVE-2025-21750
                https://gitee.com/openeuler/kernel/pulls/15370
CVE-2025-21844
                https://gitee.com/openeuler/kernel/pulls/15581
CVE-2025-21776
                https://gitee.com/openeuler/kernel/pulls/15360
CVE-2025-21724
                https://gitee.com/openeuler/kernel/pulls/15473

        最新tag 6.6.0-84.0.0
        openEuler-24.03-LTS-SP1 ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1


OLK-5.10进展同步
近两周(2025.03.14 ~ 03.28)内进展同步:
    OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-257.0.0
        ISO镜像和update rpm包获取链接: 
            https://repo.openeuler.org/openEuler-22.03-LTS-SP3
            https://repo.openeuler.org/openEuler-22.03-LTS-SP4
    从 5.10.0-254.0.0 更新至 5.10.0-257.0.0, 回合补丁数16个
    git log 5.10.0-254.0.0..5.10.0-257.0.0 --oneline --no-merges | wc -l
 
CVE
        CVE-2022-49444        https://gitee.com/openeuler/kernel/pulls/15501 
        CVE-2022-49711        https://gitee.com/openeuler/kernel/pulls/15379 
 
Bugfix
Fix instance dir use-after-free in tracefs
                https://gitee.com/openeuler/kernel/pulls/15606 
[OLK-5.10] backport important bugfix from the kernel-5.10.y
                https://gitee.com/openeuler/kernel/pulls/14918 
[OLK-5.10] backport important bugfix from the kernel-5.10.y
                https://gitee.com/openeuler/kernel/pulls/14905 
 
Intel
[Intel-SIG] 5.10-x86/cpu: Clearwater Forest new model and ISAs support.
        https://gitee.com/openeuler/kernel/pulls/15272 
 
安恒
igc: add default intel igc driver module support
        https://gitee.com/openeuler/kernel/pulls/2893 
 
海思
drivers:misc:sdma-dae: sync code to openEuler
        https://gitee.com/openeuler/kernel/pulls/15643 
【olk 5.10】revert and backport a bugfix
        https://gitee.com/openeuler/kernel/pulls/15591 

议题二：征集中，可直接填报到此处（备注汇报人）


三、本期遗留问题

-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/3/14 Kernel SIG 双周例会】
轮值主持：廖涛 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：曾昭荣
会议链接：https://meeting.huaweicloud.com:36443/#/j/965671868
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪


二、议题列表

议题一：进展update（李楠&仉鹏）
OLK-5.10进展同步
近三周(2025.02.28 ~ 03.14)内进展同步:
    OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-254.0.0
        ISO镜像和update rpm包获取链接: 
            https://repo.openeuler.org/openEuler-22.03-LTS-SP3
            https://repo.openeuler.org/openEuler-22.03-LTS-SP4
    从 5.10.0-251.0.0 更新至 5.10.0-254.0.0, 回合补丁数219个
    git log 5.10.0-251.0.0..5.10.0-254.0.0 --oneline --no-merges | wc -l

CVE（12）
        CVE-2024-58009  https://gitee.com/openeuler/kernel/pulls/15397 
        CVE-2024-56606  https://gitee.com/openeuler/kernel/pulls/14810 
        CVE-2025-21756  https://gitee.com/openeuler/kernel/pulls/15413 
        CVE-2024-58001  https://gitee.com/openeuler/kernel/pulls/15422 
        CVE-2025-21719  https://gitee.com/openeuler/kernel/pulls/15403 
        CVE-2025-21779  https://gitee.com/openeuler/kernel/pulls/15373 
        CVE-2024-57947  https://gitee.com/openeuler/kernel/pulls/15295 
        CVE-2022-49096  https://gitee.com/openeuler/kernel/pulls/15307 
        CVE-2022-49651  https://gitee.com/openeuler/kernel/pulls/15382 
        CVE-2022-49564  https://gitee.com/openeuler/kernel/pulls/15387 
        CVE-2024-54680  https://gitee.com/openeuler/kernel/pulls/15232 
        CVE-2025-21735  https://gitee.com/openeuler/kernel/pulls/15419 
 
bugfix（10）
UBI/UBIFS mainline patch backport
        https://gitee.com/openeuler/kernel/pulls/15246 
orangefs: fix a oob in orangefs_debug_write
        https://gitee.com/openeuler/kernel/pulls/15389 
try to backport "block: fix rq-qos breakage from skipping rq_qos_done_bio"
        https://gitee.com/openeuler/kernel/pulls/15053 
ubi: fastmap: wl: Schedule fm_work if wear-leveling pool is empty
        https://gitee.com/openeuler/kernel/pulls/15428 
backport mainline bugfix patch
        https://gitee.com/openeuler/kernel/pulls/15391 
[OLK-5.10]Intel: Backport to fix EDAC driver for GNR platform
        https://gitee.com/openeuler/kernel/pulls/15269 
KVM: arm64: pvsched bugfix and module param
        https://gitee.com/openeuler/kernel/pulls/15241 
smb: client: Fix netns refcount imbalance
        https://gitee.com/openeuler/kernel/pulls/15232 
bpf bugfix mainline patch
        https://gitee.com/openeuler/kernel/pulls/15348 
mailbox: pcc: Fix the possible race in updation of chan_in_use flag
        https://gitee.com/openeuler/kernel/pulls/15429 

申威
[OLK-5.10]:update patches for sw64 architecture
        https://gitee.com/openeuler/kernel/pulls/15279 

海光
Fix northbridge init warning in guest for Hygon family 18h model 4h
        https://gitee.com/openeuler/kernel/pulls/15226 
EDAC/amd64: Add support family types for hygon family 4h~5h and 7h.
        https://gitee.com/openeuler/kernel/pulls/15228 
[OLK-5.10] perf/x86/uncore: Add support for Hygon family 18h model 4h-7h   and 10h DF PMU
        https://gitee.com/openeuler/kernel/pulls/10860 
Add device HID for Hygon GPIO controller
        https://gitee.com/openeuler/kernel/pulls/15217 

海思（7）
RDMA/hns: Fix mbox timing out by adding retry mechanism
        https://gitee.com/openeuler/kernel/pulls/15454 
net: hns3: some bugfixes for hns3 driver
        https://gitee.com/openeuler/kernel/pulls/15300 
Some bug fix patches for RDMA/hns to olk-5.10
        https://gitee.com/openeuler/kernel/pulls/15447 
Some bug fix patches for OLK-5.10 hns RoCE
        https://gitee.com/openeuler/kernel/pulls/15426 
soc: hisilicon: Fix one printing issue and simplify some printing
        https://gitee.com/openeuler/kernel/pulls/15456 
v2  soc: hisilicon: Add checks against NULL pointer reference
        https://gitee.com/openeuler/kernel/pulls/15460 
ras: ACPI: HED: Always initialize before evged
        https://gitee.com/openeuler/kernel/pulls/15293 
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20250314：
OLK-6.6进展同步：

新分支已合入PR 56个，commit 396个
近两周(2.27-3.14)新合入特性PR：

处理器及板卡支持专项(5)：
Intel(1):
[Intel-SIG] x86/cpu: Clearwater Forest support including CPU model and new ISAs
                https://gitee.com/openeuler/kernel/pulls/15417 
海光(4):
[OLK-6.6]Hygon: Rename Hygon SM{3,4} feature macro to X86_FEATURE_HYGON_SM{3,4}
                https://gitee.com/openeuler/kernel/pulls/15326 
fix HCT build err once VFIO disabled
                https://gitee.com/openeuler/kernel/pulls/15438 
Add device HID for Hygon GPIO controller
                https://gitee.com/openeuler/kernel/pulls/15147 
Fix northbridge init warning in guest for Hygon family 18h model 4h
                https://gitee.com/openeuler/kernel/pulls/15149 

LTS补丁回合(10):
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.69-6.6.70 LTS Additional Patches
                https://gitee.com/openeuler/kernel/pulls/15423 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.54-6.6.55 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/15227
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.60-6.6.61 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/15375 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.69-6.6.70 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15204 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.70-6.6.72 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15440 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.64-6.6.66 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/15248 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.62-6.6.63 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/15376 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.56-6.6.57 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/15292 
[openEuler-24.03-LTS][linux-6.6.y sync] KVM: x86: Play nice with protected guests in complete_hypercall_exit()
                https://gitee.com/openeuler/kernel/pulls/15164 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.57-6.6.58 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/15302 

Bugfix(11):
perf/core: Save raw sample data conditionally based on sample type
                https://gitee.com/openeuler/kernel/pulls/15334
orangefs: fix a oob in orangefs_debug_write
                https://gitee.com/openeuler/kernel/pulls/15385 
[OLK-6.6] [Backport] scsi: lpfc: Update phba link state conditional before sending CMF_SYNC_WQE
                https://gitee.com/openeuler/kernel/pulls/14975 
cifs: Prevent NULL pointer dereference caused by cifs_sb->rsize is 0
                https://gitee.com/openeuler/kernel/pulls/15225 
libbpf: Fix segfault due to libelf functions not setting errno
                https://gitee.com/openeuler/kernel/pulls/15367 
backport mainline bugfix patch
                https://gitee.com/openeuler/kernel/pulls/15390 
v2  mm: Backport two patch
                https://gitee.com/openeuler/kernel/pulls/15270
some readahead improvement
                https://gitee.com/openeuler/kernel/pulls/15470 
NFS: remove unused variable nfs_rpcstat
                https://gitee.com/openeuler/kernel/pulls/15229 
Mainline Patch
                https://gitee.com/openeuler/kernel/pulls/15347 
smb: client: Fix netns refcount imbalance causing leaks and use-after-free
                https://gitee.com/openeuler/kernel/pulls/15221 
CVE(20):
CVE-2025-21767
                https://gitee.com/openeuler/kernel/pulls/15331 
CVE-2024-58001
                https://gitee.com/openeuler/kernel/pulls/15418 
CVE-2025-21719
                https://gitee.com/openeuler/kernel/pulls/15404 
CVE-2025-21736
                https://gitee.com/openeuler/kernel/pulls/15402 
CVE-2025-21795
                https://gitee.com/openeuler/kernel/pulls/15265 
CVE-2024-54456
                https://gitee.com/openeuler/kernel/pulls/15263 
CVE-2025-21743
                https://gitee.com/openeuler/kernel/pulls/15298 
CVE-2024-57981
                https://gitee.com/openeuler/kernel/pulls/15309 
CVE-2025-21814
                https://gitee.com/openeuler/kernel/pulls/15299 
CVE-2025-21783
                https://gitee.com/openeuler/kernel/pulls/15363 
CVE-2024-58070
                https://gitee.com/openeuler/kernel/pulls/15424 
CVE-2025-21817
                https://gitee.com/openeuler/kernel/pulls/15346 
CVE-2025-21733
                https://gitee.com/openeuler/kernel/pulls/15278 
CVE-2025-21732
                https://gitee.com/openeuler/kernel/pulls/15308 
CVE-2025-21789
                https://gitee.com/openeuler/kernel/pulls/15364 
CVE-2025-21729
                https://gitee.com/openeuler/kernel/pulls/15283 
CVE-2025-21796
                https://gitee.com/openeuler/kernel/pulls/15266 
CVE-2025-21776
                https://gitee.com/openeuler/kernel/pulls/15345 
CVE-2025-21767
                https://gitee.com/openeuler/kernel/pulls/15331 
CVE-2024-57899
                https://gitee.com/openeuler/kernel/pulls/15043 

        最新tag 6.6.0-82.0.0
        openEuler-24.03-LTS-SP1 ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS-SP1



议题二：议题征集中，可在此填报（请备注汇报人）
1. 情况通报：openEuler-rpm-config 现已新增 kabi 和 kmod 的依赖关系生成器，将 kabi 和 kmod 的 provides 在rpm包层级暴露出来，方便下游包使用。 -- Funda Wang
见：
https://eulermaker.compass-ci.openeuler.openatom.cn/package/downloadDetail?osProject=openEuler-master:everything&packageName=kernel&jobId=cbs.8277343&rpmName=kernel-6.6.0-35.0.0.43.oe2503.x86_64.rpm
当前会输出类似 kernel(__ipv6_addr_type) = 0x0d542439 kmod(ac.ko) 这样的 Provides，希望评估使用场景，是否有必要把这一特性backport到 24.03 LTS 分支中

结论：遗留（仉鹏），下次例会跟踪

2. sched_ext的进展如何？
pr：https://gitee.com/openeuler/kernel/pulls/15063
这个会合入2403-sp1吗？

结论：门禁需要先通过，同步review

议题三：crypto、vfio、misc下部分驱动committer申报 -- (华为-刘龙芳)
drivers/crypto/hisilicon
drivers/vfio/pci/hisilicon
drivers/misc/uacce
之前这部分由沈旸审核，当前沈旸不投KAE，增加一个committer审核patch。当前刘龙芳是drivers/vfio/pci/hisilicon和drivers/crypto/hisilicon 中hpre与sec的maintainer，现申请成为openEuler这些模块的committer，参与这些模块patch的review工作。

结论：同意

三、本期遗留问题

当前会输出类似 kernel(__ipv6_addr_type) = 0x0d542439 kmod(ac.ko) 这样的 Provides，希望评估使用场景，是否有必要把这一特性backport到 24.03 LTS 分支中 -- 仉鹏、Funda Wang

-------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2025/2/28 Kernel SIG 双周例会】
轮值主持：李楠 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：廖涛
会议链接：https://meeting.huaweicloud.com:36443/#/j/962501137
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（李楠&仉鹏）
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20250227：
OLK-6.6进展同步：

新分支已合入PR 55个，commit 684个
近两周(2.15-2.27)新合入特性PR：

特性(1):
Cgroup限额触发CPU调度抑制(1)
The QoS feature adapts to the cfs bandwidth throttling
                https://gitee.com/openeuler/kernel/pulls/15170 

处理器及板卡支持专项(11)：
海光(4):
Upgrade Hygon HCT driver to version 0.6
                https://gitee.com/openeuler/kernel/pulls/15133 
[OLK-6.6]Hygon: Support CSV3 Attestation
                https://gitee.com/openeuler/kernel/pulls/14819 
[OLK-6.6]Hygon: Support kernel boot verification and secret injection for Hygon CSV3 VM
                https://gitee.com/openeuler/kernel/pulls/14820 
Fix  the performance monitor  relates to core for Hygon family 18h processor
                https://gitee.com/openeuler/kernel/pulls/14939 
海思(3):
hwtracing: hisi_ptt: Initialize the filter sysfs attribute when allocation
                https://gitee.com/openeuler/kernel/pulls/15185 
[olk 6.6] backport some feature patches for hibmcge driver
                https://gitee.com/openeuler/kernel/pulls/15076 
Revert "irqchip/gic-v3-its: Fix VSYNC referencing an unmapped VPE on GIC v4.0"
                https://gitee.com/openeuler/kernel/pulls/15161
澜起(1)：
[OLK-6.6]crypto: montage - fix variable 'device_handle' is uninitialized warning for Mont-TSSE driver
                https://gitee.com/openeuler/kernel/pulls/13446 
兆芯(3):
[OLK-6.6] crypto: zhaoxin - Optimize the assembly code in the SM3 driver
                https://gitee.com/openeuler/kernel/pulls/15078 
[OLK-6.6] crypto: zhaoxin - Fix incorrect parameter in sm4 driver
                https://gitee.com/openeuler/kernel/pulls/15080 
[OLK-6.6] update ITMT support patch for Zhaoxin CPUs
                https://gitee.com/openeuler/kernel/pulls/14179 

LTS补丁回合(4):
麒麟：
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.68-6.6.69 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15197 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.66-6.6.68 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15142 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.64-6.6.66 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15068 
统信：
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.53-6.6.54 LTS Conflicts Patches
                https://gitee.com/openeuler/kernel/pulls/15178 

Bugfix(7):
Intel: Backport upstream auto-tune per-CPU pageset size patchset
                https://gitee.com/openeuler/kernel/pulls/15251 
arm64/mpam: Try reading again if monitor instance returns not ready
                https://gitee.com/openeuler/kernel/pulls/15200 
v2  fs/resctrl: Adapt to the hardware topology structures of RDT and MPAM
                https://gitee.com/openeuler/kernel/pulls/15190 
binfmt_flat: Fix integer overflow bug on 32 bit systems
                https://gitee.com/openeuler/kernel/pulls/15184 
Backport tracing fix patch
                https://gitee.com/openeuler/kernel/pulls/15167 
mm, madvise: fix potential workingset node list_lru leaks
                https://gitee.com/openeuler/kernel/pulls/15123 
kobject: Fix global-out-of-bounds in kobject_action_type()
                https://gitee.com/openeuler/kernel/pulls/15181

CVE(31):
CVE-2024-46834
                https://gitee.com/openeuler/kernel/pulls/15103 
CVE-2024-57931
                https://gitee.com/openeuler/kernel/pulls/14972 
CVE-2024-57807
                https://gitee.com/openeuler/kernel/pulls/15192 
CVE-2025-21689
                https://gitee.com/openeuler/kernel/pulls/15214 
CVE-2025-21648
                https://gitee.com/openeuler/kernel/pulls/15106 
CVE-2024-39282
                https://gitee.com/openeuler/kernel/pulls/15111 
CVE-2024-57904
                https://gitee.com/openeuler/kernel/pulls/15118 
CVE-2024-53079
                https://gitee.com/openeuler/kernel/pulls/15159 
CVE-2025-21631
                https://gitee.com/openeuler/kernel/pulls/15175 
CVE-2025-21699
                https://gitee.com/openeuler/kernel/pulls/15191 
CVE-2025-21656
                https://gitee.com/openeuler/kernel/pulls/15144 
CVE-2024-57804
                https://gitee.com/openeuler/kernel/pulls/15143 
CVE-2024-56607
                https://gitee.com/openeuler/kernel/pulls/15132 
CVE-2024-56647
                https://gitee.com/openeuler/kernel/pulls/15109 
CVE-2024-57930
                https://gitee.com/openeuler/kernel/pulls/15166 
CVE-2024-57893
                https://gitee.com/openeuler/kernel/pulls/15128 
CVE-2024-50146
                https://gitee.com/openeuler/kernel/pulls/15101 
CVE-2024-56703
                https://gitee.com/openeuler/kernel/pulls/15105 
CVE-2024-54683
                https://gitee.com/openeuler/kernel/pulls/15107 
CVE-2024-57907
                https://gitee.com/openeuler/kernel/pulls/15140 
CVE-2024-53195
                https://gitee.com/openeuler/kernel/pulls/15121 
CVE-2025-21704
                https://gitee.com/openeuler/kernel/pulls/15203 
CVE-2024-57801
                https://gitee.com/openeuler/kernel/pulls/15110 
CVE-2024-57949
                https://gitee.com/openeuler/kernel/pulls/15067 
CVE-2024-53096
                https://gitee.com/openeuler/kernel/pulls/15119 
CVE-2025-21647
                https://gitee.com/openeuler/kernel/pulls/15113 
CVE-2025-21667
                https://gitee.com/openeuler/kernel/pulls/15055 
CVE-2024-57946
                https://gitee.com/openeuler/kernel/pulls/15176 
CVE-2024-56559
                https://gitee.com/openeuler/kernel/pulls/15083 
CVE-2025-21653
                https://gitee.com/openeuler/kernel/pulls/15112 
CVE-2024-56658
                https://gitee.com/openeuler/kernel/pulls/15102 

        最新tag 6.6.0-79.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS

OLK-5.10进展同步
近三周(2025.02.14 ~ 02.28)内进展同步:
    OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-251.0.0
        ISO镜像和update rpm包获取链接: 
            https://repo.openeuler.org/openEuler-22.03-LTS-SP3
            https://repo.openeuler.org/openEuler-22.03-LTS-SP4
    从 5.10.0-249.0.0 更新至 5.10.0-251.0.0, 回合补丁数38个
    git log 5.10.0-249.0.0..5.10.0-251.0.0 --oneline --no-merges | wc -l
 
CVE（24）
        CVE-2024-50268  https://gitee.com/openeuler/kernel/pulls/15081 
        CVE-2024-56754  https://gitee.com/openeuler/kernel/pulls/15136 
        CVE-2024-57900  https://gitee.com/openeuler/kernel/pulls/15100 
        CVE-2024-53156  https://gitee.com/openeuler/kernel/pulls/15095 
        CVE-2025-21662  https://gitee.com/openeuler/kernel/pulls/15137 
        CVE-2024-53096  https://gitee.com/openeuler/kernel/pulls/15124 
        CVE-2024-57857  https://gitee.com/openeuler/kernel/pulls/15198 
        CVE-2024-50150  https://gitee.com/openeuler/kernel/pulls/15134 
        CVE-2024-53057  https://gitee.com/openeuler/kernel/pulls/15089 
        CVE-2024-57795  https://gitee.com/openeuler/kernel/pulls/15186 
        CVE-2024-57792  https://gitee.com/openeuler/kernel/pulls/15199 
        CVE-2024-53148  https://gitee.com/openeuler/kernel/pulls/15129 
        CVE-2024-46782  https://gitee.com/openeuler/kernel/pulls/15085 
        CVE-2024-57912  https://gitee.com/openeuler/kernel/pulls/15196 
        CVE-2024-53141  https://gitee.com/openeuler/kernel/pulls/15087 
        CVE-2024-47697  https://gitee.com/openeuler/kernel/pulls/15079 
        CVE-2024-56601  https://gitee.com/openeuler/kernel/pulls/15096 
        CVE-2024-56600  https://gitee.com/openeuler/kernel/pulls/15097 
        CVE-2025-21647  https://gitee.com/openeuler/kernel/pulls/15099 
        CVE-2024-56658  https://gitee.com/openeuler/kernel/pulls/15117 
        CVE-2024-56650  https://gitee.com/openeuler/kernel/pulls/15094 
        CVE-2025-21667  https://gitee.com/openeuler/kernel/pulls/15127 
        CVE-2024-50125  https://gitee.com/openeuler/kernel/pulls/15086 
        CVE-2024-57908  https://gitee.com/openeuler/kernel/pulls/15177 
        CVE-2025-21648  https://gitee.com/openeuler/kernel/pulls/15098 
 
Bugfix
Revert "media: uvcvideo: Require entities to have a non-zero unique ID"
        https://gitee.com/openeuler/kernel/pulls/15146 
kasan: fix incorrect return type of quarantine_put()
        https://gitee.com/openeuler/kernel/pulls/15077 
apparmor: fix 'Do simple duplicate message elimination'
        https://gitee.com/openeuler/kernel/pulls/15139 
KVM:arm64:Add a kvm parameter to control guest wfi trapping
        https://gitee.com/openeuler/kernel/pulls/14910 
 
海光
[OLK-5.10] Enhanced Hygon processor's processing capabilities for large memory copying
        https://gitee.com/openeuler/kernel/pulls/14327 


议题二：申请合入申威架构更新补丁（申威——郜晨）
https://gitee.com/openeuler/kernel/pulls/15180
各领域committer review完成以后正常合入


议题三： 机密虚机支持uefi启动 -- 鲍鹏、张强


议题四：议题征集中，可直接在此填报。（注意备注报告人）

三、本期遗留问题


-------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------
【2025/2/14 Kernel SIG 双周例会】
轮值主持：桑力鹏 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：李楠
会议链接：https://meeting.huaweicloud.com:36443/#/j/960217398
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

遗留问题1：6.6内核支持CSV3虚拟机远程认证，CSV3启动度量扩展（用于Qemu的kernel启动hash验证，CSV3密钥封印等），CSV3虚拟机秘密注入（海光-韩里洋）
https://gitee.com/openeuler/kernel/pulls/14819 (4)
https://gitee.com/openeuler/kernel/pulls/14820 (8)
待收集intel、AMD以及虚拟化领域committer意见

二、议题列表

议题一：进展update（李楠&仉鹏）
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
OLK-5.10进展同步
近三周(2025.01.17 ~ 02.14)内进展同步:
    OLK-5.10（22.03-LTS-SP3、SP4）更新到tag 5.10.0-249.0.0
        ISO镜像和update rpm包获取链接: 
            https://repo.openeuler.org/openEuler-22.03-LTS-SP3
            https://repo.openeuler.org/openEuler-22.03-LTS-SP4
    从 5.10.0-246.0.0 更新至 5.10.0-249.0.0, 回合补丁数89个
    git log 5.10.0-246.0.0..5.10.0-249.0.0 --oneline --no-merges | wc -l
 
CVE（22）
        CVE-2024-56626  https://gitee.com/openeuler/kernel/pulls/14829
        CVE-2024-57892  https://gitee.com/openeuler/kernel/pulls/14943
        CVE-2024-56648  https://gitee.com/openeuler/kernel/pulls/14803
        CVE-2024-56758  https://gitee.com/openeuler/kernel/pulls/14854
        CVE-2024-26594  https://gitee.com/openeuler/kernel/pulls/14937
        CVE-2024-57850  https://gitee.com/openeuler/kernel/pulls/14875
        CVE-2024-53222  https://gitee.com/openeuler/kernel/pulls/14954
        CVE-2024-56728  https://gitee.com/openeuler/kernel/pulls/14852
        CVE-2024-56780  https://gitee.com/openeuler/kernel/pulls/14870
        CVE-2024-56777  https://gitee.com/openeuler/kernel/pulls/14862
        CVE-2024-53050  https://gitee.com/openeuler/kernel/pulls/14853
        CVE-2024-57896  https://gitee.com/openeuler/kernel/pulls/14894
        CVE-2024-50051    https://gitee.com/openeuler/kernel/pulls/15015 
        CVE-2024-57910    https://gitee.com/openeuler/kernel/pulls/15051 
        CVE-2024-49571    https://gitee.com/openeuler/kernel/pulls/15024 
        CVE-2024-47141    https://gitee.com/openeuler/kernel/pulls/15046 
        CVE-2024-53690    https://gitee.com/openeuler/kernel/pulls/15014 
        CVE-2024-57887    https://gitee.com/openeuler/kernel/pulls/15044 
        CVE-2024-53203    https://gitee.com/openeuler/kernel/pulls/14991 
        CVE-2024-57893    https://gitee.com/openeuler/kernel/pulls/15061 
        CVE-2024-57849    https://gitee.com/openeuler/kernel/pulls/14891 
        CVE-2024-49569    https://gitee.com/openeuler/kernel/pulls/15010 
 
Bugfix（8）
mm/compaction: fix UBSAN shift-out-of-bounds warning
        https://gitee.com/openeuler/kernel/pulls/14995
sched: psi: fix bogus pressure spikes from aggregation race
        https://gitee.com/openeuler/kernel/pulls/14857
mm/slub: Reduce memory consumption in extreme scenarios
        https://gitee.com/openeuler/kernel/pulls/14947
memcg: fix memcg_swapmax_read() not declared warning
        https://gitee.com/openeuler/kernel/pulls/14966
NFS: Fix up nfs_ctx_key_to_expire()
        https://gitee.com/openeuler/kernel/pulls/14866
nilfs2: fix null-ptr-deref in block_touch_buffer tracepoint
        https://gitee.com/openeuler/kernel/pulls/14851
fs/dirty_pages: Add exclusive open lock to prevent null pointer dereference
        https://gitee.com/openeuler/kernel/pulls/14865 
nbd: don't allow reconnect after disconnect
        https://gitee.com/openeuler/kernel/pulls/14956 
 
Feature:
xsk: Add generic xdp multi-buffer send support
        https://gitee.com/openeuler/kernel/pulls/14663
 
灵达
SCSI: Support Linkdata HBA/RAID Controllers
        https://gitee.com/openeuler/kernel/pulls/14286 
 
AMD
AMD QoS new features BMEC and SMBA
        https://gitee.com/openeuler/kernel/pulls/9883 
 
海思
Mainline patch to olk-5.10 v3
        https://gitee.com/openeuler/kernel/pulls/14948
mainline to olk-5.10 RDMA/hns: Check atomic wr length
        https://gitee.com/openeuler/kernel/pulls/14960
sdma-dae: add print in exceptional branch
        https://gitee.com/openeuler/kernel/pulls/14414
RDMA/hns: Fix free_mr_qp not assigning qp->device in error flow
        https://gitee.com/openeuler/kernel/pulls/15059 

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20250214：
OLK-6.6进展同步：

新分支已合入PR 150个，commit 866个
近两周(1.17-2.14)新合入特性PR：

特性(2):
mm: shmem: control THP support through the kernel command line
                https://gitee.com/openeuler/kernel/pulls/14767 
[OLK-6.6] rcu: Provide a boot time parameter to control lazy RCU
                https://gitee.com/openeuler/kernel/pulls/14321 

处理器及板卡支持专项(6)：
Intel(1)：
[OLK-6.6] Intel: Backport KVM Fix for Clearing SGX EDECCSSA to OLK-6.6
                https://gitee.com/openeuler/kernel/pulls/15052 

LeapIOraid(2):
LeapIOraid: Fix hiding ugood disk problem
                https://gitee.com/openeuler/kernel/pulls/14325 
LeapIOraid: update leapioraid driver version
                https://gitee.com/openeuler/kernel/pulls/14900 

海思(3):
RDMA/hns: Fix unmatch exception handling when request_irq() fails
                https://gitee.com/openeuler/kernel/pulls/14925 
RDMA/hns: Fix mbox timing out by adding retry mechanism
                https://gitee.com/openeuler/kernel/pulls/15060 
net: hns3: add sync command to sync io-pgtable
                https://gitee.com/openeuler/kernel/pulls/15048 

LTS补丁回合(2):
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.62-6.6.63 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/14873 
[openEuler-24.03-LTS][linux-6.6.y sync] Backport 6.6.63-6.6.64 LTS Patches
                https://gitee.com/openeuler/kernel/pulls/15056

Bugfix(16):
Mainline patch to olk-6.6
                https://gitee.com/openeuler/kernel/pulls/14951 
BMA: Fix Oops and spin lock deadlock problem, and change the version number.
                https://gitee.com/openeuler/kernel/pulls/14974 
tracing/kprobe: Make trace_kprobe's module callback called after jump_label update
                https://gitee.com/openeuler/kernel/pulls/14930 
mainline patches
                https://gitee.com/openeuler/kernel/pulls/14990 
mm/compaction: fix UBSAN shift-out-of-bounds warning
                https://gitee.com/openeuler/kernel/pulls/14994 
bpf: Fix theoretical prog_array UAF in __uprobe_perf_func()
                https://gitee.com/openeuler/kernel/pulls/14931 
memcg: fix memcg_swapmax_read() not declared warning
                https://gitee.com/openeuler/kernel/pulls/14962 
Revert "Revert "driver core: Fix uevent_show() vs driver detach race""
                https://gitee.com/openeuler/kernel/pulls/14898 
perf/x86/intel/ds: Unconditionally drain PEBS DS when changing PEBS_DATA_CFG
                https://gitee.com/openeuler/kernel/pulls/14897 
mm：some shmem bugfix
                https://gitee.com/openeuler/kernel/pulls/14823 
mm: khugepaged: fix call hpage_collapse_scan_file() for anonymous vma
                https://gitee.com/openeuler/kernel/pulls/14953 
bpf: Check size for BTF-based ctx access of pointer members
                https://gitee.com/openeuler/kernel/pulls/14874 
v2  fix BUG: unable to handle kernel paging request in build_id_parse
                https://gitee.com/openeuler/kernel/pulls/14964 
swiotlb: fix swiotlb_bounce() to do partial sync's correctly
                https://gitee.com/openeuler/kernel/pulls/14946
nbd: don't allow reconnect after disconnect
                https://gitee.com/openeuler/kernel/pulls/15031 
sched: qos sched support online task to preempt offline task
                https://gitee.com/openeuler/kernel/pulls/14877 

CVE(73):
CVE-2024-56677
                https://gitee.com/openeuler/kernel/pulls/14780 
CVE-2024-53209
                https://gitee.com/openeuler/kernel/pulls/14914 
CVE-2024-54193
                https://gitee.com/openeuler/kernel/pulls/14973 
CVE-2024-26954
                https://gitee.com/openeuler/kernel/pulls/14935 
CVE-2024-53051
                https://gitee.com/openeuler/kernel/pulls/14813 
CVE-2024-53203
                https://gitee.com/openeuler/kernel/pulls/14882 
CVE-2024-57888
                https://gitee.com/openeuler/kernel/pulls/14987 
CVE-2024-57849
                https://gitee.com/openeuler/kernel/pulls/14892 
CVE-2024-53223
                https://gitee.com/openeuler/kernel/pulls/14889 
CVE-2024-57850
                https://gitee.com/openeuler/kernel/pulls/14876 
CVE-2024-57809
                https://gitee.com/openeuler/kernel/pulls/14977 
CVE-2024-55639
                https://gitee.com/openeuler/kernel/pulls/14904 
CVE-2024-56701
                https://gitee.com/openeuler/kernel/pulls/14682 
CVE-2024-57922
                https://gitee.com/openeuler/kernel/pulls/14970 
CVE-2024-56590
                https://gitee.com/openeuler/kernel/pulls/14886 
CVE-2024-56640
                https://gitee.com/openeuler/kernel/pulls/14911 
CVE-2024-57892
                https://gitee.com/openeuler/kernel/pulls/14944 
CVE-2025-21632
                https://gitee.com/openeuler/kernel/pulls/14976 
CVE-2024-50304
                https://gitee.com/openeuler/kernel/pulls/14907 
CVE-2024-45828
                https://gitee.com/openeuler/kernel/pulls/15009 
CVE-2024-56698
                https://gitee.com/openeuler/kernel/pulls/14888 
CVE-2024-57926
                https://gitee.com/openeuler/kernel/pulls/14952 
CVE-2024-53187
                https://gitee.com/openeuler/kernel/pulls/14741 
CVE-2024-57896
                https://gitee.com/openeuler/kernel/pulls/14893 
CVE-2024-56641
                https://gitee.com/openeuler/kernel/pulls/14916 
CVE-2024-49568
                https://gitee.com/openeuler/kernel/pulls/14988 
CVE-2024-56718
                https://gitee.com/openeuler/kernel/pulls/14915 
CVE-2024-57910
                https://gitee.com/openeuler/kernel/pulls/14920 
CVE-2024-53145
                https://gitee.com/openeuler/kernel/pulls/14884 
CVE-2024-53124
                https://gitee.com/openeuler/kernel/pulls/14912 
CVE-2025-21670
                https://gitee.com/openeuler/kernel/pulls/14984 
CVE-2024-57917
                https://gitee.com/openeuler/kernel/pulls/14969 
CVE-2025-21658
                https://gitee.com/openeuler/kernel/pulls/14945 
CVE-2024-56729
                https://gitee.com/openeuler/kernel/pulls/14588 
CVE-2024-56567
                https://gitee.com/openeuler/kernel/pulls/14681 
CVE-2024-56786
                https://gitee.com/openeuler/kernel/pulls/14847 
CVE-2024-56779
                https://gitee.com/openeuler/kernel/pulls/14981 
CVE-2024-56787
                https://gitee.com/openeuler/kernel/pulls/14924 
CVE-2024-57906
                https://gitee.com/openeuler/kernel/pulls/14941 
CVE-2024-56758
                https://gitee.com/openeuler/kernel/pulls/14833 
CVE-2024-57889
                https://gitee.com/openeuler/kernel/pulls/14880 
CVE-2024-47794
                https://gitee.com/openeuler/kernel/pulls/14901 
CVE-2024-56777
                https://gitee.com/openeuler/kernel/pulls/14863 
CVE-2024-48873
                https://gitee.com/openeuler/kernel/pulls/14997 
CVE-2024-56769
                https://gitee.com/openeuler/kernel/pulls/14835 
CVE-2024-43098
                https://gitee.com/openeuler/kernel/pulls/14985 
CVE-2024-57916
                https://gitee.com/openeuler/kernel/pulls/15018 
CVE-2024-56614
                https://gitee.com/openeuler/kernel/pulls/14913 
CVE-2024-56715
                https://gitee.com/openeuler/kernel/pulls/14845 
CVE-2024-57872
                https://gitee.com/openeuler/kernel/pulls/14879 
CVE-2024-49998
                https://gitee.com/openeuler/kernel/pulls/14908 
CVE-2024-53690
                https://gitee.com/openeuler/kernel/pulls/15013 
CVE-2024-57874
                https://gitee.com/openeuler/kernel/pulls/14993 
CVE-2024-49569
                https://gitee.com/openeuler/kernel/pulls/15008
CVE-2024-57939
                https://gitee.com/openeuler/kernel/pulls/15002 
CVE-2024-50051
                https://gitee.com/openeuler/kernel/pulls/15016 
CVE-2024-57932
                https://gitee.com/openeuler/kernel/pulls/15041 
CVE-2024-57882
                https://gitee.com/openeuler/kernel/pulls/15039 
CVE-2025-21684
                https://gitee.com/openeuler/kernel/pulls/15062 
CVE-2024-57791
                https://gitee.com/openeuler/kernel/pulls/15036 
CVE-2024-57933
                https://gitee.com/openeuler/kernel/pulls/15040 
CVE-2025-21668
                https://gitee.com/openeuler/kernel/pulls/15065 
CVE-2024-47141
                https://gitee.com/openeuler/kernel/pulls/15027 
CVE-2025-21645
                https://gitee.com/openeuler/kernel/pulls/15019 
CVE-2024-52332
                https://gitee.com/openeuler/kernel/pulls/14979 
CVE-2024-57925
                https://gitee.com/openeuler/kernel/pulls/14989 
CVE-2024-56369
                https://gitee.com/openeuler/kernel/pulls/15020 
CVE-2024-57940
                https://gitee.com/openeuler/kernel/pulls/14963 
CVE-2024-57841
                https://gitee.com/openeuler/kernel/pulls/15038 
CVE-2024-47408
                https://gitee.com/openeuler/kernel/pulls/15037 
CVE-2024-49571
                https://gitee.com/openeuler/kernel/pulls/15025 
CVE-2024-57949
                https://gitee.com/openeuler/kernel/pulls/15067 
CVE-2025-21694
                https://gitee.com/openeuler/kernel/pulls/15069 

        最新tag 6.6.0-77.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS

议题二：海光CSV3安全评估报告（海光-韩里洋）


三、本期遗留问题


-------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2025/1/17 Kernel SIG 双周例会】
轮值主持：仉鹏 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：桑力鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/988444011
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

确认6.6的bpftool是否已删除构建
经确认暂未删除6.6 bpftool构建

二、议题列表

议题一：进展update（李楠&仉鹏）

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20250117：
OLK-6.6进展同步：

新分支已合入PR 122个，commit 274个
近两周(1.4-1.17)新合入特性PR：

处理器及板卡支持专项(5)：
海光(1):
[OLK-6.6][bugfix]Hygon: Remove 'CONFIG_' prefix under Kconfig entry HYGON_CSV
                https://gitee.com/openeuler/kernel/pulls/14840 
龙芯(3):
LoongArch: fix some dwmac/pci/SE/i2c/interrupt issues
                https://gitee.com/openeuler/kernel/pulls/14738 
LoongArch: Add CPU HWMon platform driver
                https://gitee.com/openeuler/kernel/pulls/14418 
LoongArch: compile loongson drm driver as module
                https://gitee.com/openeuler/kernel/pulls/14387 
增加华为智能网卡bifur驱动(1):
Add Huawei Intelligent Network Card Driver:hibifur
                https://gitee.com/openeuler/kernel/pulls/14761 

性能优化(2):
Improve the tmpfs large folio read performance
                https://gitee.com/openeuler/kernel/pulls/14690 
Backport fs optimizing patch from mainline
                https://gitee.com/openeuler/kernel/pulls/14035 

Bugfix(14):
ext4: correct behaviors under errors=remount-ro mode
                https://gitee.com/openeuler/kernel/pulls/14475 
sunrpc: fix one UAF issue caused by sunrpc kernel tcp socket
                https://gitee.com/openeuler/kernel/pulls/14243 
bpf: Fix narrow scalar spill onto 64-bit spilled scalar slots
                https://gitee.com/openeuler/kernel/pulls/14698 
sunrpc: clear XPRT_SOCK_UPD_TIMEOUT when reset transport
                https://gitee.com/openeuler/kernel/pulls/14244 
merge mainline patches into OLK-6.6
                https://gitee.com/openeuler/kernel/pulls/14611 
sched: Fix bpf cpustats refcount leak
                https://gitee.com/openeuler/kernel/pulls/14730 
sched: psi: fix bogus pressure spikes from aggregation race
                https://gitee.com/openeuler/kernel/pulls/14856 
[OLK-6.6]Workaround ARM PMUs cpu maps having offline cpus
                https://gitee.com/openeuler/kernel/pulls/14412 
cgroup/cpuset: remove kernfs active break
                https://gitee.com/openeuler/kernel/pulls/14828 
backport mainline bugfix patch
                https://gitee.com/openeuler/kernel/pulls/14634 
The bugfix for LPM trie
                https://gitee.com/openeuler/kernel/pulls/14524 
arm64: probes: Disable kprobes/uprobes on MOPS instructions
                https://gitee.com/openeuler/kernel/pulls/14694 
sched: fix warning in sched_setaffinity
                https://gitee.com/openeuler/kernel/pulls/14667 
etmem: fix use-after-free of mm in the scan release process
                https://gitee.com/openeuler/kernel/pulls/14724 
memcg: fix soft lockup in the OOM process
                https://gitee.com/openeuler/kernel/pulls/14648 
CVE(100):
CVE-2024-56548
                https://gitee.com/openeuler/kernel/pulls/14518 
CVE-2024-56583
                https://gitee.com/openeuler/kernel/pulls/14531 
CVE-2024-56597
                https://gitee.com/openeuler/kernel/pulls/14792 
CVE-2024-56653
                https://gitee.com/openeuler/kernel/pulls/14666 
CVE-2024-53155
                https://gitee.com/openeuler/kernel/pulls/14486 
CVE-2024-56692
                https://gitee.com/openeuler/kernel/pulls/14562 
CVE-2024-53207
                https://gitee.com/openeuler/kernel/pulls/14722 
CVE-2024-56660
                https://gitee.com/openeuler/kernel/pulls/14749 
CVE-2024-56726
                https://gitee.com/openeuler/kernel/pulls/14424 
CVE-2024-56624
                https://gitee.com/openeuler/kernel/pulls/14506 
CVE-2024-56605
                https://gitee.com/openeuler/kernel/pulls/14670 
CVE-2024-53208
                https://gitee.com/openeuler/kernel/pulls/14714 
CVE-2024-56720
                https://gitee.com/openeuler/kernel/pulls/14770 
CVE-2024-53231
                https://gitee.com/openeuler/kernel/pulls/14818 
CVE-2024-53171
                https://gitee.com/openeuler/kernel/pulls/14591 
CVE-2024-56763
                https://gitee.com/openeuler/kernel/pulls/14776 
CVE-2024-56705
                https://gitee.com/openeuler/kernel/pulls/14715 
CVE-2024-53219
                https://gitee.com/openeuler/kernel/pulls/14384 
CVE-2024-56622
                https://gitee.com/openeuler/kernel/pulls/14791 
CVE-2024-53173
                https://gitee.com/openeuler/kernel/pulls/14389 
CVE-2024-56585
                https://gitee.com/openeuler/kernel/pulls/14848 
CVE-2024-53194
                https://gitee.com/openeuler/kernel/pulls/14569 
CVE-2024-53157
                https://gitee.com/openeuler/kernel/pulls/14659 
CVE-2024-56672
                https://gitee.com/openeuler/kernel/pulls/14602 
CVE-2024-56663
                https://gitee.com/openeuler/kernel/pulls/14784 
CVE-2024-56719
                https://gitee.com/openeuler/kernel/pulls/14846 
CVE-2024-56745
                https://gitee.com/openeuler/kernel/pulls/14718 
CVE-2024-56687
                https://gitee.com/openeuler/kernel/pulls/14763 
CVE-2024-56557
                https://gitee.com/openeuler/kernel/pulls/14656 
CVE-2024-56578
                https://gitee.com/openeuler/kernel/pulls/14438 
CVE-2024-53165
                https://gitee.com/openeuler/kernel/pulls/14439 
CVE-2024-56759
                https://gitee.com/openeuler/kernel/pulls/14796 
CVE-2024-56633
                https://gitee.com/openeuler/kernel/pulls/14772 
CVE-2024-56620
                https://gitee.com/openeuler/kernel/pulls/14394 
CVE-2024-56543
                https://gitee.com/openeuler/kernel/pulls/14759 
CVE-2024-53241
                https://gitee.com/openeuler/kernel/pulls/14786 
CVE-2022-49034
                https://gitee.com/openeuler/kernel/pulls/14459 
CVE-2024-56582
                https://gitee.com/openeuler/kernel/pulls/14807 
CVE-2024-53201
                https://gitee.com/openeuler/kernel/pulls/14677 
CVE-2024-56665
                https://gitee.com/openeuler/kernel/pulls/14519 
CVE-2024-53237
                https://gitee.com/openeuler/kernel/pulls/14800 
CVE-2024-56681
                https://gitee.com/openeuler/kernel/pulls/14441 
CVE-2024-53196
                https://gitee.com/openeuler/kernel/pulls/14729 
CVE-2024-56631
                https://gitee.com/openeuler/kernel/pulls/14614 
CVE-2024-53191
                https://gitee.com/openeuler/kernel/pulls/14568 
CVE-2024-56623
                https://gitee.com/openeuler/kernel/pulls/14608 
CVE-2024-56586
                https://gitee.com/openeuler/kernel/pulls/14489 
CVE-2024-53221
                https://gitee.com/openeuler/kernel/pulls/14516 
CVE-2024-53190
                https://gitee.com/openeuler/kernel/pulls/14817 
CVE-2024-56575
                https://gitee.com/openeuler/kernel/pulls/14385 
CVE-2024-56584
                https://gitee.com/openeuler/kernel/pulls/14469 
CVE-2024-56638
                https://gitee.com/openeuler/kernel/pulls/14511 
CVE-2024-56649
                https://gitee.com/openeuler/kernel/pulls/14747 
CVE-2024-56596
                https://gitee.com/openeuler/kernel/pulls/14472 
CVE-2024-56619
                https://gitee.com/openeuler/kernel/pulls/14490 
CVE-2024-53227
                https://gitee.com/openeuler/kernel/pulls/14517 
CVE-2024-53213
                https://gitee.com/openeuler/kernel/pulls/14542 
CVE-2024-53050
                https://gitee.com/openeuler/kernel/pulls/14766 
CVE-2024-56572
                https://gitee.com/openeuler/kernel/pulls/14757 
CVE-2024-56744
                https://gitee.com/openeuler/kernel/pulls/14447 
CVE-2024-53160
                https://gitee.com/openeuler/kernel/pulls/14719 
CVE-2024-53229
                https://gitee.com/openeuler/kernel/pulls/14573 
CVE-2024-56702
                https://gitee.com/openeuler/kernel/pulls/14593 
CVE-2024-56538
                https://gitee.com/openeuler/kernel/pulls/14618 
CVE-2024-56662
                https://gitee.com/openeuler/kernel/pulls/14787 
CVE-2024-56776
                https://gitee.com/openeuler/kernel/pulls/14861 
CVE-2024-56691
                https://gitee.com/openeuler/kernel/pulls/14739 
CVE-2024-56683
                https://gitee.com/openeuler/kernel/pulls/14454 
CVE-2024-53170
                https://gitee.com/openeuler/kernel/pulls/14617 
CVE-2024-53215
                https://gitee.com/openeuler/kernel/pulls/14769 
CVE-2024-56609
                https://gitee.com/openeuler/kernel/pulls/14525 
CVE-2024-56728
                https://gitee.com/openeuler/kernel/pulls/14764 
CVE-2024-56654
                https://gitee.com/openeuler/kernel/pulls/14712 
CVE-2024-56595
                https://gitee.com/openeuler/kernel/pulls/14587 
CVE-2024-53218
                https://gitee.com/openeuler/kernel/pulls/14455 
CVE-2024-56747
                https://gitee.com/openeuler/kernel/pulls/14605 
CVE-2024-56594
                https://gitee.com/openeuler/kernel/pulls/14528 
CVE-2024-56627
                https://gitee.com/openeuler/kernel/pulls/14415 
CVE-2024-56739
                https://gitee.com/openeuler/kernel/pulls/14720 
CVE-2024-53180
                https://gitee.com/openeuler/kernel/pulls/14574 
CVE-2024-56562
                https://gitee.com/openeuler/kernel/pulls/14754 
CVE-2024-56693
                https://gitee.com/openeuler/kernel/pulls/14621 
CVE-2024-53518
                https://gitee.com/openeuler/kernel/pulls/14699 
CVE-2024-56679
                https://gitee.com/openeuler/kernel/pulls/14731 
CVE-2024-56613
                https://gitee.com/openeuler/kernel/pulls/14762 
CVE-2024-53128
                https://gitee.com/openeuler/kernel/pulls/14507 
CVE-2024-56570
                https://gitee.com/openeuler/kernel/pulls/14488 
CVE-2024-56700
                https://gitee.com/openeuler/kernel/pulls/14546 
CVE-2024-56604
                https://gitee.com/openeuler/kernel/pulls/14635 
CVE-2024-56742
                https://gitee.com/openeuler/kernel/pulls/14655 
CVE-2024-56741
                https://gitee.com/openeuler/kernel/pulls/14504 
CVE-2024-56756
                https://gitee.com/openeuler/kernel/pulls/14746 
CVE-2024-53239
                https://gitee.com/openeuler/kernel/pulls/14673 
CVE-2024-53131
                https://gitee.com/openeuler/kernel/pulls/14765 
CVE-2024-53224
                https://gitee.com/openeuler/kernel/pulls/14664 
CVE-2024-56667
                https://gitee.com/openeuler/kernel/pulls/14785 
CVE-2024-56626
                https://gitee.com/openeuler/kernel/pulls/14589 
CVE-2024-53234
                https://gitee.com/openeuler/kernel/pulls/14789 
CVE-2024-56592
                https://gitee.com/openeuler/kernel/pulls/14466 
CVE-2024-56546
                https://gitee.com/openeuler/kernel/pulls/14710 

        最新tag 6.6.0-74.0.0
        openEuler-24.03-LTS ISO镜像下载链接：https://repo.openeuler.org/openEuler-24.03-LTS


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
OLK-5.10进展同步
近两周(2025.01.03 ~ 01.17)内进展同步:
​        OLK-5.10主干更新到tag 5.10.0-246.0.0
​        openEuler-22.03-LTS-SP3、SP4分支，**更新到tag** 5.10.0-246.0.0
​                ISO镜像和update rpm包获取链接: 
​                        https://repo.openeuler.org/openEuler-22.03-LTS-SP3
​                        https://repo.openeuler.org/openEuler-22.03-LTS-SP4
​        openEuler-22.03-LTS-SP1分支，**更新到tag** 5.10.0-136.108.0，SP1已停维，此后不再更新代码、发布update版本
​                ISO镜像和update rpm包获取链接: 
​                        https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
​        从 5.10.0-244.0.0 更新至 5.10.0-246.0.0, 回合补丁数106个
​        git log 5.10.0-244.0.0..5.10.0-246.0.0 --oneline --no-merges  | wc -l
 
CVE（73）
        CVE-2024-56567    https://gitee.com/openeuler/kernel/pulls/14560 
        CVE-2024-53147    https://gitee.com/openeuler/kernel/pulls/14317 
        CVE-2024-56709    https://gitee.com/openeuler/kernel/pulls/14380 
        CVE-2024-53201    https://gitee.com/openeuler/kernel/pulls/14679 
        CVE-2022-49034    https://gitee.com/openeuler/kernel/pulls/14460 
        CVE-2024-56662    https://gitee.com/openeuler/kernel/pulls/14790 
        CVE-2024-50264    https://gitee.com/openeuler/kernel/pulls/14097 
        CVE-2024-56596    https://gitee.com/openeuler/kernel/pulls/14481 
        CVE-2024-56570    https://gitee.com/openeuler/kernel/pulls/14496 
        CVE-2024-56633    https://gitee.com/openeuler/kernel/pulls/14768 
        CVE-2024-53158    https://gitee.com/openeuler/kernel/pulls/14700 
        CVE-2024-53224    https://gitee.com/openeuler/kernel/pulls/14535 
        CVE-2024-56629    https://gitee.com/openeuler/kernel/pulls/14419 
        CVE-2024-53218    https://gitee.com/openeuler/kernel/pulls/14456 
        CVE-2024-56763    https://gitee.com/openeuler/kernel/pulls/14777 
        CVE-2024-56631    https://gitee.com/openeuler/kernel/pulls/14616 
        CVE-2024-50233    https://gitee.com/openeuler/kernel/pulls/14623 
        CVE-2024-53219    https://gitee.com/openeuler/kernel/pulls/14381 
        CVE-2024-56627    https://gitee.com/openeuler/kernel/pulls/14470 
        CVE-2024-56572    https://gitee.com/openeuler/kernel/pulls/14758 
        CVE-2024-56615    https://gitee.com/openeuler/kernel/pulls/14409 
        CVE-2024-53146    https://gitee.com/openeuler/kernel/pulls/14407 
        CVE-2024-53239    https://gitee.com/openeuler/kernel/pulls/14822 
        CVE-2024-56619    https://gitee.com/openeuler/kernel/pulls/14497 
        CVE-2024-50188    https://gitee.com/openeuler/kernel/pulls/14503 
        CVE-2024-56604    https://gitee.com/openeuler/kernel/pulls/14636 
        CVE-2024-56681    https://gitee.com/openeuler/kernel/pulls/14436 
        CVE-2024-53155    https://gitee.com/openeuler/kernel/pulls/14495 
        CVE-2024-53187    https://gitee.com/openeuler/kernel/pulls/14579 
        CVE-2024-56672    https://gitee.com/openeuler/kernel/pulls/14598 
        CVE-2024-56747    https://gitee.com/openeuler/kernel/pulls/14604 
        CVE-2024-56700    https://gitee.com/openeuler/kernel/pulls/14547 
        CVE-2022-48975    https://gitee.com/openeuler/kernel/pulls/14209 
        CVE-2024-56548    https://gitee.com/openeuler/kernel/pulls/14515 
        CVE-2024-56705    https://gitee.com/openeuler/kernel/pulls/14713 
        CVE-2024-56759    https://gitee.com/openeuler/kernel/pulls/14795 
        CVE-2024-53190    https://gitee.com/openeuler/kernel/pulls/14815 
        CVE-2024-53237    https://gitee.com/openeuler/kernel/pulls/14801 
        CVE-2024-56692    https://gitee.com/openeuler/kernel/pulls/14563 
        CVE-2024-53173    https://gitee.com/openeuler/kernel/pulls/14388 
        CVE-2024-56562    https://gitee.com/openeuler/kernel/pulls/14755 
        CVE-2024-56598    https://gitee.com/openeuler/kernel/pulls/14351 
        CVE-2024-56584    https://gitee.com/openeuler/kernel/pulls/14467 
        CVE-2024-56586    https://gitee.com/openeuler/kernel/pulls/14498 
        CVE-2024-56739    https://gitee.com/openeuler/kernel/pulls/14742 
        CVE-2024-56594    https://gitee.com/openeuler/kernel/pulls/14526 
        CVE-2024-53221    https://gitee.com/openeuler/kernel/pulls/14512 
        CVE-2024-56701    https://gitee.com/openeuler/kernel/pulls/14599 
        CVE-2024-56741    https://gitee.com/openeuler/kernel/pulls/14450 
        CVE-2024-56608    https://gitee.com/openeuler/kernel/pulls/14344 
        CVE-2024-56597    https://gitee.com/openeuler/kernel/pulls/14793 
        CVE-2024-56623    https://gitee.com/openeuler/kernel/pulls/14606 
        CVE-2024-56691    https://gitee.com/openeuler/kernel/pulls/14751 
        CVE-2024-56569    https://gitee.com/openeuler/kernel/pulls/14378 
        CVE-2024-53194    https://gitee.com/openeuler/kernel/pulls/14572 
        CVE-2024-56538    https://gitee.com/openeuler/kernel/pulls/14620 
        CVE-2024-56605    https://gitee.com/openeuler/kernel/pulls/14668 
        CVE-2024-53165    https://gitee.com/openeuler/kernel/pulls/14440 
        CVE-2024-56581    https://gitee.com/openeuler/kernel/pulls/14354 
        CVE-2024-53171    https://gitee.com/openeuler/kernel/pulls/14583 
        CVE-2024-53217    https://gitee.com/openeuler/kernel/pulls/14363 
        CVE-2024-53161    https://gitee.com/openeuler/kernel/pulls/14366 
        CVE-2024-47730    https://gitee.com/openeuler/kernel/pulls/14627 
        CVE-2024-56756    https://gitee.com/openeuler/kernel/pulls/14601 
        CVE-2024-56634    https://gitee.com/openeuler/kernel/pulls/14402 
        CVE-2024-53185    https://gitee.com/openeuler/kernel/pulls/14473 
        CVE-2024-53197    https://gitee.com/openeuler/kernel/pulls/14375 
        CVE-2024-56748    https://gitee.com/openeuler/kernel/pulls/14396 
        CVE-2024-56595    https://gitee.com/openeuler/kernel/pulls/14582 
        CVE-2024-49907    https://gitee.com/openeuler/kernel/pulls/14626 
        CVE-2024-50001    https://gitee.com/openeuler/kernel/pulls/14629 
        CVE-2024-56583    https://gitee.com/openeuler/kernel/pulls/14530 
        CVE-2024-53227    https://gitee.com/openeuler/kernel/pulls/14513 
 
Bugfix（11）
v2  fs: Filter specific inodes to prevent UAF issues    https://gitee.com/openeuler/kernel/pulls/14838 
merge mainline patch into OLK-5.10    https://gitee.com/openeuler/kernel/pulls/14844 
arm64: stacktrace: Handle 'lr' in interrupt context    https://gitee.com/openeuler/kernel/pulls/14392 
The bugfix for LPM trie    https://gitee.com/openeuler/kernel/pulls/14523 
Revert "unicode: Don't special case ignorable code points"    https://gitee.com/openeuler/kernel/pulls/14268 
cgroup: Fix potential overflow issue when checking max_depth    https://gitee.com/openeuler/kernel/pulls/14457 
backport mainline bugfix patch    https://gitee.com/openeuler/kernel/pulls/14651 
bpf: Fix narrow scalar spill onto 64-bit spilled scalar slots    https://gitee.com/openeuler/kernel/pulls/14704         
memcg: fix soft lockup in the OOM process    https://gitee.com/openeuler/kernel/pulls/14650 
Fix iBMA bug and change version    https://gitee.com/openeuler/kernel/pulls/14734 
etmem: fix use-after-free of mm in the scan release process    https://gitee.com/openeuler/kernel/pulls/14575 
     
AMD
update AMD Zen5 Turin feature    https://gitee.com/openeuler/kernel/pulls/14371 
 
海思
RDMA/hns backport some bugfix from maillist-v6.13 2025/01/03    https://gitee.com/openeuler/kernel/pulls/14539 
backport some patches from upstream about HCCS low power    https://gitee.com/openeuler/kernel/pulls/14397 


议题二：6.6内核支持CSV3虚拟机远程认证，CSV3启动度量扩展（用于Qemu的kernel启动hash验证，CSV3密钥封印等），CSV3虚拟机秘密注入（海光-韩里洋）
https://gitee.com/openeuler/kernel/pulls/14819 (4)
https://gitee.com/openeuler/kernel/pulls/14820 (8)
待收集intel、AMD以及虚拟化领域committer意见

议题三: OLK-6.6内核支持lazy-rcu开关 (统信-关文涛)
https://gitee.com/openeuler/kernel/pulls/14321 (2)
已合入

三、本期遗留问题


-------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------
【2025/1/3 Kernel SIG 双周例会】
轮值主持：曾昭荣 【轮值主持顺序：曾昭荣->仉鹏->桑力鹏->李楠->廖涛】
下次轮值主持：仉鹏
会议链接：https://meeting.huaweicloud.com:36443/#/j/966804758
会议纪要：https://etherpad.openeuler.org/p/Kernel-meetings

一、上期遗留问题跟踪

二、议题列表

议题一：进展update（李楠&仉鹏）

OLK-5.10进展同步
近两周(2024.12.20 ~ 1.03)内进展同步:
​        OLK-5.10主干更新到tag 5.10.0-244.0.0
​        openEuler-22.03-LTS-SP3、SP4分支，**更新到tag** 5.10.0-244.0.0
​                ISO镜像和update rpm包获取链接: 
​                        https://repo.openeuler.org/openEuler-22.03-LTS-SP3
​                        https://repo.openeuler.org/openEuler-22.03-LTS-SP4
​        openEuler-22.03-LTS-SP1分支，**更新到tag** 5.10.0-136.106.0，
​                ISO镜像和update rpm包获取链接: 
​                        https://repo.openeuler.org/openEuler-22.03-LTS-SP1
以OLK-5.10为例:
​        从 5.10.0-242.0.0 更新至 5.10.0-244.0.0, 回合补丁数169个
​        git log 5.10.0-242.0.0..5.10.0-244.0.0 --oneline --no-merges  | wc -l
 
CVE (5):
        CVE-2024-53150    https://gitee.com/openeuler/kernel/pulls/14333
        CVE-2024-56630    https://gitee.com/openeuler/kernel/pulls/14339
        CVE-2024-49856    https://gitee.com/openeuler/kernel/pulls/14314
        CVE-2024-50086    https://gitee.com/openeuler/kernel/pulls/13006
        CVE-2024-50287    https://gitee.com/openeuler/kernel/pulls/14315
 
Bugfix (11):
crypto: arm64/sm4 - simplify sm4_ce_expand_key() of CE implementation
        https://gitee.com/openeuler/kernel/pulls/14205
printk: Fix the qspinlock deadloop caused by zap_locks()
        https://gitee.com/openeuler/kernel/pulls/14309
Fix perf coredump and refcnt inccoret
        https://gitee.com/openeuler/kernel/pulls/14208
sunrpc: fix one UAF issue caused by sunrpc kernel tcp socket
        https://gitee.com/openeuler/kernel/pulls/14241
xfs: fix attr inactive issue
        https://gitee.com/openeuler/kernel/pulls/14235
mm: avoid unconditional one-tick sleep when swapcache_prepare fails
        https://gitee.com/openeuler/kernel/pulls/14331
iomap: fix zero padding data issue in concurrent append writes
        https://gitee.com/openeuler/kernel/pulls/14269
sunrpc: clear XPRT_SOCK_UPD_TIMEOUT when reset transport
        https://gitee.com/openeuler/kernel/pulls/14242
mm/khugepaged: fix ->anon_vma race
        https://gitee.com/openeuler/kernel/pulls/14330
etmem : fix page_ref count leak and head missing useing problem
        https://gitee.com/openeuler/kernel/pulls/14060
Fix the incorrect definition and use of IMA_FIX_OVERLAYFS_DETECTION
        https://gitee.com/openeuler/kernel/pulls/14293
 
Feature (1):
erofs: add ondemand mode support
        https://gitee.com/openeuler/kernel/pulls/14289
 
hisi (3)
soc: hisilicon: hbmdev: Only support built-in
        https://gitee.com/openeuler/kernel/pulls/14246
backport some bugfix of hisi_sas module from upstream
        https://gitee.com/openeuler/kernel/pulls/14252
RDMA/hns: Some patches are integrated into OLK-5.10
        https://gitee.com/openeuler/kernel/pulls/14305
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
20250103：
OLK-6.6进展同步：

新分支已合入PR 52个，commit 146个
近两周(12.20-1.3)新合入特性PR：

处理器及板卡支持专项(6)：
海光(2):
【OLK-6.6】 Hygon  family 18h model 6h~fh L3 PMU config incorrect issue fix
                https://gitee.com/openeuler/kernel/pulls/14259 
[OLK-6.6]Hygon: Fix objtool warning cause by csv3_active()
                https://gitee.com/openeuler/kernel/pulls/14373 
龙芯(1):
Fix extioi restart issue in vm
                https://gitee.com/openeuler/kernel/pulls/14229 
海思(3):
v2  scsi: hisi_sas: Enable force phy when SATA disk directly connected
                https://gitee.com/openeuler/kernel/pulls/14258 
RDMA/hns: Fix creating GSI QP in non-extended SGE QP bank
                https://gitee.com/openeuler/kernel/pulls/14256 
OLK-6.6: Some patches of RDMA/hns from Linux to olk-6.6 v2
                https://gitee.com/openeuler/kernel/pulls/14312 


特性(6):
v4  erofs/fscache/cachefiles: Add ondemand loading support
                https://gitee.com/openeuler/kernel/pulls/14206 
MPTCP Upstream part 24
                https://gitee.com/openeuler/kernel/pulls/14127 
v2  bpf: Add kabi reserve padding for uapi struct bpf_link_info
                https://gitee.com/openeuler/kernel/pulls/14213
kabi OLK-6.6 reverve space
                https://gitee.com/openeuler/kernel/pulls/14225
kabi reserver space for i2c
                https://gitee.com/openeuler/kernel/pulls/14251
【OLK-6.6】  drivers: arch_topology: Refactor do-while loops
                https://gitee.com/openeuler/kernel/pulls/14201 
                
Bugfix(8):
v2  scsi: hisi_sas: Enable force phy when SATA disk directly connected
                https://gitee.com/openeuler/kernel/pulls/14258
zram: fix NULL pointer in comp_algorithm_show()
                https://gitee.com/openeuler/kernel/pulls/14323 
Revert "unicode: Don't special case ignorable code points"
                https://gitee.com/openeuler/kernel/pulls/14301 
mm: avoid unconditional one-tick sleep when swapcache_prepare fails
                https://gitee.com/openeuler/kernel/pulls/14332 
[OLK-6.6] [Backport] individual submission
                https://gitee.com/openeuler/kernel/pulls/13359 
iomap: fix zero padding data issue in concurrent append writes
                https://gitee.com/openeuler/kernel/pulls/14271 
mm: Backport mainline patch
                https://gitee.com/openeuler/kernel/pulls/14336 
back some mainline patches for damon
                https://gitee.com/openeuler/kernel/pulls/14322

CVE(32):
CVE-2024-53146
                https://gitee.com/openeuler/kernel/pulls/14405 
CVE-2024-53197
                https://gitee.com/openeuler/kernel/pulls/14376 
CVE-2024-56608
                https://gitee.com/openeuler/kernel/pulls/14346 
CVE-2024-53161
                https://gitee.com/openeuler/kernel/pulls/14365 
CVE-2024-56708
                https://gitee.com/openeuler/kernel/pulls/14423 
CVE-2024-56581
                https://gitee.com/openeuler/kernel/pulls/14355 
CVE-2024-56634
                https://gitee.com/openeuler/kernel/pulls/14401 
CVE-2024-56615
                https://gitee.com/openeuler/kernel/pulls/14408 
CVE-2024-56629
                https://gitee.com/openeuler/kernel/pulls/14420 
CVE-2024-53163
                https://gitee.com/openeuler/kernel/pulls/14369 
CVE-2024-56598
                https://gitee.com/openeuler/kernel/pulls/14350 
CVE-2024-53202
                https://gitee.com/openeuler/kernel/pulls/14358 
CVE-2024-53134
                https://gitee.com/openeuler/kernel/pulls/14295 
CVE-2024-53159
                https://gitee.com/openeuler/kernel/pulls/14342 
CVE-2024-53150
                https://gitee.com/openeuler/kernel/pulls/14337 
CVE-2024-53186
                https://gitee.com/openeuler/kernel/pulls/14348 
CVE-2024-49906
                https://gitee.com/openeuler/kernel/pulls/14102 
CVE-2024-53217
                https://gitee.com/openeuler/kernel/pulls/14362 
CVE-2024-56752
                https://gitee.com/openeuler/kernel/pulls/14417 
CVE-2024-56709
                https://gitee.com/openeuler/kernel/pulls/14367 
CVE-2024-53151
                https://gitee.com/openeuler/kernel/pulls/14329 
CVE-2024-56630
                https://gitee.com/openeuler/kernel/pulls/14340 
CVE-2024-53126
                https://gitee.com/openeuler/kernel/pulls/14291 
CVE-2024-56675
                https://gitee.com/openeuler/kernel/pulls/14400 
CVE-2024-56748
                https://gitee.com/openeuler/kernel/pulls/14395 
CVE-2024-53154
                https://gitee.com/openeuler/kernel/pulls/14364 
CVE-2024-53114
                https://gitee.com/openeuler/kernel/pulls/14134 
CVE-2024-56569
                https://gitee.com/openeuler/kernel/pulls/14377 
CVE-2024-53147
                https://gitee.com/openeuler/kernel/pulls/14319 
CVE-2024-53136
                https://gitee.com/openeuler/kernel/pulls/14214 
CVE-2024-53230
                https://gitee.com/openeuler/kernel/pulls/14338 
CVE-2024-53127
                https://gitee.com/openeuler/kernel/pulls/14190 
议题二：申请新增NIC 1160网卡驱动（灵达-刘洁）

议题三：从内核切出bpftool和libtraceevent  —— 李楠
1）bpftool已在release-management会上评审通过且代码已切出，但kernel.spec中未删除相关代码，仍在编译bpftool包，需要删除kernel.spec中bpftool相关部分。
    https://gitee.com/src-openeuler/bpftool/issues/I8YGM4?from=project-issue
2）当前openeuler 22.03版本中，libtraceevent单独切出了一个仓：https://gitee.com/src-openeuler/libtraceevent。与linux上游社区相同：https://lore.kernel.org/lkml/20221130062935.2219247-5-irogers@google.com/。
      而kernel.spec中，仍然使用内核的libtraceevent且直接把它编译到perf中，导致perf和libtraceevent包无法同时使用。issue：https://gitee.com/src-openeuler/kernel/issues/I5JKG6。
      需要将perf修改为编译依赖libtraceevent包。
结论：通过，从kernel.spec中删除。

议题四：议题征集中，可直接在此填报（请备注申报人）

三、本期遗留问题
确认6.6的bpftool是否已删除构建

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
```