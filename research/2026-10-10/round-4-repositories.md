# 第四轮仓库核验：玄语与 han-riscv

核验日期：2026-10-10（UTC）。研究时间：16:01—16:06。范围为公开网页、GitHub文件与仓库元数据的只读核验；成果为两项候选条目及来源记录。独立构建、运行及性能验证列为待核实项。

## 结论

- 玄语按“中文编译型语言／LLVM文本后端”收录。中文关键字、Rust词法与解析、LLVM IR生成链、XY编译器模块和原始短例具备源码证据。自举一致性、测试通过、性能与跨平台效果继续按作者声明或待核实项处理。
- han-riscv按“实验性中文C-like编译语言／微型原型”收录。当前实现为“整/返”、无参函数、整数括号表达式及四则运算，输出RV64风格汇编。中文IR、更多C语法、RV32、运行时和自举作为设计目标记录。
- 两项均为当前43项语言目录之外的项目。玄语的旧名ZHCC、英文名XY Language在同一条目中处理。现有玄铁lang-034保留其独立仓库与条目。

## 基线与去重

1. 读取百科AGENTS.md，blob ab8038fa86c6ff04320372eea00cee9c5fd54cca，采用直接、肯定的技术陈述，并将资料缺口写为“待核实”。
2. 读取完整data/languages.json，blob 8c1596aaa26a0e1cd36f5828256b6666ba849260，共43项；核对名称、别名和仓库链接。
3. 读取research目录完整树及14篇现有日志，对玄语、xuanyu、ZHCC、han-riscv进行项目级去重。此次目录树返回main提交9cdc1399b92ec9684129a663847cafd0bced2b6e。
4. 读取开放Issues集合，核对#1、#3、#4、#5、#11、#13、#16正文；这些正文中的候选与本轮两项分别整理。
5. 现有玄铁条目指向MARKJY-China/XuanTie-Lang；本轮玄语指向chy818/xuanyu。条目分别保存可核验的名称和来源链。

基线：
- https://github.com/yuyan-lang/chinese-programming-languages/blob/main/AGENTS.md
- https://github.com/yuyan-lang/chinese-programming-languages/blob/main/data/languages.json
- https://github.com/yuyan-lang/chinese-programming-languages/tree/main/research
- https://github.com/yuyan-lang/chinese-programming-languages/issues

## 发现查询与访问记录

主任务先提供两项候选和发现查询。本次于16:03 UTC重跑同一GitHub仓库搜索：
`"中文" "编译器" created:2026-01-01..2026-10-10 stars:0..3`

使用github.search_repositories，page=1、per_page=100，响应返回47个仓库，包含chy818/xuanyu和1913964829/han-riscv。本核验集中处理这两项指定候选。仓库搜索的名称、描述、README索引和关注度过滤影响覆盖率；该查询的时间范围指仓库创建日期。

访问过程：
1. web.open读取百科AGENTS.md、data/languages.json、两个候选首页，四项均返回Cache miss。
2. 改用GitHub接口读取同一批公开资源，成功取得文件和元数据。
3. 两项目分别GET仓库元数据、commits?per_page=100、固定提交递归树、Releases、git/refs/tags。
4. 玄语commit分页第1页100项、第2页15项；han-riscv第1页6项。取得两项目parents=[]的根提交记录。
5. 玄语git/refs/tags成功返回4项。han-riscv该端点返回GitHub 404，按该端点响应保存；其Releases集合明确返回空数组。
6. 文件内容均通过GitHub接口按固定commit读取；短例逐行核对。后端实现通过获取全文后检查关键词、函数及输出链片段核验。

## 玄语：版本、作者与原始来源

- 仓库：https://github.com/chy818/xuanyu
- GitHub元数据：fork=false、archived=false、default_branch=master。
- created_at：2026-03-18T10:53:51Z。
- 根提交：e6cdc7a1065f260ab64bd7ca30669dde3c0ad90d，author.date=2026-03-18T10:55:56Z，署名chy818；其README标题为“zhcc - 中文计算体系编译器”。
- 当前固定提交：6bd1bad153de4d0c2019b6001974ddab0ad69268，author.date=2026-08-12T14:10:08Z，署名chy818。
- 完整递归树189项、truncated=false。
- 当前LICENSE第1行版权署名陈恒源；Cargo.toml的authors为“玄语 Team”。条目采用来源限定的公开署名。
- Cargo.toml和L2驱动均标注0.4.0-alpha。
- 首个可核实GitHub Release：v0.1.0-alpha，published_at=2026-07-05T10:13:16Z；正文自称首个公开预览版本。
- 其余Release：v0.2.0-beta（2026-08-07T23:56:08Z）、v0.3.0-beta（2026-08-08T23:56:31Z）、v0.4.0-alpha（2026-08-12T13:58:02Z）。
- v0.4.0-alpha标签指向c62e02b2af37102fad6c482828037e60440b1031；当前master在其后有一项版本字符串提交。标签和核验源码快照分别记录。
- 当前LICENSE使用MIT文本；v0.1.0-alpha发布说明写Apache-2.0。许可证沿革待核实。
- 建库、提交、Release发布时间分别记录；更早首次公开时间待核实。

来源：
- https://api.github.com/repos/chy818/xuanyu
- https://github.com/chy818/xuanyu/commit/e6cdc7a1065f260ab64bd7ca30669dde3c0ad90d
- https://github.com/chy818/xuanyu/blob/e6cdc7a1065f260ab64bd7ca30669dde3c0ad90d/README.md#L1-L5
- https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/LICENSE#L1-L20
- https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/Cargo.toml#L1-L25
- https://github.com/chy818/xuanyu/releases
- https://api.github.com/repos/chy818/xuanyu/git/refs/tags

### 实现证据

- token.rs第281—390行建立中文和英文关键字映射，可见“若”“函数”“返回”“定义”以及if/fn/return/let。
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/lexer/token.rs#L281-L410
- lexer.rs第270—306行扫描中文标识符并调用lookup_keyword，返回真实Token。
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/lexer/lexer.rs#L270-L306
- parser.rs第771—818行解析函数；第1093—1149行按中文关键字分派变量、返回、条件、循环等语句。
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/parser/parser.rs#L771-L818
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/parser/parser.rs#L1093-L1149
- codegen.rs第129—325行构建并返回IR字符串，322—325行包含opaque pointer后处理；第1105—1126行分派Let/Return/If/Loop等AST节点。
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/codegen/codegen.rs#L129-L325
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/codegen/codegen.rs#L1105-L1126
- main.rs第162—250行串联词法、解析、语义、IR生成；第271—376行写.ll、调用llc并以clang编译和链接runtime.c。
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/main.rs#L162-L250
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/main.rs#L271-L376
- Cargo.toml将inkwell列为可选依赖，default=[]。本条按默认文本IR生成路径说明实现。
- src/compiler_v2/xyc.xy导入XY编译器模块，compiler_new.xy第118—183行读取源码、调用四个阶段并输出IR。完整自举及其等价性需要独立复现。
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/compiler_v2/xyc.xy#L1-L14
  https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/src/compiler_v2/compiler_new.xy#L118-L183

### 原始短例

来源：https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/examples/simple.xy#L1-L4
blob：6247f5e5b042134f75536fb8a9a371192d6cdebd

```text
函数 主() : 整数 {
    打印("Hello\n")
    返回 0
}
```

采用完整四行文件，保留原文与缩进。运行验证待核实。

### 作者声明与AI材料

README第19—20行和自举章节列出自举验证、121项测试、IR一致性等结果。该部分按作者自述保存。当前静态核验支持源码存在和实现路径。

v0.2.0-beta与v0.3.0-beta的Release正文具有“Generated with Claude Code”标注。该证据能确认发布材料中的AI标注；具体源码生成范围与比例待核实。条目分类依据中文语法和编译实现。

- https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/README.md#L7-L20
- https://github.com/chy818/xuanyu/blob/6bd1bad153de4d0c2019b6001974ddab0ad69268/README.md#L551-L618
- https://github.com/chy818/xuanyu/releases/tag/v0.2.0-beta
- https://github.com/chy818/xuanyu/releases/tag/v0.3.0-beta

## han-riscv：版本、作者与原始来源

- 仓库：https://github.com/1913964829/han-riscv
- GitHub元数据：fork=false、archived=false、default_branch=main、license=null。
- created_at=2026-06-29T03:43:16Z；pushed_at=2026-06-29T06:08:32Z。
- 根提交ab68a9d7ca4ba8751c7f20eb30a8b79397fb8c0f，author.date=2026-06-29T03:50:24Z，署名moki，GitHub author映射为1913964829。
- 实现提交dd504ee77a89c65f5a9111a218acd2bf29b56045，日期2026-06-29T06:07:53Z，说明为添加最小han到RISC-V汇编编译器。
- 固定main提交cc2cc9f6c95624fa15c18b877e8e5b7df479809b，日期2026-06-29T06:08:32Z。
- 完整递归树22项、truncated=false；当前可达提交6项。
- 文档使用“第一版hancc原型”，独立语义版本号待核实。
- Releases集合为[]。git/refs/tags返回404。
- 许可证、首次公开时间和源码执行结果待核实。

### 实现证据

- CMakeLists.txt第5—11行设置C++17并构建src/hancc.cpp。
  https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/CMakeLists.txt#L1-L11
- hancc.cpp第198—229行扫描标识符，将“整”和“返”映射为关键字Token。
  https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/src/hancc.cpp#L198-L229
- 第297—363行的语法固定为整、函数名、空参数列表、花括号、返、表达式、分号；表达式分为整数、括号、乘除、加减。
  https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/src/hancc.cpp#L297-L363
- 第404—478行后端输出RV64风格汇编文本，以sd/ld保存恢复寄存器，以li/add/sub/mul/div生成表达式，将“主”或main映射为main。
  https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/src/hancc.cpp#L404-L478
- 第485—493行串联Lexer、Parser、AST和RiscvBackend；main将输入文件送入这一流程。
  https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/src/hancc.cpp#L485-L527

### 原始短例

来源：https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/examples/hello.han#L4-L6
blob：47359b273244627cce6fc31993bfeeceb6b91529

```text
整 主() {
    返 7;
}
```

采用同一文件第4—6行完整函数；前3行为注释及空行。保留原文与缩进。汇编、链接和运行验证待核实。

### 规划范围与AI自述

README和docs/07_first_compiler.md将factorial.han标为阶段目标。函数参数、局部变量、分支、循环、函数调用、递归、数组、指针、结构体和RV32列为后续工作；中文IR、优化、运行时、自举位于长期规划。条目的features仅概括当前真实源码。

仓库简介自称“vibecoding项目”。该说明记录开发方式的作者自述；具体工具、生成比例与人工修改范围待核实。项目名han-riscv、编译器hancc和.han后缀按同一语言实验处理。

- https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/README.md
- https://github.com/1913964829/han-riscv/blob/cc2cc9f6c95624fa15c18b877e8e5b7df479809b/docs/07_first_compiler.md
- https://api.github.com/repos/1913964829/han-riscv
- https://api.github.com/repos/1913964829/han-riscv/releases

## 已读取文件清单

玄语（固定当前提交）：
README.md、Cargo.toml、LICENSE、examples/hello.xy、examples/simple.xy、src/lexer/token.rs、src/lexer/lexer.rs、src/parser/parser.rs、src/codegen/codegen.rs、src/main.rs、src/compiler_v2/xyc.xy、src/compiler_v2/compiler_new.xy。另读根提交README.md以及4项Release全文。

han-riscv（固定当前提交）：
README.md、CMakeLists.txt、examples/hello.han、src/hancc.cpp、docs/07_first_compiler.md。

