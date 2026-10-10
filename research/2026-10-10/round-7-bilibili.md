# 第七轮 Bilibili 中文语言发现日志

- 核验日期：2026-10-10，UTC。
- 基线：yuyan-lang/chinese-programming-languages，main 固定提交 `697f78bd2d10a85a0c0c8cce9444bf03bdbf415a`，55项正式目录。
- 已先读：AGENTS.md、README、data/languages.json、research/2026-10-10/round-6.md、开放Issues及Issue #4讨论；同时参考第五、六轮B站日志与候选，排除重复。
- 范围：主动寻找2024—2026年中文语言、微型实现和视频项目，最多深入两项。豫言本身排除。
- 本组计数：新发现并深入候选2项；正式条目建议1项（灵创语言）；待核实1项（Californium-252未命名中文编译器）。标题级检索旁支仅保留线索，未计为已发现语言。
- 方法：普通网页搜索、GitHub连接器只读、dot云浏览器访问原视频、公开主页和Gitee源码网页。未创建编码任务，未使用用户电脑，未下载或运行代码、发行物，未向外部服务写入。

## 1. 新发现：灵创语言

### 1.1 原站元数据与语言画面

主来源：[灵创汉语编程编译器发布](https://www.bilibili.com/video/BV1Lvd8YoEjp/)。发布账号：[自研编译器与IDE](https://space.bilibili.com/476787042/)，UID476787042。

- 原页meta `video:release_date`：`2025-04-12T09:13:44.000Z`，北京时间2025-04-12 17:13:44。
- 原片长度155秒，2分35秒。
- 原简介说明文件已上传群642130808，并称VSCode插件与旧版IDE已开源。
- 作者主页公开简介所列项目群为624826263。两个群号按各自原页记录。
- 原片00:28、00:45.497、01:00.489均检查过代码画面，编辑器显示`示例.lcc`。
- 清晰的连续常量原例：

```text
常量 MU = 1
常量 MR = 2
常量 MD = 3
常量 ML = 4
```

- 同画面可见`定义 文本1 作为 字符串`和文本2声明，展示中文语法、类型及标识符。字符串和长打印语句的标点采用保守转录，正式条目代码选用可逐字读取的源码原例。
- 01:00.489画面中的说明文字称编译器已更新至1.12；按视频阶段版本记录。

同UID补充原来源：

- [灵创汉语编译器：内联汇编与别名](https://www.bilibili.com/video/BV1gNd8Y7EPi/)，原页显示北京时间2025-04-12 17:27:12。
- [灵创汉语编程支持x64所有库和IDE开发环境开源](https://www.bilibili.com/video/BV1eZjxz4EyQ/)，meta时间`2025-05-23T23:56:47.000Z`，北京时间2025-05-24 07:56:47；61秒。其简介提供网盘与群624826263，网盘未打开、未下载。x64与开源范围按作者声明记录。
- [重构：跨平台汉语编程及设计器](https://www.bilibili.com/video/BV1dLN3eFEhw/)，原页显示北京时间2025-02-08 17:34:54，78秒；简介群624826263。此视频标题和简介构成早期项目线索，正式语言首发仍留待核实。

### 1.2 公开Rust源码与生态对应

由Gitee检索结果追至[xb880727主页](https://gitee.com/xb880727)，其显示名为“灵创Compiler maniac”。公开仓库包括：

1. [rust-Compiler／rust中文编程编译器](https://gitee.com/xb880727/rust-Compiler)，浏览时main指向`b929b09e60e08dc62d62345e0da00dbcc35bff52`，描述为Rust语言编写的编译器。公开test_basic.cn含“让 年龄 = 25”等中文程序。
2. [rust---LingChang-Compiler](https://gitee.com/xb880727/rust---LingChang-Compiler)，main固定提交`e1b16b226feb81a353894175d1a120727c4473ed`。README明确称项目属于“LingChang Language（灵创语言）”生态，署名“灵创-浪漫之夏”，给出群624826263。该群号与B站主页一致。
3. [KCL](https://gitee.com/xb880727/KCL)，主页卡片称“空灵语言官方开发环境和编译器”。本轮仅保留同账号关联，未深入第三项目。

正式条目固定到第二个仓库提交。网页逐字读取的文件如下：

- [test_basic.cn](https://gitee.com/xb880727/rust---LingChang-Compiler/blob/e1b16b226feb81a353894175d1a120727c4473ed/test_basic.cn)：完整七行中文原例。
- [Cargo.toml](https://gitee.com/xb880727/rust---LingChang-Compiler/blob/e1b16b226feb81a353894175d1a120727c4473ed/Cargo.toml)：包名chinese-programming-lang，0.1.0，Rust edition 2021；二进制cnlang；description列“浪漫之夏”与同群号。根目录及文件历史的0.15标注与Cargo版本分别记录。
- [src/lexer.rs](https://gitee.com/xb880727/rust---LingChang-Compiler/blob/e1b16b226feb81a353894175d1a120727c4473ed/src/lexer.rs)：直接匹配“如果、否则、循环、当、对于、在、函数、返回、让、常量、变量、跳出、继续、且、或、非、真、假”等词，分别映射到TokenType。数组相关几个匹配项被注释，未据此计为功能。
- [src/main.rs](https://gitee.com/xb880727/rust---LingChang-Compiler/blob/e1b16b226feb81a353894175d1a120727c4473ed/src/main.rs)：`Lexer::new→tokenize→Parser::new→parse`后，解释执行分支使用`Interpreter::new/execute`，编译分支使用`CodeGenerator::new/generate`。
- [src/code_generator.rs](https://gitee.com/xb880727/rust---LingChang-Compiler/blob/e1b16b226feb81a353894175d1a120727c4473ed/src/code_generator.rs)：`OutputType::CSource`写出生成C代码；Exe、Dll、Object分支亦先生成C，再调用MinGW GCC。源码把Windows本机GCC路径写为固定字符串。跨平台适配与运行结果待核实。

精确原例：

```text
// 变量声明
让 年龄 = 25
让 姓名 = "张三"

// 打印变量
打印("你的年龄是: " + 年龄)
打印("你的姓名是: " + 姓名)
```

分类：中文通用语言生态；公开Rust路线为AST解释器及C转译编译器，编译产物由GCC生成。语言、IDE与编译器版本分别描述，.lcc与.cn两个阶段语法分别记录。中文关键字在词法器中直接有实现，原例含中文语法结构。

### 1.3 核验分层与缺口

- 作者声明：README将Rust项目归于灵创生态；视频称VSCode插件、旧版IDE以及后续x64库／IDE开源。README有MIT字样及LICENSE链接。
- 独立静态核验：公开源码文件可读，test_basic.cn、中文词法表、AST入口、C生成和GCC调用与上述记录一致；原视频实际有.lcc中文代码画面。
- 独立运行：本轮遵守只读范围。构建成功率、示例执行、跨平台运行与性能待核实。
- 许可：公开根目录文件列表未见LICENSE，MIT按README声明记录，授权范围待核实。
- 同源关系：Gitee项目名称、README自述与相同公开项目群建立生态联系；.lcc与.cn兼容性、核心代码继承与作者个人身份映射待核实。
- 后续同UID的sblang相关视频与同Gitee账号KCL仅为沿革线索，本轮未合并为独立新语言或断言兼容。
- AI参与：语言核心开发是否使用AI待核实。
- 第三方Nick文章将自己的页面标为“官网地址（仿制）”，本轮采用原B站和Gitee来源，未将该仿制页面用作官网。

## 2. 新发现待核实：Californium-252未命名中文编译器

主来源：[整活——自制中文编程语言编译器](https://www.bilibili.com/video/BV1bm421x7AK/)。作者：[Californium-252](https://space.bilibili.com/3494354284972407/)，UID3494354284972407。

- 原页meta `video:release_date`：`2024-04-20T10:11:27.000Z`，北京时间2024-04-20 18:11:27。
- 时长164秒，2分44秒。
- 作者标题和简介称自己写了中文编译器，表示以后介绍原理。原页未提供清晰正式语言名称。
- 00:34.737：中文类型声明画面可见整数、字符、布尔、列表及真值。
- 01:30.296：完整两行循环原例，按画面转录并整理缩进：

```text
for循环 x 在 列表([1,2,3,4,5,6,999]):
    标准输出(x)
```

- 02:08.679：完整两行输入／输出原例：

```text
输入内容 : 字符串 = 标准输入("请输入内容:")
标准输出("你输入的内容是:"+输入内容)
```

- 02:43.189：终端执行画面显示`./compiler 函数.zh`，下一行输出55；当前目录提示符显示`zhpy`。该观察支持.zh源文件及作者运行演示。
- 00:44、00:49、01:48等画面含正在编辑的未完成表达式，正式代码取完整连续片段。

现有条目周蟒／zhpy为gasolin维护的Python中文语法转译项目，其[固定中文关键字实现](https://github.com/gasolin/zhpy/blob/f4d932a5ab810158ef4e4113df337cbf7d83817a/zhpy2/zhpy/plugcn.py#L34-L93)已有目录记录。原视频的zhpy目录产生同源关系核验需求；语法差异本身不足以排除其可扩展关键字机制。

本轮决策：中文语法实证成立；独立条目身份待核实。正式名称、compiler来源及与gasolin/zhpy的关系是待核实重点。源码公开状态仅作为证据层级记录。若后续作者说明证明独立实现，即可按微型语言或中文翻译层分类；若确认派生，则补充周蟒实现／生态关系。

同作者推荐视频仅作线索：[用中文写C++](https://www.bilibili.com/video/BV1AJ4m1p7d7/)、[汉语拼音写C语言编程代码](https://www.bilibili.com/video/BV1tm4y1p7wb/)。本轮未核读其实现，未据此合并项目。

## 3. 本轮主动搜索记录

### 3.1 轮换关键词

公开网页搜索：

- `site:bilibili.com/video "手搓编译器" "中文"`
- `site:bilibili.com/video "自制编程语言" "中文" "2026"`
- `site:bilibili.com/video "AI写编译器"`
- `site:bilibili.com/video "全中文代码" "语言"`
- `"中文解释器" "bilibili"`
- `"手搓" "中文编程"`
- `"中文编程" "发布" "2026" "哔哩哔哩"`
- `"中文编程" "2025" "自制"`

云浏览器B站站内搜索第一页：`中文解释器`、`自制编程语言 中文`、`手搓编译器 中文`、`AI写编译器 中文`、`全中文代码 语言`。页面按搜索相关性读取，2024—2026为核验重点；未声称穷尽全部投稿。

发现路径：广搜遇到Californium原视频和灵创发布视频后，分别核验原视频；灵创再沿公开项目名和群号追至Gitee源码。仓库精确查重未见两项已入55目录。公开Issues核对未发现直接收录这两个原BV的现有条目。

### 3.2 标题级旁支，供后轮轮换

以下仅检索结果标题与作者卡片，语法、年份或项目独立性仍需原来源核实；本轮两项深入额度已用完：

- BV1N8aU6fE4f，《我终于设计了一个自己的编程语言》，整活大师1，UID1911926597；结果显示10月2日，年份待核实。
- BV1ejtj6CEbw，QuarkLang自制高性能高并发编程语言，500000马克的面包，UID3546644876364544；原语法待核实。
- BV1UFhn6QEvk，自制语言解释器NodeVM3.7发布，三氯酸蔗糖，UID3632320380668622；原语法待核实。
- BV19F5k6VEED，中文GO语言代码编辑器，唐姝，UID28695954；语言／编辑器／翻译层身份待核实。
- BV1qwtg6fEAA，lingbuilder中文代码入门，灵码LingBuilder，UID3493136793864460；原语法及实现待核实。
- BV1VKhhzBEDm，openZSY2.0抢先体验，虚拟机vmware，UID3546620085930082；检索卡日期2025年8月2日，原语法及易语言关系待核实。
- 2023年“js做一个中文编程语言”BV1PT41127DE及“炫语言”BV1KM411h7KK属于窗口外线索，未深入。

### 3.3 查重与旧Issue

- 本轮命中若干既有语言或往轮候选，包含容语言、明语言、Chinese++、玄铁、VcnStudio、甲辰Lang、星端IDE、SZ、PandaM；仅作为去重结果。
- BV125up6eEdA已有Issue #16线索，本轮未重复深入。
- Issue #4 如意III BV1GC4y1k7E8本轮读取已有讨论。两项新发现完成后按父任务要求收束，未新增原视频核验；如意III旧如意／REIDE关系仍保留原待核状态。

## 4. 访问情况及交付

- 原视频和作者主页均通过dot云浏览器公开界面读取。播放、暂停及定位时间用于画面核验。
- Gitee公开仓库和固定提交blob页面可读；commit详情页面转登录，研究停止于公开页面，无登录或绕过。
- Gitee原文件使用公开代码区文本读取，未调用隐藏接口，未下载仓库。
- 搜索时B站页面查询框曾未正确刷新，通过观察到的站内搜索地址重新打开；浏览器一次连接中断后重新读取公开页面恢复。均未影响最终原来源证据。
- 交付：round7-bili-entry.json（数组1项，无ID）；round7-bili-pending.json（数组1项）；本日志。
- 新发现2项、正式1项、待核实1项的计数按本组深入核验范围计算。
