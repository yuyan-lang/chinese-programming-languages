# 第十六轮：Z语言（zyw98020）实现补证

核验日期：2026-10-10。原百科基线93815086f1778802ea57ddeeec8ad717e355814f。对象为[Issue #45](https://github.com/yuyan-lang/chinese-programming-languages/issues/45)的第十五轮旧候选；本轮新发现0，建议新增正式语言1。

## 原作者与时间
原仓：https://github.com/zyw98020/Zlang---Chinese-programming-language 。
当前main固定bf30f52927284d96950d87ac74abd483807d7ba6，最后推送2026-07-17T13:00:19Z，archived=false。完整树49项、43个文件，truncated=false。现存提交3项：
- ed037ddd395bca8359a17572aae92bb4875d3c2e，2026-07-16T13:58:13Z，first commit，parents为空，作者账号zyw98020。
- f9cc817d6829128c679f8e326c6ee7069de9e3f6，2026-07-17T12:30:47Z，模块化、数据处理与IDE更新。
- bf30f52927284d96950d87ac74abd483807d7ba6，2026-07-17T13:00:16Z，README补充。
仓库创建2026-07-16T13:58:11Z。IDE plist的2024版权、Git时间与首次公开日期分别保存；完整自然人署名、首发及跨平台作者链待核。

## 中文原例
采用固定Z/examples/hello_new.zzz第6—15行连续原文：
```text
函 斐波那契(n)
    若 n <= 1
        回 n
    回 斐波那契(n - 1) + 斐波那契(n - 2)

// 循环示例
设 i = 0
循环 i < 10
    打印("斐波那契(" + 字符串(i) + ") = " + 字符串(斐波那契(i)))
    i = i + 1
```
保留四空格、半角符号、空行和注释；blob f3240eeb32def9fdd84b6e02cf86aedebe638e86。范围为递归定义及循环调用，文件前五行属于标题、问候及注释。运行输出待核。

第十五轮README第6—18行原例作为历史研究资料完整保留，本轮补入源码中的当前缩进原例。fibonacci.zzz同仓保留花括号风格；hello_new.zzz首行注释称始/终，实际例程以缩进组织。当前parser的block函数读取INDENT/DEDENT。同仓例程、关键词表中始/终保留项与当前语法的兼容范围待核。

## 词法、解析、执行
- token.h第90—125行保存36项中文关键词映射；数量表示映射表条数，各词完整语义覆盖另核。
- lexer.cpp第131—160行读取标识符后调用Keywords::get_keyword；第163—205行用缩进栈产生INDENT/DEDENT。
- parser.cpp第256—438行包括函数、返回、if、while与for-in；第339—354行使用缩进块。声明、表达式、类、模块和异常处理另有源码入口。
- main.cpp第9—40行读文件→Lexer.tokenize→Parser.parse→Interpreter.interpret，设置主文件目录；第43—77行为逐行REPL。
- interpreter.cpp第413—453行遍历Program，动态AST类型分派。第814—905行覆盖块环境、条件、匹配、循环、返回。
- 第1168—1203行读取相对模块并复用词法／解析／求值；第1231—1262行以闭包为父创建函数Environment、绑定参数、捕获ReturnException返回值。
- Makefile声明g++ -std=c++17。目标项目构建、执行和测试结果均待核。

## IDE、版本与许可
Objective-C的IDEWindowController.m第283—339行寻找解释器，使用NSTask将源文件路径交给zlang，并设置工作目录与stdin/stdout/stderr管道。第410—420行调用launchAndReturnError启动任务。运行输入UI和中文补全属于配套环境能力。构建脚本链接Cocoa与UniformTypeIdentifiers并将解释器放进应用包。

main.cpp REPL自报v1.0；plist的ShortVersion为1.0，BundleVersion为1。GitHub Releases返回空数组；git/refs/tags请求返回404，随后公开git/refs集合仅列main分支。正式发行记录和包制品继续待核。plist最低系统10.12与较新框架接口的实际兼容待核。

README末段声明MIT，完整树中的独立许可证文件待补；plist保留Copyright © 2024 Z语言. All rights reserved.。许可全文、权利人和字段适用范围分别核实，保持作者声明层级。AI工具、模型与开发范围待原始证据。

## 关系与去重
cnzkai/Zlang（智语言）、calvinwilliams/zlang及本项目分别按原仓和实现链记录。同名关系与设计借鉴继续核实；本项目IDE和解释器合为一个语言生态对象。已复核86语言目录、26项开放Issues及69条评论，沿既有#45更新。

## 检索与遗漏
网页查询：“zyw98020” “Z语言”；“Zlang---Chinese-programming-language”；“Z语言” “原生 macOS IDE”。搜索混入Zed、ZCode及普通macOS工具，技术事实采用原仓。范围聚焦2026项目，2024版权仅作字段。
GitHub读取原仓元数据、main、递归树、完整三提交、Releases、tag引用以及README、main.cpp、token.h、lexer.cpp、parser.cpp、interpreter.cpp、Makefile、IDEWindowController.m、plist、IDE构建脚本及两个原始例程。核验采用原件阅读；仓库文本包含的安装构建命令保持静态资料。
风险包括同仓例程与当前缩进解析的对应、REPL多行行为、36词元的实际覆盖、运行结果、平台最低版本、同名项目、许可证完整范围和AI开发依据。

## 固定原始来源
- [原作者仓库](https://github.com/zyw98020/Zlang---Chinese-programming-language)
- [固定README：语法、设计及MIT声明](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/README.md)
- [固定缩进递归及循环原例](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/examples/hello_new.zzz#L6-L15)
- [固定中文关键词表](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/token.h#L90-L125)
- [固定中文词法与缩进标记](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/lexer.cpp#L131-L205)
- [固定函数、返回和控制块解析](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/parser.cpp#L256-L438)
- [固定文件与REPL入口](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/main.cpp#L9-L87)
- [固定AST求值与控制语句](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/interpreter.cpp#L814-L905)
- [固定模块加载、闭包环境及函数调用](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/interpreter.cpp#L1168-L1262)
- [固定C++17构建配置](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/Makefile)
- [固定IDE启动解释器与标准流管道](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/IDEWindowController.m#L283-L339)
- [固定IDE构建与系统框架](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/build.sh)
- [固定IDE版本、系统及版权字段](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/Z-IDE-Info.plist#L17-L28)
- [同仓花括号例程](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/examples/fibonacci.zzz)
- [现存根提交](https://github.com/zyw98020/Zlang---Chinese-programming-language/commit/ed037ddd395bca8359a17572aae92bb4875d3c2e)
- [模块化与数据处理更新提交](https://github.com/zyw98020/Zlang---Chinese-programming-language/commit/f9cc817d6829128c679f8e326c6ee7069de9e3f6)
- [GitHub正式发行集合](https://api.github.com/repos/zyw98020/Zlang---Chinese-programming-language/releases?per_page=100)
- [原待核议题](https://github.com/yuyan-lang/chinese-programming-languages/issues/45)

## 独立复核修订
现存根提交已同时保存花括号fibonacci.zzz和缩进hello_new.zzz，与当前对应文件blob相同；根parser也使用缩进块。两种例程的形成顺序及兼容范围待核。正文按同仓并存记录。
- [IDE实际启动调用](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/IDEWindowController.m#L410-L420)

- [Git refs完整集合](https://api.github.com/repos/zyw98020/Zlang---Chinese-programming-language/git/refs)：2026-10-10读取仅列refs/heads/main。

