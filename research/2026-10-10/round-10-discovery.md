# 第十轮：Gitee／GitCode及中文社区新发现

核验日期：2026-10-10（UTC）。基线：[320b1f6904747bd8afcbb0c1d3655d965ed53ed3](https://github.com/yuyan-lang/chinese-programming-languages/tree/320b1f6904747bd8afcbb0c1d3655d965ed53ed3)。

## 结果

本支线深入2组新原仓：说了算（Saysuan）和LightLang（NomiLight2026）。两组均取得GitCode原作者项目页的当前README和连续中文程序；源码级分类、首发日期及部分版本字段继续核实。正式新增条目0项，新增待核实候选2组。

LightLang一名与现有光明lang-009别名相同。当前记录按新原仓候选保存，同源关系继续核实。说了算的当前定位从早期中文编程语言转为中文数据口语工具，适合优先核查数据DSL分类。

产物：
- round10-discovery-entry.json：空数组，正式收录保留到源码和分类证据补齐。
- round-10-discovery-pending.json：2组结构化候选，含连续原例、来源、版本分层、访问状态与待核事项。

本支线采用只读公开检索及公开网页浏览器。豫言、目录及其他官网／原作者仓库保持原样。

## 开轮排重

已取得并按全文名称／原仓地址排重：
- 根AGENTS.md。
- 68条data/languages.json，含别名及全部引用。
- 第九轮11个研究文件：round-9汇总、existing、history、history-pending、issue22、issue22-pending、kernels、kernel-pending、bilibili、bilibili-pending与y4。
- 开放Issue #1、#3、#4、#5、#11、#13、#16、#18、#19、#22、#23、#24、#26、#27、#29的正文及全部评论，共15个开放Issue。

badhope/saysuan及NomiLight2026/lightLang两个原仓地址在上述基线资料中均未保存。LightLang命名冲突已列入后续核验；已有墨言Issue #26、衍真Issue #3、洛书lang-005、CNSHlang-053等命中按既有对象处理。

## 1. 说了算（Saysuan）

原项目：[badhope/saysuan](https://gitcode.com/badhope/saysuan)。当前原文入口：[README](https://gitcode.com/badhope/saysuan?tab=md#markdown-card-anchor)。

### 原始证据

2026-10-10约19:02:44 UTC，公开网页浏览器直接读到：
- GitCode维护账号badhope；main，0星，12次提交，1标签。
- 当前头提交719f1b3db510902527c0ad9cc7d439fad92b16fc，标题“v1.1 打磨优化：性能 + 一致性 + UX”。[原页提供的提交入口](https://gitcode.com/badhope/saysuan/commit/719f1b3db510902527c0ad9cc7d439fad92b16fc?ref=main)，详情待核实。
- 根目录src、例子、SPEC.md、README.md、LICENSE、CHANGELOG.md、demo*.suan、运行时.py等条目。
- 当前README定位为中文数据口语工具，列Python＋pandas命令行路线与JavaScript＋Chart.js浏览器路线。
- 可读v1.0提交摘要明确记录定位转型，并列types、tokenizer、compiler、cli、repl拆分和compiler-js.js、runtime-js.js。
- 当前README有v1.1章节，原页头提交摘要说明package.json与compiler.js统一为1.1.0；发行侧栏v0.9.0仍标最新发行。
- 原目录v0.9.0提交标题自述为“首个开源版本”，页面相对时间与发行侧栏同为11天前。绝对时间和最早公开日期待核实。
- 当前原README与侧栏列MIT；LICENSE正文及署名待核实。

### 连续中文原例

以下原文来自当前原README首个代码块：

```text
从 "订单.csv" 读入 「订单表」

取 「订单表」 里 金额 大于 200 的 行
按 「订单表」 的 类别 分组，汇总 金额 的总和
按 「排序后结果」 的 金额_总和 从大到小 排序
显示 「排序后结果」
```

原例保留可读换行与标点；输入文件、隐式中间结果名绑定以及执行结果待核实。原页头提交已知，固定提交文件正文的逐字比对待补。

当前原README显示104项编译器测试及4项REPL测试的作者自述。编译／执行源码、测试文件正文、测试记录与独立运行分层核验。

### 索引与当前版本差异

搜索索引保留较早的“一门用现代口语中文写程序的编程语言”、5次提交、92＋4测试、单一Python后端及“本月排行 来自”代码块。公开网页浏览器读取到12次提交、数据工具定位与双后端。研究结论以当前直接原页为准，旧索引作为版本变化线索，准确变更日期继续核实。

### 下一步

读取固定SPEC、tokenizer、compiler、cli／repl和两个后端，核查表DSL与通用控制结构的实际语义；补LICENSE和首个发行绝对日期；追查badhope真实署名及跨平台作者互链；补AI参与的明确原作者声明。源码与运行证据补齐后再确定正式条目分类。

## 2. LightLang（NomiLight2026）

原项目：[NomiLight2026/lightLang](https://gitcode.com/NomiLight2026/lightLang)。当前原文入口：[README](https://gitcode.com/NomiLight2026/lightLang?tab=md#markdown-card-anchor)。

### 原始证据

2026-10-10约19:03:02 UTC，公开网页浏览器直接读到：
- 原仓维护账号NomiLight2026；main，1星，19次提交，4标签；贡献者侧栏为NomiLight2026一位。
- 当前README定义早期实验性中文编程语言，.light文件、顶层语句、中文控制结构与模块语法。
- 文档说明lightc包含词法、解析、类型推导及LLVM代码生成，lightrt为Rust运行时；lightGo采用工程清单、Cargo与Rust FFI；lightweb使用tiny_http。
- 文档说明light命令通过临时编译运行源码，REPL每次重编整段会话。实际源码与运行机制待核实。
- README交互示例、安装文件名标0.2.1；发行侧栏显示0.2.0，14天前发布。绝对日期和版本对应待核实。
- README及侧栏标GPL-3.0；第三方依赖按各自许可。LICENSE正文待核实。
- 项目侧栏有atomcode标签。开发过程和运行时AI参与范围待原作者明确材料核实。

### 连续中文原例

原README“3. 中文语法，面向快速表达”下的完整连续程序：

```text
名字 = 输入()
如果 名字 != "":
    打印 "你好，" + 名字
否则:
    打印 "请输入名字"
```

已读原文提供中文控制结构证据。固定提交、文件字节、词法表和解析分支待核实。README另有函数／返回、导入、尝试／捕获／最终等连续例程；本轮保留最小清晰原例。

### 分类与同名关系

现有光明lang-009同样使用LightLang和.light。当前原页账号为NomiLight2026，文档路线为Rust／LLVM／lightGo；现有光明资料的作者与工具链另有记录。后续以原作者互链和固定源码比较核实继承或独立关系。当前候选保持账号限定名称。

### 访问边界

点击公开README后，文件区明确显示“当前访问频次受限，请登录后继续访问”。README主体仍可读。本轮在已加载公开原文范围记录证据，受限文件及提交路径的后续请求停止。登录、换环境及绕路访问均未进行。

## 检索平台、词组与时间范围

研究目标优先2024—2026公开的微型或AI相关中文语法项目，截止2026-10-10。日期数字作为搜索词时属于索引筛选线索；真实公开日期依原作者记录另核。

### 轮换检索

- Gitee：site:gitee.com "中文" "编程语言" "2026"；site:gitee.com "中文编程语言"；site:gitee.com 中文解释器；site:gitee.com 中文编译器。
- GitCode：site:gitcode.com "中文" "编程语言" "2025"；site:gitcode.com "中文关键字"；site:gitcode.com 中文编程语言 -site:blog.gitcode.com -site:news.gitcode.com。
- 中文社区／全网："手搓" "中文" "编译器" "2025"；"自制语言" "中文" "2024"；"中文解释器" "2025"；"手搓" "中文编程"；site:linux.do 中文 编程语言 编译器；site:v2ex.com "中文解释器"；site:linux.do "自制" "中文编程语言"。
- 候选追溯：saysuan badhope github；"saysuan"；"说了算" "Saysuan" 编程；"说了算" "Saysuan" AI；"说了算" "编程" site:blog.csdn.net；"NomiLight2026" "lightLang"；"NomiLight2026"；"NomiLight2026" "Light"；"lightLang" "中文"；"lightLang" site:linux.do；"lightLang" "NomiLight2026" AI。
- GitHub原生仓库搜索：saysuan（空结果）；lightLang（首屏30项，用于同名消歧，明确原作者关联待核实）。

### 命中及遗漏风险

- Gitee结果以历史项目、资料镜像和fork为主，包含洛书、中文编程组织、知语言fork及UniGal-Script旧设计；本轮深入对象限于两组GitCode新原仓，其他结果仅记录渠道覆盖。
- GitCode精确编程语言搜索命中本轮两组，也重复命中衍真、洛书、CNSH。宣传博客、新闻稿、自动镜像及目录仅用于发现，不进入本轮技术事实依据。
- LightLang检索大量混入网页翻译扩展、国外同名项目与光明项目。同名结果通过维护账号和原仓URL区分，源码同源关系待核。
- 社区精确词组缺少直接作者原帖，作者跨平台链和最早发布时间继续待补。
- 时间区间由检索目标与词组限定，搜索索引完整性、最近抓取时间和相对日期会影响覆盖。动态页面当前内容与缓存索引已有显著差异。
- 普通网页根页及README候选路径返回Internal Error，公开网页浏览器成功显示原文；后续Page.getFrameTree与DOMSnapshot读取超时。上述读取状态只说明本次访问结果。
- 当前资料为文档、目录和提交摘要等级；词法／解析源码、完整许可、版本附件与独立运行仍为后续任务。

## 后续衔接

建议为这两组原仓保存新候选议题，分别跟进DSL定位、实际实现和LightLang同名关系。已有墨言Issue #26保持原状。本轮新增候选数为2，正式新增数为0。

