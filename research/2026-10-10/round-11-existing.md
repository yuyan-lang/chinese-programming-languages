# 第十一轮已有语言条目完善：PythonCN与将军令

核验日期：2026-10-10（UTC）。百科基线：[b8bced915e093ccdfde6b32804f7bd2b4c6a0786](https://github.com/yuyan-lang/chinese-programming-languages/tree/b8bced915e093ccdfde6b32804f7bd2b4c6a0786)，原有71项语言、8项内核。本项工作完善PythonCN lang-027与将军令 lang-028两项，语言新增0项，原ID保持。两项原有8条参考的标题及URL全部保留。

## 开轮检查与方法

已读取根AGENTS.md、data/languages.json两项完整对象、第十轮汇总与已有条目日志，以及Issue #1正文和全部10条现存评论。最新衔接评论记录PR #34已完善小易与DGY，剩余薄条目继续处理。

- [公开技术文档规范](https://github.com/yuyan-lang/chinese-programming-languages/blob/b8bced915e093ccdfde6b32804f7bd2b4c6a0786/AGENTS.md)
- [固定语言数据](https://github.com/yuyan-lang/chinese-programming-languages/blob/b8bced915e093ccdfde6b32804f7bd2b4c6a0786/data/languages.json)
- [第十轮汇总](https://github.com/yuyan-lang/chinese-programming-languages/blob/b8bced915e093ccdfde6b32804f7bd2b4c6a0786/research/2026-10-10/round-10.md)
- [第十轮已有条目研究](https://github.com/yuyan-lang/chinese-programming-languages/blob/b8bced915e093ccdfde6b32804f7bd2b4c6a0786/research/2026-10-10/round-10-existing.md)
- [Issue #1衔接评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/1#issuecomment-6101200469)

本轮使用普通网页、公开搜索索引及GitHub只读接口，核对固定源码、完整文件树和版本历史。外部项目的源码、安装包、测试程序和二进制保持只读；独立安装、构建、执行与性能验证列为待核实。研究交付文件在本地整理，外部仓库写入为0。

## PythonCN lang-027

### 定位、作者及关系

README_CN.md将项目面向中文用户与初学者，说明.pycn源码转为Python。compiler.py头部@author与两次提交均署PythonDeveloper29042，作者实名待核实。基于实际执行入口，分类细化为“Python中文关键字与全角字符转译层”。

README安装段链接PythonCN/PythonCN，该仓库API在本轮返回404。此地址与当前PythonDeveloper29042/PythonCN的迁移关系待核实。README把Gitee发布、VS Code插件、IDE及库适配列为未来计划；当前实现范围按5文件固定树记录。GitHub元数据fork=false。与中蟒、草蟒及其他中文Python实现的源码继承关系保留待核实。

### 短原例与实际入口

chinese_code.pycn完整原件为7行、291字节，blob SHA为57716223d63083872b02e4a3687dc59aa79d832d。条目保留原有第4—7行条件分支，直接逐字核对；全角空格、全角数字、引号、标点及末尾无换行状态保持原样。code_context交代其依赖第3行输入赋值。原例以input对应的文本输入值直接参与取模，整数转换与运行结果待核实。

固定compiler.py的静态链为：

1. main读取用户提供的文件名，以UTF-8读取全文并交给compile_code。
2. translate_code合并builtins、keywords、symbols三组字典，依次对全文调用str.replace。
3. builtins含输出、输入、整数、字符串及容器名称等映射；keywords保存条件、循环、函数、类、导入和异常处理等名称；symbols转换全角空格、标点、引号和数字。
4. compile_code写出UTF-8的temp.py，并通过os.system调用python temp.py。Python承担结果源码的解析、类型语义与执行。

该链由实际源码确认。替换作用于全文中的匹配文本，包含字符串、注释和标识符。keywords中的“是”出现两次，字典后值is覆盖True。字典顺序先处理“循环”再处理“循环当”，按规则静态可推得“循环当”转为for当。上述结果为源码推导，独立运行与边界测试待核实。main的空文件名判断、文件读取异常、输出覆盖及系统python命令环境分别保留运行核验缺口。

### 日期、版本、维护与许可

- 仓库创建：2025-05-12T10:18:19Z。
- 根提交：37eca6d525916c38b98c6bce63541963476cfe08，作者与提交者时间均为2025-05-12T10:18:21Z；无父提交，加入双语README、compiler.py、chinese_code.pycn和.gitignore。
- 当前main：e41006e637f5381801551e4b2554a1b05a5918fa，2025-05-12T11:12:12Z。该提交只为源码头部@date补入2025-05-12，功能代码与根提交的对应部分相同。
- 最后推送：2025-05-12T11:12:30Z。
- 首次公开：首次对外发布日及更早材料待核实。上述日期分别对应仓库元数据和Git历史。
- 发行与版本：本轮Releases和git/matching-refs/tags/均返回空列表；正式编号、发行物和发布日期待核实。
- 维护：archived=false，后续维护计划待核实。
- 许可：中英文README均声明MIT并链接LICENSE；完整5文件树的许可证全文待核实，API license为null。条目按README声明的证据层级记录。
- AI：已读双语README、整个compiler.py及2次可达提交；可明确归属的AI开发声明、模型与范围待核实。

### PythonCN来源

1. [项目README（原有参考）](https://github.com/PythonDeveloper29042/PythonCN/blob/e41006e637f5381801551e4b2554a1b05a5918fa/README.md)
2. [实际词表、文本转换及运行入口（原有参考）](https://github.com/PythonDeveloper29042/PythonCN/blob/e41006e637f5381801551e4b2554a1b05a5918fa/compiler.py)
3. [仓库元数据（原有参考）](https://api.github.com/repos/PythonDeveloper29042/PythonCN)
4. [中文原例（原有参考）](https://github.com/PythonDeveloper29042/PythonCN/blob/e41006e637f5381801551e4b2554a1b05a5918fa/chinese_code.pycn)
5. [中文README及MIT声明](https://github.com/PythonDeveloper29042/PythonCN/blob/e41006e637f5381801551e4b2554a1b05a5918fa/README_CN.md)
6. [根提交](https://github.com/PythonDeveloper29042/PythonCN/commit/37eca6d525916c38b98c6bce63541963476cfe08)
7. [末次提交及日期补充](https://github.com/PythonDeveloper29042/PythonCN/commit/e41006e637f5381801551e4b2554a1b05a5918fa)
8. [固定完整文件树](https://github.com/PythonDeveloper29042/PythonCN/tree/e41006e637f5381801551e4b2554a1b05a5918fa)
9. [公开发行列表](https://github.com/PythonDeveloper29042/PythonCN/releases)
10. [标签引用列表](https://api.github.com/repos/PythonDeveloper29042/PythonCN/git/matching-refs/tags/)

## 将军令 lang-028

### 定位、作者与历史身份

历史README使用“将军令项目组”署名，将项目定位为基于中式军事指挥思想的中文编程语言；当前README强调中文用户的编程学习。GitHub组织为jiangjun-ling，现存5次提交均由账号z200215署名。MIT版权署名为2025 jiangjun-ling，自然人实名和设计分工待核实。

2025-11-12T06:05:59Z的历史README将jiangjun-ling/lang列为语言核心主仓库，该地址本轮API返回404。条目保留这条历史指向，迁移、更名与代码同源关系待核实。GitHub元数据fork=false；Python为实现语言，与其他中文解释器的源码继承关系继续核实。

### 连续原例与实现链

基础语法.jl全文55行、1169字节，blob SHA为fb0e297cf486ca6c6033415bccdde1d63b41ecf6。条目保留第17—20行条件分支，按原文件连续截取，保留4空格缩进、CRLF换行及第20行行末换行。原条目的可见代码文字保持，原有LF展示换行按原件恢复为CRLF。该片段依赖第5—8行令声明块中的姓名和年龄；完整原例链接保留。例子、README、main.py及全部19个文件的内容均已保存为静态取证材料。

实际执行链为根目录main.py的运行文件函数：UTF-8读入源码→将军令词法分析器.分析→将军令语法分析器.解析程序→将军令解释器.解释。

1. 词法分析器逐行处理缩进并生成INDENT／DEDENT。普通空格逐个计数，制表符计4个空格；#开始行内注释，单引号和双引号表示字符串。
2. 关键词表包含征、策、令、策行、令行、报、访、若、则、否则、否则若、于、返、为。标识符扫描采用字符分类与中文范围识别；中英文冒号、逗号各映射到相同令牌。
3. 语法分析器递归构造程序、函数定义、声明块、赋值、函数调用、输出、访问循环、条件及返回节点。数值、字符串、列表、括号及函数调用有对应表达式规则。
4. 解释器按AST节点类型分派，变量和函数通过字典保存，查询沿父环境链进行。用户函数创建以调用环境为父级的子环境；访问循环为每个元素创建子环境，赋值写入当前环境。
5. 内置函数登记报、长度、类型和范围；数字转为Python int或float，列表和字符串有相应求值路径。
6. main.py提供文件参数、-i交互、-h帮助及-t测试调度。交互模式重复读取单行，沿用同一解释器全局环境。

### 功能边界

二元运算通过一个循环从左向右组合，加减乘除及六种比较运算处于同一解析层，括号提供显式分组。否则若在词法层为ELIF，其解析分支递归调用以期待IF开头的方法，令牌衔接待核实。用户函数仅在函数体顶层RETURN节点触发提前终止，条件解释方法返回None，嵌套返回的控制流传播待核实。

普通赋值语句以令行进入，声明块内部另行处理标识符和等号；函数样例的裸赋值与该规则衔接待核实。控制流样例中的且、函数样例的列表索引、词法表中的征／为，其完整解析及运行语义继续核实。词法器在检查行内容是否为空之前处理缩进，空行也参与块边界计算，相关程序布局与运行结果待核实。

当前README保留your-username克隆占位，命令示例指向示例/基础语法.jl；实际固定树将三个.jl文件和核心.py平铺根目录。main.py的测试分支导入测试.测试套件，现存测试套件.py位于根目录。文档路径、测试入口及包布局的衔接待核实。语言规范.md、贡献指南.md、requirements.txt和__init__.py为零字节；CONTRIBUTING.md另有完整贡献说明。

上述判断由静态源码及固定文件树支持。样例覆盖、执行正确性、测试数量和性能待独立验证。

### 分列时间、版本、维护与许可

- 仓库创建：2025-11-12T06:02:46Z。
- 可达根提交：5ccf22ed85c7599d56ff9b9ae911760bb09583d2，2025-11-12T06:02:46Z，无父提交，加入README和LICENSE。
- 早期项目说明：7ee2a789ae3ad74642bd79b7a626167ba30702ba，2025-11-12T06:05:59Z，补军事指挥命名思想及核心仓库链接。
- 首次实现上传：59405d4c7ec6c4f0928a7c91d799178519bc330e，2025-11-12T06:39:38Z，加入词法、语法、AST、解释器、main.py、测试及样例等文件。
- 工作流增加：ce2708d4014094eab4da62d22fb6f46b043a1756，2025-11-12T06:50:07Z。
- 当前main：72943b33184bc4bab505c787bc3c29e022e2ceb3，2025-11-12T06:59:12Z，加入CONTRIBUTING.md；仓库最后推送时间相同。
- 首次公开：作者首次公告及仓库转为公开的时间待核实；Git历史与仓库创建分列保存。
- 版本与发行：仓库description和早期README自称实验版本；数字版本号待核实。本轮Releases与标签引用均为空列表，全部Git引用仅含main。
- 维护：archived=false，后续计划待核实。
- 许可：LICENSE原件为MIT，Copyright (c) 2025 jiangjun-ling，仓库元数据一致。当前README侧重简介与运行方法，许可依据独立文件记录。
- AI：已核全部当前文本文件、5次提交与议题记录；明确归属的AI开发声明、模型和参与范围待核实。模板占位、源码风格和实现缺口按资料特征记录。

只读工作流元数据显示两次运行结论为failure，最新运行链接为https://github.com/jiangjun-ling/jiangjunling-lang/actions/runs/19289132706 。工具返回的最新作业steps为空，具体失败原因待核实；该状态与独立测试结论分别记录。

### 将军令来源

1. [当前README（原有参考）](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/README.md)
2. [中文词元与缩进处理（原有参考）](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/%E8%AF%8D%E6%B3%95%E5%88%86%E6%9E%90%E5%99%A8.py)
3. [仓库元数据（原有参考）](https://api.github.com/repos/jiangjun-ling/jiangjunling-lang)
4. [完整基础语法原例（原有参考）](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/%E5%9F%BA%E7%A1%80%E8%AF%AD%E6%B3%95.jl)
5. [文件及交互实际入口](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/main.py)
6. [语句及表达式解析](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/%E8%AF%AD%E6%B3%95%E5%88%86%E6%9E%90%E5%99%A8.py)
7. [抽象语法树节点](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/%E6%8A%BD%E8%B1%A1%E8%AF%AD%E6%B3%95%E6%A0%91.py)
8. [解释器、环境与函数返回](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/%E8%A7%A3%E9%87%8A%E5%99%A8.py)
9. [MIT许可证原件](https://github.com/jiangjun-ling/jiangjunling-lang/blob/72943b33184bc4bab505c787bc3c29e022e2ceb3/LICENSE)
10. [根提交](https://github.com/jiangjun-ling/jiangjunling-lang/commit/5ccf22ed85c7599d56ff9b9ae911760bb09583d2)
11. [核心实现与原例上传](https://github.com/jiangjun-ling/jiangjunling-lang/commit/59405d4c7ec6c4f0928a7c91d799178519bc330e)
12. [历史README与核心仓库指向](https://github.com/jiangjun-ling/jiangjunling-lang/blob/7ee2a789ae3ad74642bd79b7a626167ba30702ba/README.md)
13. [固定完整文件树](https://github.com/jiangjun-ling/jiangjunling-lang/tree/72943b33184bc4bab505c787bc3c29e022e2ceb3)
14. [公开发行列表](https://github.com/jiangjun-ling/jiangjunling-lang/releases)
15. [标签引用列表](https://api.github.com/repos/jiangjun-ling/jiangjunling-lang/git/matching-refs/tags)


## 检索覆盖与风险

PythonCN检索覆盖GitHub公开仓库元数据、默认分支、全部2次可达提交、完整递归树、README及源码、发行和标签引用。代码历史日期范围为2025-05-12T10:18:21Z至2025-05-12T11:12:12Z；外部网页检索使用项目精确名称与作者账号回溯，时间上限为2026-10-10。

普通网页及搜索索引关键词包括：
- “PythonDeveloper29042” “PythonCN”
- “PythonCN” “compiler.py”
- “PythonCN” “中文” “2025”
- “PythonDeveloper29042”
- “PythonCN” “编程语言”
- “PythonCN” “Chinese syntax”
- site:github.com “PythonDeveloper29042” “PythonCN”
- site:gitee.com “PythonCN” “编程”
- “PythonCN” “PythonDeveloper” AI

精确组合检索结果较少；宽泛PythonCN检索混入中文Python用户组、社区和部署工具等同名内容。条目依据作者仓库及固定源码确认项目身份，同名检索结果各自保留来源边界。首次公开、Gitee实际发布、README下载地址身份、许可证全文及AI参与均继续核实。GitHub通用tags路径遇工具端点限制后，使用受支持的git/matching-refs/tags/只读引用接口，获得空列表。

将军令覆盖GitHub全部5次main可达提交、完整19文件树、历史README、全部引用、发行、标签、议题和现存工作流；源码历史范围为2025-11-12T06:02:46Z至2025-11-12T06:59:12Z。普通网页实际检索词为“jiangjunling-lang”、“将军令” “z200215”、“将军令” “编程语言”、“jiangjun-ling”；检索时段为2026-10-10 19:30—19:34 UTC，未设置日期过滤，回溯全部可索引历史。

普通网页工具读取将军令仓库、标签、发行、组织及用户主页时返回Cache miss；GitHub只读接口成功取得仓库与源码，网页工具失败按通道状态记录。精确检索的可可靠归属独立公告继续待核实。模板占位、英文提交摘要和实现缺口各按资料事实保留，AI归因依据作者声明或明确来源继续核实。搜索索引完整性、历史删除或改名仓库、首次公开时间及独立运行均是本轮遗漏风险。

## 交付与静态核验

data/languages.json中的lang-027与lang-028保存两项完整对象：

- PythonCN lang-027：介绍361字，4行连续原例，10条参考，其中原有4条标题URL完整保留。
- 将军令 lang-028：介绍318字，4行连续原例，15条参考，其中原有4条标题URL完整保留。

合计25条参考，原有8条保留，新增17条。两个code均从固定文件连续截取，PythonCN片段186字节，将军令片段105字节；原空白与换行经过精确检查。PythonCN的4份已读源码／文档和将军令的全部19个文件合计23份文本重算Git blob SHA，均与来源元数据一致。此核验只处理来源文本与研究JSON，项目源码执行为0。

JSON解析、原ID、200—400字介绍、原参考保留、URL重复、短例对应及写作规范检查均通过。仓库创建、可达根提交、源码上传、最近提交和正式发行分开记录；网页可见的first_publication和version同步保存关键日期与发行缺口。AI、同源、维护、许可、功能边界和独立运行状态分别说明。

本项完善2项，新增0项，百科71语言／8内核数量保持。Issue #1后续可记录PythonCN的文本转译实际入口和许可原件缺口，以及将军令的Python AST解释链、MIT许可与实验阶段功能边界；其余薄条目和首发资料继续跟进。
