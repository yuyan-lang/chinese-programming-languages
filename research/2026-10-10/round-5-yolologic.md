# 第五轮：YoloLogic 的 ChinesePython 与 ChineseTypeScript

核验日期：2026-10-10（UTC）。

## 结论与范围

- ChinesePython（YoloLogic）具备官方中文程序、关键字手册、发行记录和公开库层／报错层实现，按CPython中文方言及本地化发行工具链整理为1项。Windows ChinesePython与LinuxChinesePython按官方同源声明合并；核心解释器修改和精确构建对应保留为待核实项。
- ChineseTypeScript具备固定原始程序、中文词法表、解析与JavaScript输出实现、官方发行及上游基线，按TypeScript中文方言工具链整理为1项。
- 本组共整理2项收录记录。现有中蟒lang-013保持2002年SourceForge身份。Chinese++ lang-046保持第四轮的独立条目。
- 研究始于当前46项语言目录、AGENTS.md、第四轮总结、Issue #16及其1条评论；本轮采取公开网页与GitHub只读静态核验。执行、安装、构建、性能及作者自测结果均继续列为待核实。

## 1. ChinesePython（YoloLogic）

### 固定来源、名称与平台关系

- [Windows固定main](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/README.md)：`ad29d1cddae32e8d7a550ba022471dfead835d9c`，提交时间2026-10-09T12:52:28Z；仓库创建时间2026-09-28T20:13:00Z，pushed_at为2026-10-09T12:54:21Z。
- [Linux固定main](https://github.com/YoloLogic/LinuxChinesePython/blob/bafe42513e12eff00dbee02d57ebbffb5dcf58aa/README.md)：`bafe42513e12eff00dbee02d57ebbffb5dcf58aa`，作者时间2026-10-10T08:29:57Z、提交者时间2026-10-10T08:32:46Z；仓库创建时间2026-10-09T13:40:44Z，pushed_at为2026-10-10T08:32:50Z。
- GitHub两仓均返回fork=false、archived=false。Windows完整递归树4582项、Linux2164项，truncated均为false。
- Linux README第4—5行把该包写为ChinesePython 0.1.1的Linux x86-64直接可用构建，并声明与Windows版同源。因此两平台合为一个语言项目，平台版本与包装分别记录。
- [作者仓库简介](https://api.github.com/repos/YoloLogic/ChinesePython)主动介绍2002年同名项目，并把2026项目称作第二次实现。本轮按YoloLogic身份保存现代项目；原SourceForge中蟒lang-013继续独立。代码继承关系待核实。
- 作者采用YoloLogic署名，旧标签LICENSE-MIT也标注Copyright (c) 2026 YoloLogic。真实姓名关联沿用第四轮已核验的[官网作者页](https://logicyolo.com/about#%E4%BD%9C%E8%80%85)及Chinese++身份链。本轮官网访问结果见检索记录。

### 实际中文程序与实现证据

[README第20—25行](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/README.md#L20-L25)是完整连续原始代码块，blob为`e1eba9838f66ab425d3d0ce914763b3e221c2cc8`。原例依次导入操作系统和并行.futures，定义平方，使用线程池并执行中文列表推导。收录JSON逐字保存这6行及4空格缩进。

[用户手册](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C.md)的关键字表明确列35个硬关键字和3个软关键字：如if→如果、def→定义、return→返回、for→对于、in→属于、with→使用；软关键字match→匹配、case→情形、type→类型别名。硬关键字和软关键字按原手册分别记录。

[NOTICE](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/NOTICE.txt)披露CPython词法／语法修改、中文内置与异常别名、中文库和中文报错层；[LICENSE-SCOPE](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/LICENSE-SCOPE.md)列出开发树中的Parser、Grammar相关组件及生成器路径。公开发行树保存bin、Lib、include及配套资料，Parser／Grammar／Python／Tools核心源码路径查询结果为空；开发仓入口和核心实现继续待核实。对可能的YoloLogic/Python仓库请求返回404；账号仓库搜索返回10个公开仓库。

可直接实读的实现：
- [Lib/操作系统.py](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/Lib/%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F.py#L1003-L1165)：文件头说明从os.py生成，表内“取当前目录”指向getcwd；第1137—1139、1163—1165行用globals().update建立两向名字转发。项目库层按副本、薄包装与别名资料说明。
- [Lib/zh_traceback.py第27—39行](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/Lib/zh_traceback.py#L27-L39)：读取CHINESEPYTHON_ERRORS，处理zh／en／both三种显示模式；后文按译文表匹配错误正文。
- [include/patchlevel.h第18—28行](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/include/patchlevel.h#L18-L28)：版本宏标注3.14.7。
- [官方CPython v3.14.7标签接口](https://api.github.com/repos/python/cpython/git/ref/tags/v3.14.7)返回标签对象`dccefbc14adf6cd13693f3b6b2802945c4e23e01`；ChinesePython的精确上游基线及完整差异仍待核实。

### 版本、构建身份与许可

- 现存Windows根提交`f176719e0eea089ddaa013d813083f88fb7f6aa1`，日期2026-10-05T06:33:30Z，parents为空。现存20条提交完整返回。
- [v0.1](https://github.com/YoloLogic/ChinesePython/releases/tag/v0.1)发表于2026-10-05T07:30:38Z；当前资产创建时间为2026-10-06，发行建立时间与附件时间分别保存。
- [v0.1.1](https://github.com/YoloLogic/ChinesePython/releases/tag/v0.1.1)发表于2026-10-07T08:29:00Z，当前所列5个附件在当日08:28左右上传。标签接口把v0.1.1指向`2ba64af3fe1b7f9b56906614834847e617c83877`，该提交日期2026-10-06T09:03:29Z，说明为“发行0.1.0”；实际“发行0.1.1”提交为10月7日`f6850d9309fecb601f59cacbac71845c5c71380d`。资产、标签、源码的对应性待核实。
- [linux-v0.1.1](https://github.com/YoloLogic/LinuxChinesePython/releases/tag/linux-v0.1.1)发表于2026-10-09T13:43:11Z，标签指向根提交`ead4ad5b3a12991642347ac98594e93b4c71b13a`。README说明Ubuntu 24.04构建、glibc≥2.39、系统Tcl/Tk 8.6等要求。[实际资产接口](https://api.github.com/repos/YoloLogic/LinuxChinesePython/releases/407954828/assets)返回空数组；发行文字中的tar包及其校验和继续作为作者发布说明保存。
- [Windows构建数据](https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/Lib/zh_buildinfo_data.py)身份为`73da4c3ea6fe6978181956095bcdd087b019358bdec62848aed2f38f8a5b891a`；[Linux构建数据](https://github.com/YoloLogic/LinuxChinesePython/blob/bafe42513e12eff00dbee02d57ebbffb5dcf58aa/lib/python3.14/zh_buildinfo_data.py)身份为`86569b93598f742aea6b82aba97f84069487744e402d6acac76083398d5807da`。两份开发仓HEAD及生成器哈希也有差异。Linux README仍列前一身份，最新提交另记Lib同步待完成。因此“同源”用于项目关系，逐字节构建一致性待核实。
- [2026-10-09许可切换提交](https://github.com/YoloLogic/ChinesePython/commit/9e724d23cd8898a7ca39b599769778b7c636939d)新增自定义LICENSE、LICENSE-SCOPE、TRADEMARK及第三方披露；当前主分支将原创部分列为源码可见，CPython派生部分列PSF。历史v0.1.1标签实读仍有[LICENSE-MIT](https://github.com/YoloLogic/ChinesePython/blob/2ba64af3fe1b7f9b56906614834847e617c83877/LICENSE-MIT)。当前README尾段也保留MIT字样，条目以版本化许可记录呈现；具体下载包随附许可待核实。

## 2. ChineseTypeScript

### 固定来源与上游关系

- [固定main](https://github.com/YoloLogic/ChineseTypeScript/tree/8218a6c501ddd503703fe33e4a3d82c49c77b576)：`8218a6c501ddd503703fe33e4a3d82c49c77b576`，提交时间2026-10-10T13:06:21Z；仓库创建时间2026-10-09T14:27:19Z，pushed_at为2026-10-10T13:06:26Z。元数据返回fork=false、archived=false、主要语言Go。
- 实际项目介绍位于[README-我们的说明.md](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/README-%E6%88%91%E4%BB%AC%E7%9A%84%E8%AF%B4%E6%98%8E.md#L11-L31)，根README.md保存上游介绍。
- 官方说明列上游`microsoft/typescript-go`基线`e26b8d24bee09bf66d59941912166c5aa7975d20`，并介绍浅克隆边界改写后的新根。实读[上游提交](https://api.github.com/repos/microsoft/typescript-go/git/commits/e26b8d24bee09bf66d59941912166c5aa7975d20)及[本仓无父根提交](https://api.github.com/repos/YoloLogic/ChineseTypeScript/git/commits/8b3e2a588fd53f317d763bea69df4587d718d6f3)，二者Git树均为`43c09c14c51d177dfd50e17425e63e09fe6ae1da`。这组成上游派生关系的对象级证据。
- 该根的2026-08-27日期属于上游提交历史。中文关键字首次实现[0e38f235…](https://github.com/YoloLogic/ChineseTypeScript/commit/0e38f235186caabc72daa490db6e361abd0896be)署期2026-10-06T16:00:47Z。首次实现署期、仓库创建、公开发行各自保留。

### 原例、词法、解析及输出路径

- [教程/例子/01-骨架.ts第11—13行](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/%E6%95%99%E7%A8%8B/%E4%BE%8B%E5%AD%90/01-%E9%AA%A8%E6%9E%B6.ts#L11-L13)用“函数”“数字”“返回”定义相加。blob为`f7d6e69d7e5b84b2f09101c50e1ffc4034e92aa3`；与v0.1标签同路径blob相同。收录JSON保留原文、两空格缩进和原注释。
- [zh_keywords.txt](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/scanner/zh_keywords.txt)忽略注释与空行后共85条；[生成表](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/scanner/zh_keywords_generated.go)将中文拼写映射到既有ast.Kind。
- [scanner.GetIdentifierToken第2218—2234行](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/scanner/scanner.go#L2214-L2235)对非ASCII标识符查独立zhTextToKeyword。英文textToKeyword保留原查表路径。
- [scanner.TokenToString第2268—2277行](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/scanner/scanner.go#L2268-L2277)由textToToken反建规范文字表；[printer.writeTokenText第941—950行](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/printer/printer.go#L938-L951)调用该函数写出关键字。中文输入接入TypeScript编译管线，产物目标为JavaScript。
- [parser第5959—5963行](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/parser/parser.go#L5941-L5963)将值位置“未定义”构造为undefined标识符；第5819行另处理简写属性用法。语法位置按实际解析分支区分。
- [printer.emitIdentifierText第1143—1168行](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/printer/printer.go#L1143-L1168)对标准库中文全局名／成员名查表并输出英文名；[Program第2038—2075行](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/compiler/program.go#L2038-L2075)收集用户源码声明过的名称，在输出时保护同名用法。其当前实现为名称集合驱动的保守屏蔽；文档使用的“符号感知”术语在条目中按这段代码具体说明。
- [默认中文诊断入口](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/cmd/tsc/main.go#L36-L51)在未给出locale参数时补入zh-CN；诊断补译表位于tsc/internal/diagnostics/zh_extra.go。语言服务补全另在tsc/internal/ls/completions.go实现。
- [标准库译名TSV](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/stdlib/%E8%AF%95%E7%82%B9-%E6%95%B0%E7%BB%84%E4%B8%8E%E6%95%B0%E5%AD%A6.tsv)当前1827行。README中的100、166等历史进度按其阶段说明理解；当前收录依据固定表计数。
- [2026-10-08调整提交9446f735…](https://github.com/YoloLogic/ChineseTypeScript/commit/9446f735e2a523100a7ef1f998f4e15eee16b0ad)记录从.chts／.d.chts转为普通TypeScript后缀，中文关键字对.ts、.tsx、.mts、.cts及.d.ts生效。中文保留字与标识符的冲突按词法映射带来的语言边界记录。

### 发行与许可

- [v0.1](https://github.com/YoloLogic/ChineseTypeScript/releases/tag/v0.1)发表于2026-10-10T03:34:57Z，标签提交`6bbf6f6090f15298dca57aa5ec75f1e092e3ce8d`署期03:33:56Z。
- 当前资产名ChineseTypeScript-0.1-win64.zip，大小54,197,117字节，GitHub digest为`sha256:3df4ca16460562419a4c767099108de4a47fbf146b8c9eb96302b93bdbe53ee8`。发行说明列编译器chtsc.exe、Node v24.15.0、9个示例、教程及自检文件。二进制内容与执行待核实。
- [core/version.go](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/tsc/internal/core/version.go#L1-L12)记录上游工具链版本变量默认值7.1.0-dev，注释说明构建时可用ldflags覆盖；项目发行版本另为v0.1。
- 最新main位于v0.1标签之后。标签的program.go实读尚为早期blob`34f713918a6ad3453ee8211f6460e20f603ac852`；当前用户同名名称保护与最新回归修复属于后续源码。发行包是否包含后续修复待核实。
- [LICENSE-SCOPE](https://github.com/YoloLogic/ChineseTypeScript/blob/8218a6c501ddd503703fe33e4a3d82c49c77b576/LICENSE-SCOPE.md)与NOTICE将原创汉化表、工具、文档和声明层列为自定义源码可见许可，将typescript-go派生源码／二进制列Apache-2.0，Node等第三方按各自许可记录。与Chinese++、ChinesePython的关系为同作者产品线，各有语言前端和发行身份。

## 3. 检索与覆盖记录

平台：GitHub只读连接器和公开web工具。查询日期：2026-10-10。范围：Issue #16中YoloLogic的两组候选及Linux同源平台线。

实际检索与读取：
1. 目标仓库AGENTS.md、46项data/languages.json、research/2026-10-10/round-4.md、Issue #16及全部1条评论。
2. GitHub查询`user:YoloLogic`，返回10个公开仓库；读取ChinesePython、LinuxChinesePython、ChineseTypeScript的元数据、main分支、Release、tags、目录和固定文件。
3. Windows／Linux Python完整递归树；三个仓库的commit集合；TypeScript按zh_keywords.txt及extension.go路径取历史。
4. web查询`site:logicyolo.com/chinese-typescript`和`"YoloLogic" "ChineseTypeScript"`，返回空结果。
5. web直读https://logicyolo.com/chinese-typescript/、https://logicyolo.com/chinese-python/及https://logicyolo.com/about，返回不可访问；HTTP与www变体也返回不可访问。作者及官网入口沿用第四轮实读证据，本轮主要事实来自固定GitHub原始材料。
6. TypeScript全递归树请求遇到Transport closed，随后按固定root、tsc/internal、scanner、教程、stdlib等目录读取并核对具体文件。全仓覆盖和完整文件数待核实。
7. 本轮下载附件、程序运行和构建重现处于待核实状态。作者测试通过数、兼容性及性能保持作者自述属性。

## 4. 后续待核实

- ChinesePython核心开发仓、词法／解析器实际补丁、精确CPython上游基线。
- Python v0.1.1标签、资产内容、主分支构建身份及Linux元数据之间的对应。
- 各Python发行包随附许可文本及Linux当前tar附件可取得性。
- ChineseTypeScript v0.1二进制与标签对应、后续main修复覆盖、中文标准库名字遮蔽的复杂作用域行为。
- 两项目的跨平台执行、回归、重建及性能。

