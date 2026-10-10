# 第十轮研究汇总

核验日期：2026-10-10（UTC）。基线：[320b1f6904747bd8afcbb0c1d3655d965ed53ed3](https://github.com/yuyan-lang/chinese-programming-languages/tree/320b1f6904747bd8afcbb0c1d3655d965ed53ed3)。

## 开轮检查

已读取根AGENTS.md、当前目录、68项语言和8项内核、第九轮日志，以及全部15个开放Issue正文和43条评论。开放PR为0。既有线索、别名、原仓地址和发布账号用于排重。

## 数量与结果

- 本轮新发现并深入5组：云易、说了算、NomiLight2026 LightLang，以及VergeOS的两条发布身份。云易1组完成分类收录；其余4组保留待核实。VergeOS按两条发布身份计数，同源及合并关系继续核实。
- 旧线索转正式2项：zhsc-compiler与chinalang，来自Issue #22。
- 正式新增3项语言分类资料：lang-069至lang-071。目录增至71项语言、8项内核。
- 已有条目完善2项：小易lang-025、档案管理语言lang-026。原有6条参考完整保留，补充34条。
- 旧线索补证1组：飞鱼中文编程，保留待核实。
- 本轮待核实候选合计5组：新候选4组、旧候选1组。正式条目的待补字段另行记录。

## 分类与核验

1. lang-069 中文智能合约编译器（zhsc-compiler）：中文Solidity DSL设计及部分实现原型。完整中文合约原例、规范映射、AST、调度入口和MIT已核；核心词法、解析及生成模块的公开实现待核实。
2. lang-070 chinalang：中文／英文双关键字戏仿语言，Go实现rune词法、Pratt解析、AST宏展开及解释执行。两个提交的Cursor共同署名已核；具体AI生成比例、整体许可与独立运行待核实。
3. lang-071 云易（云易IDE中文前端）：易语言风格中文C++转译实现／Web IDE。B站原作者简介直链GitHub，固定ZIP的Git blob SHA核对一致；归档中文原例、Python词法／AST／语义检查／C++生成及MinGW调用链已静态核验。易语言兼容范围与源码继承关系继续核实。

小易补全正则预处理→LibCST→Python文本／子进程路径、0.1.2发行阶段、当前入口重构及归档状态。DGY补全Forth设计借鉴、词典／栈式教学定位、连续中文短例及完整九九乘法表原件，明确语义占位、空测试入口与字节码VM设计阶段。

## 议题衔接

- [Issue #1](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)：补小易、DGY两项已有资料。
- [Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)：初始10组累计完成分类6组，剩余4组继续核实。
- [Issue #31](https://github.com/yuyan-lang/chinese-programming-languages/issues/31)：说了算数据DSL定位、双后端及版本；NomiLight2026 LightLang源码、日期及与光明的同名关系。
- [Issue #32](https://github.com/yuyan-lang/chinese-programming-languages/issues/32)：TX／FendosPE与NewEra两条VergeOS身份、自身内核边界、明确中国归属及同源关系。
- [Issue #33](https://github.com/yuyan-lang/chinese-programming-languages/issues/33)：飞鱼原片、作者、UNI／VUE平台定位及语法概览；连续原例继续核实。

上述议题各有待补事项，保持开放。内核正式目录沿用8项；VergeOS Open已取得固定32位x86 C／汇编内核源码，明确中国作者／社区归属继续待核实。

## 来源与保存

- [zhsc与chinalang](round-10-issue22.md) · [字段待补](round-10-issue22-pending.json)
- [小易与DGY](round-10-existing.md)
- [Gitee／GitCode新发现](round-10-discovery.md) · [候选](round-10-discovery-pending.json)
- [VergeOS发布身份与源码](round-10-kernels.md) · [候选与37条来源](round-10-kernel-pending.json)
- [B站云易与飞鱼](round-10-bilibili.md) · [飞鱼候选](round-10-bilibili-pending.json)
- [云易固定归档及文件摘要](round-10-yunyi-manifest.json)
- [补充检索词](round-10-search.md)

## 覆盖与遗漏风险

本轮轮换Bilibili视频、简介、作者频道及教程，GitHub固定源码、提交、标签、发行与许可，GitCode原作者README、目录及提交摘要，Gitee及linux.do、V2EX、CSDN检索。新发现优先2024—2026，飞鱼回溯2022年。各分项保存完整检索词与原始URL。

GitCode当前原页与旧索引存在版本差异，时间侧栏的相对日期按原值保存。LightLang文件区出现频次受限登录提示后，后续源码请求停止。B站部分播放器画面与DOM读取超时；已取得的原片元数据、概览帧与可靠连续代码分开保存。作者称自研、代码可见、作者演示和独立运行各按证据层级记录。名称、中文内容及B站发布身份仅用于检索，中国归属依据明确公开材料核验。

## 审阅与后续方向

静态审阅覆盖完整变更、原例逐字对应、分类、固定提交、日期、原有参考保留、JSON、详情页和来源链接。中文本站URL及内核URL沿用主页现有文字与href。运行、构建与兼容性采用待核实状态。

下一轮优先取得视频项目的静态文档和原始语法文件，继续处理Issue #22剩余候选与lang-027之后的薄条目。GitCode候选在可正常公开访问时补词法／解析及版本原件；内核候选优先补明确作者归属与同源关系。平台轮换增加中文技术社区、论文及历史目录，沿原作者链接追溯2024—2026实验项目。
