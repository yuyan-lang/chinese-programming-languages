# 2026-10-25 内核积压资料处理：#13、#23、#29、#32、#52

基线：`3f59f9224b48998b4260b36792fad57ec130ca63`，103项语言、11项内核。工作分支：`contrib/kernels-b`。本组覆盖11个既有候选发布身份，正式资料新增6项，继续待核5项。五个议题均含实质剩余子项，整议题关闭建议为0项。目录页与计数由汇总步骤统一更新。

## 标准与核验范围

收录依据为自身内核工程、可明确记录的原作者或中文开发社区关联、已知组件及继承来源。条目按固定源码阶段记录，作者声明、源码可见、作者演示和独立运行分别呈现。国籍采用直接公开自述；中文社区发布与源码互链按社区关联记录。独立运行、首次公开日期、完整历史和全部第三方许可作为具体待核范围保存。

读取了根目录 [AGENTS.md](../../AGENTS.md)，仓库 `.agents/skills` 目录未设置。本组完整读取了五个议题正文及全部18条评论：#13为4条、#23为4条、#29为2条、#32为1条、#52为7条。相关旧研究覆盖2026-10-10的首轮、第三至第十一轮内核专项日志和配套待核数据；后续日志中的既有对象排重段；2026-10-11的第十八轮和第二十一轮。旧资料保持原始核验时间。

平台为GitHub原仓连接器、原作者B站公开视频元数据、作者官网及公开检索。候选代码、脚本、安装包和镜像的执行、安装、构建和启动次数均为0。百科本地资料检查采用Python标准库。公开API视频资料只用于标题、账号、日期和简介，功能画面沿用明确注明的旧记录或继续待核。

## #13：KunOS 与 NeoRunST

### KunOS：完成当前阶段收录

- 编辑：[结构化资料](../../data/kernels.json)，对象`kunos`；[详情](../../内核/kunos.html)。
- 固定源码：[2e5e70dc6ff43330cb4869719c66dab51eda1788](https://github.com/hellopgrmm/KunOS/commit/2e5e70dc6ff43330cb4869719c66dab51eda1788)，2026-10-25T08:54:10Z。
- 本轮重新读取[boot.asm](https://github.com/hellopgrmm/KunOS/blob/2e5e70dc6ff43330cb4869719c66dab51eda1788/BK/boot.asm)、[kernel.asm](https://github.com/hellopgrmm/KunOS/blob/2e5e70dc6ff43330cb4869719c66dab51eda1788/BK/kernel.asm)、[3_fileman.asm](https://github.com/hellopgrmm/KunOS/blob/2e5e70dc6ff43330cb4869719c66dab51eda1788/BINARY/3_fileman.asm)、[构建脚本](https://github.com/hellopgrmm/KunOS/blob/2e5e70dc6ff43330cb4869719c66dab51eda1788/build.bat)及README。引导器读取32扇区到0x7e00并远跳转；自身命令内核、BIOS服务与固定应用布局分别记录。
- 新直接来源：[原片公开元数据](https://api.bilibili.com/x/web-interface/view?bvid=BV1Gkho6fEcd)返回UP小猫头鹰Owl-、UID3494379228498773，简介直接链接hellopgrmm/KunOS。该链支持中文技术社区发布与源码关联，作者国籍待核实。
- version 4、应用入口地址与镜像blob沿用问题已在[6396549562](https://github.com/yuyan-lang/chinese-programming-languages/issues/13#issuecomment-6396549562)补证，本轮按既有证据收录。9月原片01:40的XKFS菜单属于旧作者演示记录；version 4的运行效果继续待核。
- 剩余：随附镜像与源码构建对应、XKFS第二软盘初始化和应用装入正确性、标准许可证和随附工具来源、独立运行。作者允许下载、修改和分发的自定义授权可准确记录。

### NeoRunST：新增SDK阶段，保留内核来源缺口

GitHub定向仓库检索`NeoRunST`取得[CN-RTStudio/NeoRunST-DEV-KIT](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT)。固定提交[477078db66e35cb23b9eed20e7228b605f29ea83](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT/commit/477078db66e35cb23b9eed20e7228b605f29ea83)，2026-10-23T15:38:02Z；仓库创建时间2026-10-23T15:26:12Z。

[完整树](https://api.github.com/repos/CN-RTStudio/NeoRunST-DEV-KIT/git/trees/477078db66e35cb23b9eed20e7228b605f29ea83?recursive=1)共14项，含11个文件与3个目录，truncated=false。内容为README、SDK文档、C头文件、crt0、buildnep.cpp及工具二进制。[readme.md](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT/blob/477078db66e35cb23b9eed20e7228b605f29ea83/readme.md)声明NEP程序在Ring 3运行、每进程独立地址空间及抢占调度，并说明SDK使用MIT许可；这些内核能力按作者声明保存。

[tools/nep.h](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT/blob/477078db66e35cb23b9eed20e7228b605f29ea83/tools/nep.h)可见C内联汇编`int $0x80`及rax编号、rdi/rsi/rdx参数接口；例如窗口创建包装使用编号1。此为用户侧ABI实现。内核侧分派、页表隔离、任务抢占、固件与TheseusOS阶段继承待核实。SDK安装示例提及`NeoRunST-CustomOS/kernel/bin/NeoRunST.img`，该路径的对应公开内核仓库待定位。`org:CN-RTStudio`检索返回OpenQGL、runst_x、OpenCosy与本SDK；检索结果属于本次公开索引范围。

[原视频元数据](https://api.bilibili.com/x/web-interface/view?bvid=BV1tyH76QERz)确认热土工作室RTStudio、UID3546925078940468及2026-10-04T13:14:18Z；当前简介为`-`。SDK组织与原视频作者的直接互链继续待核实。可收录的自有内核实现材料仍是本子项实质缺口。

**议题处理：保持开放。** KunOS条目完成，NeoRunST继续跟进SDK与内核、TheseusOS和当前阶段之间的来源关系。

评论草稿（整合PR合并后使用）：

> 本次资料更新已收录KunOS的16位实模式汇编内核阶段，分别记录BIOS引导、自身命令内核、应用布局、XKFS及README自定义授权。version 4与镜像blob对应问题沿用6396549562的既有证据。另定位NeoRunST NEP SDK固定477078db（2026-10-23T15:38:02Z），取得用户侧C/int 0x80包装与构建工具源码；内核侧实现、SDK与原视频作者的直接互链及TheseusOS沿革继续待核。研究见`research/2026-10-25/kernels-b.md`。KunOS子项已完成限定阶段收录；NeoRunST保留实质缺口，本议题保持开放。

## #23：QuantumNEC、racaOS、BearOS 与 OS002

### QuantumNEC、racaOS、OS002：完成分阶段收录

编辑对象分别为`quantumnec`、`racaos`、`os002`；详情为[QuantumNEC](../../内核/quantumnec.html)、[racaOS](../../内核/racaos.html)、[OS002](../../内核/os002.html)。全部字段原始URL在data/kernels.json各对象sources中。

- QuantumNEC固定[6216373689baa6302cdb2a3b4656955063510b1e](https://github.com/SegmentationFaultCD/QuantumNEC/commit/6216373689baa6302cdb2a3b4656955063510b1e)，2026-07-27T15:30:53Z；本轮重新读取启动入口、MuQSS和README。入口接入中断结构、内存和任务初始化；SMP、系统调用、模块加载和开中断调用处于注释阶段。调度源码存在与当前多任务实际运行分别记录。
- racaOS固定[72ab92f0e296fd6889059315afa5a9850ae582ba](https://github.com/zzjrabbit/racaOS/commit/72ab92f0e296fd6889059315afa5a9850ae582ba)，2025-12-08T14:53:56Z；本轮重新读取Zodiac入口、模块清单及README。edition21为LoongArch64/Rust模块化内核阶段，多任务、用户态和磁盘文件系统按路线图保存。历史x86-64、TrashOS/rCore参考、edition19 Apache-2.0与edition21许可缺口分别记录。[edition19清单](https://github.com/zzjrabbit/racaOS/blob/6dd22e52f28459f191d35d1815b6b960842d167f/zodiac/Cargo.toml)本轮重新确认署名Zhenjia Zeng、0.3.0和Apache-2.0。
- 两项社区关联由[固定plos-clan介绍](https://github.com/plos-clan/.github/blob/3671e17129ec6f9e08eccf547ab7b3d1caa1addd/profile/README.md)及[QuantumNEC](https://github.com/plos-clan/docs/blob/fc84dc13f484e8a0bc87e62d1956312b6a9a6a46/docs/project/QuantumNEC.md)/[racaOS](https://github.com/plos-clan/docs/blob/fc84dc13f484e8a0bc87e62d1956312b6a9a6a46/docs/project/racaos.md)项目页直接成立：组织介绍其为OS & PL开发交流群的GitHub组织，列出UEFIer/zzjrabbit与SegmentationFaultCD；项目页明确归属和源码。国籍继续待核。
- QuantumNEC作者[原片公开元数据](https://api.bilibili.com/x/web-interface/view?bvid=BV1yuWFzSEbi)给出2025-09-21T03:16:02Z，修正旧页面显示的9月20日。原片时间与固定源码对应继续待核。
- OS002固定[be37cce6b0963e35d4481ea22d7688b76e19e80c](https://github.com/Chunyi1031/OS002-UEFI/commit/be37cce6b0963e35d4481ea22d7688b76e19e80c)，2026-04-03T11:36:44Z；本轮重新读取GNU-EFI引导入口、自身C内核入口和线程实现。[原片公开元数据](https://api.bilibili.com/x/web-interface/view?bvid=BV1sTwtzuEP8)确认Liu_Chunyi、UID3546765877840766，2026-03-14T13:23:35Z，简介直链Chunyi1031/OS002-UEFI。按原作者中文技术发布与源码关联记录。3月作者演示与4月加入ExitBootServices的源码分开保存。

合理标准：三项均已有明确可读的自身内核工程、固定入口和原作者/社区关系，许可证和已知组件可分层呈现。源码存在、启用调用与实际运行分别核实。新增条目不声称性能、稳定性、完整功能或作者国籍。

### BearOS：完善当前公开阶段，保留实现依据缺口

本轮重新读取[作者官网](https://www.medaifan.net/)与[项目页](https://www.medaifan.net/bearos.html)。官网首页当前也列V0.20，旧记录“首页V0.10、详情V0.20”的页面阶段差异已经消除。作者说明保留x86 32位保护模式、任务调度、内存、DMA、AC97、BasC逻辑回归等内容；这些仍为作者声明。官网和频道互链、四条原BV沿用既有核验。`BearOS medaifan`定向GitHub仓库检索为空，结果只代表当前索引范围。

自身内核源码或能核对内核/上游边界的技术原件、系统专属许可及发行物与原片对应继续待核。首页版本一致性属于材料更新，完整内核实现判断仍需原件。

**议题处理：保持开放。** 三项限定阶段资料完成；BearOS继续等待实现与上游边界证据。

评论草稿：

> 本次资料更新已收录QuantumNEC、racaOS及OS002，按固定源码阶段记录自身入口、调度/模块状态、内存和已知继承来源。QuantumNEC/racaOS以plos-clan中文开发社区的明确项目归属关联收录；OS002以原作者中文发布与源码直链记录，作者国籍分别待核。racaOS旧x86-64/edition19许可与当前LoongArch64 edition21分开保存，OS002三月原片与四月ExitBootServices快照分开保存。BearOS官网首页现为V0.20；其内核实现原件与上游边界继续待核。研究见`research/2026-10-25/kernels-b.md`。本议题保持开放。

## #29：编剧笨笨 AI Rust / Halo OS

当前候选仓库[bigbenben77/Halo-OS](https://github.com/bigbenben77/Halo-OS)的main仍为`2677b1cec975a0bff572e622f787f682b836cea2`，2026-09-24T14:56:19Z。[固定完整树](https://api.github.com/repos/bigbenben77/Halo-OS/git/trees/2677b1cec975a0bff572e622f787f682b836cea2?recursive=1)仍为README和两项虚拟盘文件，truncated=false；自身内核源链仍待取得。B站与GitHub账号的直接身份互链继续待核。

本轮新直接证据为原片公开API的`pubdate`绝对时间，旧记录的自然日矛盾可明确为时区显示：

| 原片 | UTC元数据 | Asia/Shanghai换算 |
| --- | --- | --- |
| [首发BV1Thh264EtM](https://api.bilibili.com/x/web-interface/view?bvid=BV1Thh264EtM) | 2026-09-25T11:41:57Z | 2026-09-25 19:41:57 |
| [更新BV1oZap6CE8X](https://api.bilibili.com/x/web-interface/view?bvid=BV1oZap6CE8X) | 2026-09-29T16:25:08Z | 2026-09-30 00:25:08 |
| [扫雷BV1hwYA65EqL](https://api.bilibili.com/x/web-interface/view?bvid=BV1hwYA65EqL) | 2026-09-30T22:49:01Z | 2026-10-01 06:49:01 |

三项均由编剧笨笨UID595021134发布。AI、Rust、GUI、USB/网络框架、自有应用打包、空载24小时及三平台测试保留作者声明等级。首发00:02的Halo OS标志沿用旧作者演示记录。本轮完成日期规范化；自身内核实现、上游边界、候选仓库身份链仍是实质缺口。

**议题处理：保持开放。**

评论草稿：

> 原片公开API已补齐UTC发布时间，解决此前日期显示差异：首发2026-09-25T11:41:57Z、更新2026-09-29T16:25:08Z、扫雷2026-09-30T22:49:01Z；后两项北京时间分别为9月30日00:25:08和10月1日06:49:01。三项UP均为编剧笨笨UID595021134。候选bigbenben77/Halo-OS当前固定树仍为README和两项虚拟盘；自身内核实现、源码上游以及B站/GitHub直接身份互链继续待核。研究见`research/2026-10-25/kernels-b.md`。本议题保持开放。

## #32：VergeOS 两条发布身份

### VergeOS Open：完成源码阶段收录

编辑对象`vergeos-open-newera`；[详情](../../内核/vergeos-open-newera.html)。固定[d6041c2f2c2a95d73b22a7df8142a0d7d345f319](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/commit/d6041c2f2c2a95d73b22a7df8142a0d7d345f319)，2026-07-02T07:36:55Z。本轮重新读取32位Multiboot入口、kernel_main、task_yield和README。固定任务代码采用主动yield链表轮转及ESP切换；抢占、Ring 3隔离、PE兼容范围继续待核。MIT根许可、VoidOS v0.2标记、工具链及有限Win32桩分别呈现。

[原视频公开元数据](https://api.bilibili.com/x/web-interface/view?bvid=BV1fPTj6FEcb)确认新启年工作室-NES、UID3546976190728987、2026-07-02T10:33:07Z，简介明确链接源码。按工作室中文技术发布与源码关联收录，成员国籍待核实。自身内核工程、已知上游和作者关联已经足以准确呈现此阶段。

### TX/FendosPE VergeOS：保留实现与同名关系缺口

[原片元数据](https://api.bilibili.com/x/web-interface/view?bvid=BV1UaHp6KEYx)确认FendosPE系统官方、UID3493125223877029、2026-10-05T04:42:06Z，简介链接txgzsgw.mysxl.cn。网页提取本轮访问TX/新启年官网失败；沿用旧记录已核实的发布身份、官网和ISO分发入口。`VergeOS FendosPE`定向GitHub仓库检索为空。

当前实质缺口为自身内核与固件/界面层边界、原始源码或其他足以确定该边界的技术原件，以及与NewEra同名项目的合作/继承关系。ISO哈希、完整历史和独立运行分别作为后续核验项。

**议题处理：保持开放。** Open源码阶段资料完成；TX发布身份继续待核。

评论草稿：

> VergeOS Open已按NewEra Studio的固定d6041c2源码阶段收录，记录Multiboot→32位C内核、主动yield任务轮转、内存和tar initrd，并限定PE桩、抢占与用户隔离的证据范围。原片API确认2026-07-02T10:33:07Z和新启年工作室-NES简介直链源码，成员国籍待核。FendosPE/TX原片确认2026-10-05T04:42:06Z及官网链接；其自身内核边界、技术原件和与Open同名项目的继承关系继续待核。两条发布身份分别保存。研究见`research/2026-10-25/kernels-b.md`，本议题保持开放。

## #52：MimicryOS 与 Causenix

### MimicryOS：完成当前BOOTBOOT阶段收录

编辑对象`mimicryos`；[详情](../../内核/mimicryos.html)。固定[e5d79e4311910c44b870ad7c36e4e8268eac9f6e](https://github.com/Annihilation006/MimicryOS/commit/e5d79e4311910c44b870ad7c36e4e8268eac9f6e)，2026-10-24T16:35:42Z。本轮重新读取README、BUILD、Makefile、kernel.c、linker.ld、bootboot.h、MIT许可及模块源码。中国作者归属采用Annihilation006的[明确自述](https://github.com/yuyan-lang/chinese-programming-languages/issues/52#issuecomment-6362756351)。

已有[6391980826](https://github.com/yuyan-lang/chinese-programming-languages/issues/52#issuecomment-6391980826)的font.psf输入、Makefile规则、重建历史和源码阶段属于既有补证。条目准确保存1MiB单向链表堆、16KiB内核栈、简化FAT12风格文件操作、ATA与PS/2轮询；README双向链表用语按具体源码限定。新直接静态核验补充：`desktop`命令实际调用desktop_draw，模块包含背景、任务栏和窗口边框绘制；kernel_main自动注册的desktop项处于注释状态。完整桌面互动和鼠标指针接入继续待核。

本轮新直接证据：原仓[README](https://github.com/Annihilation006/MimicryOS/blob/e5d79e4311910c44b870ad7c36e4e8268eac9f6e/README.md)内短链`https://b23.tv/UrL2fwN`以HTTP跳转解析到[原片BV1MAHM6fEq3](https://www.bilibili.com/video/BV1MAHM6fEq3/)。[公开API](https://api.bilibili.com/x/web-interface/view?bvid=BV1MAHM6fEq3)返回UP Annihilation006、UID3546392479926809，2026-10-24T16:30:33Z，时长493秒，简介明确“MimicryOS，一个新的自制操作系统，由AI和人类一起开发”。原片、作者账号及仓库链已经成立，具体功能时间点与源码对应继续待核。

合理标准：明确作者自述、自身ELF64入口工程、具体内核实现、BOOTBOOT与stb_image等依赖和许可已经具备。font.psf原始许可、打包配置、完整重建历史及独立运行保留具体待核事项。

### Causenix：保留完整内核源链缺口

[固定main](https://github.com/FRCREEPER/causenix/commit/f7ab3f38bac9b944b184e9226a6e8da5d65dde2e)仍为f7ab3f38（2026-10-06T15:46:44Z）。[完整树](https://api.github.com/repos/FRCREEPER/causenix/git/trees/f7ab3f38bac9b944b184e9226a6e8da5d65dde2e?recursive=1)仍为9文件、2目录，包含两项应用ELF、下载页、清单及网络队列/接口片段，truncated=false。自身内核入口、构建和调度/内存等核心实现、系统上游边界继续待补。当前名称搜索仍定位同一原仓；企业Causenix同名站点单独消歧。

**议题处理：保持开放。** MimicryOS完成当前阶段收录；Causenix仍有自身内核实现证据缺口。

评论草稿：

> MimicryOS已按e5d79e43的BOOTBOOT/ELF64内核阶段收录，作者中国开发者自述、当前源码与许可分层保存。font.psf和构建规则沿用6391980826既有补证。本次通过README短链定位原片BV1MAHM6fEq3：UP Annihilation006（UID3546392479926809），2026-10-24T16:30:33Z，493秒，简介明确MimicryOS及AI/人类共同开发。具体功能时间点、配置、字体来源和独立运行继续待核。Causenix当前固定树仍只有下载页、两项应用及网络/接口片段，完整内核源链继续待补。研究见`research/2026-10-25/kernels-b.md`，本议题保持开放。

## 检索、访问限制与校验

本轮GitHub定向查询：`NeoRunST`、`org:CN-RTStudio`、`BearOS medaifan`、`VergeOS FendosPE`、`Causenix`。普通网页查询围绕KunOS/NeoRunST/OS002/SegmentationFaultCD/plos-clan的中国关联、BearOS/MedAIFan/宁净、新启年工作室。聚合文章及同名无关结果只用于发现和消歧。网页工具对部分B站和官网返回不可访问；GitHub连接器成功读取固定原件。B站公开API采用只读curl成功取得视频元数据，Python默认请求曾返回HTTP412；本轮取得的规范时间明确记录UTC，旧页面显示值保留在旧日志中。

本组资料新增6项详情与数据对象；五个议题均因独立子项的实现或身份缺口继续开放。发布、评论、推送、PR和合并由汇总任务处理，本组执行次数为0。候选执行次数为0；百科JSON、来源引用、UTF-8 HTML、原11项对象完整性与diff空白检查在交付前核验。
