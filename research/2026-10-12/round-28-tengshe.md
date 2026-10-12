# 螣蛇（Tengshe）独立静态复核

核验日期：2026-10-12。原仓固定提交：fd8251db3c3d835508c85d222dd00a919ae0047b。百科基线：40962dd4adb9eeed2bc115966572c90ce3500a05，data/languages.json含96项。对应议题：https://github.com/yuyan-lang/chinese-programming-languages/issues/65 。

## 结论

连续中文原例、词法识别、语句解析、AST求值与文件／工作台入口均可核对，支持作为中文／拼音双写动态语言、Go树遍历AST解释器收录。功能说明宜按源码可见范围表达，README设计宣传与当前词形边界分别记录。完整27字段条目保存在data/languages.json的lang-097。

已读百科AGENTS.md与Issue65正文，按直接陈述方式整理。源码核验阶段只读读取GitHub；候选程序、构建脚本、测试与二进制执行均为0。

## 固定资料

- 完整递归树20项，均为根目录blob，truncated=false：14项文本，6项二进制。
- 文本：README.md、ARCHITECTURE.md、build.sh、build.ps1、go.mod、main.go、indent.go、extras.go、workbench.go、main_test.go、workbench_test.go、hello.tsh、office.tsh、workbench.tsh。
- 二进制：Windows、Darwin、Linux，各amd64／arm64。仅读取树中的名称、大小、blob标识，不读取或运行二进制。
- main.go源码blob：c19b3015caa8592bb154f07875fa27c8da8fd8c7。
- 原例blob：677c3420156b0910471a3c8398e7f71fc65e0155。
- go.mod为module tengshe、go 1.22、空require列表。

## 原例

[hello.tsh第2—4行](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/hello.tsh#L2-L4)：

```text
把 18 给 年龄
约束 年龄 为 整数
说("年龄：" + 年龄)
```

这是根目录真实文件连续原文。README多处使用examples/hello.tsh，固定树实际路径为hello.tsh。原例语义静态链为：
1. 把→AssignStmt，18→NumberExpr(float64)，年龄→Env.set。
2. 约束→ConstraintStmt，Env.constraints保存整数；typeMatches验证当前float64值是否可表示为整数。
3. 说→PrintStmt；BinaryExpr的+在左值为string时将右值formatValue后连接；输出路径为受OutputMu保护的fmt.Fprintln。
静态推演预期文本为“年龄：18”及换行，执行结果待独立核验。

## 全链证据

1. [main.go 1352—1414](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/main.go#L1352-L1414)：main先检查runEmbedded，再分派REPL、版本、帮助、工作台、打包或普通文件。普通文件通过os.ReadFile进入runSource。
2. [main.go 1310—1334](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/main.go#L1310-L1334)：executeSource依次detectMode→prepareSource→lex→Parser.Parse→创建Runtime/Globals→Runtime.run。
3. [extras.go 34—60](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/extras.go#L34-L60)：首个非空行识别模式并可能移除该行。
4. [indent.go](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/indent.go)：按行、缩进和关键字前缀插入大括号；单独“结束”清空全部缩进栈；返回重组文本。
5. [main.go 47—230](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/main.go#L47-L230)：归一词形和全角标点；注释/字符串/数字/标识符分支；字符串内容保留原标点。
6. [main.go 376—629](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/main.go#L376-L629)：语句和代码块解析；含花括号块及单语句块。
7. [main.go 631—725](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/main.go#L631-L725)：优先级解析、值节点、名称调用和点号属性。
8. [main.go 747—817](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/main.go#L747-L817)：环境读写、向已有父作用域变量写入、约束。
9. [main.go 863—1307](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/main.go#L863-L1307)：逐语句执行、递归求值、原生内置函数和用户函数、列表过滤／映射。
10. [workbench.go 175—218](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/workbench.go#L175-L218)：HTTP/api/run读code/input，直接调用executeSource，再返回output/error/mode/trace/drawings；服务绑定127.0.0.1。
11. [extras.go 399—465](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/extras.go#L399-L465)：packBinary复制当前解释器，追加源文件及16字节尾部（TSHBIN01 + uint64长度）；runEmbedded反向读取并进入runSource。这条路径保留解释执行架构。

## 词形与语义边界

- 词法器把连续字母、汉字、数字、下划线合为一个TokIdentifier；normalizeWord仅查询完整词，拼音表内词形查询前小写化，表外标识符保留原样。连续汉字不自动切成关键词。
- 让/rang、如果/ruguo、调用未在keywordAliases、statement或原生call中定义；按README设计或文档示例记录，支持状态待核实。
- 一直与做分别存在归一及解析；README“一直做”“重复 一直做”连写形成单独标识符。indent.go的opensIndentBlock接受“一直做”前缀，其后lex仍按完整词处理。
- 不/not会归一为“不”，primary仅在TokOperator中接受+、-、!，该一元逻辑词的完整实现待核实。
- 用/yong跳过整行，产生字符串表达式“已准备使用内置库”，运行后不输出；动态模块加载语义待核实。算啦/suanla同样跳过整行。
- 声明所有关键词双写宜收窄为“词法表内的中文／拼音别名”；布尔字面量、类型名和核心内置函数另有词形范围。扩展内置函数通过isExtraName直接接受部分拼音，区分大小写。
- 工作台词典dayin/daying的首选为“打印”，rugou首选为“如果”；运行时原生语句使用“说”“要是”。建议UI首选词与解释器词形对应待核实。
- typeMatches对整数、小数／数值、文本／字符串、布尔值、列表进行匹配；未知类型名默认返回true。因此类型约束表的完整性另记待核实。
- 飞循环创建每次独立子环境，父环境为普通map；Env.set可以写父环境，OutputMu仅保护打印。并发变量安全、race测试与性能待核实。
- WhileStmt具有1000000次guard；“死循环”应准确记录为带上限的当前执行路径。
- 重复次数转int执行；ReturnSignal在部分循环／try路径的继续传播、异常和复杂控制流边界待独立验证。
- 用户函数结构只保存参数与Body；调用时以调用处env创建child。闭包捕获与词法作用域等语义应另核。
- equality通过formatValue比较；且/或两侧在operate前已求值。浮点数范围、模运算的零值及参数数量边界另核。
- prepareSource按文本前缀和包含判断处理，模式删除与插入大括号会改变行数；错误行号回映射及字符串／注释跨阶段边界待核实。
- README“？”归一为?，lex后续无?分支；标点支持宜列实际表及解析支持范围。

## 工作台与AI证据

[workbench.go 105—166](https://github.com/Xzach88/Tengshe/blob/fd8251db3c3d835508c85d222dd00a919ae0047b/workbench.go#L105-L166)：
- 离线小灵按错误及问题文本生成固定引导语。
- 设置TENGSHE_AI_ENDPOINT后进入remoteMentor；KEY存在时追加Authorization头，源码调用条件仅要求ENDPOINT。ARCHITECTURE同时提及ENDPOINT和KEY，可按实现实际触发条件表达。
- 请求携带用户程序代码、报错和问题。模型默认gpt-5-mini，为产品参数事实。
- 该接口与项目开发中的AI编码参与分开记录。现读README、架构、源码和4条提交没有可核实的开发参与比例、模型及人工复核声明，均待核实。
- 工作台包含浏览器SpeechRecognition入口和zh-CN设置。浏览器权限、联网行为及实际兼容性未执行验证。
- 文件、SMTP、HTTP机器人属于语言调用时的扩展功能。工作台服务隔离、恶意程序安全与可配置网络接口不据文档宣传认定为已验证安全。

## 历史、作者、许可和关系

[仓库元数据](https://api.github.com/repos/Xzach88/Tengshe)：
创建2026-08-22T07:32:19Z，pushed_at为2026-08-25T10:02:17Z，fork=false，license=null。首次公开时点与建库时间分开。

[main提交集合](https://api.github.com/repos/Xzach88/Tengshe/commits?per_page=100)完整返回4条：
1. fb564dbf47579d9f1f3ef427e0d3e645b30e8748，2026-08-22T07:32:20Z，Initial commit，parents=[]；仅两行README。作者署名Xcz并关联Xzach88。
2. 86cc18db2c763660751fb2501468505a57dc6a50，2026-08-22T08:28:33Z，Add files via upload；加入解释器、工作台、示例、测试、构建与二进制。作者署名Xcz并关联Xzach88。
3. 8eb232172b4d49f4f1a16034a9c0bd104c83bb05，2026-08-25T09:25:48Z，docs: add official browser workbench website。署名Xzach88，账号关联null。
4. fd8251db3c3d835508c85d222dd00a919ae0047b，2026-08-25T10:02:16Z，docs: remove Pages website bundle。署名Xzach88，账号关联null。
第2与第4提交实际tree同为31ebaeefabac442310699b66ac1005d2a0bfd898，支持说明当前源码与8月22上传快照相同。

README与CLI的V1.0／原型／工作台标识分别保存。Releases成功返回[]；git/refs/tags返回404；/tags被连接器白名单拒绝，这次拒绝不作为“无标签”事实。正式发行与二进制版本对应待核实。

许可正文在固定20文件树中待核实；license=null不等于已授予开源许可。上游源码继承、Python兼容关系、作者其他项目的技术继承均待核实。fork=false仅记录GitHub平台字段。

## 测试和实现验证分层

main_test.go含6个Test函数：中文与拼音、全角标点、管道、约束错误、try/catch、并发输出。
workbench_test.go含5个Test函数：模式／教学追踪、趣味绘图、模糊拼音、HTTP JSON对象属性、便携文件读写。
固定测试文件中可核实11个Test函数。README列出的缩进测试覆盖另需核实。
本次仅阅读测试源码。独立构建、测试运行、race检查、性能、六平台实机启动及二进制溯源均待核实。

## 后续资料缺口

1. 原作者完整许可、开发贡献和AI参与说明。
2. 正式版本、六项二进制与源码／构建脚本对应。
3. 按明确授权进行源码构建和边界测试，包含文档词形、缩进、变量并发、复杂控制流、参数数量和数值边界。
4. 更新正式资料时保留“静态核验”层级；中文主例采用固定根文件连续原文。



## 检索与覆盖

本轮沿2024—2026低关注GitHub/Gitee/GitCode索引发现螣蛇，词组为汉字编程、中文DSL、中文解释器、自然语言转译。核对96条目、开放议题与全仓索引中的Tengshe／螣蛇，名称无旧命中；同账号Longyin-OS按其他项目记录。核验时间2026-10-12，研究范围为原仓当前20文件及4次保留提交。搜索排序、站外镜像、未公开历史和图片资料存在遗漏风险。

原始发现与独立静态复核分别完成，主审再次核对原例、词法归一、语句解析、AST执行与入口。新增发现已记Issue65，本次正式收录1项，其余96项保留，目录97语言／10内核。许可、运行、上游及二进制对应继续作为待核字段；Issue65未完成范围保留。
