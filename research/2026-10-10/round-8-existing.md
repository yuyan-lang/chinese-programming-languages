# 第八轮已有条目完善：曜语与CNplus

核验日期：2026-10-10（UTC）。范围为公开网页、GitHub静态文件、仓库／提交／标签／发行元数据。交付为lang-021、lang-022两个完整替换对象，保留ID及原有全部6条引用。原项目的源码、脚本、测试和二进制均按静态资料阅读；独立运行结果待核实。

## 一、基线与本轮结果

百科基线为[48e7a753e30e8059b0c617a1c38f5385c54e3b4f](https://github.com/yuyan-lang/chinese-programming-languages/tree/48e7a753e30e8059b0c617a1c38f5385c54e3b4f)。

开轮已读取：
- [根AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/48e7a753e30e8059b0c617a1c38f5385c54e3b4f/AGENTS.md)：肯定陈述、直接说明事实，证据缺口标注待核实。
- [data/languages.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/48e7a753e30e8059b0c617a1c38f5385c54e3b4f/data/languages.json)中的曜语lang-021与CNplus lang-022完整对象。
- [round-7.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/48e7a753e30e8059b0c617a1c38f5385c54e3b4f/research/2026-10-10/round-7.md)。
- [Issue #1全部7条评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)，包括第七轮文语、灵语完善与原始引用保留要求。

结果：
1. 曜语补齐固定递归函数原例、根提交与发行时间、两个标签对应关系、实际C编译链、简化语义检查范围、Gemini声明范围、曜语词法器样例和Java Android演示应用关系。
2. CNplus将当前版本更新为源码及正式发行一致的1.7.0；补完整阶乘调用原例、独立前端与三后端执行链、历史作者账号链、2021／2022／2026日期、旧仓迁移说明与archive逐文件同源核验。
3. 两条description分别为279字与318字（含字母及标点的字符串长度），落在目标200—400字区间。
4. 源码构建、安装、执行、二进制、性能与测试通过数量继续按证据范围标注待核实。

## 二、检索入口及查询记录

### GitHub只读查询

对两个现有原仓分别读取：
- 仓库元数据与默认分支：GET /repos/{owner}/{repo}、/branches。
- 固定递归树：/git/trees/{固定SHA}?recursive=1。
- 默认分支历史：/commits?per_page=100；两个现有原仓与两个历史仓库的返回均到达parents为空的根提交。
- 标签：/git/refs/tags；对CNplus v1.7.0继续读取注解标签对象。
- 发行：/releases；CNplus另读/releases/latest。
- 固定README、包元数据、语言样例、源码、规范、项目规则、历史归档文件。
- 关键原例按start_line／end_line再次读取，以核对换行、缩进、标点和引用行号。

当前分支核验：
- a737812/yaolang只有main，HEAD为8b639836a59c9a9e96f70de67a6a1ad51d157c9d，与本轮给定固定点一致。
- CNplus/CNplus-lang只有main，HEAD为5000dc1de6554ce567cad80372f39b9808566b7d，与本轮给定固定点一致。
- 曜语默认历史45条、递归树49项；CNplus默认历史76条、递归树546项。两棵树truncated=false。
- 历史CNplus-python默认历史44条；CNplus-mixed默认历史13条。

### 普通网页查询

实际查询：
- “曜语” “曜神”
- “CNplus” “AS13379”
- “CNplus” “2021”
- “CNplus-lang” “AI”
- “曜语” “a737812”
- “CNplus-python” “2021”

网页搜索回传少量语言相关线索及大量同名商业项目。现有条目的事实依据采用原作者仓库、原始文件及发行元数据。第三方聚合搜索结果用于发现入口。

直接读取[CNplus官网](https://cnplus.org)与[曜语README所列官网](https://a737812.github.io/yaolang)时，网页工具返回不可访问。对应仓库文档与静态源码保持可读，本轮沿该原始入口完成核验。官网当前呈现及在线运行效果待核实。

### 工具读取边界

GitHub的/tags集合URL在当前fetch工具中返回端点错误，随后通过支持的/git/refs/tags完整读取标签。CNplus树遍历evaluator.py首次全文读取发生内部错误，随后读取固定第1—150行成功，取得后端能力与执行入口。其余实际执行路径通过CLI、两个转译后端及发射器交叉核对。以上属于资料读取范围，运行表现另行标注待核实。

## 三、曜语lang-021

### 固定来源

固定点：[8b639836a59c9a9e96f70de67a6a1ad51d157c9d](https://github.com/a737812/yaolang/tree/8b639836a59c9a9e96f70de67a6a1ad51d157c9d)。

主要材料：
- [README](https://github.com/a737812/yaolang/blob/8b639836a59c9a9e96f70de67a6a1ad51d157c9d/README.md)。
- [编译器源码](https://github.com/a737812/yaolang/blob/8b639836a59c9a9e96f70de67a6a1ad51d157c9d/src/yaolang.c)。
- [综合例程](https://github.com/a737812/yaolang/blob/8b639836a59c9a9e96f70de67a6a1ad51d157c9d/test/comprehensive.%E8%80%80)。
- [曜语词法器例程](https://github.com/a737812/yaolang/blob/8b639836a59c9a9e96f70de67a6a1ad51d157c9d/test/yao_lexer.%E8%80%80)。
- [APK构建脚本](https://github.com/a737812/yaolang/blob/8b639836a59c9a9e96f70de67a6a1ad51d157c9d/build_apk.py)。
- [Java演示Activity](https://github.com/a737812/yaolang/blob/8b639836a59c9a9e96f70de67a6a1ad51d157c9d/apk/src/com/yaolang/app/MainActivity.java)。

### 日期、作者与版本

- 仓库created_at：2026-08-20T12:45:12Z。
- [根提交59022b110d2055e1dfe9d70bd29ba0be36ee11d4](https://github.com/a737812/yaolang/commit/59022b110d2055e1dfe9d70bd29ba0be36ee11d4)时间：2026-08-20T13:34:19Z，parents为空，作者署名a737812。
- [v0.1.0-alpha Release](https://github.com/a737812/yaolang/releases/tag/v0.1.0-alpha)发布时间：2026-08-20T13:37:25Z，作者a737812，prerelease=false，附yaolang_app.apk，大小6900字节。
- main固定点提交时间：2026-08-20T14:21:07Z。仓库pushed_at为2026-09-06T03:26:32Z；分别保留提交时间和仓库推送元数据的含义。
- [标签引用](https://api.github.com/repos/a737812/yaolang/git/refs/tags)：v0.1.0-alpha指向根提交59022b1；v0.1.0指向当前8b63983。
- 两个标签的src/yaolang.c共用blob 63a2b4ff61c5bcf006f19f6214248ed5e0292b38，源码第3行与第32行版本均为0.1.0-alpha。v0.1.0的标签名按标签记录，稳定性继续待核实。
- 源码第14行署名“曜神（由Gemini构造）”。条目保留作者自述与仓库账号，个人实名及协作者待核实。
- 源码第15行及README声明MIT。独立许可证文件与完整许可范围待核实。

### 中文原例与实际实现

选用[综合例程第9—21行](https://github.com/a737812/yaolang/blob/8b639836a59c9a9e96f70de67a6a1ad51d157c9d/test/comprehensive.%E8%80%80#L9-L21)，为相邻两个完整函数：阶乘和斐波那契。原文件第48行起另有主函数调用及输出。交付code来自再次按行取回的文本，属于连续定义片段。

源码链路：
- 第48—55行接受.yao、.耀扩展名。
- 第364—427行为中文关键字表；支持中文及ASCII标识符的逻辑见第188—199行。
- 第571行起词法扫描，第1055行起解析接口，第2039行起程序解析。
- 第2250—2316行为语义登记；第一遍收集顶层函数、结构、枚举、变量、类型别名，第二遍进入作用域并登记函数参数。第2312行把函数体深入检查列为TODO。
- 第2925行起由AST生成C源码，输出运行时函数采用_yao_*名称。
- 第3534—3602行依次调用lex、parse_program、types_init、sema_analyze、cgen_program。
- 第3614—3635行提供C代码输出；第3645—3685行保存临时C文件并通过popen调用cc，常规链接-lm，X11分支另带-DHAS_X11与-lX11。

README的静态类型／系统编程定位与源码已实现部分分别记录；完整类型检查、所有权模型及零成本抽象实现深度待核实。

### AI、自举与Android范围

Gemini声明来自编译器文件头，按该处原文记录。源码生成比例、模型版本、人工修改过程及其他文件的AI参与范围待核实。

test/yao_lexer.耀第1—5行自述“自举第一步”，其主体是以曜语写成的词法扫描例程。docs/download/09-compiler-internals.txt自述可解析自身；样例主函数第57行读取的是test/hello.耀。当前资料证明词法器样例存在，完整编译器自举及实际运行另列待核实。

build_apk.py第53—244行直接写出Java MainActivity与YaoRuntime；Java模板第224—225行自行实现fib/fact。第273行起提供javac调用，第281行起提供D8调用，后续包含资源封装与签名调用路径。第411—423行资源回退将文本manifest直接装入ZIP，并写入META-INF占位内容；第440—446行apksigner查找分支的路径赋值与有效性待核实。脚本路径及资源、签名回退的实际有效性继续待核实。仓库独立的MainActivity.java第109—110行也包含Java fib/fact。Release将附件称作Android demo app。条目据此记录Java演示应用与工具脚本，曜语源文件到APK的集成转换链继续待核实。

### 遗漏风险

更早的站外公开记录、源码历史重写情况、作者实名及合作关系仍待补。仓库简介曾出现“曶语”字样，源文件部分注释出现其他用字；当前名称依固定README与编译器标题统一为曜语，其他拼写的正式别名地位待核实。关键词表条目数量、文件内自述、自举级测试末尾的“通过”文字均各自保留证据层级，运行结果继续待核实。

## 四、CNplus lang-022

### 固定来源及前端／后端链

固定点：[5000dc1de6554ce567cad80372f39b9808566b7d](https://github.com/CNplus/CNplus-lang/tree/5000dc1de6554ce567cad80372f39b9808566b7d)。

- [pyproject.toml第1—9行](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/pyproject.toml#L1-L9)：名称cnplus、版本1.7.0、Python>=3.11、作者AS13379、Apache-2.0。
- [中文关键字与别名表](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/cnplus/lexer/keywords.toml)：设／令／让、如果／若／假如等；同一文件列出全角标点归一化规则。
- [Pratt解析器](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/cnplus/parser/parser.py#L1-L27)：调用自有扫描器，导入独立AST节点。
- [CLI第62—107行](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/cnplus/cli.py#L62-L107)：解析→静态检查→所选后端执行；编译命令分别写.py、.js。
- [树遍历入口](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/cnplus/backends/treewalk/evaluator.py#L83-L125)：在环境中装载内置函数并执行AST语句。
- [Python后端](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/cnplus/backends/python_emit/%E5%90%8E%E7%AB%AF.py#L19-L50)：发射源码→compile→exec；发射器第86—94行将运行时正文内联。
- [JavaScript后端](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/cnplus/backends/js_emit/%E5%90%8E%E7%AB%AF.py#L20-L52)：发射源码→临时.js→node子进程；发射器第76—84行内联运行时。
- [后端注册表](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/cnplus/backends/%E6%B3%A8%E5%86%8C%E8%A1%A8.py)：列出树遍历、Python转译、JS转译三项。
- [语义约定](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/docs/spec/00-%E8%AF%AD%E4%B9%89%E7%BA%A6%E5%AE%9A.md)：严格布尔条件、类型比较、集合与参数规则。
- [LICENSE](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/LICENSE)：Apache-2.0正文。

树遍历、Python后端能力表声明支持Python库导入；JS后端能力表为支持导入=False，发射器将导入语句转换为相应诊断调用。README将字节码VM列在待办阶段。当前实现类别按独立前端与三执行后端记录。

### 中文原例

[示例/09-阶乘.cnp第5—14行](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/%E7%A4%BA%E4%BE%8B/09-%E9%98%B6%E4%B9%98.cnp#L5-L14)包含完整阶乘函数和调用循环。原文件前4行为说明及空行，程序主体为此次连续摘录。code已经逐字复核，覆盖中文函数、条件、返回、声明、循环、输出及文本转换。

原条目README中依赖前文单价／数量的条件片段作为历史选例保留在原引用中；本轮主code采用依赖定义完整的阶乘例程。

### 当前版本与发行

- main固定提交5000dc1时间：2026-09-19T04:04:06Z。
- 包版本：1.7.0。
- [v1.7.0注解标签对象](https://api.github.com/repos/CNplus/CNplus-lang/git/tags/af566efe720c84c21559c1861ab3646d20c51ffb)时间：2026-09-19T04:04:43Z，目标为5000dc1de6554ce567cad80372f39b9808566b7d。
- [v1.7.0 Release](https://github.com/CNplus/CNplus-lang/releases/tag/v1.7.0)时间：2026-09-19T04:04:51Z，prerelease=false。/releases/latest与该项一致。
- 发行附件cnplus-1.7.0-py3-none-any.whl为114206字节；cnplus-1.7.0.vsix为116285字节。附件内容、安装与运行待独立核实。
- README开发路线中的v1.2.0标记LSP阶段，后续包元数据、CHANGELOG及发行更新至1.7.0。
- Release自报“2166 passed, 8 skipped”及独立审查通过；本轮按项目自报记录，测试数量与结果待独立核实。

### 作者与日期链

[CNplus-python元数据](https://api.github.com/repos/CNplus/CNplus-python)：
- created_at为2021-12-11T09:26:41Z，当前archived=true。
- [根提交33b99259](https://github.com/CNplus/CNplus-python/commit/33b99259d5a2309afd4ef40e39dde44c3965f2bb)时间09:26:42Z，README记录项目名称及Python版本定位。提交署名Charlie894，GitHub返回的作者账号为AS13379。
- [2021-12-18的import.py](https://github.com/CNplus/CNplus-python/blob/eb90369644b69f3baa783dc7c914d898a03650d7/import.py)已有普通Python def／if实现的中文打印函数；该提交时间2021-12-18T07:53:28Z。
- 旧仓2022年提交还出现Vperfact署名，2026迁移说明署名Leander，GitHub作者对象均对应AS13379。

[CNplus-mixed元数据](https://api.github.com/repos/CNplus/CNplus-mixed)：
- created_at和[根提交fad3b704](https://github.com/CNplus/CNplus-mixed/commit/fad3b704997dfa9f44d12e759399e1e89f680443)时间均为2022-06-25T04:55:06Z，当前archived=true。
- 其main.cpp通过string.find识别打印、退出、设置等命令；第28行是待完成的cout语句；第68行自报0.0.1-dev，第69行同时列Charlie894与t.me/AS13379。
- 文件和提交均支持2022年C++交互工具阶段这一沿革。

[CNplus-lang根提交fa6e422](https://github.com/CNplus/CNplus-lang/commit/fa6e422f04ccf81319fa91b9c17dc0df8fd22c1f)时间2026-08-21T05:24:21Z，parents为空；当前仓库created_at为05:24:55Z。该提交明确宣布项目重启并归档旧仓。当前可读76条提交中GitHub作者账号cnplus-agent为74条，AS13379为2条。pyproject署名AS13379，结合旧仓作者对象构成账号级关联；个人实名及具体分工待核实。

### archive与后续语言的关系

本轮直接比对内容与Git blob SHA：

1. archive/CNplus-python/CNplus.py与旧仓d3677455f694778135b55ee04a857b14922a3c70的CNplus.py一致，blob为0e846fb238f589444a9635ee866a3fac7da091c2。
2. archive/CNplus-python/README.md与旧仓2022-06-18固定点da544b50050320eea34a0d1cca90c01c291e3056一致，blob为26008880cc6d36998d3c6a693b19a9b9cf35e908。
3. archive/CNplus-mixed/main.cpp与旧仓8bdd2987dba0a59dac2210c7c6df7646187aa06d一致，blob为28dc8e47ea6189add1a1de8c56cd6fdec2360116。
4. archive/CNplus-mixed/README.md与同一旧仓固定点一致，blob为d7b743add0c09436d9ffe70d0b6b4f1573b268de。

[旧Python仓库2026-08-24迁移README](https://github.com/CNplus/CNplus-python/blob/d3677455f694778135b55ee04a857b14922a3c70/README.md#L1-L9)明确请读者移步CNplus/CNplus-lang。2026重启README与旧仓反向迁移公告，加上归档blob一致性，共同支持同一项目的历史阶段关联。旧Python阶段以中文API封装记录，C++阶段以交互工具记录，当前阶段以独立lexer／parser／AST及多后端语言记录。

### AI资料及遗漏风险

[固定AGENTS.md第1—18行](https://github.com/CNplus/CNplus-lang/blob/5000dc1de6554ce567cad80372f39b9808566b7d/AGENTS.md#L1-L18)面向AI助手，重启计划第4行也给出AI助手实施规则。上述文件及cnplus-agent提交身份构成公开协作流程证据。具体模型、代码生成比例、各文件的人机分工与执行真实性待核实。

旧仓库创建时间、根提交时间、首次代码提交及当前独立实现的重启时间分别记录。更早站外公告、旧发行物、论坛与Wiki资料仍有遗漏风险。历史README样例中的标点、Python导入及代码细节按原始文件保留；历史API实际运行条件及版本兼容性待核实。

## 五、交付核对

- 两个对象ID仍为lang-021、lang-022。
- 原有6条references逐项保留标题与URL；新增固定源码、例程、历史、版本、许可证及发行引用。
- description采用项目介绍，200—400字；资料限制集中在相应状态、实现或核验字段。
- 中文原例连续摘录，代码与code_source／code_context对应。
- author、first_publication、implementation、version、relations、status、verification_notes及verified_at均已扩展或更新。
- 公开写作采用直接事实陈述；未知内容明确为待核实。
- 外部仓库写入、原项目运行、构建、安装及测试操作均在本轮研究范围之外。

