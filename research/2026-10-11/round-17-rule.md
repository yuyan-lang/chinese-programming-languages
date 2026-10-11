# 第十七轮：Issue #35 Rule DSL Core 核验

核验日期：2026-10-11（UTC）。本项研究约14:01—14:09 UTC，来源读取随后接受独立静态审阅。范围为[Issue #35](https://github.com/yuyan-lang/chinese-programming-languages/issues/35)既有候选。基线为565357c62953e94ea6824b32e801e82622278861；实际读取main的数据文件显示90项语言，按Rule DSL、RuleDSL、blizzard1413及原仓路径排重，命中0项。内核目录为9项。

## 结果

旧候选核实并整理为正式条目1项，新增发现0项。正式条目编号为lang-091。

取得固定提交199a2bac8e5b5dcf68be1e87756b4764b3c74e40的语法、中文源程序、Go解析入口、AST Visitor、模块加载、引擎组装、语句求值、规则执行、MIT全文、go.mod、生成任务与.gitignore，共13份文本。文本通过公开Gitee代码页pre.textContent读取，保留页面呈现的源码空格和换行。原始下载字节与哈希属于进一步核验层。

## 启动读取

- 根AGENTS.md全文：公开技术文档使用肯定陈述，资料缺口写待核实。
- main data/languages.json全文由普通GitHub文件接口取得，JSON解析为90项。
- research/2026-10-10/round-16.md全文。
- Issue35正文及全部1条评论（评论ID6101472276），正文comments=1与返回数量相符。
- GitHub PR查询“repo:yuyan-lang/chinese-programming-languages is:open”结果为空。
- 追加读取round-11-community.md，沿用既有候选及访问记录。

## 固定连续原例

主例采用中文示例.dsl第28—34行完整连续求和规则：

```text
export 规则 求和 = (开始: number, 结束: number): number => {
    让 总和 = 0;
    循环 (让 i = 开始; i <= 结束; i = i + 1) {
        总和 = 总和 + i;
    }
    返回 总和;
}
```

[原文件及行段](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/examples/05-chinese-keywords/%E4%B8%AD%E6%96%87%E7%A4%BA%E4%BE%8B.dsl#L28-L34)。程序使用原文件的“循环”，保留export、number、半角标点与四空格缩进。第5—7行另有完整问候规则，第10—20行是嵌套中文条件。独立审阅已复读固定网页核对求和7行与嵌套条件。项目执行和输出待专项核验。

## 实现链

1. RuleDSL.g4第25—32行定义规则及箭头函数，第77—111行定义变量、条件、循环和返回，第238—254行定义17个中文词元，第312—315行定义英文／中文标识符。
2. parser/parser.go第35—79行创建ANTLR输入流、生成词法器、Token流与生成解析器，读取Program后以ASTBuilder构造AST。
3. visitor_declarations.go第104—159行把规则名、参数、返回类型及函数体写入AST；visitor_statements.go第109—151行保存C式循环初始化、条件、更新、循环体及for-of字段。
4. module/loader.go第67—112行解析源文本，保存Program并登记导出规则；engine/engine.go组装解析器、加载器、求值器与执行器，按名称进入规则执行。
5. evaluator/statements.go第93—141行处理C式循环；第173—184行求值返回表达式并构造ReturnValue。engine/executor.go第63—113行执行规则体并接收ReturnValue。
6. .gitignore第33—36行将parser/generated/、interp及tokens文件列为生成产物；Taskfile.yml第1—8行提供ANTLR4生成Go解析器任务。固定parser目录可见语法、Visitor和测试文件，生成产物另按构建边界记录。项目安装、生成、编译、测试及运行保持待核。

## 文档差异及覆盖边界

- 固定语法FOR_CN为“循环”，固定中文源程序求和使用“循环”。同目录README的表格写“循环”，其循环例写“对于”；examples总览文档也写“对于”。以固定实现和源程序描述已核词元，文档写法按原文保留。
- README条件例出现连写“否则如果”。语法将ELSE_CN与IF_CN分开，中文Identifier可连续匹配这些汉字；最长词元匹配形成静态冲突风险。固定中文源程序采用嵌套“否则 { 如果 ... }”。
- VisitIfStatement保存首个条件、首条then及末条else语句。else-if链中间条件与分支的完整处理继续待核。
- for-of语法及AST字段可见；executeForStmt主体按Init／Condition／Update／Body处理。for-of求值覆盖继续待核。
- 中文Identifier起始字符范围为U+4E00—U+9FA5，后续还可含ASCII字母、数字与下划线。结构标点在语法中以半角表示；全角结构标点待核。
- number、string、boolean、object、array是固定类型关键字。中文README将Array、String、Math等接口列为英文内置函数名。
- 上述结论分为源码直接可见结构和静态风险推断；独立执行结果保持待核。

## 作者、日期、版本、许可与关系

固定LICENSE完整21行显示MIT License，版权行为Copyright (c) 2026 blizzard1413。原仓显示名blizzard，README署名DSL Core Team；自然人姓名和团队构成待核。

固定go.mod为Go1.24.0，ANTLR Go运行时v4.13.1；原README前置要求写Go1.21+，条目以固定模块要求记录。Go版本属于实现工具链要求。

原仓根页列main、46次提交、v1.0.0／v1.1.0／v1.2.0三个标签，头提交标题为v1.2.0。README给出v1.0.0完成日2026-01-06；Go包目录显示v1.2.0发布日2026-01-08，并有模块存在更新版本的提示。日期分层保存。固定提交详情在云浏览器跳转Gitee登录页，读取在此结束；标签绝对时间、最新版本、仓库创建、根提交与首次公开日期待核。

原仓和Go模块同路径，按同一项目。JS／TS为作者语法风格说明，ANTLR4和Go为源码确认的工具与实现；源码上游继承待核。.kiro/specs为可见工具目录，AI开发声明、模型与贡献比例待核。作者测试覆盖、性能与完成度数字属于文档声明。

## 访问与检索记录

普通网页工具：
- 原仓根页成功读取。
- 固定RuleDSL.g4的blob与raw、固定parser/parser.go、evaluator/evaluator.go、engine/engine.go、LICENSE、commit、tags及evaluator目录：Cache miss或工具不可访问。
- pkg.go.dev固定v1.2.0、parser、evaluator、generated、generated?tab=source、05-chinese-keywords及license标签的直接open：Cache miss。
- proxy.golang.org的v1.2.0.info单次读取：Cache miss。
- Go包根、examples、05-chinese-keywords、parser、ast、module与engine的搜索索引：可读原项目文档与公开API类型。
- GitHub仓库查询blizzard1413：返回空集合。

精确检索词：
- "blizzard1413" "dsl" "RuleDSL.g4"
- "blizzard1413" "dsl" github
- site:pkg.go.dev/gitee.com/blizzard1413/dsl/parser/generated "RULE"
- "blizzard1413" "DSL" -site:pkg.go.dev -site:gitee.com
- "blizzard1413/dsl" "LICENSE"
- "blizzard1413" "Rule" 作者
- "blizzard1413" "github.com"
- site:pkg.go.dev/gitee.com/blizzard1413/dsl/evaluator "Eval"

云端浏览器：
- 公开网页浏览器成功读取固定源码。
- 首次按chinese.dsl猜测文件名返回Gitee404；随即读取实际目录，定位中文示例.dsl，取得完整129行。目录为README.md、main.go及中文示例.dsl。
- 固定README页面为渲染文档，首个pre仅是运行说明；该片段从源码副本集合中移除。README差异以完整页面文本和独立审阅记录保存。
- 固定commit详情跳转登录，研究在认证边界停止。
- 研究使用公开网页、普通GitHub只读工具及本地静态文件整理；远端写入、安装、编译、执行、测试和第三方联系均为0。

## 后续可推进事项

1. 若开展独立构建专项，先核生成器产物与当前go.mod，再验证示例模块加载与输出；本轮正式分类依据固定源码。
2. 针对原文差异核实“对于”、连写“否则如果”、else-if Visitor及for-of求值的版本演变，采用新的固定提交或原作者修复记录。
3. 在公开可读资料出现时补标签绝对时间、准确最新发行、作者构成和AI开发声明。
4. 本轮停止扩大查找范围，保留Issue35旧资料链接与既有来源。

## 全部条目来源

- [原仓说明与版本标签入口](https://gitee.com/blizzard1413/dsl)
- [固定中文求和原例](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/examples/05-chinese-keywords/%E4%B8%AD%E6%96%87%E7%A4%BA%E4%BE%8B.dsl#L28-L34)
- [固定完整中文原例与嵌套分支](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/examples/05-chinese-keywords/%E4%B8%AD%E6%96%87%E7%A4%BA%E4%BE%8B.dsl#L1-L41)
- [固定词法、语法与中文标识符规则](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/parser/grammar/RuleDSL.g4)
- [固定Go解析入口](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/parser/parser.go#L35-L79)
- [固定规则与箭头函数AST构造](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/parser/visitor_declarations.go#L104-L159)
- [固定分支及循环AST构造](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/parser/visitor_statements.go#L84-L151)
- [固定模块解析与规则导出登记](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/module/loader.go#L67-L112)
- [固定引擎组装与按名执行](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/engine/engine.go)
- [固定循环与返回求值](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/evaluator/statements.go#L93-L184)
- [固定规则执行与返回值接收](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/engine/executor.go#L63-L113)
- [固定MIT许可及版权署名](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/LICENSE#L1-L21)
- [固定Go版本与ANTLR依赖](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/go.mod#L1-L15)
- [固定ANTLR生成任务](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/Taskfile.yml#L1-L8)
- [固定生成目录忽略规则](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/.gitignore#L33-L36)
- [固定中文README的文档差异](https://gitee.com/blizzard1413/dsl/blob/199a2bac8e5b5dcf68be1e87756b4764b3c74e40/examples/05-chinese-keywords/README.md)
- [Go包目录版本发布日期](https://pkg.go.dev/gitee.com/blizzard1413/dsl)
- [原始待核议题与旧来源记录](https://github.com/yuyan-lang/chinese-programming-languages/issues/35)

辅助核对：
- [唯一旧评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/35#issuecomment-6101472276)
- [第十六轮日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/round-16.md)
- [第十一轮候选日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/round-11-community.md)
- [Go examples总览](https://pkg.go.dev/gitee.com/blizzard1413/dsl/examples)
- [Go中文例程说明](https://pkg.go.dev/gitee.com/blizzard1413/dsl/examples/05-chinese-keywords)
- [Go Parser API](https://pkg.go.dev/gitee.com/blizzard1413/dsl/parser)
- [Go AST API](https://pkg.go.dev/gitee.com/blizzard1413/dsl/parser/ast)
- [Go Module API](https://pkg.go.dev/gitee.com/blizzard1413/dsl/module)
- [Go Engine API](https://pkg.go.dev/gitee.com/blizzard1413/dsl/engine)

