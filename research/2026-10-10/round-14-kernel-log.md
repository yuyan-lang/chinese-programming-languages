# 第十四轮内核研究：HOS（HuangCheng72）

核验日期：2026-10-10；研究时间21:01—21:08 UTC。
百科基线：[46734fc65a9a5da4cdc230c78c9f835134973e9a](https://github.com/yuyan-lang/chinese-programming-languages/tree/46734fc65a9a5da4cdc230c78c9f835134973e9a)。

## 结果与计数

- 真正新发现1项：HOS（HuangCheng72）。
- 建议正式收录1项，ID为hos-huangcheng72，类别为教学／实验宏内核。
- 旧线索补证收录0项；既有formal条目修改0项。
- 本轮深入对象1项。筛选阶段的网页命中与仓库元数据分别作为检索记录。
- 形成35条参考资料；其中知乎HOS专栏为README直接关联的公开入口，正文及原始日期继续核实。
- 本轮独立构建、运行与硬件测试结果：待核实。


后续字段记录属于HOS已收录条目的后续字段，计数沿用同一项目。主目录整合后为9项内核。

## 基线、排重与选择

已读固定基线AGENTS.md、data/kernels.json、第十三轮总日志与内核日志，以及当前23个开放Issues的正文、全部60条评论。8项既有内核为DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS／na-kernel与TextOS。

排重使用项目名、原仓、作者账号及链接；同时对前十三轮研究文件和证据目录全文检索HuangCheng72及其HOS原仓。HOS与已有条目、开放议题和保存研究记录分别核对，计为本轮真正新发现。通用名称HOS保留作者限定，以便与同名工程区分。

CoreZ-OS、lgc-os、Halo、VergeOS、QuantumNEC、racaOS、BearOS、OS002、KunOS和NeoRunST沿用已有调查。PlantOS、LunaixOS、XinhaoOS、VimtuOS识别为先前背景入口；本轮选择HOS深入。

HOS符合本轮中国作者公开归属条件：作者个人仓库固定README直接自述“I'm from China”。国别依据取自明确自述。

## 作者与公开发布链

1. [作者固定个人README](https://github.com/HuangCheng72/HuangCheng72/blob/b1b61fa12af12390344d14de45f0054e8cd627b8/README.md#L1-L8)自署Huangcheng并明确来自中国。正式条目仅保留署名和归属短句。
2. [HOS固定README](https://github.com/HuangCheng72/HOS/blob/7bf86ad11e069f6f6a590d2ee80cdf64e03353c9/README.md)说明教材来源、列出成系列开发文章，并以“我的知乎专栏”直链[HOS栏目](https://www.zhihu.com/column/c_1776978835558858752)。
3. [固定LICENSE](https://github.com/HuangCheng72/HOS/blob/7bf86ad11e069f6f6a590d2ee80cdf64e03353c9/LICENSE)署名Copyright (c) 2024 HuangCheng72。
4. 仓库元数据homepage重复指向同一知乎栏目；公开原仓fork=false，核验时6 stars。关注度为读取时的元数据。
5. 公开GitHub原始文档和源码构成本轮作者发布依据。知乎网页读取返回内部错误；跨平台入口的正文、作者显示名及日期继续核实。
6. 原作者Bilibili视频、视频时间点及录屏与源码对应：待核实。本轮以公开作者文档为主材料。

## 自身内核边界

核验快照为[7bf86ad11e069f6f6a590d2ee80cdf64e03353c9](https://github.com/HuangCheng72/HOS/commit/7bf86ad11e069f6f6a590d2ee80cdf64e03353c9)。

- [x86主Makefile](https://github.com/HuangCheng72/HOS/blob/7bf86ad11e069f6f6a590d2ee80cdf64e03353c9/Program_x86/Makefile)明确采用i686-elf工具链，把内核、库、设备、用户组件与文件系统对象统一链接为kernel.bin，并在注释中称“宏内核”。
- [loader.asm](https://github.com/HuangCheng72/HOS/blob/7bf86ad11e069f6f6a590d2ee80cdf64e03353c9/Program_x86/boot/loader.asm)通过BIOS磁盘读取装入内核，设置A20、GDT、CR0.PE，进入bits 32后跳到内核地址。
- [链接脚本](https://github.com/HuangCheng72/HOS/blob/7bf86ad11e069f6f6a590d2ee80cdf64e03353c9/Program_x86/kernel/kernel_linker.ld)指定ENTRY(kernel_main)；[内核入口](https://github.com/HuangCheng72/HOS/blob/7bf86ad11e069f6f6a590d2ee80cdf64e03353c9/Program_x86/kernel/kernel.c)自行初始化分页、GDT、IDT、任务管理、内存与设备。
- ARM路线使用U-Boot加载HOS内核。Program_arm与Program_OrangePiOne的kernel_main继续管理页表、栈、任务、中断与设备；C编译参数包含freestanding和nostdlib。

上述证据支持具有自身引导交接、内核初始化与核心管理逻辑的教学／实验内核分类。项目以两部教材为学习基础，具体移植来源单列。

## 架构与功能分层

完整固定树为535项，truncated=false。四个程序目录分别是Program_x86、Program_arm、Program_JZ2440和Program_OrangePiOne。

### 源码可见

- x86：32位保护模式；4KiB分页、物理及虚拟地址位图、页映射与释放；高地址内核映射和16MiB RAMDISK映射。
- 调度：PIT中断消耗时间片，ready_list轮转；task_switch处理页目录、TSS.esp0和汇编上下文切换。页表及任务参数的安全正确性继续核实。
- 用户态：process.c创建用户页目录、用户栈并建立进程入口；int 0x80包装进入分发器，编号1—5处理字符串输出、任务名称、页分配、页释放和整数输出。
- HCFileSystem：固定fs.h、fs.c包含格式化、文件读写、移动、删除、重命名与CRC32接口。版本1.0／20.06.2024属于文件系统组件注释，内核整体版本以提交标识。
- 文件权限：fs.h将测试阶段的文件以完整权限处理。权限控制完整性、系统调用参数检查和隔离结果继续核实。
- QEMU ARM：启动脚本使用qemu-system-arm -M virt、128MiB内存和U-Boot。
- Orange Pi One：作者记录全志H3／ARMv7；入口建立GPIO灯闪烁任务，调用设备管理接口。

### 作者声明

- 第34篇记述Orange Pi One分页测试；第36篇记述多任务运行；第38篇记述GPIO红绿灯闪烁。
- 第33篇保存JZ2440任务切换停在一轮的阶段结果。后续修复与硬件验证继续核实。
- 第39篇将Shell、FAT32、MMC、DMA和GPIO扩展列为未来计划。对应实现状态按后续证据更新。
- 相关文章中的测试描述按作者声明记录；图片逐像素核对、录屏及版本对应继续核实。

### 构建资料边界

Orange Pi One主Makefile的compile目标调用fs子目录。535项固定树中该平台列有entry、kernel、lib和devices等目录；fs路径补全及默认构建配置列为后续检查项。当前保持源码静态事实，独立构建结果待核实。

## 历史、版本、许可及来源

- [仓库元数据](https://api.github.com/repos/HuangCheng72/HOS)创建时间：2024-05-21T05:45:45Z。
- [现存无父根提交](https://github.com/HuangCheng72/HOS/commit/0ff1ebce807468ed0cdb310cd95cf226092d36fd)作者时间：2024-05-21T05:45:45Z。
- main历史读取3页，分别100、100、37条；最终记录为上述根提交。列表入口为https://api.github.com/repos/HuangCheng72/HOS/commits?per_page=100&page=1 ，页码2、3按同参数读取。
- 最新main提交：2024-12-12T13:45:54Z，修改Timer1时钟源。仓库pushed_at为2026-06-25T07:08:00Z，按另一项平台字段保存。
- [Releases](https://api.github.com/repos/HuangCheng72/HOS/releases?per_page=100)及[Git标签引用](https://api.github.com/repos/HuangCheng72/HOS/git/matching-refs/tags/)均返回空数组。正式发行与版本待核实。
- 项目根LICENSE为MIT。教学参考《30天自制操作系统》《操作系统真象还原》、JZ2440借用的韦东山例程、GPIO明确移植的OrangePiH3_uboot及随附U-Boot二进制各自保留来源范围。
- 第17篇明确尝试JesFs移植；第18篇说明为学习目的编写HCFileSystem，并学习JesFs的层次划分。两阶段分别记录。
- 第38篇明确GPIO原始地址为orangepi-xunlong/OrangePiH3_uboot的drivers/gpio/sunxi_gpio.c。对应上游提交、完整许可适用与分发材料待核实。
- 第17篇明确记述ChatGPT解释文件构成与辅助review。其覆盖范围按这篇作者声明记录；整体AI参与范围待核实。

## 检索范围、关键词与访问记录

目标时窗：2024-01-01至2026-10-10，兼顾作者发布历史。主要平台为普通网页搜索、Bilibili公开索引、GitHub原始仓库及知乎入口。

执行的发现搜索：
- site:bilibili.com/video 自制 操作系统 内核 2025 Github 国产
- site:bilibili.com/video 自制操作系统 2026 github，排除已深入项目
- 自制内核 2025；自制操作系统 github 2025；自制操作系统 中国
- icestaros github；icestaros 国产；icestaros 作者；OrangeOS c语言大虾
- Uinxed Kernel bilibili
- 自制操作系统 2025 开源
- GitHub仓库：“操作系统” “自制” created:2024-01-01..2026-10-10，读取首50项结果
- HuangCheng72；HOS HuangCheng72；HOS 1776978835558858752；HuangCheng72 bilibili

HOS与Haoyu-1231/HelixOS曾在筛选阶段读取README；后者返回404，停在筛选。HuangCheng72个人README明确中国归属后，深入范围收束到HOS。其他命中作为发现路线保存，正式与待核对象均围绕同一个HOS。

普通网页读取GitHub作者页面和知乎专栏出现cache miss／内部错误；GitHub原始文件工具成功取得作者固定个人README及项目材料。GitHub tags集合URL返回工具路径校验错误，随后使用受支持的Git标签引用只读端点取得空集合。

本轮使用普通网页和GitHub只读读取，静态资料按原始来源整理。源码构建、镜像启动及硬件操作留待独立验证。

## 静态检查与遗漏风险

- 正式数组长度1，ID唯一；pending数组长度1且关联相同entry_id。
- 35项source ID全部闭合；HTML引用锚点完整且唯一。
- 页面复用既有TextOS的header／main／footer结构和../style.css，返回链接使用中文域名。
- 公开正文按肯定式陈述；缺口使用“待核实”。
- JSON解析通过；项目源码独立构建及执行保持待核实。

主要遗漏风险：GitHub搜索首50项与B站索引覆盖、同名HOS的噪声、知乎正文读取、原视频与原图取得、Git作者日期与实际公开日差异、四平台阶段差异、源码默认构建目录完整性、教学与第三方组件的精确许可及版本对应。

本轮有限收束为一个真正新项目；下一步围绕该条目的字段补齐，优先处理原始发布日期、构建目录对应、各平台运行及第三方来源。

