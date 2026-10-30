# Halo-OS 仓库发布阶段收录核验（2026-10-30）

本轮处理 Issue #29 的 GitHub 候选。按固定仓库文档与发行物，新增 `Halo-OS（bigbenben77，仓库发布阶段）`。B站编剧笨笨与此维护者、原片版本与此Demo盘的直接对应继续待核实，Issue #29 保持开放。

## 来源与收录范围

[固定README](https://github.com/bigbenben77/Halo-OS/blob/2677b1cec975a0bff572e622f787f682b836cea2/README.md)以中国项目自述介绍 Halo-OS，并声明使用 AI、Rust 和多语言显示。本条采用该项目自述记录中国关联；个人国籍待核实。“中国第一个”、全部代码由AI完成及原创范围均属于作者声明，独立核验待核实。

[公开GitHub档案](https://github.com/bigbenben77)与[固定提交](https://github.com/bigbenben77/Halo-OS/commit/2677b1cec975a0bff572e622f787f682b836cea2)将 bigbenben77 关联到公开别名“码农笨笨”。该提交时间为2026-09-24T14:56:19Z。[较早上传提交](https://github.com/bigbenben77/Halo-OS/commit/180e78b5c912cc7c7025b6691fe302a141fad426)时间为2026-09-24T14:07:12Z，作者明确将上传内容说明为操作系统Demo版虚拟盘，并表示后续另发满意版本。本条采用“2026-09-24仓库Demo虚拟盘阶段”；正式版本号与最早公开时间待核实。

[固定完整树](https://api.github.com/repos/bigbenben77/Halo-OS/git/trees/2677b1cec975a0bff572e622f787f682b836cea2?recursive=1)的 `truncated=false`，包含README、8,728,039字节的MYOS-UEFI-vbox.zip和9,111,552字节的MYOS-UEFI-vmware.vmdk。完整内核源码入口、项目与第三方组件许可继续待核实。完整源码公开和独立运行验证作为资料状态记录；当前有限条目的依据是作者发布链、中国关联自述与发行物内实际内核实现。

## 本轮有界作者渠道检查

完整阅读本轮快照的Issue正文及4条评论，并复用2026-10-28静态记录。GitHub当前main仍为上述固定提交。Halo-OS的README与仓库homepage字段未给出其他发布渠道；公开个人档案未给出B站链接。

本轮沿同账号公开仓库补查作者项目的README：

- [BenbenPainterQT6 README](https://github.com/bigbenben77/BenbenPainterQT6/blob/HEAD/README.md)，读取blob为`9f42f1be7d4299331a8ac93becbdc8e2c39e252a`，内容为绘图软件功能说明。
- [Paint-AI README](https://github.com/bigbenben77/Paint-AI/blob/HEAD/README.md)，读取blob为`5a3a06aabf840acec106f0e43573de0874998653`，内容为绘图软件功能说明。
- BenbenPainter、benbenpainterQT5及同名个人档案仓库的README.md请求返回404。

上述成功读取的文档未出现公开发布渠道或B站身份链接。该结果限定于实际检查入口。未重复请求旧B站频道、动态或视频；未重试Safari与先前审批状态不明的请求；未从邮箱域名推定个人网站。

## 固定发行物与静态调用链

本轮复用2026-10-28本地原件，重新计算SHA256，六项全部与[已入库元数据](../2026-10-28/kernels-b-artifact-metadata.json)一致。候选执行、安装、构建、启动和挂载次数均为0。

| 对象 | 字节 | SHA256 |
| --- | ---: | --- |
| MYOS-UEFI-vbox.zip | 8728039 | `15ed9728d7ac972ff66aa7b2074f49010876fe1ab8f2057a3c783927703702cb` |
| ZIP内VDI | 27262976 | `690d58a444b69f53eb956c2172e6682d77664779d8c374b75e4d2c8eca5ff050` |
| BOOTX64.EFI | 23629824 | `fd6de65404fcafcb6735f1e3e13c94bac7dca711be9e9ca6cf2d3881b65e87a3` |
| EFI偏移68608的ELF | 23542152 | `43b7a53121dee60b34a0e10c0cfadd16f7b4e578f6b688702d940348bb160270` |
| EFI偏移1539316的ELF | 10735328 | `c8f37d1f83abcdab7b612e1cd3ad07d0573f2786ad9453f649cb13b6cdf69fd8` |
| EFI偏移12371560的ELF | 24680 | `49170519ce611a416644884f6382687ad090e97f8723671c6983637ae1b72228` |

[固定ZIP原件](https://github.com/bigbenben77/Halo-OS/blob/2677b1cec975a0bff572e622f787f682b836cea2/MYOS-UEFI-vbox.zip)的Git blob为`8f42d47a98bce2e8edc46f23e82d16a0cfe23692`。VDI为动态容器，虚拟容量67,108,864字节。既有只读枚举识别FAT32与`EFI/BOOT/BOOTX64.EFI`，工具同时报告Headers Error；容器完整性状态按该提示保留。

外层文件为PE32+ x86-64 EFI application。偏移68608的ELF为小端ELF64 x86-64 ET_EXEC，入口0xe80900，8个程序头、22个节，保存符号与DWARF。其入口`_start`在0xe80905直接调用`_start_uefi`（0xdfd650）；该路径直接调用FrameAllocator、页表、堆、GDT、IDT/PIC及硬件中断注册。逐条地址与机器码保存在[本轮入口调用摘录](halo-entry-callchain.txt)。这补充了2026-10-28仅列单函数开头的证据。

[既有机器码摘录](../2026-10-28/halo-static-evidence.txt)记录EFI交接路径写CR3、设置RSP、RDI传入BootInfo并间接跳转；内核context_switch机器码保存/恢复通用寄存器和RSP。内核还保存调度、VFS与块设备接口、ATA/AHCI、USB模块代码。以上依据是静态字节、调用指令和符号的组合；固件退出服务、成功交接及各功能运行正确性继续待核实。

发行物内部`myos`符号、`AetherOS Portal`字符串分别记录为内部名称线索；它们与Halo-OS的命名沿革、完整源码和上游继承关系待核实。Rust标准库、bootloader_api 0.11.17、uefi 0.38.0及x86_64-patched属于调试路径中的依赖线索，精确组件来源及许可继续待核实。

## 编辑与议题判断

新增`data/kernels.json`对象`halo-os-bigbenben77`及`内核/halo-os-bigbenben77.html`。保留基线25个内核对象、既有HTML与引用；目录汇总由集成分支统一更新。本条分开记录作者声明、发行物静态实现、身份与来源未知项。

Issue #29原始目标为B站编剧笨笨发布的Halo。该议题当前最小仍缺项：由原作者明确发布的身份互链或说明，将B站账号与bigbenben77关联，并明确原片Halo与此仓库Demo盘的版本关系。新增仓库阶段条目完成可独立成立的资料；原议题继续开放。myos/AetherOS沿革、许可、完整源码与运行结果保留条目待核状态。

拟在资料PR合并后发表的评论：

> 本次资料PR（合并后填入链接）新增 **Halo-OS（bigbenben77，仓库发布阶段）**。固定提交2677b1ce的README提供项目中国关联与AI/Rust自述；公开GitHub别名为码农笨笨，作者上传提交将盘称为操作系统Demo。固定VirtualBox发行物含UEFI引导器和ELF64 Rust内核，静态入口直接调用页帧、页表、堆、GDT/中断初始化，并保存调度与VFS实现。记录附原件SHA256及机器码摘录，全部AI开发与原创范围仍按作者声明/待核实处理。B站编剧笨笨与GitHub维护者的身份直链、视频版本与此Demo盘对应仍待核实；myos/AetherOS内部名与完整源码继承也分别保留待核。本议题继续开放，待原作者身份和版本链接补齐后再判断完成。

## 验证

结构、来源ID、旧对象与旧HTML保留、相对链接和diff空白检查由本地验证完成；结果与提交一并交父任务。独立审阅另核原件哈希、Git blob及入口调用链。候选代码/二进制运行次数为0。本轮没有新的审批拒绝、待批动作或执行结果不明动作。
