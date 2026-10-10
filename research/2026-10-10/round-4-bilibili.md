# 第四轮Bilibili候选核验：Chinese++与SZ语言

核验日期：2026-10-10（UTC）。研究时段约15:59—16:08 UTC。范围为Issue #11的两条指定原视频、原作者公开评论、链接到的官网及GitHub资料。本轮采用公开网页、原视频与源码静态阅读。

## 结论

- Chinese++具备中文语法、作者来源链、实际编译器补丁和发行记录，本轮新增收录1项。Windows、Linux平台线与Afiredream同源分叉按一个项目整理。
- SZ语言已确认原发布账号、Beta1.0标题、Python实现自述及编辑器演示。原片实际语言示例可读到英文var和SC库访问写法；中文关键字和中文控制结构证据列为待核实。本轮将其留在Issue #11。
- Chinese++条目编号为lang-046。

## 基线与防重

核对资料：
- [AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/AGENTS.md)，SHA ab8038fa86c6ff04320372eea00cee9c5fd54cca。
- [data/languages.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/data/languages.json)，SHA 8c1596aaa26a0e1cd36f5828256b6666ba849260，共43项。
- [Issue #11](https://github.com/yuyan-lang/chinese-programming-languages/issues/11)正文及全部1条评论；[评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/11#issuecomment-6099298963)记录容语言已收录，Chinese++官网待身份关联。
- research/2026-10-10的round-3.md、round-3-bilibili.md、round-3-design.md、round-3-existing.md、round-3-kernels.md。两组候选及已有仓库链接参与全文防重。
- 当前43项的名称、aliases与references中，两条指定候选均属于待研究对象。Chinese++的多个平台仓库按作者资料合并。

公开表述采用直接肯定陈述；功能、作者声明和资料缺口分别记录。

## Chinese++：原视频、作者与官网关联

原片：[BV1g6a46kEjx](https://www.bilibili.com/video/BV1g6a46kEjx/)。
发布账号：[-Logic-罗辑-，UID485953759](https://space.bilibili.com/485953759/)。
原视频标题为“中文编程，我已经实现了，现代最强Chinese++ vs 史上最强易语言”。

原简介直接提供：
- https://github.com/YoloLogic/ChinesePlusPlus
- https://github.com/YoloLogic/ChinesePlusPlus/releases/latest

简介同时标注Chinese++ 0.1，并给出包含“#包含”“整数”“主函数”“返回”的完整小程序。00:13暂停画面显示中文预处理及主函数代码；该帧用于视频来源复核。结构化条目的逐字短例采用固定GitHub文件，便于逐字符核验。

公开置顶评论来自同一UID485953759，内容为https://logicyolo.com/，页面显示2026-10-09 19:30。官网[关于](https://logicyolo.com/about#%E4%BD%9C%E8%80%85)明确署名YoloLogic（张永乐），并链接https://github.com/YoloLogic。原片、原作者置顶、官网署名和仓库所有者形成同源链。

### 日期与版本

- Windows仓库created_at：2026-09-26T20:55:50Z。
- [Windows v0.1](https://github.com/YoloLogic/ChinesePlusPlus/releases/tag/v0.1)首次published_at：2026-09-26T21:18:27Z；其当前资产更新于2026-10-05，Release另说明后续重打。发行首次时间与当前附件时间分别记录。
- 原片video:release_date：2026-09-26T23:16:16.000Z。北京时间为2026-09-27 07:16:16；浏览器客户端页面显示2026-09-26 16:16:16。本记录采用带Z元数据并明确时区。
- [Windows v0.3](https://github.com/YoloLogic/ChinesePlusPlus/releases/tag/v0.3)：published_at=2026-10-09T07:26:25Z。
- [Linux v0.3](https://github.com/YoloLogic/LinuxChinesePlusPlus/releases/tag/v0.3)：published_at=2026-10-09T14:20:40Z。
- [Linux v0.4](https://github.com/YoloLogic/LinuxChinesePlusPlus/releases/tag/v0.4)：published_at=2026-10-10T02:54:50Z；发行标题里的日历日期写2026-10-09，结构化条目采用GitHub带Z发布字段。
- 语言更早公开日期待核实。

### 固定原例

[Windows示例.cpp第23—28行](https://github.com/YoloLogic/ChinesePlusPlus/blob/8a528b432a6df276dbe095a97adc868ae4831eac/vscode-kit/%E7%A4%BA%E4%BE%8B.cpp#L23-L28)的连续原文：

```cpp
双精度 合计(常量 std::vector<商品>& 货物) {
    双精度 和 = 0;
    对于 (常量 自动& 件 : 货物)      // 对于 = for，自动 = auto
        和 += 件.单价();
    返回 和;                        // 返回 = return
}
```

文件blob为1b99ebc8355aa6edaa670745f75c4843c42747da。该函数使用前文商品类型及vector导入；缩进、注释、空格保持原文。运行验证待核实。

### 实现与源码覆盖

Windows固定main：8a528b432a6df276dbe095a97adc868ae4831eac，2026-10-09T12:28:59Z。
Linux固定main：006ff08ebf22f7040f163f2c9192d67c5c26cae8，2026-10-10T03:19:09Z。

Windows固定递归树含517项，truncated=false；公开材料包括发行二进制、库头、脚本和示例。Linux固定递归树含2,893项，truncated=false；包括编译器补丁、生成器、测试、文档和打包资料。核心修改证据采用Linux公开补丁：

- [中文关键字表](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/patches/zh-keywords.patch#L285-L292)：对于、如果、整数、返回等映射。
- [词元注册](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/patches/zh-keywords.patch#L803-L819)：AddKeyword注册到tok::kw_*。
- [入口映射](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/patches/zh-keywords.patch#L890-L893)：主函数映射main。
- [预处理映射](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/patches/zh-keywords.patch#L855-L861)：中文指令映射pp词元。
- [诊断选择](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/patches/zh-diagnostics.patch#L23918-L23931)：按编号取得中文正文、英文回退及开关。
- [Windows中文向量库](https://github.com/YoloLogic/ChinesePlusPlus/blob/8a528b432a6df276dbe095a97adc868ae4831eac/zhstdlib/%E6%A0%87%E5%87%86%E5%BA%93/%E5%90%91%E9%87%8F#L3998-L4017)：名域、模板、类型、公开、使用等实际代码。
- [Linux README](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/README.md#L1-L13)：明确关联Windows线，说明两边分别演进。
- [Afiredream元数据](https://api.github.com/repos/Afiredream/ChinesePlusPlusCompiler)：fork=true，parent/source均YoloLogic/ChinesePlusPlus；其分支头62a9384017ee397e6cc5cd71988fdc527880a8a6属于官方历史提交。

上游完整LLVM基线、补丁重放、发行资产与源码对应性、跨平台行为和性能属于后续核验范围。Linux v0.4发行说明按自身libstdc++环境记录中文库层覆盖；Windows中文复制层和Linux中文别名层分别描述。

### AI与许可

[官方补丁第322—328行](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/patches/zh-keywords.patch#L322-L328)记录将class译为“类型”的决定源于与其他AI的对话。[译名清单](https://github.com/YoloLogic/LinuxChinesePlusPlus/blob/006ff08ebf22f7040f163f2c9192d67c5c26cae8/docs/%E5%85%B3%E9%94%AE%E5%AD%97/%E5%85%B3%E9%94%AE%E5%AD%97%E6%94%B9%E5%8A%A8%E6%B8%85%E5%8D%95.md#L395)提供同样记录。因此AI参与范围可确认到译名讨论，核心代码生成和贡献比例待核实。

[LICENSE](https://github.com/YoloLogic/ChinesePlusPlus/blob/8a528b432a6df276dbe095a97adc868ae4831eac/LICENSE)把0.3起的原创部分置于自定义source-available条款，规定内部修改与再发布范围；LLVM、MSVC等派生部件按各自许可。项目许可存在组成范围，条目采用混合许可事实。个别新增表头与整体许可分区的精确适用关系待核实。

### 版本差异

- 官网首页与v0.3发行说明采用bundled工具链描述；官网Chinese++概览仍保留安装Visual Studio Build Tools的旧要求。条目依据对应版本发行资料。
- Windows README记录26项自测，固定verify.ps1和v0.3发行说明记录29项；独立运行结果待核实。
- 文档与Linux实际补丁在诊断总数和DiagnosticParseKinds.td修改范围上有差异。条目采用实际补丁提供的功能证据，数字全覆盖和兼容性结论留待复验。
- Win/Linux关键字数量受运算符、上下文关键字与平台版本分类影响；当前条目按明确语法和词元实现记录。

## SZ语言：中文语法继续待核实

原片：[BV1kJa66eErd](https://www.bilibili.com/video/BV1kJa66eErd/)。
发布账号：[不懂python的Jerry，UID3690995380128358](https://space.bilibili.com/3690995380128358/)。
标题：“自制编程语言|SZ语言Beta1.0宣告片”。
简介：“SZ，为每一个编程幻想而生”。
video:release_date=2026-10-01T13:58:03.000Z，北京时间为2026-10-01 21:58:03。浏览器客户端显示06:58:03；本记录采用带Z元数据。

### 原片关键位置

原片总长01:09，本轮逐段定位关键画面：
- 00:04、00:11：功能宣传字幕。
- 00:20：编辑器展示Python实现，窗口构建与界面代码可见。
- 00:25：编辑器展示Python Parser与SZParseError等实现代码，中文位于注释和错误信息中。
- 00:31：文件管理器展示多份.py文件。
- 00:36：Python实现代码画面。
- 00:46：字幕介绍SC系统库。
- 00:50、00:54：SZ IDE中的语言示例可读到英文var及SC库访问写法。
- 00:59：创作者署名画面。

本轮在可见原片取得Python实现与英文语言示例证据。中文关键字、中文控制结构、完整语法规范与逐字可用中文短例均待核实。原片播放器提供的画面为640×360，源码字符较小，完整程序逐字转录留待更清晰的第一方文本来源。

公开热评中，用户建议更换实现语言；同一UID作者明确回复使用Py的原因包括熟悉、简单、便于排查BUG。Python实现按作者自述与视频画面两类证据记录。执行模型、语言版本细节、公开源码入口、AI参与和同源关系待核实。标题Beta1.0按视频版本标签保存，首次公开时间待核实。

评论区显示7条评论、6条回复入口；未登录可见作者上述回复，其余讨论需登录。完整讨论范围待核实。

## 有限后续线索

本轮仅记录入口和状态，后续深查按新批次安排：
- [ChineseTypeScript官网](https://logicyolo.com/chinese-typescript/)：页面显示0.1及“如果、常量、字符串”的中文例子，宣称基于microsoft/typescript-go。下载、实现及发布状态待逐项核对。
- [ChineseJava官网](https://logicyolo.com/chinese-java/)：页面明确为计划中的OpenJDK语言链，当前处于占位与准备阶段。它的实际中文编译实现、仓库及发行物均为待核实项。
- [官网作者页](https://logicyolo.com/about#%E4%BD%9C%E8%80%85)为上述同作者归属入口。
- SZ原片推荐位出现[“中文编程？不一样的体验！”BV125up6eEdA](https://www.bilibili.com/video/BV125up6eEdA/)，发布账号抽空抽象抽象层（UID489636691）。本轮仅记录标题级候选，原片语法、语言名称与归属待核实。
- Chinese++原片推荐位出现[“中文编程元语言更新进展”BV1duhd6aEsJ](https://www.bilibili.com/video/BV1duhd6aEsJ/)，为现有元语言作者遽火的资料补充，按既有条目线索处理。

## 实际检索平台、关键词与时间范围

- GitHub接口：直接读取目标百科AGENTS、语言目录、Issue #11和全部评论、5份round-3日志；读取YoloLogic两个C++仓库的固定文件、完整树、发行及历史元数据，并核对Afiredream分叉。
- GitHub仓库搜索：精确关键词“SZ语言”“不懂python的Jerry”，本轮均返回空数组。
- 公共网页搜索：\"Chinese++\" \"-Logic-罗辑-\"；\"SZ语言\" \"不懂python的Jerry\"；\"logicyolo.com\"；\"BV1kJa66eErd\"；\"SZ语言\" 编程；\"不懂python的Jerry\" 语言。
- Bilibili公开网页：两条精确BV、原作者链接、简介、公开置顶/热评及带Z发布日期元数据；视频按上述关键时间点检查。
- 作者官网：logicyolo.com首页、/about、/chinese-plusplus/，并有限查看/chinese-typescript/和/chinese-java/以记录后续入口。
- 查询未设置搜索时间过滤，证据集中于2026年9—10月。仓库版本与视频发布日期按对应来源分别记录。

## 覆盖限制与遗漏风险

- 公共网页搜索对精确BV和两个新项目的索引有限，返回内容以无关同名词为主；作者直接链接与原始仓库形成主要证据。
- Bilibili未登录公开评论仅覆盖页面展示部分。Chinese++显示73条评论，SZ显示7条评论；登录可见内容可能另含源码、发布或AI说明。
- 原片采用关键段抽查；360p画质影响逐字抄录，代码引用优先采用固定仓库原文。
- 页面时间字段存在时区显示差异；本记录保留带Z元数据和北京时间换算。
- 仓库平台线、分叉及版本分开识别；同名ChineseCpp、ChinesePlusPlus项目的作者关系依来源链核对。
- 本轮完成资料核验；安装包内容、实际构建、性能与完整行为均为后续验证范围。

