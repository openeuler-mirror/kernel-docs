Intel Advanced Matrix Extensions (AMX)及其虚拟化支持
Intel AMX是Intel下一代面向数据中心应用的机器学习推理和训练的内嵌AI加速引擎，是众多集成于Sapphire Rapids CPU中的加速硬件模块之一。它由一套可扩展的二维寄存器组，以及新的矩阵乘法模组和指令组成，可用于极大提升众多深度学习相关应用的性能。
![输入图片说明](https://foruda.gitee.com/images/1676530564094033084/019014fc_5605309.jpeg "amx.jpg")

Intel Software Guard Extensions (Intel SGX)及其虚拟化支持
Intel SGX 是Intel提供的一个基于硬件内存加密技术的安全计算解决方案，通过创建可信执行环境（trusted execution environment，TEEs），将相关的应用代码和数据隔离于内存中，从而达到保护的作用。Intel SGX允许用户代码分配私有的内存区域（称为enclaves），并利用硬件内存加密技术，以及硬件级别的访问控制机制，确保这些区域不会被更高权限的进程或应用来访问。
![输入图片说明](https://foruda.gitee.com/images/1676530681333180884/4f14e378_5605309.jpeg "SGX.jpg")

Intel Data Streaming Accelerator (Intel DSA)
Intel DSA是集成于下一代Intel Xeon处理器中的高性能数据拷贝和转换加速器，是Intel QuickData IO加速的下一代技术，用于优化高性能存储、网络、持久内存以及各种数据处理应用中流数据的移动和转换操作。它能在提高整体系统性能的同时，释放CPU的带宽给更高级别的功能。应用程序可以利用MOVDIR64B或者ENQCMD、ENQCMDS指令向专有工作队列（Dedicated Work Queue）或共享工作队列（Shared Work Queue）提交请求。DSA设备中的各个组件（配置寄存器、工作队列、仲裁器、数据处理引擎、地址翻译和缓存接口等）配合工作，以提供易失内存、持久内存、内存映射I/O，以及非透明桥，和远端节点的易失和持久内存之间的高性能数据移动和转换。
![输入图片说明](https://foruda.gitee.com/images/1676530773413195298/5f5b5465_5605309.jpeg "DSA.jpg")

Sapphire Rapids新指令以及虚拟化的支持
这部分回合包括对Sapphire Rapids平台新指令AVX_VNNI（VPDPBUS、VPDPBUSDS、VPDPWSSD、VPDPWSSDS等），AVX512_FP16的支持，以及相应虚拟化的支持，这些指令可以提高人工智能等应用的性能。

PMU Core and Uncore Support for Sapphire Rapids
增加 Sapphire Rapids平台Core PMU Events的支持，同时，增加了通用的uncore发现机制以及Sapphire Rapids平台Uncore PMU Events。通过这些Events的支持，可以更细致和准确地分析Sapphire Rapids平台的性能。

Intel Platform Monitoring Technology（PMT）支持
Intel Platform Monitoring Technology (PMT)是用以枚举和访问Intel平台硬件监控机制和能力的技术架构。PMT定义了一系列PCIE Designated Vendor extended capability (DVSEC)来支持从硬件收集监控数据。Intel PMT驱动的支持使得用户可以通过标准的intel_pmt sysfs数据以及“telem”二进制sysfs属性数据来访问设备有关性能数据的telemetry数据。

Intel_idle驱动支持与更新
Intel_idle驱动的更新增加了CPU C1, C1E c-state针对Sapphire Rapids平台的支持。同时更新了关于SnowRidge平台的 C state表支持， Icelake平台 C6 state的支持、Icelake-D平台的支持，以及Skylake平台C6 state等的支持。

IPI虚拟化支持
Inter-Processor Interrupts （IPIs）虚拟化是Sapphire Rapids平台新增加的vt-x特性。它基于现有的虚拟中断分发机制，使得VMX环境中虚拟CPU无需VMExit，而能够直接在虚拟机中处理Inter-Processor Interrupt，以提高相应中断的处理效率，从而提高虚拟机的整体性能。

系统总线锁检测和限流（Bus lock detection and ratelimit）
内存访问在某些情况下需要获取系统总线锁，想比较于cache line内部的原子操作，这通常需要多于1000个指令周期，同时也会影响其他CPU core的性能。一些CPU在用户的指令获取了系统总线锁的情况下，可以通过#DB trap来通知内核，这样内核可以对相关的应用进行限制。

Bus Lock VM Exit
Sapphire Rapids平台增加了一个新的VM-execution控制 “bus-lock detection”，设置该标志可以使得虚拟机中的应用获取了系统总线锁时会产生VM Exit，这样虚拟机控制器VMM可以针对性地对相关虚拟机进行限制。

Notify VM Exit
一些恶意的虚拟机在没有中断发生等情况下有可能长时间占用CPU，这样使得其他的虚拟机或应用无法获得CPU。在新的CPU平台上，虚拟机控制器VMM可以使能“Notify VM Exit”功能，这样，如果在一段特定的时间内，虚拟机没有发生VM Exit，将强制产生一个VM exit，以此实现更加公平的CPU使用。

Sapphire Rapids平台HBM EDAC支持和MCA故障恢复功能增强
操作系统内核支持下的MCA故障恢复能够获得uncorrected data并由EDAC驱动可以翻译出相应的内存错误地址，比如socket/MC/channel/dimm/bank/row/column etc. 这些数据非常有利于开发和运维。
本回合包括了一些MCA故障恢复功能的更新，以及EDAC针对Sapphire Rapids平台的 HBM(High Bandwidth Memory)的支持以及一些功能增强。

Intel的PCIe非透明桥的驱动支持
Intel PCIe Non-Transparent bridge(NTB)是用于点对点平台互联的PCIe桥设备。本回合增加了针对Sapphire Rapids平台的Intel PCIe Non-Transparent bridge(NTB)驱动支持，增加了针对gen4的Intel NTB LTR vendor支持。

Intel Hardware Feedback Interface的支持
Intel 硬件反馈接口（Hardware Feedback Interface， HFI）是通过位于内存中的硬件反馈接口为操作系统内核调度器提供优化的负载调度指导的机制。HFI为操作系统提供系统中每个CPU的性能和能耗效率数据，Linux内核可以利用这些数据来优化系统中进程的分布决策。

Intel_rapl驱动的Sapphire Rapids平台支持
在Sapphire Rapids平台上，Psys domain Power Limit Register的布局和以前的系统是不同的。本回合增加了针对Sapphire Rapids平台引入的新的Psys PowerLimit寄存器的布局的支持。
