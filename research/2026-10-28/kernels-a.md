# hudos 与 KrcyOS 的有限收录分类

核验日期：2026-10-28（UTC）。基线为 `4e00d5240ff5ca99c745c2b00179c11e42bef800`，110项语言、20项内核。贡献分支为 `contrib/kernel-backlog-a-20261028`。

本轮完整阅读 #49、#64 正文及当前全部8条评论，读取根 AGENTS.md、PR #79 的内核A组记录、总台账及两项候选JSON。工作树的 `.agents/skills` 目录不存在。旧研究与引用保持原样，本记录说明新增证据及对旧待核结论的收敛。

结果：KrcyOS新增当前主仓作者资料，明确所在地自述与项目的直接关联；hudos完成固件与自身资源管理连续源码分类。新增两项限定条目，建议资料PR合并后关闭 #64、#49。非必要历史、全部许可追溯与独立运行继续按条目字段待核。候选安装、构建、启动、测试与执行均为0。

## KrcyOS：作者主仓自述与跨平台身份

此前实质缺口是当前作者地域或中文开发社区的直接关联。2026-10-25已将GitHub缓存所见HeFei纠正为历史观察；英文主页支持作者—项目关系。

本轮在[作者主仓账号页](https://code.kercy666.com/Kercy)发现所在地资料后，直接读取[主仓公开API](https://code.kercy666.com/api/v1/users/Kercy)。HTTP 200，响应Date为 **Wed, 28 Oct 2026 08:11:03 GMT**，Cache-Control为 `max-age=0, private, must-revalidate`。公开字段为：

- `login=Kercy`、`username=Kercy`、`full_name=KercyDing`。
- `location=HeFei`、`website=https://kercy666.com`。
- 简介为 Talk less, code more.，可见性为public。

[主仓仓库API](https://code.kercy666.com/api/v1/repos/Kercy/krcyos)同样返回200，Date为08:11:53 GMT，确认 `full_name=Kercy/krcyos`，owner为上述Kercy／KercyDing账号，owner.location为HeFei。描述为Zig RISC-V实验内核，默认分支main。该仓库地址与已固定[GitHub README](https://github.com/KercyDing/krcyos/blob/0f0115ecc83610335642ee51e4f1f2c9d1886028/README.md#L1-L7)的主仓声明一致。

为避免平台混淆，本轮另读[GitHub公开API](https://api.github.com/users/KercyDing)，HTTP 200、Date为08:13:21 GMT，结果仍为 `location=null`，`blog=https://code.kercy666.com/Kercy`。两平台形成可直接检查的身份链：GitHub作者主页指向主仓账号；主仓账号以全名KercyDing拥有主仓；固定README声明主仓与镜像关系；[作者原站](https://kercy666.com/)自述维护KrcyOS。

收录依据采用**主仓所在地自述**，国籍待核实。中文用户名、域名、README和第三方聚合描述各自保留原证据层级。本轮搜索KercyDing／KrcyOS与LINUX DO、V2EX、知乎等组合，未取得可归属的中文开发社区原作；这些搜索结果不参与所在地结论。

技术资料沿用固定 [`0f0115ec`](https://github.com/KercyDing/krcyos/commit/0f0115ecc83610335642ee51e4f1f2c9d1886028)，提交时间2026-10-22T05:02:42Z。已有自身riscv64-freestanding入口、Sv39、陷阱与调度，以及OpenSBI v1.9分工足以支持学习型内核分类；本轮集中补齐身份与所在地来源。主仓逐提交同步、固件逐字节对应、实板覆盖和独立运行留在条目待核。

新增 `内核/krcyos.html` 与 `data/kernels.json` 的 `krcyos` 对象，22项来源。旧候选JSON作为历史记录保留。**最终建议：资料PR合并后关闭 #64，关闭仅确认作者关联、所在地自述及有限内核分类。**

建议评论草稿：

> 2026-10-28取得新的直接作者来源：KercyCode主仓公开API的Kercy账号自述full_name为KercyDing、location为HeFei，主仓Kercy/krcyos元数据确认同一所有者；本轮两个HTTP 200响应分别带08:11:03和08:11:53 GMT的Date及must-revalidate缓存标记。GitHub公开API同日仍为location=null，blog直接指向该主仓账号。主仓所在地自述、GitHub字段与此前历史缓存现已分平台记录，国籍继续待核实。结合固定0f0115ec已有RISC-V/Zig自身入口、Sv39／陷阱／调度及OpenSBI v1.9分工，本项按学习型内核完成正式收录。主仓逐提交同步、固件构建对应、全部历史与独立运行留在条目待核，本议题的合理收录分类工作已完成；候选软件安装、构建和执行均为0。

## hudos：连续程序管理路径

固定源码为 [`b4a244b8`](https://github.com/xuchenruisz/hudos/commit/b4a244b808b6786d5c3a1fd98102055f7f582488)，提交时间2026-10-06T23:21:49Z。作者与中文社区发布链、原片规范时间及分支映射沿用2026-10-25研究，本轮补齐具体执行与资源控制分工。

1. [efi_main](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L5537-L5622)保存固件系统表，进行EL0自检，查找ESP、初始化图形／输入，装载gui.elf或tdesktop.elf并进入shell。[Makefile](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/Makefile#L1-L28)生成ARM64 EFI_APPLICATION。
2. [elf_load](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L1268-L1379)检查ELF64／AArch64及PT_LOAD范围，计算映像页数并附加64页用户栈，调用UEFI AllocatePages取得存储，复制段并处理限定RELATIVE／ABS64重定位。布局和映像管理由项目负责，物理存储分配由固件提供。
3. [exec_co与exec_co_argv](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L4931-L5028)经项目文件接口读取ELF，保存子程序映像、栈、参数和协程状态，再调用el0_co_setup。当前为单组父子协程，后续新子程序先清理旧组。
4. [el0_co_setup](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L1875-L1956)保存固件TTBR0，取得EL0异常使用的栈，按默认关闭的g_el0_phaseb开关选择克隆页表或默认授权路径。[el0_grant_pages／ungrant](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L2349-L2424)遍历固件页表，按4KiB页面调整AP／UXN，必要时拆分块描述符并保存原值；撤销时恢复描述符、释放拆分页表并刷新TLB。该机制支持页权限管理；完整内存隔离效果待核实。
5. [hudos_el0_co_start](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/mmu_asm.S#L464-L500)保存父端上下文，切到子端内核栈，设置SP_EL0、ELR_EL1及SPSR_EL1，经ERET进入EL0。普通[EL0入口](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/mmu_asm.S#L426-L455)另有保存／退出上下文。
6. [自有向量和同步入口](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/mmu_asm.S#L216-L289)保存寄存器帧后调用项目C处理器。[hudos_el0_sync_handler](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L1968-L2077)保存ELR／SPSR、暂时恢复固件向量，按SVC号进入sys_dispatch或退出；分派完成后恢复子端异常状态和项目向量，再经ERET回到EL0。[syscall.c](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/syscall.c#L1-L32)与[crt0.S](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/crt0.S#L15-L38)提供SVC与EL1函数指针两种调用路径。
7. [read分派](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L4459-L4487)在终端输入为空时将协程置blocked并让出；[图形提交](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L4640-L4653)按开关触发主动让出。[el0_co_yield](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L1775-L1859)保存通用与特权上下文，恢复父端固件页表／向量并co_switch返回父端。
8. [co_resume](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L5029-L5101)由父应用主动推进，初次进入EL0、后续恢复完整上下文或返回保存的内核调用路径；exit将状态置done，完整上下文恢复分支返回后在g_el0_yield_pending条件下检查done并调用[co_child_cleanup](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L2695-L2710)撤销授权、释放映像／栈／参数并关闭文件表。该连续链体现项目自身程序和协程生命周期管理；首次进入与内核调用恢复分支的退出回收覆盖待核实。

## hudos：资源控制分工与分类

| 资源 | 项目自身实现 | 固件提供的基础 |
| --- | --- | --- |
| 程序与特权 | ELF段装载／重定位、EL0入口、SVC分派、退出与限定分支回收 | EFI映像环境、EL1服务调用窗口 |
| 内存 | 映像与栈布局、临时页权限、描述符恢复、可选克隆页表 | 物理页／缓冲区分配与默认地址空间 |
| 调度与中断 | 单父子协程、主动让出／恢复、自有同步异常向量 | 普通EL1服务窗口的异步中断基础；EL0窗口屏蔽IRQ／FIQ |
| 文件与通用设备 | 文件表、挂载表、控制台绘制、应用API | EFI文件／块设备协议、GOP、键盘和指针协议 |
| 网络与音频 | VirtIO-MMIO队列／轮询、网络协议、PCI HDA寄存器与DMA描述符 | 固件分配／等待及持续运行环境 |

设备部分具有明确分工：[GOP与输入](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L2720-L2783)通过UEFI协议取得；[VirtIO-MMIO](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L3157-L3258)自行设置队列和设备特性；[PCI HDA](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L4088-L4370)自行扫描配置空间、编程控制器与DMA，分配／等待调用固件。

分类判断依据项目已经实现的特权入口、同步异常、程序装载、权限与协程资源管理，将其收录为 **ARM64 UEFI承载实验内核与系统**。这是限定承载模型的分类判断。默认私有页表关闭、EL1回退、自有向量与固件向量窗口往返、普通异步中断基础及协作式调度均在条目显式保存。独立裸机资源接管、抢占式多任务与完整隔离的能力仍按各自状态待核。本轮依据连续资源路径作判断，单一ExitBootServices字段保持其实际含义。

根README许可、字体／游戏／证书等来源沿用已见范围；完整桌面构建输入、全部资源许可、发布镜像及录像的精确源码对应和运行正确性继续作为条目待核资料。新增 `内核/hudos.html` 与 `data/kernels.json` 的 `hudos` 对象，共51项来源。旧候选JSON保持历史快照。**最终建议：资料PR合并后关闭 #49，明确完成资源分工与有限分类。**

建议评论草稿：

> 2026-10-28完成固定b4a244b8的连续资源控制审阅，按“ARM64 UEFI承载实验内核与系统”收录。可读路径已串联efi_main／exec_co→ELF装载与栈布局→页权限授权→汇编设置EL0状态并ERET→自有SVC向量与分派→输入／图形处主动让出→co_resume恢复→完整上下文恢复分支的父端资源回收。物理页分配、文件／GOP／输入和普通异步中断基础持续使用固件；项目自身管理映像、特权同步异常、页权限及单父子协程，VirtIO-MMIO与PCI HDA另有直接寄存器路径。条目明确默认私有页表关闭、EL1回退、协作式调度和固件向量往返，独立裸机、抢占及完整隔离保持待核。中文原作者发布链沿用已有证据，国籍、完整桌面／许可、镜像对应和独立运行继续按字段保存。资源分工与合理收录分类已经完成，本轮候选安装、构建和执行均为0。

## 原始回执与验证

[证据附件](kernels-a-evidence.json)保存三项当前公开API的URL、HTTP Date、缓存字段、选定公开资料和原始响应SHA-256；另列本轮固定源码连续路径来源。原始回执时间明确标为HTTP响应Date。

本轮仅修改新增条目、内核数据／索引与本组新研究文件。现有20项对象、110项语言与全部旧研究引用保留。资料更新后的本工作树内核计数为22项，最终总数由父任务集成其他分组后重算。HanOS #46范围决定、PR #62取消合并及PR #76草稿边界保持原有状态。

验证包括JSON解析、旧对象比较、唯一ID、source_ids闭合、HTML锚点／引用和索引集合一致，以及diff空白检查。候选原仓源码只按文本读取；未运行其中脚本、二进制或构建入口。只读网络成功完成，没有denied、pending或uncertain动作。本组不执行push、PR、评论、关闭或合并，由父任务集成及独立审阅。
