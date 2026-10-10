# 第十轮已有语言条目完善：小易与档案管理语言

核验日期：2026-10-10（UTC）。百科基线：[320b1f6904747bd8afcbb0c1d3655d965ed53ed3](https://github.com/yuyan-lang/chinese-programming-languages/tree/320b1f6904747bd8afcbb0c1d3655d965ed53ed3)。范围为小易lang-025、档案管理语言lang-026。此次完善2项已有条目，新增语言0项；两项原有6条参考的标题及URL完整保留。

## 开轮检查与方法

已读取根AGENTS.md、data/languages.json两项完整对象、research/2026-10-10/round-9.md、第九轮已有条目研究，以及Issue #1的全部9条现存评论。最新评论记录第九轮经PR #30完善lang-023和lang-024，剩余薄条目继续处理。

- [根写作规范](https://github.com/yuyan-lang/chinese-programming-languages/blob/320b1f6904747bd8afcbb0c1d3655d965ed53ed3/AGENTS.md)
- [当前数据](https://github.com/yuyan-lang/chinese-programming-languages/blob/320b1f6904747bd8afcbb0c1d3655d965ed53ed3/data/languages.json)
- [第九轮汇总](https://github.com/yuyan-lang/chinese-programming-languages/blob/320b1f6904747bd8afcbb0c1d3655d965ed53ed3/research/2026-10-10/round-9.md)
- [第九轮已有条目核验](https://github.com/yuyan-lang/chinese-programming-languages/blob/320b1f6904747bd8afcbb0c1d3655d965ed53ed3/research/2026-10-10/round-9-existing.md)
- [Issue #1最新衔接评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/1#issuecomment-6100953653)

本轮使用GitHub公开只读接口、普通网页与公开搜索索引，读取静态源码及历史记录。两仓源码、编译器、测试程序、安装包及已存二进制均保持只读。安装、构建、执行与性能复现列入待核实。本地文件仅用于研究交付；外部仓库写入为0。豫言及其他条目沿用百科基线。

## 小易 lang-025

### 定位、作者和同项目身份链

小易的README明确定位为简化的Python中文语言，并提供.xy运行及转为.py的入口。pyproject.toml给出作者署名liuzhongyi，Git提交主要署名LZY，根提交署名cnlnr。中文实名继续待核实。

README、CLI帮助和包元数据都同时记录cnlnr/xiaoyi与Gitee LZY4/xiaoyi。提交44ef511eedb3bb9a8f471b83e80473684f716cc3的消息明确记录从gitee.com:LZY4/xiaoyi合并，双亲为54fd27e55c1528ba77c5c34f9c026603df7dced7与8781fbc630da8d1675219fa1415be93bc13b8205。该身份链支持将两个托管入口归入同一条目。Gitee主页面、blob和raw页面在本轮网页读取中均返回不可访问，当前镜像同步状态待核实。

分类收束为“Python中文方言／源码转译层”。该定位依据转换器输出Python源码、LibCST使用及Python子进程调用。易语言在百科中保留独立项目记录；相关源码继承关系待核实。

### 中文语法与完整原例

当前config.py中包含7项保留字映射、2项装饰器映射、5项内置名称映射和1项属性映射。保留字为导入、从、返回、跳出、继续、全局、非局部；内置名称为打印、输入、范围、打开、退出；属性为替换。中英语法对照文档与源码相互佐证。

code字段直接采用固定测试.xy全文，4行、96字节；blob SHA为ae52c483004faa58ab4a81060f4eb5f737f45b73。其中第三行保留4个空格，文件末尾保持原始无换行状态；嵌套引号、f字符串和中文内容原样保存。例子定义并调用问候函数，包含输入、返回和打印。该文本也见于当前README的函数示例。Python与LibCST版本兼容性、转换输出及实际执行待核实。

### 静态实现链与分发边界

1. xiaoyi/xiaoyi.py的code串接compile_chinese_code与rename_identifiers。
2. re_class_def.py暂存匹配到的引号、注释、海象及部分括号内容，处理反斜杠换行，使用str.replace处理关键字，再通过正则补全class和def，最后恢复暂存内容。递归括号正则来自regex依赖。
3. cst_name.py调用LibCST的parse_module，遍历Name及Attribute节点并输出.code。leave_Name作用于匹配名称的节点，覆盖相应定义与引用；条目将其描述为名称节点转换。
4. cli.py以UTF-8读取输入。有输出文件参数时写出Python文本；直接执行路径使用subprocess.run调用当前Python解释器的-c参数。该调用属于进程执行路径，安全沙箱隔离待核实。
5. 当前pyproject.toml的project.scripts仍为xiaoyi.xiaoyi:cli；当前xiaoyi/xiaoyi.py只定义code，cli定义位于xiaoyi/cli.py。拆分后代码的绝对导入、安装入口和包结构衔接待核实。
6. 0.1.2标签所指f970fd8b689a4b307c4f608841e8c0d9e38aa87e中的xiaoyi/xiaoyi.py保留完整cli定义及整个转换链。这一发行阶段与2025-08-21的拆分源码分别记录。
7. 0.1.2标签README的Bug节保存语法糖内部中文保留字、exec字符串转换、.xy模块导入方面的历史限制。相应实际行为和当前修复范围待核实。

### 时间、版本、维护与许可

- 仓库创建：2025-08-01T02:25:13Z。
- 可达根提交：3123dc997e4cfc0dbe84a4720f38a5004fcc6005，2025-08-01T02:25:14Z；根提交仅加入初始LICENSE，按仓库历史记录。
- PyPI公开包历史：官方项目页的可读索引列0.1.0于2025-08-16、0.1.1于2025-08-17、0.1.2于2025-08-18发布。
- 0.1.1注释标签：2025-08-17T07:05:48Z，指向3159360a819bb9d909cc5ae6976d1f5ed9301604。
- 0.1.2对应提交：f970fd8b689a4b307c4f608841e8c0d9e38aa87e，2025-08-18T14:33:30Z；注释标签时间2025-08-18T15:23:24Z。
- 固定main：58c6e6b7cbb35ade751aace13b61a6c8d4b7193e，2025-08-21T09:18:42Z；最后推送2025-08-21T09:23:26Z。
- 维护状态：本轮GitHub元数据archived=true；当前README说明作者后续投入有限并欢迎Fork。
- GitHub Releases：本轮返回空列表。版本标签与PyPI包发行各自保留。
- 许可：当前LICENSE为Apache-2.0，pyproject.toml字段相同；根提交历史初始许可单独属于当时快照。
- AI声明：102e4cc95b149b15fbd917d4501bf7ca9928ccb0于2025-08-18T02:33:24Z提交，消息为“给ai格式化了一下代码”，文件变动为xiaoyi/xiaoyi.py增加11行、删除9行。该证据支持一次AI格式化说明，具体模型和其他生成范围待核实。

PyPI页面索引可读且列出包日期及文件名；直接页面、0.1.0／0.1.2页面与JSON接口均出现读取失败。因此条目明确标记为官方页面的可读索引，精确上传时刻、当前服务状态及发行包内部内容待核实。源发行物和wheel均保持只读元数据范围。语言更早的首次公开日期继续待核实。

### 小易引用

1. [项目README（核验快照）](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/README.md)
2. [实现或样例证据](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/%E6%B5%8B%E8%AF%95.xy)
3. [仓库元数据](https://api.github.com/repos/cnlnr/xiaoyi)
4. [包元数据：作者、依赖、许可证、双仓入口及命令配置](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/pyproject.toml)
5. [中英语法对照](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/docs/%E4%B8%AD%E8%8B%B1%E8%AF%AD%E6%B3%95%E5%AF%B9%E7%85%A7.md)
6. [中文关键字、内置名称及属性映射表](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/xiaoyi/config.py)
7. [源码转换组合入口](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/xiaoyi/xiaoyi.py)
8. [声明补全、占位处理及关键字转换](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/xiaoyi/re_class_def.py)
9. [LibCST名称与属性转换](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/xiaoyi/cst_name.py)
10. [Python文本输出及子进程执行路径](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/xiaoyi/cli.py)
11. [0.1.2标签的完整CLI及转译实现](https://github.com/cnlnr/xiaoyi/blob/f970fd8b689a4b307c4f608841e8c0d9e38aa87e/xiaoyi/xiaoyi.py)
12. [0.1.2阶段README及历史功能边界](https://github.com/cnlnr/xiaoyi/blob/f970fd8b689a4b307c4f608841e8c0d9e38aa87e/README.md)
13. [0.1.2注释标签元数据与时间](https://api.github.com/repos/cnlnr/xiaoyi/git/tags/d134566e5db956c7654f191a8ae1f063c85c2578)
14. [PyPI官方项目及公开包发行历史（可读索引）](https://pypi.org/project/xiaoyi/)
15. [Apache-2.0许可证全文](https://github.com/cnlnr/xiaoyi/blob/58c6e6b7cbb35ade751aace13b61a6c8d4b7193e/LICENSE)
16. [Git根提交与日期](https://github.com/cnlnr/xiaoyi/commit/3123dc997e4cfc0dbe84a4720f38a5004fcc6005)
17. [Gitee分支合并记录](https://github.com/cnlnr/xiaoyi/commit/44ef511eedb3bb9a8f471b83e80473684f716cc3)
18. [AI格式化代码的单次提交说明](https://github.com/cnlnr/xiaoyi/commit/102e4cc95b149b15fbd917d4501bf7ca9928ccb0)

## 档案管理语言 lang-026

### 定位与Forth关系

README和README-dev将DGY说明为档案管理语言的拼音缩写，定位用于计算机教学，以操纵数据及参考文档为核心。作者账号和主要提交署名为wwwwyyt，中文实名待核实。

2026-05-20日志明确记录参考Forth设计，并讨论Word、数据栈、寄存器式存值与后缀调用。2026-09-11日志进一步讨论词典索引、代码栈与数据栈分离、返回地址及循环变量。源码提供自己的词法和语句匹配模块。分类采用“独立中文教学语言／词典与栈式编译解释器原型”；Forth关系按设计借鉴记录，特定Forth实现的直接代码继承待核实。

### 完整原例与语法阶段

完整原文件test/test_01_九九乘法表.dgy为37行、955字节，blob SHA为126a8bfd12e4853fd3ea24fd094a3ba70745d89e。已逐行读取全文，原文件链接完整保留。官网code主例采用其中第21—24行连续4行，展示词语A／B定义与两条存值语句；保留4空格缩进及行末换行，code_context明确其为完整程序中的连续短片段。完整37行九九乘法表可通过来源链接阅读。

原例以等号围合复杂词语，包含设、存、令、结果存、无结果、如果／否则结束、重复执行／检测／直到等中文结构。同提交README的初始化为一条“存 1 1 到 #A #B”；test文件采用连续两条“存 1 到 #A”“存 1 到 #B”，与README-dev逐条存值文法更容易对应。交付短例逐字符采用test文件的对应四行，各原始版本各自保存。

程序调用打印、格式的、加一等词语，已读dgy_builtin.c注册4个整数算术词。完整内置库覆盖、调用环境、九九乘法表的算法行为与输出正确性待核实。完整原文件证明中文语法和作者示例的存在；程序执行能力需后续独立核验。

### 静态前端与实际完成边界

1. dgy_lexer.c通过fgetwc读取宽字符，按立即数、字符串、注释、保留字、操作符、词语、单元分组匹配；_reservedSymTable包含21个中文保留字，逻辑操作符含且、或、非。匹配结果以带类型的cell_t写入符号栈。
2. dgy_parser.c的getSymbol调用dgyDoLexerOnce；dgyDoParserOnce逐步匹配语句状态，形成dgy_stat.h中的DgyStatement。README-dev称其为基于LR(0)原理的简化语法识别；条目采用“逐句匹配／中间语句结构”表述。
3. dgyDoAnalyserOnce调用解析器，再按StatType查函数表。parse_WordBegin、parse_WordEnd和parse_SimpWord包含词典及代码栈相关处理。
4. parse_Mov、parse_Exec、分支、跳转与循环处理函数当前主要保留取得statement的占位代码。字节码执行框架作为设计阶段信息保存。
5. DgyCore包含数据栈、代码栈、词典、16个寄存器和分析器及输入输出流；dgy_core.c当前提供初始化／销毁函数。
6. dgy_builtin.c保留相加、相减、相乘、相整除的栈算术实现及函数指针表。其dgyDictAdd调用使用旧4参数形式，当前dgy_dict.h声明使用DgyDict*和DictItem*两个参数。接口协调与构建结果待核实。
7. dgy_main.c的main调用dgyUnitTest。dgy_test.c将test_lexer和test_parser放在if(0)分支中，当前有效调用为test_analyser，该函数体为空。
8. Makefile列gcc构建src/*.c。固定树另有dgy.exe与dgy.pdb。文件名和二进制存在性分别记录，构建对应关系及可执行功能待核实。

完整的词法、语法、部分词语分析与数据结构已有静态证据；生成字节码、加载完整程序、执行循环和内置库的端到端流程继续待核实。

### 沿革、日期与许可

- 根提交：97b8f6d30d81a3a136efabd365cd6bb2978177c1，作者与提交者时间均为2026-04-22T06:56:14Z，无父提交；包含demo.md与空demo.py。
- 仓库创建：2026-04-22T09:01:49Z。
- 早期Python文件：8aa3c3790bedb5a6cc82f8a6cb4c8e49317a6ba6的demo.py是返回空符号表的lexer占位，并保存一行中文输入例。按早期实验记录。
- Forth设计日志：2026-05-20。日志日期是作者阶段记录；首次公开日期待核实。
- 旧托管名称：历史合并提交da607080f6fff50ded6cf2693b0786fff1e2b839在2026-05-25记录github.com:wwwwyyt/datamate-lang。该旧路径API当前返回Moved Permanently，目标为repositories/1217829829，与当前dgy-lang元数据ID一致。两个路径归同一仓库沿革。
- 固定main：3d626fa851325d6cbe1c405ac7d88a633ef523ab，2026-09-12T05:43:59Z；最后推送2026-09-12T05:44:22Z。
- 当前开发资料：日志最后日期节为2026-09-11，README标注开发中，GitHub元数据archived=false。后续维护计划待核实。
- 版本／发行：本轮Releases与git/matching-refs/tags/均返回空列表，正式编号及公开发行日期待核实。
- 许可：当前递归树40项、truncated=false，仓库元数据license=null；项目许可待核实。
- AI：本轮已读原始资料中可明确归属的AI开发声明待核实。

仓库创建、Git提交、作者日志和对外发行分别列示。实际首次公开日期、正式发行物、许可证及独立运行状态保留缺口。

### 档案管理语言引用

1. [项目README（核验快照）](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/README.md)
2. [实现或样例证据](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_lexer.c)
3. [仓库元数据](https://api.github.com/repos/wwwwyyt/dgy-lang)
4. [完整连续九九乘法表原始文件](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/test/test_01_%E4%B9%9D%E4%B9%9D%E4%B9%98%E6%B3%95%E8%A1%A8.dgy)
5. [开发文档：BNF文法、单元与寄存器、语法分析方法](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/README-dev.md)
6. [语言设计：词典、栈式模型与字节码目标](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/design.md)
7. [开发日志：Forth设计借鉴与2026年阶段记录](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/log.md)
8. [逐句语法匹配与词法器调用](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_parser.c)
9. [语句中间结构DgyStatement](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_stat.h)
10. [语义分析分派、词语处理与占位函数](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_analyser.c)
11. [运行状态、栈与16寄存器声明](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_core.h)
12. [核心初始化及销毁](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_core.c)
13. [内置整数运算模块](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_builtin.c)
14. [当前词典接口](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_dict.h)
15. [当前main入口](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_main.c)
16. [当前测试入口与空分析测试函数](https://github.com/wwwwyyt/dgy-lang/blob/3d626fa851325d6cbe1c405ac7d88a633ef523ab/src/dgy_test.c)
17. [Git根提交及日期](https://github.com/wwwwyyt/dgy-lang/commit/97b8f6d30d81a3a136efabd365cd6bb2978177c1)
18. [根提交中的中文设计草案](https://github.com/wwwwyyt/dgy-lang/blob/97b8f6d30d81a3a136efabd365cd6bb2978177c1/demo.md)
19. [早期Python词法器占位](https://github.com/wwwwyyt/dgy-lang/blob/8aa3c3790bedb5a6cc82f8a6cb4c8e49317a6ba6/demo.py)
20. [旧datamate-lang仓库路径的重定向](https://api.github.com/repos/wwwwyyt/datamate-lang)
21. [固定完整文件树](https://github.com/wwwwyyt/dgy-lang/tree/3d626fa851325d6cbe1c405ac7d88a633ef523ab)
22. [公开发行列表](https://github.com/wwwwyyt/dgy-lang/releases)

## 检索覆盖与读取限制

GitHub覆盖两仓元数据、默认分支、完整递归树、分页提交列表、根提交、标签引用、注释标签、Releases、固定文件与0.1.2历史源码。小易默认分支100次可达提交，第二页为空；DGY为71次，第二页为空。源码日期范围为2025-08-01至2025-08-21、2026-04-22至2026-09-12。

普通网页与索引检索词包括：
- “xiaoyi” “0.1.2” “pypi”
- “LZY4/xiaoyi”
- “wwwwyyt” “dgy”
- site:gitee.com/LZY4/xiaoyi “GitHub”
- site:pypi.org/project/xiaoyi/0.1.0/ “Aug”
- site:gitee.com “小易中文编程语言” “LZY”
- “wwwwyyt” “datamate”
- “小易中文编程语言” “2025”
- “档案管理语言” “Forth”

检索定位出PyPI官方原页的可读索引，版本日期依据该原页索引保存；第三方包镜像只作定位辅助。Gitee对应页面和PyPI直读接口读取失败，保持准确来源级别。DGY根提交README.md读取返回文件缺口后，使用递归树定位真实demo.md并读取；中文草案的来源因此明确。

## 交付与核验结果

data/languages.json中的lang-025与lang-026为两项完整对象数组：
- 小易lang-025：介绍347字；4行完整原例；18条引用，其中原有3条标题URL完整保留。
- 档案管理语言lang-026：介绍315字；4行连续中文短例，来源保留完整37行程序；22条引用，其中原有3条标题URL完整保留。

合计40条引用，原有6条保留，新增34条。小易code与完整测试文件逐字符相等；DGY code与固定原文件第21—24行逐字符相等；中文URL及JSON转义保持有效。日期、首发、版本、维护、许可、实现边界及项目关系分别记录。完善2项，新增0项；百科原有68语言／8内核数量由这项工作保持。

Issue #1可继续记录这两项完善，重点为小易的LibCST转译、发行阶段与当前入口差异，以及DGY的词典／栈式教学定位、连续短例与完整原件、开发原型边界。剩余首发、安装、构建与运行缺口继续保留。

