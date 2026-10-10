# 第八轮普查汇总

核验日期：2026-10-10（UTC）。基线提交48e7a753e30e8059b0c617a1c38f5385c54e3b4f。

## 本轮范围与结果

开轮读取根AGENTS.md、当前目录、第七轮研究日志、61项语言资料、7项内核资料、全部12个开放Issue正文及31条评论，以及开放PR列表（0项）。沿用既有研究结果并按原作者、仓库、别名及视频BV去重。

- 新发现4组：rzc中文Rust方言、墨言、唐姝中文Go映射编辑器、流明风P的AI中文伪代码实验。
- 新发现中完成分类收录1项：rzc；其余3组继续待核实。
- 旧候选完成分类收录2项：太和、ChineseToyLang，来自Issue #22。
- 新增正式语言条目合计3项，目录61→64项。
- 已有语言条目完善2项：曜语lang-021、CNplus lang-022。
- 旧内核候选深化2项：BearOS与OS002；正式内核目录保持7项，明确中国开发者／社区公开归属继续待核实。
- Issue #3中的Sneko与CN_Interpreter补存固定快照及证据范围，继续保留后续核验。

本轮核验指原始中文语法、项目资料及相应实现证据成立。构建运行、性能及作者录像的独立复现状态各自标明。

## 语言条目

| ID | 项目 | 分类与主要证据 |
|---|---|---|
| lang-062 | 太和 | Python中文编译器／AST解释器实验；固定递归原例、llvmlite、llc／Clang调用路径、MIT |
| lang-063 | ChineseToyLang | 中文语言前端与LLVM IR实验；中文原例、AST主入口、独立IR测试、后端手工指令演示 |
| lang-064 | rzc（i18n-rust中文方言） | Rust中文方言／词元转译工具；中文语言包、rustc／Cargo入口、MIT、v0.8.3发行 |

太和各文件0.1／0.2编号分别记录，集合语义中的简化值与显式错误路径列入核验说明。ChineseToyLang按当前前端、IR与后端实验层次记录。rzc的GitCode／GitHub入口由固定README互链确认，合计一个项目。

曜语补中文递归原例、Gemini源码头声明、语义检查深度、C生成及cc链接，Android Java演示脚本的调用路径、资源及签名回退有效性分别说明。CNplus补当前1.7.0正式发行、三后端、2021—2026阶段和旧archive四文件blob同源证据。两项原有6条参考链接完整保留。

## 内核与视频候选

BearOS官网与B站频道形成双向关联，补4条原BV、x86定位与V0.20资料。功能按作者声明保存，源码、许可与公开归属继续核实。

OS002原视频直接链接Chunyi1031/OS002-UEFI，固定源码展示UEFI引导、独立内核、C／内联汇编、线程、中断和物理内存管理。2026-04-03提交新增ExitBootServices，2026-03-14演示与当前源码分阶段记录。原片功能时间点、独立运行及公开归属继续核实。

唐姝视频描述JSON中文映射与编辑器中间层，连续中文原程序和保存／翻译边界待核实。流明风P视频展示中文条件片段及Python_REPL运行录像，按AI驱动中文伪代码实验候选保存，正式名称、语法规范与项目身份继续核实。标题级英文语法命中另记筛选过程。

## 议题和证据文件

- [Issue #22：太和与ChineseToyLang完成分类资料，其他8组继续核实](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)。已收录两项的剩余字段另保存于round-8-issue22-pending.json。
- [Issue #23：BearOS与OS002补证](https://github.com/yuyan-lang/chinese-programming-languages/issues/23)。证据见round-8-kernels.md及round-8-kernel-pending.json。
- [Issue #26：墨言](https://github.com/yuyan-lang/chinese-programming-languages/issues/26)。固定头提交、作者账号和发行侧栏已保存，语法及源码正文待核实。
- [Issue #27：两项B站工具／伪代码候选](https://github.com/yuyan-lang/chinese-programming-languages/issues/27)。保存原站UTC日期、UID、原例和时间点。
- [Issue #3：Sneko与CN_Interpreter](https://github.com/yuyan-lang/chinese-programming-languages/issues/3)。本轮为固定资料增量，正式收录计数沿用原值。

## 检索覆盖及下一轮

本轮轮换GitCode／Gitee公开索引、中文历史及论文关键词，并以GitHub原始源码、B站原片、作者官网交叉核验。分项日志保存实际查询、固定提交、元数据、日期和遗漏风险。

GitCode墨言文件区持续显示加载占位，当前名称、提交及发行侧栏可读；完整代码与发布正文继续核实。B站原片存在匿名试看和浏览器交互超时，可靠画面与待补片段分别记录。历史方向定位汉语编程单片机专利与元易达原始资料入口，正式语言身份与原例留待下一轮。

下一轮优先继续Issue #22中的低关注度微型语言，同时深入历史资料中的实际程序；B站继续中文Go原例及AI伪代码的分类；既有条目按薄弱程度补齐。各类新发现按证据分组计数，附属BasC线索保留在BearOS资料中。

## 审阅

两项旧候选与rzc经固定来源交叉核验。所选五段中文原例与固定文件相符；太和CRLF在JSON中规范为LF。其他原目录对象、豫言、主页中文URL与内核路径保持原值。资料通过贡献分支及PR提交，独立执行状态明确为待核实。
