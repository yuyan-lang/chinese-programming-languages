# 2026-10-28 内核剩余资料：#13、#23、#29、#32、#52

基线`4e00d5240ff5ca99c745c2b00179c11e42bef800`，110语言、20内核。独立分支`contrib/kernels-b-20261028`。本轮保留既有20个内核全部字段与HTML，新增BearOS作者技术文档阶段；目录和总数由汇总任务更新。原作者声明、发行物静态代码、作者画面和独立运行分层记录。全部候选执行、安装、构建、启动以及宿主磁盘挂载次数为0。

已读根AGENTS.md，当前工作树未设置`.agents/skills`。完整读取本组5个议题正文及快照中的全部23条评论（#13为5，#23为5，#29为3，#32为2，#52为8），并复核2026-10-25本组日志、此前对应专项和正式目录。#79已收录的KunOS、QuantumNEC、racaOS、OS002、VergeOS Open、MimicryOS及其余条目原样保留。

## #13 NeoRunST：维护者身份链完成，内核实现仍待核

新直接证据：[GitHub组织主页](https://github.com/CN-RTStudio)与[SDK发布者RETUSTU主页](https://github.com/RETUSTU)均链接`https://rtstu.com/`。该[工作室官网](https://rtstu.com/)的联系方式同时直接链接`https://github.com/CN-RTStudio`和`https://space.bilibili.com/3546925078940468?spm_id_from=333.337.0.0`，后者正是NeoRunST原片发布账号。由官网直接互链建立SDK组织与原视频维护者关联。公开身份采用工作室角色与中文社区发布，个人国籍待核实。

[SDK发布集合](https://api.github.com/repos/CN-RTStudio/NeoRunST-DEV-KIT/releases)另保存[NeoRunST v0.13.0](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT/releases/tag/v0.13.0)，发布时间2026-10-24T11:54:12Z，作者RETUSTU；资产`disk.vhd`为423,732,224字节，平台SHA256为`c41552de8ab94fab53563220d768f23ffce233a57d9cb141d9baf0b1b8489e15`。本轮只读取发行元数据，未下载该423MB镜像。[分支集合](https://api.github.com/repos/CN-RTStudio/NeoRunST-DEV-KIT/branches)只列main，固定`477078db66e35cb23b9eed20e7228b605f29ea83`（2026-10-23T15:38:02Z）。

已知SDK用户侧`int 0x80`包装与文档声明按各自证据等级保留。SDK没有提供内核侧调度、页表隔离及系统调用分派的实际实现，TheseusOS旧阶段与当前独立内核的继承关系继续待核。工作室官网的产品线入口已核对；本轮所读公开目录未提供对应内核源码。

**结论：保持开放。** 已解决“SDK与原视频作者直接互链”这一具体缺口。最小剩余事项为当前内核侧实现/发行物内核边界，以及TheseusOS阶段对应；完整历史和独立运行各自保留后续核验。

评论草稿：

> 本轮补齐NeoRunST维护者身份链：CN-RTStudio与SDK发布者RETUSTU均链接rtstu.com，官网直接链接同一GitHub组织与原视频B站UID3546925078940468。另核实SDK仓v0.13.0正式发布及disk.vhd元数据（423,732,224字节；2026-10-24T11:54:12Z），本轮未下载该镜像。用户侧SDK证据沿用；内核侧实现与TheseusOS阶段对应继续待核，因此议题保持开放。具体来源与范围见本轮研究记录。

## #23 BearOS：按作者技术文档限定收录

编辑：data/kernels.json新增`bearos-medaifan`；详情`内核/bearos-medaifan.html`。收录依据为[作者官网](https://www.medaifan.net/)、[项目技术页](https://www.medaifan.net/bearos.html)及官网直接嵌入的四条原作者视频。作者官网与胖嘟嘟的超级熊频道互链沿用已核实原件。公开原作者身份为宁净／嘟嘟熊，国籍继续待核。

项目技术页具体说明：16位实模式向32位保护模式演进、转入保护模式后的BIOS中断边界、自行实现硬件驱动、自定义磁盘文件系统与程序装载、内存分配回收、以时钟中断修改栈返回地址切换任务、Shell拆分为通过系统调用访问内核的应用、PIO向DMA磁盘访问演进、AC97声卡与BasC语言。这些属于可定位的内核技术声明，足以按作者文档阶段记录自身内核项目。各功能均标作者声明，隔离正确性、源码继承与上游版本继续待核。

本轮直接读取官网HTML，确认嵌入的原片与CID：P1 [BV13oj66LEnk](https://www.bilibili.com/video/BV13oj66LEnk/)／39244205370；P2 [BV1goj665EC6](https://www.bilibili.com/video/BV1goj665EC6/)／39244206041；P3 [BV1goj665EXe](https://www.bilibili.com/video/BV1goj665EXe/)／39244267564；P4 [BV1ttHC6bE9g](https://www.bilibili.com/video/BV1ttHC6bE9g/)／42539814823。官网提供V0.10及V0.20百度网盘入口。通过公开视频官方播放API取得P1/P4媒体元数据；媒体CDN下载返回curl错误56、文件0字节，本轮新增可靠功能关键帧为0，视频画面继续待核。收录采用技术文档与原作者发布链这一证据范围。

**结论：独立来源审阅通过，按作者技术文档阶段完成收录；合并并关联证据后关闭。** QuantumNEC、racaOS、OS002已由#79收录；BearOS当前技术文档阶段完成。本项保留源码入口、项目及组件许可、包内容与上游边界、具体视频功能时间点、独立运行的后续核验字段。源码公开、完整历史和独立运行采用后续资料范围。

评论草稿：

> BearOS已按原作者技术文档阶段收录。官网具体记载16→32位内核演进、BIOS边界、时钟中断与栈返回地址任务切换、自定义FS及程序装载、Shell系统调用边界和PIO→DMA/AC97；全部能力明确标为作者声明。官网直接嵌入四条原作者视频，并与作者频道互链；国籍、源码继承、许可、发行物和独立运行仍按后续待核字段保存。QuantumNEC、racaOS、OS002已通过#79收录，本次提交剩余BearOS的限定资料条目；独立来源审阅确认分类并合并后可完成本议题。

## #29 Halo候选发行物：取得完整Rust内核静态实现

原始固定来源：[MYOS-UEFI-vbox.zip](https://github.com/bigbenben77/Halo-OS/blob/2677b1cec975a0bff572e622f787f682b836cea2/MYOS-UEFI-vbox.zip)，快照`2677b1cec975a0bff572e622f787f682b836cea2`（2026-09-24T14:56:19Z）。本轮只读下载ZIP8,728,039字节，使用本机已有7zz、qemu-img、LLVM和自写Python字节解析。候选内容未执行、未挂载。

ZIP内为`MYOS-UEFI-vbox.vdi`，27,262,976字节；qemu-img识别VDI动态容器、虚拟容量67,108,864字节（64MiB）。7zz在VDI内识别FAT32，保存Headers Error警告；可枚举文件只有`EFI/BOOT/BOOTX64.EFI`，23,629,824字节。该警告与目录观察分别保留。

EFI外层为PE32+／x86-64／EFI application，入口RVA0x5e10，文件SHA256 `fd6de65404fcafcb6735f1e3e13c94bac7dca711be9e9ca6cf2d3881b65e87a3`。其文件偏移68608处内嵌完整ELF64 x86-64 ET_EXEC，23,542,152字节，入口0xe80900，8个程序头、22个节；含可执行PT_LOAD、.symtab及DWARF调试资料。

静态实现依据：该ELF符号及对应反汇编可见`myos::interrupts::init`、`myos::mm::paging::init`、`myos::sched::context_switch`、`myos::sched::timer_tick_schedule`、VFS、ATA/AHCI及USB模块。内核入口路径调用页表和中断初始化；内核代码包含lgdt、lidt、iretq及定时器任务路径。EFI引导交接在VA0x140007177写CR3，0x14000719f设置RSP，0x1400071a2将BootInfo参数置于RDI，0x1400071a9间接跳至内核入口。该证据支持发行物包含独立内核代码与引导交接，具体成功执行及ExitBootServices调用路径继续待核。

内嵌调试路径及字符串可识别Rust标准库、`bootloader_api-0.11.17`、`uefi-0.38.0`与`x86_64-patched`；这些属于构建依赖和包名线索。内部还出现`MYOS UEFI Kernel started`与`AetherOS Portal ready`，名称对应和具体上游继承继续待核。字符串或符号本身不建立项目原创性、许可及完整功能正确性。

完整文件大小/SHA256见[kernels-b-artifact-metadata.json](kernels-b-artifact-metadata.json)，有界反汇编摘录见[halo-static-evidence.txt](halo-static-evidence.txt)。二进制保留在`/tmp/kernels-b-20261028`，本仓只保存元数据与短摘录。

**结论：保持开放，候选的自身实现证据已取得重大增量。** 最小余缺为编剧笨笨UID595021134与bigbenben77/Halo-OS的直接身份关联，以及含myos/AetherOS名称的此固定发行物与原片Halo阶段的对应。源码/上游和许可按具体范围保留后续核验；单个EFI容器不足以把项目分类为固件界面壳。

评论草稿：

> 已静态分析候选Halo-OS固定2677b1ce的VirtualBox发布包：ZIP8,728,039字节，内含64MiB虚拟VDI及EFI/BOOT/BOOTX64.EFI；EFI内嵌完整ELF64 x86-64内核（入口0xe80900），保留myos调度、中断、页表、VFS及ATA/AHCI等符号和机器码。EFI交接可见CR3/RSP设置、BootInfo参数与内核跳转。此为发行物静态实现证据，执行/启动次数0。内部myos/AetherOS名称、编剧笨笨与仓库直接身份互链及原片版本对应继续待核，议题保持开放；具体哈希和摘录见本轮研究记录。

## #32 TX/FendosPE VergeOS：原始分发页可读，ISO内容待取得

通过正常只读HTTP取得[TX官网](https://txgzsgw.mysxl.cn/)完整HTML；官网链接B站UID3493125223877029，以及[公开VergeOS.iso分享页](https://1817497108.share.123pan.cn/123pan/nvdTjv-DG3ih?pwd=1234)。分享页HTML标题明确为VergeOS.iso，页面由前端动态加载文件详情，静态HTML未给出镜像下载地址。此次未取得ISO字节、大小、哈希或目录，未判断其为Linux/UEFI壳或独立内核。

公开分发页的UI读取尝试：cua.getState成功；createBrowserTab(iab)返回`Browser is not available: iab`；随后`cua.getApp("com.apple.Safari")`挂起，工具最终只返回`aborted by user after 1132.3s`。该调用未返回应用状态或审批文本，模型无法确定用户端是否显示过审批；无导航、点击、登录或下载后续动作。此调用已停止，本轮没有重试或换入口处理该待定UI动作。

**结论：保持开放。** 实质余缺为可解析的公开ISO或足以确定自身内核与上游边界的技术原件；同名VergeOS Open继承关系继续按独立发布身份保存。

评论草稿：本轮只补充可读官网HTML与同一分享页标题，核心实现证据继续缺失；建议不重复发布无实质进展评论。

## #52 Causenix：完整公开历史排查，内核产物链接属于文档声明

本轮沿原仓Git历史读取全部17个提交，均为2026-10-06；[当前分支](https://api.github.com/repos/FRCREEPER/causenix/branches)只有main，Releases为空。[早期下载页782cabe](https://github.com/FRCREEPER/causenix/blob/782cabeecb9c8c2e0b2738f9456fe25ff0b02bcf/index.html)（2026-10-06T06:37:58Z）列出`downloads/myos.elf.b64`、应用和`src/main.c`等相对下载链接。当前保留历史的文件导入记录只对应README、网络队列/接口头、下载页/软件清单及snake/conway应用；该旧下载页的内核链接是作者页面声明，实际内核原件待取得。

[作者公开主页](https://github.com/FRCREEPER)及账号范围仓库查询返回4项：causenix、空个人README仓库、FNF-vsDUCK-round和openclaw-plus-plus，未提供第二个内核项目直链。完整公开Git历史、当前分支/发行集合和旧页面链接属于本轮新的取证路径。作者的中文下载中心与软件源可以确认项目发布上下文，独立内核入口、调度/内存与e1000实现仍待实质材料。

**结论：保持开放。** MimicryOS已由#79收录；Causenix的完整自身内核/发行物边界继续是具体余缺。此次排查未取得新的核心实现，建议不重复发布旧状态评论。

## 交付与校验

BearOS有限收录已由独立sol逐项阅读官网原件复核，全部功能限定为作者声明；#23在条目合并并关联证据后关闭。#13、#29保留精确余缺并可发布实质补证；#32、#52未取得核心实证，保持开放并省略重复评论。国籍、完整历史和独立运行各自采用直接公开证据与后续核验字段。

本地交付包含BearOS数据及详情、五题研究日志、Halo文件SHA256和有界反汇编摘录。未推送、创建PR、发布评论或关闭议题；外部写入由root汇总。原20项字段与HTML完整性、JSON source_ids及本轮HTML结构、diff空白在提交前核验。
