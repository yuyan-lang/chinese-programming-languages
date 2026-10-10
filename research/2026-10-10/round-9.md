# 第九轮研究汇总

核验日期：2026-10-10（UTC）。基线提交：[d4b23b6fb82c695a34f600582a4fa6399c44fb89](https://github.com/yuyan-lang/chinese-programming-languages/tree/d4b23b6fb82c695a34f600582a4fa6399c44fb89)。

## 开轮检查

已读取根AGENTS.md、当前目录、64项语言和7项内核资料、第八轮日志，以及全部14个开放Issue正文和评论。开放PR为0。原有议题范围和研究记录用于排重及衔接。

## 数量与条目

- 本轮新发现并深入3组：Y4-Lang、TextOS、编剧笨笨AI Rust操作系统。其中2组完成正式分类收录，1组保留待核实。
- 旧线索转正式3项：pchinese、MiniLang（FI0m9ySans）、汉语程序设计语言（沈志斌）。汉编的两个历史入口在第八轮已发现，本轮合并为一个项目组。
- 正式新增合计5项：语言4项、内核1项。目录增至68项语言、8项内核。
- 已有语言条目完善2项：基石lang-023、易码lang-024。
- 旧待核实语言线索推进2项：如意III、唐姝中文Go编辑器，均保留待核实。
- 本轮待核实候选合计3组：新内核1组和上述旧语言2组。正式条目的待补字段另行记录。

### 正式新增

1. lang-065 pchinese：Python中文语法转译层，固定中文原例、代码区整词映射和compile／exec调用链；源码1.2.0与v1.1.0-alpha1分别记录。
2. lang-066 MiniLang（FI0m9ySans）：Python实现的中文独立AST解释器，固定阶乘原例及词法、递归下降解析、执行链；数学库包版本／许可与语言整体信息分项保存。
3. lang-067 汉语程序设计语言（沈志斌）：1995年公开说明书的中文词定义、数摞与词典结构，以及元易达应用文档的32位编译系统。各历史阶段按同一项目组整理，源码继承和最早书目原件待核实。
4. lang-068 Y4-Lang：Go实现的独立中文脚本语言，由V2EX作者帖发现，固定源码与v0.0.3公开发行交叉核验。默认分支快照和发行标签历史分别保存。
5. TextOS：x86-64 C／汇编内核，作者中国地域自述、B站与源码互链、SigmaBoot和kernel.elf、任务／内存／VFS及上游组件来源已核。

### 已有条目

基石补齐2026-10-10T15:55:49Z发布的v0.2.2、中文原程序、Rust默认执行链、独立C VM及ABI v2、MIT-0和AI辅助开发自述。易码补齐1.0.0及Windows编辑器Release、中文完整原例、自有AST解释和打包链，并把历史2.0文字、论坛身份及重编号缺口分别记录。原有6条参考的标题和URL完整保留。

## 议题衔接

- [Issue #1](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)：记录基石与易码两项完善。
- [Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)：pchinese与MiniLang转正式；连同第八轮太和、ChineseToyLang，初始10组已有4组正式收录，其余6组继续核实。
- [Issue #5](https://github.com/yuyan-lang/chinese-programming-languages/issues/5)：补易码2.0旧RPG与当前仓库的内容沿革；论坛账号互链、首发及版本重编号解释待核实。
- [Issue #4](https://github.com/yuyan-lang/chinese-programming-languages/issues/4)：补如意III的VS2019转译链、五种定义行教程及2020 REIDE同作者材料；连续源码待核实。
- [Issue #27](https://github.com/yuyan-lang/chinese-programming-languages/issues/27)：唐姝中文Go原简介与编辑器映射定位复核；中文显示与保存源码边界待核实。
- [Issue #29](https://github.com/yuyan-lang/chinese-programming-languages/issues/29)：保存新发现的编剧笨笨AI Rust操作系统原片、作者说明及待补项目边界。

上述议题各自仍有未完成资料，继续保留开放。

## 来源与研究记录

- [pchinese与MiniLang](round-9-issue22.md) · [字段待补](round-9-issue22-pending.json)
- [汉编历史原件](round-9-history.md) · [字段待补](round-9-history-pending.json)
- [Y4-Lang发现与核验](round-9-y4.md)
- [基石与易码完善](round-9-existing.md)
- [TextOS及AI Rust内核线索](round-9-kernels.md) · [新待核实内核](round-9-kernel-pending.json)
- [B站旧线索](round-9-bilibili.md) · [待核实资料](round-9-bilibili-pending.json)

## 检索覆盖与风险

本轮轮换Bilibili原视频、教程、简介和公开评论，V2EX作者帖，GitHub固定源码、提交、发行与许可证，linux.do原帖，以及历史公开说明书、影印件和保存的开发者文档。新项目检索优先2024—2026；原始材料追溯到1994—1995及2023。主要词组包含自制编程语言、中文脚本语言、手搓内核、AI写操作系统、自制操作系统，以及如意III、REIDE等具体名称。分项日志保留完整检索词、来源和时间范围。

部分B站代码画面受公开清晰度和播放器超时影响，评论的登录层及完整回复仍有遗漏。V2EX原帖直读失败后以索引正文定位原仓，技术结论再用固定源码验证。历史书目、原始发行物和早期网页保存程度影响首发判断。GitHub当前根提交可能为孤儿快照，日期核验同时参考标签、Release和开发者变更记录。

## 审阅与核验边界

中文原例按固定文件或影印页核对；各日期分别标明仓库创建、Git提交、公开发行或作者回溯说明。语言分类、内核自身工程和上游关系按证据等级保存。结构化JSON、条目ID、来源引用、中文URL及详情页相互对应。已有条目和参考完整保留；豫言条目沿用基线。

本轮采用公开资料与静态源码核验。安装、构建、程序运行、发行附件内部内容及性能复现继续待核实。

## 下一轮方向

继续从Issue #22的余下6组中选择有可读中文原例的候选，优先微型DSL或旧分支。新发现检索轮换Gitee／GitCode与中文社区，沿作者原始链接寻找2024—2026低关注项目。B站候选优先静态文档、清晰原例及作者版本说明；内核线索优先补独立内核边界和明确公开归属。已有资料继续推进lang-025之后的薄条目。
