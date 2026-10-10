# 第十二轮已有条目完善：NyaPlus与Nuzo

核验日期：2026-10-10（UTC）。百科基线：[9776f45bed00a6f1c9a594eb8142dd5b4428095d](https://github.com/yuyan-lang/chinese-programming-languages/tree/9776f45bed00a6f1c9a594eb8142dd5b4428095d)，73项语言、8项内核。本项工作更新lang-029和lang-030，原ID、原有6条参考及两个中文代码片段保持。

## 开轮检查与方法

已读取基线AGENTS.md、data/languages.json两项完整对象、第十一轮汇总及已有条目日志、Issue #1正文与全部11条评论。最新[衔接评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/1#issuecomment-6101470509)记录PR #37已补PythonCN与将军令，后续薄条目继续推进。

- [公开技术文档规范](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/AGENTS.md)
- [固定语言数据](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/data/languages.json)
- [第十一轮汇总](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/research/2026-10-10/round-11.md)
- [第十一轮已有条目日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/research/2026-10-10/round-11-existing.md)

本轮使用普通网页和GitHub公开只读接口。项目源码、脚本、安装器、构建和测试保持静态阅读范围。研究资料进行格式、原文及Git blob哈希核对。

## NyaPlus lang-029

### 定位与作者

GitHub仓库持有人为nekonekods，根提交及当前快照的Git署名为nekods。作者实名与细分贡献待核实。README定位为Java中文编程框架，面向宿主开发者定制输入输出及函数，用户以简单语句描述逻辑。分类继续保存为“嵌入式中文脚本框架／DSL”。

固定树包含69个文件，本轮读取27份核心源码、文档、许可证和原例。源码固定在d00f5df7c7927dce3c93fdcff040ce274ea69560；全部25次main可达提交已检查时间、父子关系及摘要，根提交和最新提交另读文件差异。

### 连续原例

保留have_a_try/test_dic.nya第25—27行的原有3行代码，文件blob为62ada13cda45f79fbf179fc410a58f4bdb9042ab，全文322字节。源文件第24行“测试2”为匹配输入的代码头，空行结束该块。代码中的双空格、分号旁空格及字面量反斜线n保持。

样例初始化和更新子句均带前导空格。LineAnalyser.analyze只去除行末空白，单字符赋值采用整行正则匹配；LoopHead直接把分号分割后的子句交回该方法。因此条目将样例前导空白与运行结果列为待核实，并提供完整原件和源码入口。该记录来自静态分析。

### 实际执行链

1. have_a_try/startHere.bat指向Maven JAR中的com.nekods.nyaPlus.test.testMain。testMain创建TaskDistributer，设置Outputter和VMF，然后持续读取输入。
2. TaskDistributer.execute把文件路径、输入和宿主附带信息组成Task，交给ThreadPool队列。
3. NyaThread.search按文件顺序读取代码头，用Java String.matches匹配整个输入；首个匹配块的语句收集到下一空行或文件末尾。捕获组写入“括号n”，全部输入存入“括号0”和“参数-1”。
4. LineAnalyser.analyze对单行依次处理注释、行末空白、百分号变量引用、JSON访问、方括号算术及美元符号函数调用，随后识别单字符赋值；普通文本累积为输出。
5. 整块执行使用行号、条件层数和LoopHead栈处理如果、如果尾、循环、循环尾、返回和跳转标签。输出阶段转换换行、空格和制表符转义，再调用宿主输出器。
6. OperationAnalyser把算术表达式转为后缀形式，用Double栈计算加减乘除、余数和幂。结果的小数部分接近整数时进行取整。BoolExprAnalyser先做比较替换，再以字符栈计算逻辑表达式；相等使用字符串比较，大小比较转Double，且与或处于同一优先级。
7. Functions.getFuncs读取宿主函数类声明的方法，通过@Outside(name=...)建立中文名称映射；LineAnalyser反射调用方法，并按首参数类型注入Task。VarManager保存任务局部和共享全局的Object映射，JSON转换使用Fastjson。

pom.xml配置Java 21，Maven坐标com.nekods:NyaPlus_，Fastjson版本2.0.54；JUnit 3.8.1仅处于测试依赖范围。

### 功能与资料边界

- 基础文档把脚本内函数定义列为后续计划，调用规则为并排函数及变量引用。宿主Java函数扩展有实际注解和反射路径。
- 文档说明括号可组织算术，OperationAnalyser.getResult的入口正则限定数字与运算符链；括号表达式文档和现实现入口的衔接待核实。
- Functions中的“取变量”方法返回void，反射返回值与文档预期显示内容的衔接待核实。
- 初始循环条件为假时，源码设置loopLevel=1；循环尾读取循环栈顶部。该路径及嵌套结构的健壮性待核实。
- ThreadPool构造过程启动工作线程并更新静态INSTANCE，NyaThread注释标记初始化时序风险。动态调整调用shutdown后重建线程；生命周期和并发行为待核实。
- AppTest唯一测试方法调用assertTrue(true)；演示入口与功能测试覆盖分开记录。独立测试通过状态待核实。

上述细节用作运行核验清单。文档宣称、已读代码、静态推导及独立运行各自保留证据层级。

### 日期、版本、维护与许可

- 仓库创建：2025-02-15T08:44:09Z。
- 可达根提交：b16af523f11d70aebf60d7fbe4269769b168fb62，2025-02-15T16:10:21Z，无父提交，包含Java实现及构建文件。作者和提交者时间相同。
- 早期历史包含撤回与恢复提交；2025-02-15T16:57:59Z的7e73b0fad0a009c07e1ccae5a478d7e768d7c9dc重新加入相关文件。首次公开公告和仓库转为公开的时间待核实。
- LICENSE加入：11028d3488d32392dffdc7bb683f786b9137590e，2025-02-16T02:06:56Z，摘要为Create LICENSE LGPL。
- 当前main提交：d00f5df7c7927dce3c93fdcff040ce274ea69560，2025-04-09T07:19:25Z；本次扩充逻辑非、JSON操作、跳转和函数处理等内容。
- 仓库最后推送：2025-04-09T07:20:57Z；archived=false。后续维护计划待核实。
- Maven构建版本：1.0-SNAPSHOT。本轮公开Releases与git/matching-refs/tags/均返回空列表；正式版号、发行物和发布日期待核实。
- 许可：固定LICENSE为GNU LGPL 2.1全文，README声明LGPL，GitHub元数据标识LGPL-2.1。更具体的版本选择声明待核实。

### 原始关系与AI信息

README说明语法借鉴QRspeed，未来规划兼容语法和优化语法两条方向；源码中的单数字方括号处理注释亦记录兼容差异。兼容范围和成熟度按计划与实际路径分别记载。

OperationAnalyser第12行注释说明算术解析代码来自网络，BoolExprAnalyser据此改造，具体原始文章、作者与许可链待核实。部分文件带FernFlower反编译头，作为文件来源特征记录。AI参与声明、模型及范围继续待核实。

### NyaPlus参考

1. [作者README（原有参考）](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/README.md)
2. [中文脚本示例（原有参考）](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/have_a_try/test_dic.nya)
3. [Java构建清单（原有参考）](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/pom.xml)
4. [仓库元数据（原有参考）](https://api.github.com/repos/nekonekods/NyaPlus)
5. [输入与代码块、变量及函数语法](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/docs/syntax/basic.md)
6. [条件、循环和返回语法](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/docs/syntax/logic.md)
7. [宿主演示入口](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/test/testMain.java)
8. [任务分发入口](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/TaskDistributer.java)
9. [任务队列与线程生命周期](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/ThreadPool.java)
10. [输入正则匹配与代码块读取](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/NyaThread.java)
11. [逐行文本解释与控制流](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/LineAnalyser.java)
12. [中文函数登记、反射接口及内置操作](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/Functions.java)
13. [算术后缀表达式与网络来源说明](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/OperationAnalyser.java)
14. [布尔表达式求值](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/BoolExprAnalyser.java)
15. [宿主输出器与变量工厂接口](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/main/java/com/nekods/nyaPlus/core/Controller.java)
16. [JUnit样板测试范围](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/src/test/java/com/nekods/nyaPlus/AppTest.java)
17. [LGPL 2.1许可证全文](https://github.com/nekonekods/NyaPlus/blob/d00f5df7c7927dce3c93fdcff040ce274ea69560/LICENSE)
18. [可达根提交与首次源码记录](https://github.com/nekonekods/NyaPlus/commit/b16af523f11d70aebf60d7fbe4269769b168fb62)
19. [当前快照提交与更新说明](https://github.com/nekonekods/NyaPlus/commit/d00f5df7c7927dce3c93fdcff040ce274ea69560)
20. [固定完整文件树](https://github.com/nekonekods/NyaPlus/tree/d00f5df7c7927dce3c93fdcff040ce274ea69560)
21. [公开发行列表](https://github.com/nekonekods/NyaPlus/releases)
22. [标签引用列表](https://api.github.com/repos/nekonekods/NyaPlus/git/matching-refs/tags/)

## Nuzo lang-030

### 原作者材料与中文原例

[TRAE原帖](https://forum.trae.cn/t/topic/14494)仍可读取，作者显示为魔114514，页面时间2026-05-04 11:24，时区待核实。原帖链接的仓库为nimamasl114514/nuzo。跨平台账号归属的进一步说明、实名及更早首发待核实。

原有4行递归函数与原帖中文版逐字核对，函数、如果、返回及缩进保持。原帖后续一行提供调用；条目的code_context说明节选范围。原帖展示与实际运行验证分别记录。

作者将实现描述为Rust的双语词元、语法树、字节码编译器和栈式虚拟机，说明使用递归下降及Pratt表达式解析。特性、439项测试通过及GC等待完善范围均保留作者自述层级。原帖末段明确写明AI开发、人类主导架构，并声明Apache License 2.0；具体模型、源码与许可证原件待核实。

### 访问状态、地址与发行

2026-10-10对精确仓库API只读访问返回404。本轮随后转向作者原帖、账号公开仓库搜索与项目精确名称检索。GitHub搜索“nuzo user:nimamasl114514”和“nuzo language:Rust”均为空；“user:nimamasl114514”返回16个公开仓库。新地址、改名与迁移声明、公开发行物及版本日期继续待核实。

原帖作者主页读取返回Cache miss，文章JSON端点返回工具不可访问。原帖正文和中文示例可读。访问状态按本次通道记录，仓库历史变化继续保留待核实。

同名nuzo-memory检索结果使用独立作者和AI记忆工具资料，项目身份按原作者原帖及仓库指向确定，作者关系和代码同源证据继续待核实。

### Nuzo参考

1. [作者原帖：用 SOLO 使用 RUST 从零迭代出一门 400+ 测试的复杂编程语言（原有参考）](https://forum.trae.cn/t/topic/14494)
2. [作者原帖所列项目仓库（当前内容待核实）（原有参考）](https://github.com/nimamasl114514/nuzo)

原仓访问状态接口：https://api.github.com/repos/nimamasl114514/nuzo 。

## 检索覆盖与遗漏风险

检索时间窗为2026-10-10 20:01—20:04 UTC，网页未设置时间过滤。NyaPlus代码历史覆盖2025-02-15至2025-04-09，Nuzo可归属公开介绍为2026-05-04。检索关键词包括：

- “NyaPlus” “nekonekods”；“NyaPlus” Java QRspeed；“NyaPlus” 编程语言；“NyaPlus” “nekods” “AI”
- “Nuzo” “nimamasl114514”；“Nuzo” “魔114514”；“Nuzo” 编程语言 Rust
- “nimamasl114514” nuzo 仓库；“Nuzo” “Apache” “Rust”；site:github.com/nimamasl114514 Nuzo
- site:forum.trae.cn “魔114514” “Nuzo”；“Nuzo” “编程语言” “发布”
- GitHub仓库查询：nuzo user:nimamasl114514、nuzo language:Rust、user:nimamasl114514、NyaPlus

NyaPlus普通网页检索混入土耳其语Python包、VRChat商店与其他同名仓库，项目以原作者账号、Java实现及QRspeed来源链识别。作者文档站网页工具返回不可访问，固定docs文本通过GitHub读取成功。Nuzo原帖以外的搜索混入AI记忆工具、公司、教育材料等同名内容，原帖作者明确的新地址线索继续待核实。

搜索索引完整性、历史更名或访问变化、首次公开日期、NyaPlus引用的网络代码来源，以及Nuzo源码、发行和许可证原件构成当前资料缺口。源代码执行、兼容性和性能维持独立待核。

## 交付与校验

- 两项完整对象更新至data/languages.json，保留lang-029、lang-030。
- NyaPlus介绍322字，原3行代码保持；参考22条，其中原4条标题与URL完整保留。
- Nuzo介绍259字，原4行代码保持；原2条参考完整保留。
- 合计24条参考，原6条保留，新增18条。
- 两项均补齐页面展示字段：description、author、first_publication、features、code、code_context、code_source、implementation、version、status、relations、verification_notes和verified_at。许可信息在version中同步显示，并另存license字段。
- NyaPlus取得实际源码层完善；Nuzo本轮完善原作者资料，源码与发行层继续待核实。两者独立运行结果均待核实。
- 本项新增语言0项；百科数量维持73项语言、8项内核。Issue #1其余待核资料继续跟进。


最终静态检查：两个JSON对象解析、原ID、介绍长度、6条原参考、URL唯一性、所有页面关键字段及旧代码逐字保持均通过。27份NyaPlus文本重算Git blob SHA全部一致；NyaPlus代码与固定原件第25—27行连续对应。
