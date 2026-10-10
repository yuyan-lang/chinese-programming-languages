# 第六轮既有条目：光明、天工语及段言沿革补订

核验日期：2026-10-10（UTC）。
资料基线：yuyan-lang/chinese-programming-languages，main提交38de4b3dc0580eb8c3dcad682d9c7e18c7798bdd。
核验方式：公开GitHub接口、原作者仓库文件、PyPI公开发行资料及普通网页搜索；实施范围为文献与源码静态核验。

## 一、基线与本轮交付

已读取根AGENTS.md、data/languages.json中的lang-008／009／010、languages/lang-008.html、Issue #1与全部5条评论、Issue #5及其空评论集合。相关日志包括research/2026-10-09/community.md、research/2026-10-10/existing.md、round-3-existing.md、round-4-existing.md及round-5-existing.md。

本轮形成三条资料：

- lang-009光明：补正式名称、现行包名、版本、连续中文原例、Python／LLVM路径、分层语法和段言合流沿革。
- lang-010天工语：补原作者署名、中文原例、Rust／Logos／AST解释链、版本显示差异和开发路线。
- lang-008段言：保留历史条目、原入口与入门教程，补现行迁移公告和历史版本，采用单个教程代码块的连续原文。

008与009保留各自历史名称和原ID；当前统一工具链在009记录。目录数量按“条目数”表述，历史阶段与现行实现按relations字段关联。

安装、构建、测试执行及样例运行属于后续验证范围。本轮生成的文档资料供统一PR使用。

## 二、光明的身份、日期与版本

### 当前来源链

- PyPI原入口：https://pypi.org/project/guangming/
- 本轮检索可读的0.4.0页面：https://pypi.org/project/guangming/0.4.0/
- 原仓库：https://github.com/skywalk163/light
- 固定main提交：f3cd01eec801360275a50a7ed01753cefb8b45a9
- 提交时间：2026-10-10T09:58:01Z。
- 仓库创建时间：2026-08-09T10:58:07Z；pushed_at：2026-10-10T09:58:08Z；archived=false。
- 当前递归Git树完整返回，truncated=false，共2511项。
- 当前README标题为“光明（LightLang）编程语言”；pyproject.toml采用“光明（Light）”，发行包名guangming。
- pyproject.toml作者署名Light Contributors；CONTRIBUTORS.md保存主要署名skywalk163及其他提交署名。个人实名待核实。
- PyPI页面列维护者skywalk163，发布证明指向GitHub skywalk163/light，发布提交a2c9929ccbb27bccbc60429202db9e53cbabe0ac。该证明将包和原仓库直接关联。

固定资料：

- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/README.md#L1-L35
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/pyproject.toml#L5-L30
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/CONTRIBUTORS.md
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/src/version.py#L8-L44

### 版本分开记录

1. src/version.py第9—22行为0.4.0、发布日期2026-10-03、stable；pyproject.toml同为0.4.0。
2. GitHub Releases完整集合共6项：
   - v7.0.0：2026-09-26T07:14:21Z，正式发行标志。
   - v0.3.0：2026-10-02T03:45:28Z，正式发行标志。
   - v0.4.0-rc1：2026-10-02T10:34:27Z，预发行。
   - v0.4.0-rc2：2026-10-02T14:58:25Z，预发行。
   - v0.4.0-rc3：2026-10-03T05:46:26Z，预发行。
   - v0.4.0：2026-10-03T07:07:46Z，正式发行标志。
3. v0.4.0发行说明记录全仓公开版本号统一到0.4.0家族；部分正文保存预发行候选叙述。正式版本状态由release的prerelease字段、当前包配置和版本常量交叉核验。
4. v7.0.0发行页正文保存双线合流阶段的历史说明；原合流提交时间为2026-08-14，GitHub Release发布时点为2026-09-26。
5. 语言名称首次对外公开时点、首个光明安装包上传记录及其他发行渠道更早记录待核实。

发行链接：

- https://github.com/skywalk163/light/releases/tag/v7.0.0
- https://github.com/skywalk163/light/releases/tag/v0.3.0
- https://github.com/skywalk163/light/releases/tag/v0.4.0

### 日期口径

- 2026-06-10：继承的段言根提交与源码历史。
- 2026-08-09：光明仓库创建和分支名称变更。
- 2026-08-14：两条开发分支的实际合流提交。
- 2026-09-26：现存GitHub v7.0.0发行记录。
- 2026-10-03：0.4.0发行及当前版本常量发布日期。

首次公开公告时间作为独立待核实字段。提交时间、仓库创建时间、文档自述日期和发行时间分别保存。

## 三、光明的原例、实现和资料取舍

### 连续中文代码

文件：examples/test_hello_src.light。
固定提交：f3cd01eec801360275a50a7ed01753cefb8b45a9。
blob：bbd7b0cb4d8cdc76e82370cc28779df8e0bacb5e。
第1—11行完整原文采用以下来源：

https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/examples/test_hello_src.light#L1-L11

代码展示打印、设定变量、中文乘法、段落定义、返回和函数调用。原有缩进、空行与中文冒号按源文件保留。代码连续包含检查通过。

另外读取examples/hello.light核对函数、递归和范围循环；正式条目选用较短的独立完整原例。

### 实际入口链

- cli/light.py第213—242行：_compile_src构造LightParser，再调用PythonCodeGenerator.generate。
- cli/light_unified.py第555—622行：SRC分支构造解析器，生成Python源码，run分支执行exec。
- src/light_parser_v3.py第14—45行：组合parser_core、parser_stmt与parser_expr模块为LightParser。
- src/compiler.py第1165—1227行：另一公开编译接口包含词法、语法、AST适配、优化、类型检查。
- src/llvm/compiler.py第559—607行：调用clang编译runtime_typed.c、LLVM IR并链接。
- cli/light.py第1722行及1774行：CLI后端选项为src、antlr、native、llvm-typed；native和llvm-typed进入同一编译路径。
- src/llvm/compiler.py第1282—1297行：Python模块依赖具有专门的原生编译诊断分支。
- docs/architecture.md将C、Wasm列为独立实验性后端；src/version.py的后端数组属于项目能力声明。
- bootstrap/bootstrap_v3.light在固定树中存在；完整自举流程与生成物一致性待核实。
- 架构文档中的旧行号与当前文件长度各自保存；条目的实现判断采用本轮实际读取的源码。

关键链接：

- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/cli/light.py#L213-L242
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/cli/light_unified.py#L555-L622
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/src/compiler.py#L1165-L1227
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/src/llvm/compiler.py#L559-L607
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/docs/architecture.md
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/docs/%E5%8E%9F%E7%94%9F%E8%85%BF%E8%83%BD%E5%8A%9B%E8%BE%B9%E7%95%8C.md

### 语法层级与数量口径

README说明L0—L7为文体与方言层级，列L1白话体、L2文言体、L3领域嵌入、L4外语引用及后续层级。

当前README第12行保存“30个L0核心字”的说明；src/keywords.py第7—35行指定docs/language/l0-core.md为规范来源；该规范第3行列44字。keywords.py还区分规范字集和实际词法关键字集。正文采用层级概念，规范精确字数与全部实现覆盖的统一口径待进一步核验。

- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/src/keywords.py#L1-L35
- https://github.com/skywalk163/light/blob/f3cd01eec801360275a50a7ed01753cefb8b45a9/docs/language/l0-core.md#L1-L34

完整后端覆盖、性能、宣传数字和测试通过数属于项目自述或后续验证范围。

## 四、段言与光明的真实沿革

### 原有段言资料保留

原详情页languages/lang-008.html记录中文声明、输出、函数、缩进、命令行与官方入门教程。本轮保留这些主题与两个原参考入口。

原网页代码说明为“摘自或改编”，由变量例和函数例拼接。本轮采用固定教程第446—450行的一个连续完整代码块，包含“段落 问好 接收 名字”、打印、两次调用及原注释。

- 段言固定末次提交：b2fe4d471bef736e9c32afc842968771959af804。
- 时间：2026-08-21T04:48:47Z；pushed_at：2026-08-21T04:48:53Z。
- 仓库创建：2026-06-10T03:14:51Z；archived=false。
- 递归树完整返回，truncated=false，共1944项。
- docs/30分钟入门段言.md标v6.0；blob 06fdf4783cbb357132ca82a3bf9d97724ef7c13b。
- pyproject.toml为duan 6.3.0，Duan Contributors，duan／duanc入口；README徽章为6.2.0。
- GitHub Releases集合返回空列表。PyPI历史包的实际上传记录待核实。

原例与配置：

- https://github.com/skywalk163/duan/blob/b2fe4d471bef736e9c32afc842968771959af804/docs/30%E5%88%86%E9%92%9F%E5%85%A5%E9%97%A8%E6%AE%B5%E8%A8%80.md#L446-L450
- https://github.com/skywalk163/duan/blob/b2fe4d471bef736e9c32afc842968771959af804/pyproject.toml#L5-L78
- https://github.com/skywalk163/duan/blob/b2fe4d471bef736e9c32afc842968771959af804/src/keywords.py#L13-L42
- https://github.com/skywalk163/duan/blob/b2fe4d471bef736e9c32afc842968771959af804/cli/duan_unified.py#L212-L308

### 六项交叉证据

1. 共同根提交a7fc3a30f7f17a7c50e36c71b730cbcb82a4768e，作者skywalk163，2026-06-10T03:25:57Z。两个仓库的历史接口都返回该无父提交；README标“段言（Duan）”、v1.0 MVP与中文原例。
   https://github.com/skywalk163/duan/blob/a7fc3a30f7f17a7c50e36c71b730cbcb82a4768e/README.md#L1-L17

2. 改名提交5eb250dd196a07b2e083d8b077a27cba21ea16e6，2026-08-09T15:13:10Z，主题“Rename project from duan to light”。README补丁将名称、仓库入口与后缀由段言体系改为光明。
   https://github.com/skywalk163/light/commit/5eb250dd196a07b2e083d8b077a27cba21ea16e6

3. 合流前光明父提交8df4314e0584ddcf93d10fca93456d0dd9d5e4d1，2026-08-14T06:44:20Z；pyproject.toml为light 6.0.0，README为L0—L4分层语法说明。
   https://github.com/skywalk163/light/blob/8df4314e0584ddcf93d10fca93456d0dd9d5e4d1/pyproject.toml#L5-L13

4. 合流前段言父提交390c5e0df5ddda73dfae415ef4defba990949315，2026-08-14T06:01:17Z；pyproject.toml为duan 6.3.0，README和.duan例子保留段言名称。
   https://github.com/skywalk163/duan/blob/390c5e0df5ddda73dfae415ef4defba990949315/pyproject.toml#L5-L13
   两亲的examples/hello.light与examples/hello.duan程序主体一致，首行项目名分别为光明与段言。两文件完整读取，支持同源关系和语法连续性。

5. 双亲合并提交87f393b7b4d8cf659a2844cefd0ef4bbb17e4753，2026-08-14T11:26:21Z，父节点恰为上列两项。提交说明明确段言6.3与光明6.0合流、版本统一7.0.0。提交说明中的“共同祖先16abd2b8／分叉11天”按作者说明保存，精确分叉图分析待核实。
   https://github.com/skywalk163/light/commit/87f393b7b4d8cf659a2844cefd0ef4bbb17e4753

6. 段言公告提交b6466eb7300097a0af51c531ea00334e90e6b988，2026-08-21T03:46:42Z，README第1—6行公告停止独立开发并迁移至光明；当前光明src/version.py第35—39行再次记载合流。
   https://github.com/skywalk163/duan/commit/b6466eb7300097a0af51c531ea00334e90e6b988
   https://github.com/skywalk163/duan/blob/b2fe4d471bef736e9c32afc842968771959af804/README.md#L1-L9

结论：两个历史名称、分支阶段、共同根、改名和合流均有原始记录。本轮保留008作为历史阶段，009作为当前统一项目；名称记录与实现计数采用各自清楚的口径。

## 五、言叶／文言心／言的辅助核验

原作者设计文档：
https://deepseek.csdn.net/6a059cdf662f9a54cb746b14.html

页面署名天马行空skywalk，显示2026-05-05 20:47:07发布；页面时区待核实。正文对比言叶、文言心、言，包含“定”“函”“印”、中文管道等语法，以及Python转译／SBCL方案。该材料按设计与作者自述记录。

GitHub按owner检索取得：

- 言语言：https://github.com/skywalk163/yan
- 固定提交815353dfe80dbae46ac2e0dabe5e9f447559bb78，提交2026-06-08T12:31:52Z。
- 仓库创建2026-06-02T10:55:57Z，pushed_at为2026-06-08T12:32:17Z。
- README正式标题“言语言（Yán）”，原例包括“定 平方 = 函 x：”“返回 乘 x x”“印”等，具有Python目录及解析器文件。
- README自述2026-05-28语法v2里程碑。文档里程碑日期与GitHub建库日期分别记录。
- 完整递归树可读；README及文件树支持继续核验的实际源码入口。
- 固定入口：https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/README.md
- GitHub正文搜索“言叶”“文言心”在duan／light／yan集合返回空列表；搜索“段言”在yan返回空列表。代码搜索覆盖与索引完整性待核实。
- 用户名相同、关键字相似与时间相邻分别作为关系线索；言叶、文言心、言与段言／光明之间的具体迁移记录、共享提交和兼容规范待核实。
- 另取得skywalk163/yanlv的言律README和skywalk163/yanzhi仓库元数据，作为名称消歧的辅助入口；本轮正式条目聚焦008／009／010。

Issue #5的待核实状态继续保留。对言语言的深入实现与继承核验属于后续研究范围。

## 六、天工语证据链

### 身份与时间

- 原仓库：https://github.com/HyperXenonZephyr/TianGongKaiWu-Programming_Language
- README名称：天工語（TianGong Lang）。
- Cargo包名：tiangong-lang；description为天工开物编程语言；程序名天工語。
- Cargo作者：天工语开发团队；提交作者：HyperXenonZephyr。个人实名及团队成员待核实。
- 固定main提交：50a9b051fb8cfd5403d28eee357e65344a31c985。
- 最新提交：2026-05-01T14:17:02Z；pushed_at：2026-05-01T14:17:20Z。
- 仓库创建：2026-03-29T13:18:56Z；archived=false。
- commits完整页共19项，含两个无父提交：
  - 109cee24a54a6e275d15c19b5823c03eaea73ac6，2026-03-29T13:18:56Z，Initial commit。
  - ed3ea4138c2facdd1256660cb65f947bb353db5b，2026-03-29T13:43:31Z，“首次提交本地代码”。
- 2026-03-29T13:46:44Z的eaf41422…把两条起点合并。
- CHANGELOG记0.2.0日期2026-03-31，Cargo.toml为0.2.0。
- src/main.rs第16行与REPL横幅保留0.1.0。
- GitHub Releases集合返回空列表。README预编译二进制发行入口及正式标签待核实。
- 首次公开公告日期单列待核实。

### 原例

文件examples/counted_loop.tg，blob 2ac04515f4e49441c09a7f907850e6f7e6022382。
正式条目采用第9—17行连续函数定义与调用：

https://github.com/HyperXenonZephyr/TianGongKaiWu-Programming_Language/blob/50a9b051fb8cfd5403d28eee357e65344a31c985/examples/counted_loop.tg#L9-L17

源码含“謂 星號”“設 結果”“走 數量 次”“返 結果”“執 星號(十) 曰”，保留繁体关键字、空格、原引号和星号。字符串连接调用对应标准库命名；执行结果待核实。

另外读取examples/hello.tg、README各语法块，按各自文件和版本保存。

### 静态实现核验

- Cargo.toml第1—30行：Rust 2021，Logos 0.14和常用依赖。
- src/lexer/mod.rs第5—145行：Logos派生、設／令／才、若／若否／若然則、走／次、謂／執、曰／輸出等词元。
- 第149—173行：中文及阿拉伯数字、小数、中文直角引号及英文双引号规则。
- 第179—184行：空白和//、#、注:／注：注释。
- src/parser/mod.rs第48—145行：语句分派，包括“才”通变量声明的专门分支。
- 第150—185行：表达式后置输出和省略設的赋值形式。
- 第272—352行：计次循环解析与内部计数表达式。
- 第409—482行：函数定义。
- 第670—698行：遍历语句。
- src/main.rs第82—98行：Lexer→Parser→Interpreter调用链。
- src/runtime/interpreter.rs第27—63行：逐条解释AST；ImportStatement／ExportStatement分支直接返回Value::Null。
- src/runtime/value.rs第5—16行：Number、Integer、String、Boolean、Null、Array、Dict、Function与NativeFunction。
- README列字节码／JIT、模块和扩展标准库为开发方向；机器码后端与Wasm为计划项。

链接：

- https://github.com/HyperXenonZephyr/TianGongKaiWu-Programming_Language/blob/50a9b051fb8cfd5403d28eee357e65344a31c985/src/lexer/mod.rs#L5-L184
- https://github.com/HyperXenonZephyr/TianGongKaiWu-Programming_Language/blob/50a9b051fb8cfd5403d28eee357e65344a31c985/src/parser/mod.rs#L272-L352
- https://github.com/HyperXenonZephyr/TianGongKaiWu-Programming_Language/blob/50a9b051fb8cfd5403d28eee357e65344a31c985/src/main.rs#L82-L98
- https://github.com/HyperXenonZephyr/TianGongKaiWu-Programming_Language/blob/50a9b051fb8cfd5403d28eee357e65344a31c985/src/runtime/interpreter.rs#L27-L63

### 资料边界

README将“知”列入判断设计，把“說通稅”列入注释设计；当前词法源码将說映射到Except，注释由另外的regex规则处理。这些古汉语设计词与实际语法的对应关系待核实。

README、CHANGELOG中的测试通过数、完整度和性能描述属于作者自述。源码支持“Rust实现的AST解释器”的分类。预编译发行、跨平台构建、运行行为及后续计划的完成进度待核实。

## 七、实际检索与访问状态

### 普通web查询

全年代检索；本轮查询未设日期过滤。实际读取到的项目时间范围主要为2026年3月至10月。

实际查询包括：

- "guangming" "光明" 编程
- "skywalk163" "guangming"
- site:pypi.org/project/guangming "Release history"
- site:blog.csdn.net skywalk163 光明 段言
- "光明" "言叶" 编程
- "天工語" "HyperXenonZephyr"
- "天马行空skywalk" "光明"
- "天马行空skywalk" "段言"
- "guangming" "0.1.0"
- "skywalk163" "言叶"
- "skywalk163" "文言心"
- "skywalk163" "light" "光明" "2026-08"
- "guangming" "0.3.0" "PyPI"
- "天马行空skywalk" "言叶" "段言"（csdn.net域名）
- "光明" "skywalk163" "首次"（csdn.net域名）

部分查询返回同名机构、其他PyPI包或文学作品；正式条目采用可追溯的项目原资料。

公开PyPI项目页、版本页、#history与/pypi/guangming/json直开在本轮返回Cache miss。普通搜索结果取得0.4.0页面的完整项目资料、包名、上传日期及发布证明。GitHub发布记录与源码版本用作交叉核对。PyPI全部历史上传列表及精确上传秒数待核实。

### GitHub查询

- 仓库元数据、固定文件、完整递归树、commits集合、releases集合。
- 段言／光明早期历史查询：until=2026-06-01和2026-06-11；合流前历史：until=2026-08-15；per_page=100。
- README历史：path=README.md、since=2026-08-14。
- 单独读取改名提交与双亲合并提交。
- search_repositories：user:skywalk163、user:skywalk163 yan、user:skywalk163 言、user:skywalk163 wen、user:skywalk163 yanye、user:skywalk163 wenyan。
- search正文：言叶、文言心、段言，仓库范围见第五节。
- 直接fetch搜索仓库API请求返回INVALID_ARGUMENT，之后使用工具提供的search_repositories完成检索。
- 段言根提交pyproject.toml与当前src/version.py读取返回文件缺项；版本采用实际存在的README与pyproject.toml记录。

## 八、交付核对及剩余证据

- 三条保留原ID、名称与原有参考入口。
- 三段示例均来自单一固定文件中的连续原文，且通过原字符串包含检查。
- 光明与段言的继承和合流由多份独立原始记录支持。
- 光明的现行包号、历史合流号及GitHub发行日期分别记录。
- 天工语的Cargo号和CLI字符串分别记录。
- 光明的L0数量、后端能力、各原始文档中自述的性能和测试结果，按具体资料范围保存。
- 言叶／文言心／言的项目演进关系保留待核实。
- 首次对外公开公告、完整发行包历史、个人实名、运行兼容性、构建结果和性能仍需补证。

