# 第二十轮：Issue #3 的灵码与 Smal-lang

核验日期：2026-10-11（UTC）。基线 c14ea6d635124e6a938dd4355fc4cd4b96121d7a，语言92项、内核9项；目录维护核验18:30核对开放26项Issue、0项PR。

## 结果

- 既有待核灵码（zf199606/ling-code）与Smal-lang（CodeWatcher-Smal/Smal-lang）均具备连续中文原例和可静态阅读的实际实现链，可按本轮分类进入目录。新增发现对象0项。
- 灵码按中文脚本语言／JavaScript正则转译层分类；Smal-lang按入门中文脚本语言／Python逐行解释器与PyQt IDE分类。
- 两条待集成记录分别有19、15条来源，主例分别12、15行，编号分别为lang-093、lang-094。
- Issue #3目前19组已有9组完成分类；本轮两项合并后累计11组、剩8组。研究交付阶段保持基线计数。
- 研究范围为这两项旧候选。豫言及其他条目沿用基线。本轮研究采用公开资料静态阅读，独立程序运行与环境验证继续待核。

## 先读与去重

读取根AGENTS.md、固定data/languages.json的92项名称／别名／来源、data/kernels.json的9项、十九轮Issue #3研究记录，以及Issue #3正文与全部7条评论。最后一条评论确认大雄语lang-092合并，剩余候选包含本轮两项。按仓库URL、名称及别名核对；现有灵语、LingCpp的名称相近内容按各自原仓分开。本轮条目保留原Issue及第十九轮确认评论作为原有来源。

入口：
- https://github.com/yuyan-lang/chinese-programming-languages/issues/3
- https://github.com/yuyan-lang/chinese-programming-languages/issues/3#issuecomment-6111978135

## 灵码：原例与实际转译实现

固定提交：5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb
https://github.com/zf199606/ling-code/tree/5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb

完整递归树112项，truncated=false。源码、规范与教程位于中文命名路径；历史README.md路径状态反映该具体文件。树中灵码模板保存50个编号.灵文件，灵码示例另有3个文件；包目录还包含中文库原文。

全文读取灵码编译器/ling.js、灵码示例/09_斐波那契数列.灵、灵码语言规范_V1.0.md、灵码教程_从零开始.md、中文编程软件设计方案.md、ai-server/lingma-ai.js、index.html与灵码Playground/index.html。读取元数据、四条保留提交及空Releases列表。

主例为斐波那契原文件第4—15行，连续保留完整递归函数、原注释及遍历调用：
https://github.com/zf199606/ling-code/blob/5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb/灵码示例/09_斐波那契数列.灵#L4-L15

LingTranslator第14—170行用有序正则替换处理词元、语句、字符串插值和标准库映射。第387—416行串联fs.readFileSync→translate→new Function，注入Node宿主及文件运行时。Playground第205—350行也提供转译及new Function入口。实际分类依据上述源码；Rust、独立词法／AST／IR、WebAssembly及原生后端作为设计路线与待核能力记录。

日期与署名：
- 建库2026-08-21T06:40:09Z。
- 根提交eb6704a2bbef20f4acc652bf2ba3315bb40f0b79时间2026-08-20T09:38:47Z，parents为空。
- 当前提交2026-08-23T15:14:52Z。
- 提交作者zf199606关联同名账号；设计方案页内日期2026-07-24，自署墨灵。
- 文档日期、提交日期及建库日期分开，首次公开日和署名的自然人对应关系待核实。
- 仓库fork=false；具体代码继承、更早沿革待核实。

版本分别记录：当前提交自标v3.5.1，CLI文件头V0.5、帮助v0.4，规范文件名V1.0而标题V2.0，AI引擎文件头V1.0。正式统一版本待核实。

许可与AI：
- GitHub license=null，固定完整树的项目级许可正文待补。
- index.html第4295—4325行MIT字段用于导出的项目模板；AI文件Apache 2.0字段位于ForgeStencil参考配置，适用对象逐项标识。
- AI引擎第1—8行自述规则+模板；第2847—2867行盘古适配器为增强规则模拟与本地函数分派。真实模型接口效果待核。
- 文档列举模型选型；项目开发中的AI参与、生成比例及人工复核范围待核实。
- 作者的竞品描述和外部性能数字按原文参考资料处理，目录依据可核语言实现；具体继承关系待证。

能力边界：
- --check在转译返回后打印通过信息，其范围为转译阶段，JavaScript语法解析与执行位于后续路径。
- 导入／导出语句当前转成注释。
- CLI把输入映射为prompt，Node输入适配待核。
- 正则对源字符串操作，字符串边界、复杂表达式、嵌套结构与规范对应程度待专项核验。
- 规范的静态类型、完整模块、幂运算及后端范围按实现逐项核验。
- 原例注释的速度描述作为作者原文保留，实际性能待独立验证。

## Smal-lang：大小写路径与Python解释链

固定提交：87bdf15d9d37d55ef08f038bac0fa54cbcb852ef
https://github.com/CodeWatcher-Smal/Smal-lang/tree/87bdf15d9d37d55ef08f038bac0fa54cbcb852ef

完整树3文件，truncated=false：LICENSE、ReadMe.md、main.py。历史README.md读取路径通过完整树定位到ReadMe.md。三文件正文、三条提交与空Releases列表已读。

ReadMe.md的示例含转义及HTML实体。本轮原例采用main.py第392—406行show_example三引号字符串值，保留连续15行、空行及四空格循环体；展示提取只去Python赋值／字符串包围符和末尾字符串换行。
https://github.com/CodeWatcher-Smal/Smal-lang/blob/87bdf15d9d37d55ef08f038bac0fa54cbcb852ef/main.py#L391-L408

源码链：
- 第410—413行run_code把编辑器原文送到SmalInterpreter.execute。
- 第200—295行按行解析重复和如果，收集缩进体；等于比较左右表达式。
- 第162—198行execute_line识别“设…为…”／“…是…”、“显示／打印／告诉用户”和“让用户输入”，后者调用QInputDialog。
- 第72—160行parse_expression移除引号、递归处理括号、替换空白边界变量及当前次数，按乘除、减、加的次序求值。
- 中文加法在全部项目可转数字时求和，其他情况连接字符串。
- 当前次数源码赋值i+1，与v2.3.2说明一致。

日期／署名／许可：
- 建库及根提交f7eac1f04bec3692e0d3654ada950840a8c384cf时间2025-08-12T03:42:50Z。
- 后续两条上传提交时间04:42:58Z、04:49:44Z，均在同日。
- LICENSE署名Smal Smith，提交作者关联CodeWatcher-Smal；自然人身份待核。
- README、窗口标题和关于对话框均自标2.3.2；更早版本及正式发行日期待核。
- 固定MIT许可正文、README许可说明及GitHub元数据相互对应。
- fork=false，根提交parents为空；具体上游代码继承待核。
- AI开发参与、模型、生成比例与人工复核待核。

能力边界：控制块正文交给execute_line，其处理范围为赋值、输入、输出；嵌套控制流支持待核。严格字符串语义、运算优先级、错误处理覆盖、Python/PyQt兼容性与执行结果待独立验证。

## 检索记录与遗漏风险

本轮在18:31（UTC）以普通网页检索精确账号／仓库：
- "zf199606" "ling-code"
- "CodeWatcher-Smal" "Smal"

结果为空。GitHub只读接口直接取得两原仓元数据、完整树、固定文件、提交与发行列表。仓库材料是本轮事实证据。

目录维护核验18:30另作有限发现检索：
- "AI写编译器" "中文"
- "全中文代码" "自制" "语言"
- "中文解释器" "2026" -site:blog.gitcode.com -site:csdn.net

通用网页平台，侧重2024—2026信息，结果混入较早页面。目录维护核验报告主要为AI编译器文章、已知2022火龙甲乙转述及2016论坛转载：
- https://developer.cloud.tencent.com/news/898883
- https://www.cn-dos.net/forum/viewthread.php?page=4&tid=53565

上述二手页面只作发现入口。本轮有限发现新增合格项目0项；项目原作者、原语法、沿革及相关事实依原始资料核验。搜索引擎可能遗漏低关注仓库、大小写路径、中文文件名、附件、动态、评论及不同名称。本轮结论覆盖两项既有候选和所列有限检索批次。

## 交付与后续

两项整理为正式条目，本批新增独立待核候选0项。许可、版本、AI开发参与及执行边界保存在各条目的对应字段。Issue #3其余8组保留既有待核状态：CN_Interpreter、CN Language、PYCH、Sneko、RexLang、青语言、意语言、衍真。本轮保持原议题及旧引用。

整理后目录94项语言、9项内核；Issue #3其余8组继续保留。独立审阅见[复核记录](round-20-review.md)。

