# 内核积压处理：AntzOS、KrcyOS、CoreZ-OS、lgc-os 与 hudos

核验日期：2026-10-25（UTC）。基线 `3f59f9224b48998b4260b36792fad57ec130ca63`，原有11项内核。独立工作树为 `kernels-a`，贡献分支为 `contrib/kernel-backlog-a`。

本组完整阅读 Issue #68、#64、#49、#41、#38 的正文及全部14条评论；旧研究对应第12轮、第13轮与第16轮内核日志和结构化资料。仓库根 AGENTS.md 已读，本 checkout 的 `.agents/skills` 目录为空缺。该任务采用仓库资料工作流，涉及的源码全部静态阅读。

## 收录口径与本轮结果

收录检查为：自身内核入口和具体实现、可明确记录的作者／中文技术社区关联，以及已见上游组件范围。所在地按作者自述保存，国籍单独待核实。首发日期、完整历史、所有组件许可追溯、完整运行复现与AI参与继续作为条目待核字段。功能采用作者声明、源码可见、历史作者演示与独立运行四层记录。

本组新增三项正式资料：`antzos`、`corez-os`、`lgc-os`。KrcyOS在独立审阅后改为固定资料候选；最终总数由汇总分组重算。hudos 保留为 ARM64 UEFI 承载实验系统的待核资料，主要剩余问题是正式内核分类所需的资源控制边界。

修改文件：`data/kernels.json`、`内核/index.html`、三项对应 HTML，以及本研究日志和元数据附件。原有11个对象及原有条目正文保持原样。HanOS #46、PR #62、PR #76、豫言自身资料和其他官网均在本组范围外。

## #68 AntzOS

已有完成范围：原Issue与四条评论核实了原仓、博客系列、保护模式／图形入口、九项 H.Kawai／KL-01 头文件、IRQ0与输入、`Antz.version.2.0` 字符串及四项发行。此前将明确中国归属、精确上游与运行对应等全部列为待核。

本轮直接证据：原作者[第9篇文章](https://www.cnblogs.com/LexMoon/p/antz09.html)正文现已可读，页面署名 AntzUhl，直接给出 CasterWx/AntzOS；说明图形终端实现，保存连续 C 代码。原仓固定 README 反链该系列。[GitHub主页](https://github.com/CasterWx)所在地自述为 China。该链支持作者身份、中文技术社区发布和所在地关联；国籍继续待核实。

固定版本为 [`80b57405`](https://github.com/CasterWx/AntzOS/commit/80b574057fb65642d2575c22348775e7854cdce8)，提交时间2020-03-12T14:20:08Z。[asmhead.asm](https://github.com/CasterWx/AntzOS/blob/80b574057fb65642d2575c22348775e7854cdce8/boot/asmhead.asm#L91-L136)设置 GDT、CR0、堆栈并跳转内核；[HariMain](https://github.com/CasterWx/AntzOS/blob/80b574057fb65642d2575c22348775e7854cdce8/main/bootpack.c#L235-L304)初始化中断、PIT、键盘和图形主循环。[Makefile](https://github.com/CasterWx/AntzOS/blob/80b574057fb65642d2575c22348775e7854cdce8/Makefile#L6-L38)显示 Haribote 规则和 OSASK 相关工具链；[stdio.h](https://github.com/CasterWx/AntzOS/blob/80b574057fb65642d2575c22348775e7854cdce8/include/stdio.h#L1)直接保存 H.Kawai／KL-01 署名。条目据此定位为采用这些既有组件的个人学习内核。

结果：新增14项来源的结构化条目与 `内核/antzos.html`。调度保留为作者后续工作，UNIX-based 保留为作者目标，四项发行与源码版本字符串分别记录。精确上游版号、逐文件继承、完整许可与镜像运行对应进入条目待核范围。

关闭判断：完成资料PR合并后关闭。作者关联、自身实现及已见继承范围已满足合理收录标准；精确上游版号、完整历史、全部许可、AI和独立运行保留为条目待核字段，关闭说明只确认收录分类。

建议评论草稿：

> 2026-10-25 完成本项正式资料收录。原作者博客园第9篇现已取得正文，页面署名 AntzUhl 并直接指向 CasterWx/AntzOS，原仓 README 反链同一开发系列；GitHub 所在地自述 China 按所在地记录，国籍待核实。固定 `80b57405` 的 BIOS／保护模式、GDT／IDT、PIT、输入和图形命令路径支持个人学习内核定位；Haribote 规则、OSASK相关工具与 H.Kawai／KL-01 头文件的已见继承范围已明确列出。条目保存四项发行、源码版本字符串、调度路线图及许可边界。精确上游版本、完整分发许可、镜像／演示对应与独立运行继续在条目待核字段跟进。本轮候选安装、构建、启动与测试均为0。本议题的收录与分类工作已完成，未知字段继续按条目待核记录。

## #64 KrcyOS

本轮固定镜像0f0115ecc83610335642ee51e4f1f2c9d1886028（2026-10-22T05:02:42Z），自身RISC-V/Zig入口、Sv39、陷阱、调度与OpenSBI v1.9分工已核。完整源码调查与20项原始来源保存在[krcyos-pending.json](krcyos-pending.json)。主仓逐提交同步、固件构建对应与实板覆盖继续作为资料字段。

独立审阅发现来源时效差异：网页工具所见HeFei及原站反链来自标注约2个月前抓取的缓存。2026-10-25实时[公开API](https://api.github.com/users/KercyDing)的location为null，blog为code.kercy666.com/Kercy。作者原站首页当前为英文，声明维护KrcyOS并指向GitHub，足以支持作者和项目关系。当前明确中国作者或中文开发社区关联仍待补，国籍保持待核。

结果：本组正式收录保留AntzOS、CoreZ-OS、lgc-os三项，KrcyOS保存为固定资料候选。#64保持开放。原有镜像、自身实现和OpenSBI版本证据已完成，不重复追加非必要的独立运行或全部许可追溯作为阻塞。

建议评论草稿：

> 2026-10-25固定镜像0f0115ec及RISC-V/Zig自身内核、OpenSBI v1.9分工已补成结构化资料。独立审阅复核当前GitHub公开API后发现location为null；此前HeFei来自历史缓存，按原核验层级保留。作者英文原站声明维护本项目并链接原仓，项目与账号关系已核；明确中国作者或中文社区关联仍有实质缺口，当前保留候选和本议题。主仓同步、固件构建对应与独立运行按具体资料字段待核，本轮候选执行0次。

## #38 CoreZ-OS

已有完成范围：第12轮结构化记录29项来源、BIOS／UEFI独立入口、任务和用户程序、ext2／ext4、Win32／GDI及六项第三方gitlink；Issue两条评论另补SMP历史。00:26与01:01是既有研究实际观察的作者演示，本轮按历史观察复用。

新直接证据：[B站公开接口](https://api.bilibili.com/x/web-interface/view?bvid=BV1krYP6iEv5)返回 `owner.mid=3690980152707649`、`owner.name=Lightfl0w`，简介直接链接原仓，标题为中文。`pubdate=1790824626` 对应 **2026-10-01T03:17:06Z／2026-10-01 11:17:06 UTC+8**，时长68秒。这解决此前日期显示冲突，形成明确的原作者中文社区发布关联；国籍留待核实。

固定 main 仍为 [`8016bb2e`](https://github.com/lightfl0w/CoreZ-OS/commit/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e)，2026-10-02T09:01:56Z；[仓库元数据](https://api.github.com/repos/lightfl0w/CoreZ-OS)当前 `archived=true`。[UEFI入口](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/arch/x86/uefi/main.c#L775-L800)与[内核入口](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/kernel/init/main.c#L99-L155)已重新静态读取：固件交接后由内核初始化资源并启动用户shell。

结果：复用既有29项来源，补原平台接口为第30项来源，新增 `内核/corez-os.html`。归档状态、规范原片时刻、有限API兼容及SMP文档／实现阶段差异均已保存。六项子模块属于已见上游范围，整体原创与全部资源许可继续待核。

关闭判断：完成资料PR合并后关闭。原作者社区发布、自身内核、六项明确上游及有限兼容分类已充分记录；原片规范日期与归档状态本轮收敛。视频二进制对应、精确完整继承、AI和独立运行保留条目待核。

建议评论草稿：

> 2026-10-25 完成 CoreZ-OS 正式资料收录。原平台接口重新确认 Lightfl0w（UID3690980152707649）中文原片直接指向源码；pubdate `1790824626` 固定为2026-10-01T03:17:06Z（UTC+8 11:17:06），解决此前跨页面时间差异。main 仍为 `8016bb2e`，仓库当前已归档。条目区分独立内核路径、六项第三方子模块、限定PE／GDI接口与SMP阶段差异；00:26和01:01沿用既有研究的作者演示观察。国籍、视频二进制对应、完整继承与许可、独立运行继续待核实，候选构建和执行均为0。本议题的收录与分类工作已完成，未知字段继续按条目待核记录。

## #41 lgc-os

已有完成范围：第13轮保存45项来源、配套lgc关系、独立@boot、GDT／TSS、分页与中断、8任务槽、RAMFS／ELF64和限定Linux ABI；Issue两条评论另补编译器二进制与许可时间链。既有00:18与约00:34画面观察按作者演示沿用。

新直接证据：[原平台接口](https://api.bilibili.com/x/web-interface/view?bvid=BV166at6hEgN)返回同一 Lightfl0w UID，中文标题和简介直接给出 `lightfl0w/lgc-os`，`pubdate=1790492406` 对应 **2026-09-27T07:00:06Z／15:00:06 UTC+8**，时长45秒。原作者中文社区发布链由直接元数据再次确认。

固定 main 仍为 [`ba606a06`](https://github.com/lightfl0w/lgc-os/commit/ba606a063fd557bf28ad13a4c16f9e214b0deddd)，2026-09-27T09:55:16Z。[os.lg](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/os.lg)和[core.lg](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/core.lg)的特权初始化、[build.py](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/build.py)的外部编译工具依赖已重新核对。README明示参考《操作系统真相还原》；ATA、RAMFS与shell直接引入@boot内核，微内核作为作者定位保存，服务隔离／IPC边界待核。lgc使用英文词法，按配套工具保存。

结果：复用既有45来源，增加第46项原平台接口，新增 `内核/lgc-os.html`。OS自身许可缺口、配套编译器GPL声明、BusyBox／glibc与预置编译器的范围分别记录；自举脚本设计与最终独立运行分层。

关闭判断：完成资料PR合并后关闭。原作者社区发布、自身内核、配套工具与参考来源已足以支持实验内核收录；微内核严格架构、完整自举往返及OS／预置二进制许可保留条目待核，关闭只确认实际收录与分类。

建议评论草稿：

> 2026-10-25 将 lgc-os 按 x86-64 实验内核正式收录。原平台接口确认 Lightfl0w（UID3690980152707649）的中文原片直链原仓，pubdate `1790492406` 为2026-09-27T07:00:06Z（UTC+8 15:00:06）。固定 `ba606a06` 的@boot、GDT／TSS、分页、IRQ0抢占、RAMFS与ELF64形成自身内核实现依据；“微内核”保留为作者定位。条目分别记录英文词法配套lgc、自举脚本、历史作者演示、OS和第三方二进制许可缺口。国籍、严格服务隔离、编译器与视频版本绑定及完整自举独立运行继续待核实，本轮候选安装、构建、测试与执行均为0。本议题的收录与分类工作已完成，未知字段继续按条目待核记录。

## #49 hudos／hodos

已有完成范围：第16轮38项来源与Issue两条评论核实了作者—原仓—论坛身份链、ARM64 EFI_APPLICATION构建、持续Boot Services、EL0／SVC、临时页表权限及私有页表开关。固件承载与自身资源管理范围是实质分类问题。

本轮直接证据：[原片接口](https://api.bilibili.com/x/web-interface/view?bvid=BV1wiaU6REGn)明确 `owner.mid=514146062`、作者双子星观测站，简介直接给出原仓和官方论坛，中文社区发布关联成立。`pubdate=1790946000` 对应 **2026-10-02T13:00:00Z／21:00:00 UTC+8**，时长159秒。

[分支集合](https://api.github.com/repos/xuchenruisz/hudos/branches?per_page=100)新增 `h/ux1.0` 名称；它与默认 `内核6.1` 均指向 **同一** `b4a244b808b6786d5c3a1fd98102055f7f582488`。仓库pushed_at为2026-10-24T12:19:13Z。推送时间与默认源码提交分别记录，当前分类继续依据这一固定源码。

[Makefile](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/Makefile#L1-L28)明确ARM64 EFI应用；[mmu.c](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/mmu.c#L154-L181)的初始化保持空操作，说明系统生命周期保留固件MMU与中断基础。[EL0窗口](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L1647-L1663)屏蔽IRQ／FIQ，临时使用项目向量，返回时恢复固件向量；[私有页表开关](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L1538-L1558)默认为0。[efi_main](https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c#L5537-L5622)保存Boot Services、EL0自检、ESP与图形／输入服务，再装载应用和进入shell。

结果：作者／中文社区发布、视频规范时间与新增分支对应已收敛。该固定实现准确分类为“ARM64 UEFI承载实验系统，含自身ELF／EL0／SVC与协程实现”。本组正式内核列表暂留该项待核，结构化更新保存于 `kernels-a-hudos-pending.json`。

正式内核剩余门槛：需可读连续执行路径明确展示固件服务和项目自身对内存、异步中断、调度及设备资源控制的分工，达到自身内核分类所需范围。单一 ExitBootServices 调用、国籍、最早发布日期、完整许可追溯或运行复现均不单独作为本轮门槛。当前已见代码支持上述UEFI承载系统分类；若站点接受这一类别作为正式内核子类，可按该实际边界纳入，保留裸机独立资源控制待核。

关闭判断：保留开放。原Issue的自身内核边界仍是实质问题，本轮仅完成归属链、时间与分支子项。

建议评论草稿：

> 2026-10-25 补齐作者社区关联与规范时间：B站原片接口确认双子星观测站（UID514146062）的中文发布简介直接给出 xuchenruisz/hudos 与官方论坛，pubdate `1790946000` 为2026-10-02T13:00:00Z（UTC+8 21:00:00）。当前新增 h/ux1.0 分支与默认内核6.1均指向 `b4a244b8`，仓库近期推送时间与源码快照分别记录。重新阅读 Makefile、mmu.c 和主文件后，按“ARM64 UEFI承载实验系统，含ELF／EL0／SVC与协程实现”保存；默认私有页表关闭，EL0窗口与固件向量往返的边界已明确。国籍继续单列待核，正式内核分类仍需补齐固件与项目自身资源控制分工的连续实现依据；Issue保留开放。本轮安装、构建、启动与测试均为0。

## 验证与访问边界

- JSON可解析；三项正式id唯一，所有source_ids均能解析到各对象来源；每页HTML锚点唯一且引用完整。
- 集成前各工作树统计与最终集成统计分别记录；`git diff --check`通过。最终集成应按全部分组重算索引和总数。
- 新元数据附件保存三条B站接口的作者、简介、时刻和时长，以及五仓头提交、默认分支、归档状态及hudos分支映射。
- 公开网页工具对B站原页读取失败后，采用只读公开接口取得成功；普通沙箱DNS失败后，经只读网络授权执行成功。没有权限denied、pending或uncertain动作。Kercy About为404资料访问结果。
- 第三方代码与二进制的下载执行、安装、构建、测试均为0；候选代码仅由文本和元数据读取。百科自身执行JSON和HTML结构检查。
- 本组没有push、PR、合并、评论或关闭远端议题。最终建议为资料PR合并后关闭 #68、#38、#41；#64、#49保留开放。三项收录结果与五条评论草稿交由父任务集成与完整diff审阅。
