# 第八轮：Issue #22 太和与 ChineseToyLang 核验

核验日期：2026-10-10（UTC）。目录基线：[48e7a753e30e8059b0c617a1c38f5385c54e3b4f](https://github.com/yuyan-lang/chinese-programming-languages/tree/48e7a753e30e8059b0c617a1c38f5385c54e3b4f)。

## 范围与结果

开轮读取基线AGENTS.md、完整目录树、61项语言名称／别名／仓库来源、round-7.md、round-7-language-pending.json，以及[Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)正文和现有1条评论。该评论将两项候选关联到第七轮保存资料。本轮沿用原候选身份和固定提交核验。

- 旧候选核验2项：太和／TaiHeLang、ChineseToyLang。
- 新发现0项。
- 完成分类资料2项：太和按实验性编译器与AST解释器记录；ChineseToyLang按早期前端与LLVM IR实验记录。
- 后续字段核验2组，详见配套pending.json。两组是已分类条目的剩余事项。
- 本分项收录建议采用固定中文关键字原例、原作者源码及实现路径证据。条目运行能力按实际材料分层，独立构建和执行继续待核实。

## 一、太和／TaiHeLang

固定快照：[c52c75f9ef82772017ffd19042fce72b8d891e71](https://github.com/naodingaoaoao/TaiHeLang/tree/c52c75f9ef82772017ffd19042fce72b8d891e71)。默认分支main与此提交一致；递归树38项，truncated=false。

### 中文原例与规范

[examples/fibonacci.th第4—9行](https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/examples/fibonacci.th#L4-L9)为连续完整递归函数，包含“函数、如果、返回、否则”。全文和按行读取结果逐字比对后写入code字段。examples/hello.th还给出变量、输出及当循环；spec.md标题为“太和编程语言规范v0.1”。

[lexer.py第30—109行](https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/src/taihe/lexer.py#L30-L109)提供中文关键字集合与全角标点映射。[parser.py第180—216行](https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/src/taihe/parser.py#L180-L216)将这些词元分派至函数、变量、类、返回、条件和循环解析。

### 实现路径

1. compiler.py的compile_source调用tokenize_string、Parser.parse和CodeGenerator.generate。
2. codegen.py导入llvmlite.ir与binding，建立LLVM模块，遍历AST语句，并把入口函数“主”映射为main。
3. [cli.py第201—409行](https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/src/taihe/cli.py#L201-L409)保存.ll，查找llc／Clang，生成目标文件、链接可执行程序或DLL，并提供Clang直接处理IR的回退路径。
4. runtime/taihe_runtime.c和taihe_ui.c提供Windows API运行时；两文件直接引用windows.h。
5. CLI的interpret子命令接入interpreter.py。其run再次调用相同词法与解析入口，execute_program收集类和函数后调用“主”。

以上是静态源码中的调用路径。构建完整性、运行结果及两个执行路径的语义一致性分别待核实。

### 功能边界与待核事项

[codegen.py第2285—2338行](https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/src/taihe/codegen.py#L2285-L2338)中，列表字面量采用首元素简化值，列表推导式返回长度，元组进入显式错误分支；第2661—2712行中切片和字典也有显式错误路径。因此规范中的集合功能按设计层记录。README中的性能描述属于作者介绍，实测性能待核实。

INDEX列出setup.py、requirements.txt、tests和历史规范文件，README列出Electron IDE及其安装方法；这些说明对应的完整公开材料待核实。固定树保存核心模块、4个.th样例、C运行时及egg-info。

### 作者、时间、版本与许可

- 仓库创建：2026-02-27T10:20:05Z。
- [根提交11adcd8](https://github.com/naodingaoaoao/TaiHeLang/commit/11adcd8bc435da38f09d13b8b6b94aed6e17f37f)的时间戳与仓库创建时间相同，包含README与LICENSE；6条可见提交作者均署浅生，GitHub账号对应naodingaoaoao。
- [核心上传提交65115c1](https://github.com/naodingaoaoao/TaiHeLang/commit/65115c14f95738d607e02b2ef8abafa8a7b36ba2)时间为2026-02-27T11:19:30Z。
- 当前提交时间：2026-02-27T11:42:11Z。
- [LICENSE](https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/LICENSE)采用MIT，署名2026浅生。
- spec.md自标v0.1；__init__.py与CLI自标0.1.0；PKG-INFO自标包taihe-lang 0.2.0、Alpha，依赖llvmlite 0.46.0。版本编号分别保存，统一版本关系待核实。
- Releases集合返回空数组；git/refs/tags返回404。正式发行及安装包待核实。
- [CLI第27行](https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/src/taihe/cli.py#L16-L37)在Visual Studio路径列表旁明确标注AI参与，具体生成范围及核心AI参与比例继续待核实。

### 同源检查

README、INDEX、CLI自指链接、MIT署名与提交作者组成同一项目证据链。GitHub元数据fork=false。PKG-INFO的Home-page指向taihe-lang/taihe，该公开入口本次返回404，历史归属待核实。目录61条项目按名称、别名、作者和仓库地址查重，两项均继续沿用Issue #22旧候选身份。

## 二、ChineseToyLang

固定快照：[897456459430f6c9abcb517fa3249739f502e7b2](https://github.com/sundaolin9527/ChineseToyLang/tree/897456459430f6c9abcb517fa3249739f502e7b2)。默认分支master与此提交一致；递归树101项，truncated=false。

### 中文原例与词法

[tests/examples/test.txt第3—7行](https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/tests/examples/test.txt#L3-L7)连续提供“令、恒、函、返”声明和面积函数。全文及按行返回值比对后写入code。test_variable.txt另含真／假和多种一元、二元表达式。

[docs/docs.md](https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/docs/docs.md)给出语法规则、优先级、控制结构、导入导出与结构声明。[Lexer.c第15—76行](https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/src/Frontend/Lexer.c#L15-L76)对中文关键字进行明确token映射，Parser.c有配套语句解析分派。

### 分阶段实现

- [app/Main.cpp](https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/app/Main.cpp)执行read_file→init_lexer→init_parser→parse_program→print_ast。主程序的当前链路终点是AST输出。
- [IR/CodeGenTest.cpp第11—52行](https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/tests/Unit/IR/CodeGenTest.cpp#L11-L52)提供独立入口，把AST送入CodeGenerator::EmitProgram并dumpIR；tests/Unit/CMakeLists.txt将其建为IR_CodeGenTest。
- [src/IR/CodeGen.cpp第1226—1249行](https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/src/IR/CodeGen.cpp#L1226-L1249)遍历声明、调用LLVM verifyModule并输出IR。
- 根CMake指定C11／C++17、Clang16、LLVM16并推荐16.0.6，另依赖zstd和CURL。
- [src/Backend/CodeGen.cpp第308—345行](https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/src/Backend/CodeGen.cpp#L308-L345)有独立main，以手工构造的虚拟指令演示线性扫描分配和x86指令选择。
- 固定树中ARM／X86平台实现、Sema.c、Gc.c、FullPipelineTest.cpp等文件大小为0。端到端本地编译、后端接通、运行时与GC完整性待核实。

分类采用“中文语法语言／早期编译器前端与LLVM IR实验”，保留项目真实开发层级。

### 作者、历史与版本

- 仓库账号sundaolin9527，提交署名sundaolin；原始GitHub提交author对象为null，二者身份对应按待核实记录。
- 仓库创建时间2025-06-01T08:03:13Z。
- [根提交120ea4b](https://github.com/sundaolin9527/ChineseToyLang/commit/120ea4b7dce11a98cffa724a59d2b4a78da74dcb)作者时间2025-06-01T09:34:37Z，提交时间2025-06-01T09:35:14Z，包含中文语法和原例。
- 当前可见默认分支共66条提交；最新时间2025-08-18T14:47:46Z，提交消息“gc算法开发02”。
- [c5216fe改名提交](https://github.com/sundaolin9527/ChineseToyLang/commit/c5216fee5772988f128141dcf868805da80a1132)把ChineseToyCompiler构建目标改为ChineseToyLang，计作同一项目沿革。
- 根CMake早期使用elang_core，外部同名项目的代码继承关系继续待核实。
- app/version.h.in保存版本替换模板；正式版本号待核实。
- Releases集合为空；git/refs/tags返回404。license元数据为null，许可与AI参与情况待核实。

## 检索与覆盖

GitHub精确仓库检索：
- TaiHeLang in:name fork:true：返回naodingaoaoao/TaiHeLang。
- ChineseToyLang in:name fork:true：返回sundaolin9527/ChineseToyLang。
- ChineseToyCompiler in:name fork:true：返回空列表。

普通网页检索“TaiHeLang 太和”“naodingaoaoao 太和”“ChineseToyLang sundaolin9527”本次返回空结果；直接网页抓取两仓主页遇缓存读取失败，随后通过GitHub公开读取工具取得原仓元数据与固定文件。上述搜索结果用于记录覆盖，项目身份主要依赖原作者仓库。仓库名称检索覆盖当前索引，跨站转载、早期改名与手工复制关系继续待核实。

研究读取范围为公开文档、源文件、文件树、提交及发行元数据。项目安装、构建、程序执行和二进制验证属于后续独立核验范围。

## 交付与计数说明

entry.json提供2项无ID候选正式资料，字段沿用现有languages.json；两条description分别286字和281字（按字符计数）。code字段为固定来源连续原文。pending.json保留条目剩余字段核验，不增加新发现计数。本次资料对外写作遵循根AGENTS.md的肯定陈述及“待核实”标记。

