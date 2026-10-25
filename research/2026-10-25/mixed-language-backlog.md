# 语言积压资料核验：Issue #16、#22、#26、#40

核验日期：2026-10-25。百科基线3f59f9224b48998b4260b36792fad57ec130ca63，103项语言、11项内核。本记录范围为四项议题及其评论，资料来自本仓研究记录、原仓公开只读接口、公开Git传输和原作者页面。安装、构建、候选程序执行与第三方联系均为0。

本轮新增玄（xuan.ide）1项，补齐既有墨言lang-102的固定原例及Rust实现链。新增ID采用lang-105，集成时统一分配正式数字。豫言条目、内核、其他官网与站点程序保持原样。

## 结果与议题收敛

| 议题 | 已完成范围与本轮变化 | 处理建议 | 剩余实质阻塞 |
| --- | --- | --- | --- |
| #16，7组 | 既有ChinesePython、ChineseTypeScript、Sheng、子语、ChineseCpp共5组已收录；本轮核明ChineseJava为尚未修改OpenJDK的占位计划，SPCNYY公开头与完整树保持原版本 | 保持开放；ChineseJava按作者计划保存范围结论 | SPCNYY原作者连续中文用户程序；ChineseJava形成实际中文语法或原程序后再评估正式收录 |
| #22，10组 | 既有太和、ChineseToyLang、pchinese、MiniLang、zhsc-compiler、chinalang、PyCn、XuYu共8组已分类；本轮确认中文Rust固定头和完整树保持原版本 | 保持开放 | 中文Rust作者连续中文程序；52zwbc组受PR #62取消合并边界约束，等待明确处理指令 |
| #26，墨言 | 补齐固定README逐字对应、词法→解析→AST解释→CLI完整链，核实Cargo版本和Git标签、提交身份与时间 | 本轮资料进入默认分支后可关闭 | 核心收录资料已齐；真实姓名、完整许可正文、精确首发、发行附件与独立运行作为字段待补 |
| #40，两组 | 玄取得固定完整源及编辑器15行原始程序并正式分类；Lua原仓仍为已知版本，公开README显示平台屏蔽 | 保持开放，玄子项完成 | lyzavng/lua原作者连续中文用户程序；其他中文Lua项目的原例需要直接身份链后方可归并 |

复合议题按剩余实质对象保持开放。既有收录项目的精确首发、完整历史、真实姓名或独立运行属于资料字段，依据现有原始中文程序与实现分类完成情况决定议题状态。

### 两项批量议题的全部子项台账

| 议题／子项 | 当前分类与条目 | 本轮处理与实质缺口 |
| --- | --- | --- |
| #16 ChinesePython（YoloLogic） | lang-047，中文CPython项目，Windows／Linux入口合并 | 已收录；版本、上游修改与许可范围按条目保存，当前无收录实质阻塞 |
| #16 ChineseTypeScript | lang-048，中文TypeScript方向 | 已收录；当前无收录实质阻塞 |
| #16 Sheng／结绳 | lang-049，历史中文关键字语言 | 已收录；与tiecode结绳分别保存身份，当前无收录实质阻塞 |
| #16 BV125up6eEdA | lang-051，子语 | 已完成正式名称和原视频身份对应并收录；当前无收录实质阻塞 |
| #16 ChineseCpp（JinSuperOfficial） | lang-101，含ChineseCplus前身的C++别名宏层 | 已由明确后续仓库链接归并；原例与实现限定前身阶段，当前无收录实质阻塞 |
| #16 SPCNYY | Python中文关键词转译层／编辑器候选 | 已核实现；原作者连续中文.spc用户程序待补 |
| #16 ChineseJava | 作者占位计划，尚未修改原始OpenJDK克隆 | 当前范围分类完成；形成实际中文语法和原程序后评估正式条目 |
| #22 太和／TaiHeLang | lang-062，中文编译／解释语言 | 已分类收录；当前无收录实质阻塞 |
| #22 ChineseToyLang | lang-063，早期中文前端与IR实验 | 已按阶段分类收录；当前无收录实质阻塞 |
| #22 pchinese | lang-065，Python中文语法转译层 | 已分类收录；当前无收录实质阻塞 |
| #22 MiniLang（FI0m9ySans） | lang-066，中文AST解释器 | 已分类收录；语言许可与数学库包许可按各自范围保存，当前无收录实质阻塞 |
| #22 zhsc-compiler | lang-069，中文Solidity DSL设计与部分实现原型 | 已按设计／原型分类收录；核心模块缺口按条目保存，当前无收录实质阻塞 |
| #22 chinalang | lang-070，中英双关键字Go AST解释器 | 已分类收录；当前无收录实质阻塞 |
| #22 PyCn（sunzi334481） | lang-072，Python中文转译层 | 已分类收录；当前无收录实质阻塞 |
| #22 XuYu | lang-096，中文赋值关键字与整数表达式的早期Go AST解释器 | 已按当前实现分类收录；控制流与输出属于后续计划，当前无收录实质阻塞 |
| #22 中文Rust | 中文→Rust设计与部分基础模块候选 | 固定头与树保持原版本；原作者连续中文程序待补 |
| #22 52zwbc中文CPython组 | 既有zwpy关联研究，涉及已取消合并PR #62 | 本轮沿用取消操作边界，等待明确处理指令；本轮未复制或变相合入该PR |


## #16：SPCNYY与ChineseJava

已复核[议题正文与全部4条评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/16)、round-4-discovery、round-5、round-5-historical-and-layer、round-25-issue-followup及ChineseCpp后续收录记录。5组既有条目保持原样。

### SPCNYY

2026-10-25通过GitHub连接器重新读取[最新提交集合](https://api.github.com/repos/xs-smz/spcnyy-/commits?per_page=1)、[固定完整树](https://api.github.com/repos/xs-smz/spcnyy-/git/trees/2d9087cade68fff2c966a7bf057141935b439ec0?recursive=1)及[全部Issues集合](https://api.github.com/repos/xs-smz/spcnyy-/issues?state=all&per_page=100)。头仍为2d9087cade68fff2c966a7bf057141935b439ec0，时间2026-08-15T16:46:47Z；树共5项、4文件、truncated=false，Issues返回空数组。文件为README.md、setup/pipe、setup/spcnyysetup.sh、windows_spcnyy.ps1。

本轮新增实证为当前头与树、公开议题仍保持既有边界。已有[language.py L289—311](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L289-L311)与[exec入口L600—618](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L600-L618)支持Python中文关键词转译层；整段替换参与字符串和注释的结论沿用固定源码。作者连续.spc例程仍是实质缺口。搜索SPCNYY、SPCNYY 打印、SPCNYY xs-smz未取得新增原例；搜索排序与未索引作者资料保留遗漏风险。

### ChineseJava

[原作者页面](https://logicyolo.com/chinese-java/)本轮通过公开HTTP成功读取。页面明确记录OpenJDK方向、状态开发中；作者说明本地仅有openjdk/jdk原始克隆，尚未开始修改，公开仓库、安装包、时间表和关键字表均待后续发布。页面列“整数”与int并列拼写作为计划原则。该说明确定当前阶段为占位计划，正式中文语言条目待形成原作者中文语法与连续程序后评估。

页面页脚署名YoloLogic（张永乐）。2026-10-25公开页面为动态来源，本轮保存观察日期；版本、实现与首发沿用待核状态。该范围判断能够完成当前计划阶段的分类，SPCNYY原例缺口继续使#16保持开放。

## #22：中文Rust设计与52zwbc边界

已复核[正文及全部7条评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)、round-7至round-12相关记录与round-26-xuyu。8组已分类条目保持原样。

2026-10-25通过GitHub连接器重新读取[中文Rust最新提交](https://api.github.com/repos/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/commits?per_page=1)、[固定完整树](https://api.github.com/repos/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/git/trees/4605fee9402c9ad6fe6e06771b6d2443105eada8?recursive=1)及[README](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/README.md)。头仍为4605fee9402c9ad6fe6e06771b6d2443105eada8，时间2026-07-03T05:36:32Z；完整树81项、51文件、truncated=false；README blob dc4e9ec235d2e9db1f6f4dfae6ff364c5c71d3c5。

本轮当前来源确认此前“中文→Rust设计与部分基础模块原型”分类继续适用。README为需求、映射和PlantUML流程描述；Rust目录中的cn_types、cn_config基础实现按既有固定研究保存，中文Rust连续原程序仍待核。词法、解析和生成核心模块的补全有助于后续进一步说明能力；正式设计条目的实质前提是作者连续中文程序，完整可运行实现与精确首发分别作为独立证据层级。

52zwbc中文CPython关联组关联PR #62。用户已经明确取消该PR合并，本轮一般积压授权沿用该取消边界。本轮未复制该PR内容、未改写zwpy等条目，也未执行合并或外部写入。关联组继续等待明确处理指令；这个操作边界与中文Rust原例缺口分别记录。PR #62的材料与既有关系核验保持原先状态。

## #26：墨言固定原例与Rust链补齐

### 固定对象与程序

通过原仓正常公开Git传输读取[墨言仓库](https://gitcode.com/moyan_lang/moyan_compiler)，固定master头[a392600d6b324c094b5d82367e4b86e207816b82](https://gitcode.com/moyan_lang/moyan_compiler/commit/a392600d6b324c094b5d82367e4b86e207816b82)。完整树702文件，保留历史319条提交。该头作者与提交者均署名amor2022，时间2026-10-25T23:23:03+08:00。

当前[固定README L233—245](https://gitcode.com/moyan_lang/moyan_compiler/blob/a392600d6b324c094b5d82367e4b86e207816b82/README.md#L233-L245)与此前头[11e036固定README](https://gitcode.com/moyan_lang/moyan_compiler/blob/11e0367837834df1f2fb5655a494b4fda9cdec3d/README.md)均指向Git blob bc3b87978b46731e738e24131a068d5c9de9f8b7。完整13行原例与[2026-10-13原始观察](https://github.com/yuyan-lang/chinese-programming-languages/issues/26#issuecomment-6151455940)逐字相同。正文和原例无需依赖动态分支对应推断。

```text
篇章 你好世界

引言
    注：添加常量
    恒有 问好 者，为 「你好，墨言！」。
毕

正文
    书 问好。
毕

结语
毕
```

### 静态调用链

本节全部源码固定于a392600d6b324c094b5d82367e4b86e207816b82：

- [main.rs L26—49](https://gitcode.com/moyan_lang/moyan_compiler/blob/a392600d6b324c094b5d82367e4b86e207816b82/src/main.rs#L26-L49)：命令参数解析后，run分支调用commands::run_file。
- [commands/run.rs L46—48、L140—179](https://gitcode.com/moyan_lang/moyan_compiler/blob/a392600d6b324c094b5d82367e4b86e207816b82/src/commands/run.rs#L140-L179)：读取源文件，调用Lexer.tokenize、Parser.parse、可选常量折叠和Interpreter.eval。
- [lexer/lexer.rs L845—875](https://gitcode.com/moyan_lang/moyan_compiler/blob/a392600d6b324c094b5d82367e4b86e207816b82/src/lexer/lexer.rs#L845-L875)：篇章、引言、正文、结语、毕、恒有、有、为、者等中文词元；L1015—1016的书／书行为标识符。
- [parser/parser.rs L61—136](https://gitcode.com/moyan_lang/moyan_compiler/blob/a392600d6b324c094b5d82367e4b86e207816b82/src/parser/parser.rs#L61-L136)：解析章节和引言／正文／结语，生成Program节点；L664—692构造ConstDeclaration，L399—400和L2180—2238将书／书行构造为Print。
- [interpreter/interpreter.rs L487—503、L786—799、L1105—1147](https://gitcode.com/moyan_lang/moyan_compiler/blob/a392600d6b324c094b5d82367e4b86e207816b82/src/interpreter/interpreter.rs#L1105-L1147)：依次求值三段语句，保存常量并求值输出表达式。书采用print，书行采用println。

这条完整链支持将lang-102从“项目文档语法核验”更新为“Rust实现的中文AST解释语言”。字节码VM、原生输出、异步、类和标准库的完整覆盖沿用作者说明和模块边界，独立运行仍为待核。本次没有把目录存在等同于全部功能经执行验证。

### 日期、版本、身份和许可

- 保留历史根提交[391cde95985f767a5d57eb6ef67c0ab9f726aa9e](https://gitcode.com/moyan_lang/moyan_compiler/commit/391cde95985f767a5d57eb6ef67c0ab9f726aa9e)，2025-11-30T15:54:44+08:00，署名amor2022。
- [固定Cargo.toml](https://gitcode.com/moyan_lang/moyan_compiler/blob/a392600d6b324c094b5d82367e4b86e207816b82/Cargo.toml)自标包moyan 0.2.0、Rust edition 2021，描述“墨言·文心编程语言编译器”，提供CLI及库入口。
- [v0.1.0](https://gitcode.com/moyan_lang/moyan_compiler/tree/v0.1.0)为附注标签，对象aee2a9f3ad56b1ca250219492c64e7d887266087，标签创建于2025-12-17T01:15:52Z，目标c12a3a486ba6ed96ca859eb62af7eb5d848de5a2的作者／提交时间均为2025-12-16T20:28:07+08:00。原侧栏发行日期2025-12-16与标签时间分层保存；发行正文和附件仍待补。
- 全部319条保留提交作者署名均为amor2022。原仓发布组织与提交者身份链可核，真实姓名及完整团队分工仍待补。
- 固定README声明全部用AI开发、玩具项目、仅Windows测试及部分示例未经测试；MIT声明见L573—575。完整树中的独立许可正文与版权署名待补，Cargo许可字段为空。

#26所需核心语法、固定原例与实现链均已取得，提交完成后可以关闭议题。精确首次公开、真实姓名、完整许可正文、发行附件和独立运行继续在条目字段保留待核，后续补充资料可另行更新。

## #40：玄子项完成，Lua保留原例缺口

### 玄固定来源与连续程序

通过[AtomGit原仓](https://atomgit.com/2301_77161129/xuan.ide)正常公开Git传输取得固定[a1a5d09f534e2e2b1b6f6756b56f6bbb8ddef028](https://atomgit.com/2301_77161129/xuan.ide/commit/a1a5d09f534e2e2b1b6f6756b56f6bbb8ddef028)。唯一提交作者／提交者署名2301_77161129，时间均为2026-09-13T17:18:30+08:00。完整树4文件：

| 文件 | Git blob |
| --- | --- |
| xuan_ide.cpp | 3c9bfa240be504a48ada2f0062a202ded9cd2edb |
| data/help.txt | a4845ffebe42efbcbd5d759ac113e633598ca1dc |
| data/patterns.txt | 738dea00da30d009cef3d78624673fce3ff857c2 |
| data/types.txt | a445a83d6be1e1b74cc78555837518f9ecc2fbf2 |

[xuan_ide.cpp L1468—1484](https://atomgit.com/2301_77161129/xuan.ide/blob/a1a5d09f534e2e2b1b6f6756b56f6bbb8ddef028/xuan_ide.cpp#L1468-L1484)的const char* demo保存完整15行预置程序，相邻C++字符串字面量静态解码如下，末尾换行保留。L1484直接将该程序写入编辑器：

```text
头文件《标准IO》
使用命名空间标准；

主程序：
    重复 3 次《
        输出："hi"：换行；
    》

    整数列表 v = 【10， 20， 30】；
    遍历 x 在 v 中《
        输出："x="：x：换行；
    》

    返回 0；
。
```

[固定实现](https://atomgit.com/2301_77161129/xuan.ide/blob/a1a5d09f534e2e2b1b6f6756b56f6bbb8ddef028/xuan_ide.cpp)中，get_patterns L443—454对外置词表按键长排序；translate_xuan L523起扫描输入，L618—654分别处理双引号字符串、转义标识符、行注释和块注释。L809—862包含重复计次循环生成，后续包含遍历、区间及其他专门分支；L1079—1108应用一般映射与标识符边界。

CompileAndRunTask L1173—1214转译并写output.cpp，通过外部g++ -std=c++17 -pthread和GBK输入／执行字符集参数生成output.exe；L1230—1240在runAfter分支捕获程序输出。上述是作者实现静态证据，独立编译与运行仍待核。依据真实的语言原例与转译链收录为“中文C++转译前端与Win32 IDE”。

同账号[CSDN原文](https://blog.csdn.net/2301_77161129/article/details/165223767)搜索正文已能读取项目说明和完整求和程序，并直接链接该原仓，署名“学习智者”。直接HTTP访问原文返回521。本次条目采用原仓内固定预置程序。原文首次发布时间、版本沿革、许可和AI参与待补。原仓当前Git标签为空，完整树许可正文待补。与lang-044玄语、玄铁按各自作者和仓库保存身份，代码继承关系待原始材料确认。

### Lua 5.4中文版（lyzavng）

2026-10-25[公开根页](https://gitee.com/lyzavng/lua)仍显示c0e0b83、12提交、3分支、0标签和暂无发行；简介仍为Lua 5.4中文版。根README显示平台内容屏蔽，本轮停止该正文读取，沿用既有边界。可见的根许可文本为木兰宽松许可证第2版，源码保留Lua上游MIT的不同层级继续按此前固定记录保存。

2026-10-12已在round-25-issue-followup核到固定llex.c、lparser.c、ldo.c、lua.c、lvm.c、lua.h；本轮使用该已完成的词法／解析／VM结论，原作者连续中文程序仍待补。搜索lyzavng、lyzavng/lua、果真 返回、Lua 5.4中文版 示例只返回原仓和其他作者Lua5.4.6教程等资料；具体作者与版本关系尚待原始互链，原例继续按各自身份处理。#40玄子项完成，复合议题保持开放。

## 待发布评论草稿

### #16

2026-10-25复核：ChinesePython、ChineseTypeScript、Sheng、子语及ChineseCpp五组保持已收录。ChineseJava官网明确目前仅有原始OpenJDK克隆、尚未修改，按占位计划完成当前范围分类；实际中文关键字表、连续程序和实现公开后可继续评估。SPCNYY头仍为2d9087c，完整树4文件、公开Issues为空，作者连续.spc程序仍待补。本议题继续开放，下一步集中于SPCNYY作者原例及ChineseJava新增实际语法资料。研究记录随本轮百科PR提供。

### #22

2026-10-25复核：原十组已有八组完成分类。中文Rust头仍为4605fee，完整树81项／51文件，需求映射、基础模块与CLI状态保持此前记录，作者连续中文用户程序仍为实质缺口。52zwbc关联组继续遵守PR #62已取消合并的操作边界，本轮未复制或变相合入该PR资料。本议题保留开放。

### #26

本轮补齐墨言固定原例与Rust实现链：master固定a392600，旧头11e036及当前头README均为blob bc3b879，13行原例逐字一致。已核Lexer.tokenize→Parser.parse→Interpreter.eval及CLI读文件入口，覆盖篇章三段、恒有常量和书输出。Cargo自标0.2.0，v0.1.0附注标签及2025-11-30根提交分别记录。lang-102已升级为Rust实现的中文AST解释语言。核心收录任务完成，合并本轮资料后可关闭；真实姓名、完整许可正文、精确首发、发行附件与独立运行继续在条目保留待核。

### #40

玄子项已取得原仓固定a1a5d09的完整4文件树，xuan_ide.cpp内15行完整预置程序及中文转译→g++17编译→程序输出捕获链均已核，按中文C++转译前端与Win32 IDE收录，正式编号以本轮PR为准。Lua lyzavng/lua仍保留原作者连续中文程序缺口；原README平台屏蔽边界保持原样。复合议题继续开放，后续集中补Lua原例及其身份对应。

## 验证与访问结果

GitHub原仓优先使用连接器。原作者ChineseJava网页通过公开HTTP成功读取；GitCode／AtomGit页面返回静态外壳后采用平台正常公开Git传输取得固定对象。shell默认网络DNS受限，本轮只读网络请求经既有授权的自动审查允许后执行。无自动审查拒绝。原CSDN直接HTTP 521，网页搜索能够读取；本地浏览器工具报告无可用浏览器，静态原仓资料已足够完成玄和墨言补证。Gitee屏蔽README保持原边界，未尝试其他渠道读取该屏蔽正文。

本轮只改data/languages.json中的lang-102并新增玄对象、对应两份HTML和本研究记录。提交前检查JSON语法、ID唯一、条目与HTML原例／引用对应、全部新增固定来源路径与行号、git diff --check及既有对象保持情况。仓库未配置测试脚本或CI工作流；百科静态结构验证与候选程序执行分别记录。
