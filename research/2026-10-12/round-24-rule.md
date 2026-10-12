# Issue35：Rule DSL Core剩余证据复核

核验日期：2026-10-12，约04:39—04:44 UTC。百科基线1faacdf083f72ed171053a9a948de701179a4bf8（95语言、10内核）；本轮仅更新已收录lang-091，新增语言与内核均为0。读取根AGENTS.md全文、基线lang-091、Issue35正文及全部2条评论（正文comments=2与返回数一致）、第十七轮研究记录及独立审阅。旧18项引用逐项原样保留，新增9项引用；分类、原例及实现主链保持原状。

## 结果

1. 取得三个标签的完整目标提交及秒级绝对时间，明确时间属于目标提交。
2. 取得Gitee v1.0.0发行版的发布时间，并分开记录标签最高语义版本与平台发行版“最新版”标记。
3. 取得固定grammar_test.go、parser_test.go全文，补齐保存测试源码这一证据层级。
4. 固定Kiro实施计划可读；其内容支持开发计划、任务完成声明的记录，AI模型、比例与人工复核范围继续待核。
5. Issue35建议继续开放。下述剩余点具体保留。

## 日期证据及口径

[标签页](https://gitee.com/blizzard1413/dsl/tags)公开展示3项：

- v1.0.0 → b2bbb6742a9c44699ac4ad18eca7a47ee85be43a。标签树头提交时间提示2026-01-06 18:37:26 +0800，即2026-01-06T10:37:26Z。[标签树](https://gitee.com/blizzard1413/dsl/tree/v1.0.0)
- v1.1.0 → ac1d5ef6efb3e96bc475f92c0c0edb3c1743f493。标签树头提交时间提示2026-01-07 14:22:28 +0800，即2026-01-07T06:22:28Z。[标签树](https://gitee.com/blizzard1413/dsl/tree/v1.1.0)
- v1.2.0 → 199a2bac8e5b5dcf68be1e87756b4764b3c74e40。公开根页头提交时间提示2026-01-08 10:59:41 +0800，即2026-01-08T02:59:41Z。[根页](https://gitee.com/blizzard1413/dsl)

标签页日期归在“提交信息”栏，三行均为tag-last-commit。此证据确立标签所指向提交及页面显示提交时间；标签对象tagger date、标签创建或首次推送时间仍待核。标签树页面的时间提示补足秒与时区。

[发行版列表](https://gitee.com/blizzard1413/dsl/releases)当前仅列[DSL Core v1.0.0首次稳定版](https://gitee.com/blizzard1413/dsl/releases/tag/v1.0.0)，标“最新版”，作者显示blizzard，关联b2bbb67。发行页显示2026-01-06 18:41；根页同名发行版旁的日期提示给出2026-01-06 18:41:27 +0800，即2026-01-06T10:41:27Z。将其作为平台发行时间，和v1.0.0目标提交时间分别记录。

原README完成日2026-01-06、Go包目录v1.2.0发布日期2026-01-08及“模块新版本”提示保留旧来源。Gitee标签列表最高语义版本v1.2.0，公开Release列表“最新版”为v1.0.0，平台采用不同对象展示版本。

## 生成产物、测试与AI线索

固定[parser目录](https://gitee.com/blizzard1413/dsl/tree/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/parser)列ast、grammar、doc.go、formatter.go、grammar_test.go、parser.go、parser_test.go及Visitor等文件。目录清单与第十七轮的.gitignore／Taskfile记录保持一致；生成产物正文和构建对应继续待核。

本轮取得两份固定代码页pre.textContent：

- [grammar_test.go](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/parser/grammar_test.go)：L12起TestLexerBasicTokens，L56输入含“变量名”，断言Identifier词元；L209起TestParserStatements，L220含英文for-of输入；L354起TestParserCompleteProgram建立完整程序AST并断言imports、rules、exports数量。文件直接导入parser/generated并调用生成器API。
- [parser_test.go](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/parser/parser_test.go)：L147起TestParseFormatRoundTrip，L225起TestParseControlFlow，另有规则／表达式／错误／导入导出等用例。

以上是测试代码的保存与静态阅读证据。英文for-of解析用例与for-of运行语义是不同层级。原有“循环／对于”、连写“否则如果”最长匹配、else-if Visitor、for-of求值及全角标点边界继续保留。独立运行、测试结果、覆盖率与性能待核。

固定.kiro/specs目录含dsl-core、dsl-v1.1-event-plugin、dsl-v1.2-unified-plugin；dsl-core目录含design.md、requirements.md、tasks.md。[tasks.md](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/.kiro/specs/dsl-core/tasks.md)全文可读，列十个阶段、22任务与2026-01-06完成声明。AI参与声明、具体模型、生成比例与人工复核范围待核；网页全站导航的“AI队友”属于Gitee平台导航，项目来源判断依照项目文件。

## 原Issue逐项关闭评估

1. 固定RuleDSL.g4、生成词法器／解析器、Visitor、evaluator、engine：第十七轮已取得语法及手写Go主链；生成产物正文、生成器版本与固定语法的对应待核。本项保持开放。
2. 中文词元、否则如果、全角标点及类型／内置接口边界：第十七轮静态描述已建立；本轮新增测试源码支持测试层级划分。else-if／for-of实际执行及全角标点专项结果待核。本项按静态部分已完成、动态部分待核记录。
3. 标签、发行绝对时间、根提交、仓库创建日期：本轮补齐标签目标提交、三项提交绝对时间、v1.0.0平台发行时间。tagger时间、根提交、仓库创建和首次公开仍待核。本项保持开放。
4. README中文原例与固定原文件字节对应：现有DOM逐字文本证据继续有效；原始下载字节、BOM／换行编码及Git blob对应仍待核。第十七轮原始数据入口ERR_BLOCKED_BY_CLIENT记录保留。本轮保持该边界，未重复原始下载或替换下载路径。
5. LICENSE、作者署名、上游与AI：第十七轮MIT全文与署名已核。本轮补具体Kiro实施计划文件；自然人／团队构成、源码上游继承、AI参与声明继续待核。本项保持开放。
6. 文档测试／性能声明、保存测试源码、独立运行：本轮新增两份测试正文，三类证据明确分开；独立运行结果、完整覆盖率与性能仍待核。本项保持开放。

综上，正式收录通过PR51完成；原Issue约定继续追踪的缺口仍有具体内容，建议继续开放，保留第十七轮最终评论的口径。

## 访问与操作记录

使用公开网页与GitHub只读资料。网页提取器根页可读，tags返回Internal Error；云端浏览器tags、标签树、发行页、固定目录和测试正文成功。commits/main跳转Gitee登录页，读取在认证边界结束。项目安装、生成、编译、测试、运行、远端写入、第三方联系均为0。

条目更新保留18项旧引用并新增9项，原中文示例与编号沿用基线。日期提示、标签目标和测试源码依上述原始URL核对；JSON结构及引用保留情况已检查。

## 保留的议题和研究来源

- https://github.com/yuyan-lang/chinese-programming-languages/issues/35
- https://github.com/yuyan-lang/chinese-programming-languages/issues/35#issuecomment-6101472276
- https://github.com/yuyan-lang/chinese-programming-languages/issues/35#issuecomment-6111072320
- https://github.com/yuyan-lang/chinese-programming-languages/pull/51
- https://github.com/yuyan-lang/chinese-programming-languages/blob/65be26668334bf92009e87cc275b729c81e7342d/research/2026-10-11/round-17-rule.md

## 独立复核

旧18项引用及完整原例与百科基线逐项相同。日期口径、测试源码层级与AI线索表述经独立审阅，原研究者随后补存公开tags页三行完整commit href和tag-last-commit DOM，40位SHA逐项匹配。往返测试按测试用例范围记录，完整AST等价继续待核。

公开标签片段保存于[标签证据](round-24-tag-targets.json)。
