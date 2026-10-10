# 第五轮既有条目：奇语言、CNPL

核验日期：2026-10-10（UTC）。对象为lang-011奇语言和lang-018 CNPL。采用公开GitHub连接器与普通web搜索进行只读静态核验。

## 一、基线

已读取：

- AGENTS.md：采用肯定陈述，资料缺口标为“待核实”。
- data/languages.json：保留两条原有id、名称及原参考链接。
- Issue #1及全部4条评论：议题保持开放；本轮完善两条既有项目。
- research/2026-10-09/repo.md。
- research/2026-10-10/existing.md、repositories.md、round-4-existing.md。

## 二、奇语言证据链

### 固定快照与历史

- 原仓库：https://github.com/qilang-project/qi
- 默认分支main，固定提交03692853186695c277b4fdc26187d90ab8ac138e。
- 提交时间：2026-10-10T02:40:26Z；pushed_at：2026-10-10T02:40:28Z。
- 仓库创建：2025-10-21T09:48:06Z；archived=false。
- 查询截至2025-12-31的历史提交，读到根提交b7fd9c52c47674d37e032224a237f11951c80357，时间2025-10-19T13:20:00Z，作者Liang Li，GitHub关联账号liliang-cn。
- 根提交包含DESIGN.md、DESIGN2.md、DESIGN3.md。DESIGN.md已读取，保存早期中文语法设计。根提交的README.md请求返回404，按该历史树的文件构成记录。
- 最早设计提交日期、建库日期和首次对外公开日期各自记录。首次公开的具体时点待核实。

### 版本

- GitHub releases集合以per_page=100读取，返回37项。
- 最新记录：2026.10.09-2，published_at=2026-10-09T13:47:58Z，prerelease=false。
- 最早已读记录：2026.05.30-1，published_at=2026-05-30T10:42:45Z。
- 固定Cargo.toml：包名qi-compiler，版本2026.10.9-2，authors为Qi Language Team，Rust edition 2021。
- Cargo版本与Release标签的日期补零形式分别保留。
- Cargo中的qi-lang.org／qi-lang/qi-compiler地址与README的qilang.org／qilang-project/qi地址存在区别；历史迁移或模板残留情况待核实。

### 原文代码

固定文件：

https://github.com/qilang-project/qi/blob/03692853186695c277b4fdc26187d90ab8ac138e/%E7%A4%BA%E4%BE%8B/%E5%9F%BA%E7%A1%80/%E4%BD%A0%E5%A5%BD%E4%B8%96%E7%95%8C/%E4%BD%A0%E5%A5%BD%E4%B8%96%E7%95%8C.qi#L3-L7

- 文件blob：ee7ed89d404e3d18b5a8747be38740135bb021b7。
- 摘录第3—7行，为去掉开头两行注释后的完整主体。
- 通过原文件字符串包含检查，确认连续原文。
- 中文分号、四空格缩进及“你好，Qi！”原样保留。

### 实现核验

固定提交下已取得并定点核查：

- Cargo.toml：lalrpop-util 0.22.2；Inkwell 0.8，llvm21-1特性。
- src/parser/mod.rs：Parser::parse_source使用LALRPOP生成的ProgramParser。
- src/parser/grammar.lalrpop：包、导入、声明、控制流等中文终结符及解析规则。
- src/parser/reserved.rs：当前终结符副本及上下文关键字；“长度”“新建”按上下文处理。
- src/lexer/keywords.rs：文件自身说明该表供诊断与工具使用，语法事实来源为grammar.lalrpop。该文件记录2026年9月对部分类型词的分类调整。
- src/codegen/mod.rs：当前代码生成模块采用Inkwell。
- src/codegen/inkwell_gen/mod.rs：compile_to_objects和LLVM TargetMachine的FileType::Object输出。
- src/lib.rs第662—693行：编译目标文件；Wasm分支返回目标文件；原生路径链接运行时与外部库。
- src/runtime_archive.rs：普通与GUI运行时归档选择和查找。
- src/链接.rs：外部库、搜索路径及平台链接参数。
- src/cli/commands.rs：编译入口及包管理等命令。
- docs/基础语法规范.md：当前推荐写法及若干语义／测试待完善说明。
- README.md：项目名称、目标、示例入口和开发状态。

README、基础语法规范、关键字辅助表及当前语法源码存在更新节奏差异。正文采用固定源码支持的机制；功能完整程度按具体版本核验。早期DESIGN.md中的语法与宣传性完成度分别作为历史设计资料。独立执行、测试通过数、性能、全部并发语义和平台兼容性待核实。

### 访问与范围

- qilang.org的精确实际地址为https://qilang.org；两次普通web打开均返回工具访问失败。
- 官网长期状态待核实。
- 搜索命中的GitHub镜像域名、软件聚合页面与性能文案用于发现入口；确定技术结论取原GitHub仓库。
- 当前递归Git树完整返回，truncated=false。
- 运行时及其他生态组件的完整核验属于后续范围。

## 三、CNPL证据链

### 固定快照与历史

- 原仓库：https://github.com/Zhou-zhi-peng/cnpl
- 默认分支master，固定提交f2a60c0ae7e6264f8a9406e5b8fbda6114b08ccd。
- 最新提交时间：2020-03-16T03:03:48Z，署名Kevin。
- pushed_at：2020-03-16T03:04:50Z；archived=false。
- 仓库创建时间：2020-01-15T08:36:01Z。
- commits集合以per_page=100读取，完整返回28条。
- 根提交f6b12dbbcb8e9852fb2bcd1efcccd39161760134：2020-01-15T08:36:02Z，署名Zhouzhipeng。
- 源码加入提交f2bad2a57642573eaef046854d7de9890358197a：2020-01-15T10:49:21Z，署名Kevin，加入C#前端、C++ VM、中文示例及二进制包。
- 2020-03-16的634b8eb修复解析器“小于比较”问题；随后f2a60c0更新二进制包。
- 作者中文姓名与Kevin署名的进一步身份说明待核实。
- AssemblyInfo.cs中的2019为版权元数据；课程开展时间和首发时间另列待核实。

### 原文代码

固定文件：

https://github.com/Zhou-zhi-peng/cnpl/blob/f2a60c0ae7e6264f8a9406e5b8fbda6114b08ccd/DEMO%E7%A8%8B%E5%BA%8F/%E6%A0%B7%E4%BE%8B0-%E5%9F%BA%E7%A1%80%E6%B5%8B%E8%AF%95.%E7%A8%8B%E5%BA%8F#L11-L18

- 文件blob：1def107bcc7021eed0cf91eafadfc03c446478e2。
- 第11—18行连续原文，展示数字声明、中文数字、阵列、循环、条件与输出。
- 已通过原文件字符串包含检查。
- 另读“样例1-斐波那契数列.程序”确认函数、输入与返回的源文件写法。算法运行与结果正确性待核实。

### 实现及分类

- README说明来源为公司内部《计算机语言编译原理》分享课程，整理后开源。
- README明确记载受LingDong文言项目启发，并使用白话语法。
- Token.cs和Lexer.cs直接实现“有一个数字”“有一句话”“有一个阵列”“有一种方法”“取名为”等词法。
- Lexer.cs实现中文数字字符处理，以及方括号名称、尖括号／书名号调用及中英文标点。
- GrammarParser.cs将这些词元分派为变量、函数、条件、循环、返回及调用等语法节点。
- Program.cs：-RUN执行ast.Execute；编译路径执行ast.Compile。
- Compiler.cs第256—271行：复制加载器，追加OutputByteCode输出与长度。
- Compiler.cs第304—319行：ASM、BIN和EXE三种输出选择。
- VM/VM.h：C++执行器、指令枚举、计算栈、数据栈、指令位置、宿主函数和GC结构。
- VM/VM.cpp全文已取得，供上述实现链核对。
- cnpl.csproj明确.NET Framework 4.6。
- README的平台与架构列表作为历史工具链说明。各目标组合实测与现代系统兼容性待核实。

### 版本及限制

- Properties/AssemblyInfo.cs同时标注AssemblyVersion和AssemblyFileVersion为1.0.0.0。
- 该值按程序集版本记录。
- release.bin.zip存在于固定树中；本轮以源码和文件入口进行核验。
- GitHub Releases集合返回空列表。
- tags集合请求被GitHub fetch工具的URL范围检查拒绝，错误为INVALID_ARGUMENT；标签情况待核实。
- 当前递归Git树完整返回，truncated=false。
- 独立语言版本、正式发行编号、后续维护计划及执行结果待核实。

## 四、实际平台、查询和时间范围

核验时间：2026-10-10 UTC。

### 普通web搜索

实际查询：

- “奇语言” “qilang”
- “CNPL” “Zhou-zhi-peng”
- “奇语” “Liang Li”
- “cnpl” “周志鹏”
- “奇语言” “2025”
- site:qilang.org 奇语
- “qilang-project” “liliang-cn”
- “Zhou-zhi-peng/cnpl” “2020”
- “qilang.org” “奇语”
- “CNPL” “白话文” 编程

普通搜索均采用全年代范围，未设置日期过滤。实际取得历史材料为奇语言2025—2026年资料、CNPL 2020年源码历史。姓名定向查询所得材料保持为检索线索，作者字段以原仓库账号和原提交署名为依据。

### GitHub只读接口

- 仓库元数据、默认分支、完整递归树。
- 固定提交文件。
- 两仓库Release集合；奇语言追加per_page=100完整页。
- CNPL commits集合，per_page=100。
- 奇语言历史commits，until=2025-12-31T23:59:59Z、per_page=100，追至无父提交的根节点。
- 早期提交详情与具体历史文件。
- search_commits空查询、order=asc、sort=author-date、topn=1：奇语言返回2026年提交、CNPL返回空。该检索结果按接口实际返回记录；最早历史结论来自随后读取的commits集合。
- Issue #1及全部评论，百科数据和既有日志。

## 五、交付核对与待补证据

- 两个对象保留原id、名称及参考入口。
- 两段代码均来自单个固定提交文件的连续原文。
- 日期分别记录提交、建库、推送和发行。
- CNPL的EXE输出明确为平台加载器封装字节码。
- 奇语的原生目标文件与运行时链接路径、Wasm目标文件分支分别记录。
- 两项首次对外公开时间仍待作者公告或原始发布记录补证。
- 奇语的旧域名关系、完整生态组件及运行验证待补。
- CNPL的作者中文姓名、内部课程日期、独立语言版本及现代兼容性待补。
- 本轮工作为源码与文献静态核验；安装、编译、测试和样例执行属于后续验证范围。
