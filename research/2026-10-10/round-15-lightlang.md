# 第十五轮：LightLang旧候选的公开GitHub源码补证

核验日期：2026-10-10。百科基线：[757ddd0d875cb114b7261e389aa9a8a002f86c80](https://github.com/yuyan-lang/chinese-programming-languages/tree/757ddd0d875cb114b7261e389aa9a8a002f86c80)。

## 结果与计数

- LightLang（NomiLight2026）补齐固定连续中文例程、中文词法与语法、类型推导、LLVM代码生成、Clang编译及Rust运行时链接资料，形成1个正式条目对象。
- 本项目来自第十轮[Issue #31](https://github.com/yuyan-lang/chinese-programming-languages/issues/31)旧候选，真正新发现计数为0。新取得的GitHub入口与既有GitCode候选按一个对象记录。
- 原有80项语言目录按名称、别名、作者及仓库地址核对；光明lang-009的同名关系继续保留待核实。
- Issue #31同时跟踪说了算（Saysuan）。LightLang已核与待核项分别更新，说了算任务继续保留，议题继续开放。

## 开始前读取与范围

已读根AGENTS.md、固定基线的data/languages.json全部80项目录、research/2026-10-10/round-14.md、Issue #31正文及其全部1条评论。第十四轮结果为80项语言与9项内核。Issue #31原记录保存LightLang的README原例、GitCode文件区访问限制、0.2.1文档与0.2.0发行侧栏的版本分层。

本轮使用GitHub公开只读接口核验源码与历史。普通网页来源入口为GitHub项目、文件和Git数据；研究文件保存于共享工作区。项目构建、测试、安装、运行与桌面任务均未执行。GitCode原文件区的既有访问限制继续保留。

固定研究快照：[38aa05b295a53a2591617a5c3bc8f7b08595de25](https://github.com/oneone1565/LightLang/tree/38aa05b295a53a2591617a5c3bc8f7b08595de25)。完整树响应包含97个对象，其中67个文件，truncated=false；已读61个文本文件，包括全部Rust实现、README、LICENSE、CI配置、例程与两个项目用法文档。3个Cargo.lock和3个.gitignore属于本轮正文读取范围外的文件。

## GitHub副本与原候选的同源历史

GitHub项目为[oneone1565/LightLang](https://github.com/oneone1565/LightLang)。仓库API返回public、fork=false、archived=false、default_branch=main，创建时间2026-09-25T05:19:32Z，pushed_at为2026-09-27T01:59:06Z。

历史中有两条直接指向GitCode原仓的合并记录：

1. [07a25c1766f992e2debd2c9a6c4955882c3516e4](https://github.com/oneone1565/LightLang/commit/07a25c1766f992e2debd2c9a6c4955882c3516e4)，时间2026-09-25T05:12:36Z，提交信息为“Merge branch 'main' of https://gitcode.com/NomiLight2026/lightLang”，双亲为84b1b2f20d7b9d1d695c8f596ae0f10897142f4c与3552c8d69a49429d1ad15f11cb730083e4c8a95b。
2. [371da53cf89efcdce178fb7d9fbab20e855903ae](https://github.com/oneone1565/LightLang/commit/371da53cf89efcdce178fb7d9fbab20e855903ae)，时间2026-09-25T06:13:50Z，提交信息为“Merge branch 'main' of gitcode.com:NomiLight2026/lightLang”，双亲为2acabaf99041bfbd49be92d4ced167129e1125ff与230ac6c85d6accabcb6605bc7a1915e8642007ba。

两条合并提交使用NomiLight2026署名。GitHub最早根提交的作者账号映射为oneone1565，提交作者文本为NomiLight2026。现存历史、同名工具链和相同README例程共同建立与旧候选的同源联系。两平台当前快照同步情况、同步方向、账号自然人身份与维护分工继续核实。

第十轮GitCode目录显示19提交、4标签；本轮GitHub提交集合返回15项并已到达双根历史，标签对象返回3项。两平台数字分别作为各自页面及接口在读取时的状态保留。

## 固定连续中文原例

来源：[examples/hello.lt第1—11行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/examples/hello.lt#L1-L11)。

```text
函数 main():
    让 x = 10
    让 y = 20
    打印 x + y
    让 名字 = "世界"
    打印 "你好, " + 名字
    如果 x > 5:
        打印 "x 大于 5"
    否则:
        打印 "x 不大于 5"
    返回 0
```

这是原文件的完整连续函数。JSON采用原文件第1—11行逐字内容，保留缩进、空格、半角冒号、ASCII逗号和数字；展示范围为11行。原文件后缀为.lt，当前README主要使用.light。编译入口对.rs作特殊处理，其他输入进入词法与语法分析。该例在源码中已有“函数、让、打印、如果、否则、返回”对应的词元、AST和代码生成入口。执行结果待核实。

### 第十轮原例的保留与固定

第十轮保存的README原例当前位于固定[README.md第104—108行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/README.md#L104-L108)，原文如下：

```text
名字 = 输入()
如果 名字 != "":
    打印 "你好，" + 名字
否则:
    打印 "请输入名字"
```

原GitCode出处：[原README入口](https://gitcode.com/NomiLight2026/lightLang?tab=md#markdown-card-anchor)。当前GitHub固定README提供逐行可查的同一例程。

语义核验边界：[codegen.rs第1652—1685行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/codegen.rs#L1652-L1685)在gen_cmp中对浮点路径生成fcmp，其余路径生成icmp i64。该README原例使用字符串!=比较。字符串内容比较的语义与输入判空效果继续核实。正式展示采用完整hello.lt函数，两个原例均保留各自语境。

## 可见实现链

| 环节 | 固定原件 | 静态核验所得 |
| --- | --- | --- |
| 工作区 | [Cargo.toml第1—7行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/Cargo.toml#L1-L7) | light、lightc、lightgo、lightrt、lightweb五个Rust组件 |
| 词法 | [lexer.rs第211—265行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/lexer.rs#L211-L265) | Unicode字母／数字标识符；中文关键字映射到TokenKind |
| 缩进 | [lexer.rs第324—394行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/lexer.rs#L324-L394) | 行首缩进栈、Indent/Dedent、空行和注释处理、层级检查 |
| AST | [ast.rs第1—90行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/ast.rs#L1-L90) | Program、FnDef、Stmt、Expr及条件、循环、返回等节点 |
| 函数与顶层语句 | [parser.rs第53—99行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/parser.rs#L53-L99) | parse_program→parse_item，函数定义与普通顶层语句分别入树 |
| 条件分支 | [parser.rs第414—445行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/parser.rs#L414-L445) | 如果／否则如果／否则构造Stmt::If，块由缩进界定 |
| 类型推导 | [typeinfer.rs第1—103行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/typeinfer.rs#L1-L103) | 收集函数参数和返回约束、跨函数传播，循环最多50次并在稳定时退出 |
| 输入和导入 | [main.rs第271—368行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/main.rs#L271-L368) | 文件读取→Lexer::tokenize→Parser::parse_program；递归解析导入并合并Program |
| 编译入口 | [main.rs第109—154行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/main.rs#L109-L154) | typeinfer::infer→CodeGen::gen→写临时.ll；--emit-llvm输出IR |
| LLVM生成 | [codegen.rs第437—571行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/codegen.rs#L437-L571) | 写运行时声明和函数定义，顶层语句可包装进main；生成i64参数／返回约定 |
| LLVM分支 | [codegen.rs第1280—1328行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/codegen.rs#L1280-L1328) | 条件值、br i1、then／else／elif标签与结束标签 |
| 编译链接 | [main.rs第198—245行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/main.rs#L198-L245) | Clang编译.ll为目标文件并链接lightrt和额外静态库 |
| Rust运行时 | [lib.rs第74—103行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightrt/src/lib.rs#L74-L103)、[第209—261行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightrt/src/lib.rs#L209-L261) | 字符串、数组、字典结构及整数、字符串、布尔打印接口 |
| light执行／REPL | [main.rs第243—330行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/light/src/main.rs#L243-L330) | 历史和当前输入串接后写源码，调用lightc，再启动生成程序 |
| lightGo与FFI | [main.rs第297—374行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightgo/src/main.rs#L297-L374) | Cargo构建FFI库，再以--native传给lightc |
| lightWeb | [Cargo.toml](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightweb/Cargo.toml)及[src/lib.rs](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightweb/src/lib.rs) | tiny_http依赖与HTTP运行时实现可读 |

可见前端拥有词元、语法树与语义处理，再生成LLVM IR并链接本地运行时。由这些原件采用“中文关键字编译语言／Rust—LLVM工具链”分类。模块隔离、命名空间完整性、类型系统覆盖、对象所有权正确性和平台行为继续核实。

## 作者、时间和版本分层

- GitCode维护账号为NomiLight2026；GitHub仓库归属oneone1565；Git记录署名NomiLight2026。自然人身份和团队分工待核实。
- [3552c8d69a49429d1ad15f11cb730083e4c8a95b](https://github.com/oneone1565/LightLang/commit/3552c8d69a49429d1ad15f11cb730083e4c8a95b)是现存较早的根提交，作者／提交者时间均为2026-09-25T04:53:46Z，标题Initial commit。
- [84b1b2f20d7b9d1d695c8f596ae0f10897142f4c](https://github.com/oneone1565/LightLang/commit/84b1b2f20d7b9d1d695c8f596ae0f10897142f4c)是另一个根提交，时间2026-09-25T04:56:45Z，标题“初始化 Light 项目”。
- GitHub仓库created_at为2026-09-25T05:19:32Z。仓库创建、Git提交和首次对外公开属于不同时间字段；最早公开日期待核实。
- 当前固定提交时间2026-09-27T01:58:54Z。五个Cargo清单均为0.2.1，README交互提示、发行包文件名和CI变量亦为0.2.1。
- [标签对象](https://api.github.com/repos/oneone1565/LightLang/git/refs/tags)有0.2.0、beta和v0.1.0。0.2.0指向d507d3a03a993d3613f51e5fafee4ab9944a34e0，其[lightc清单](https://github.com/oneone1565/LightLang/blob/d507d3a03a993d3613f51e5fafee4ab9944a34e0/lightc/Cargo.toml#L1-L10)确为0.2.0，该提交时间2026-09-26T07:07:53Z。
- beta指向07a25c1766f992e2debd2c9a6c4955882c3516e4；v0.1.0指向c00a25b6bb33936f3aea7c6986bdf7eb70266c3d，后者README文件名与清单例子标0.1.0。
- [GitHub发行集合](https://api.github.com/repos/oneone1565/LightLang/releases?per_page=100)返回空数组。第十轮GitCode侧栏显示0.2.0发行及“14天前”；该相对提示原样保留。GitCode发行正文、绝对发布时间与附件继续核实。

## 许可和AI范围

[README第593—597行](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/README.md#L593-L597)明确GNU General Public License v3.0（GPL-3.0），[LICENSE正文](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/LICENSE#L1-L6)为GPL第3版。README说明第三方依赖遵循各自许可。许可证应用示例保留通用占位说明；项目专属版权署名与依赖许可明细继续核实。

第十轮GitCode原页读取记录保存atomcode标签。当前历史包含[gitee-bot署名的README更新](https://github.com/oneone1565/LightLang/commit/8b37b51e3e0637009c4116bd4a7eebe4936350aa)及gitee-agent合并文字。它们按工具活动线索保存。当前61个文本文件中，面向Light编程和Rust扩展的用法文档属于仓库内容。AI开发范围、模型、代码生成比例及运行期AI参与说明待核实。可见普通编译路径以Rust前端、LLVM IR、Clang及本地运行时组成。

## 与光明lang-009的同名关系

原目录光明使用Light／LightLang别名及.light扩展名。其原仓[pyproject.toml第5—81行](https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/pyproject.toml#L5-L81)标guangming 0.4.0、Light Contributors及Python入口；项目源地址为skywalk163/light。本轮项目的工作区、提交署名、版本线、Rust前端和语言例程分别记录。

两项目共享部分英文名称与扩展名。作者声明、设计借鉴和源码继承关系继续待核实。本条目按NomiLight2026／oneone1565来源消歧，GitCode与GitHub入口合并为一个对象。

## 作者说明、源码与运行三层证据

1. 作者功能说明：README列脚本、交互模式、Rust FFI、GUI、lightWeb和多线程等用途，标注早期开发阶段。
2. 源码可见：中文前端、类型推导、LLVM生成、编译链接、REPL重编、FFI及运行时入口已固定阅读。
3. 实际执行：[.gitcode/workflows/ci.yml](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/.gitcode/workflows/ci.yml)保存Linux、ARM、Windows构建与部分冒烟步骤；[GitHub Actions集合](https://api.github.com/repos/oneone1565/LightLang/actions/runs?per_page=100)返回total_count=0。CI配置执行结果、发行产物与独立运行结果待核实。

## 读取结果和后续边界

GitHub只读入口、固定文件和Git对象可读。直接tags集合URL返回接口允许路径错误，随后使用文档支持的git/refs/tags取得3个真实标签对象。84b1b2f快照的README文件请求返回404，随后在v0.1.0所指c00a25b快照读取到README。对原GitCode访问受限文件区的限制保持原状。

下一步优先顺序：
1. GitCode发行原件与两平台固定快照关系。
2. 原例字符串比较语义、模块边界及各平台执行证据。
3. 作者身份、AI参与范围、专属版权和第三方许可。
4. 与光明的作者声明及源码沿革关系。

本轮贡献为旧候选补证。范围内没有新增独立语言发现，公开GitHub副本按同源资料入口计入该对象。

