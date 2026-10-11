# 第十六轮：GitHub微型中文语言发现与同源核验

核验日期：2026-10-10。目标仓基线：yuyan-lang/chinese-programming-languages@93815086f1778802ea57ddeeec8ad717e355814f。研究时段：22:00—22:08 UTC。

## 结果与计数

- 首次深入两组，正式候选2项：知序（Zhixu，2026）与china++（chinaplusplus，2023历史补录）。两组此前保存在第十五轮搜索级清单。
- AI-CN与知序为明确改名和共享Git历史的一组，按1项计数。
- iclasspeople/chinapp追溯到chinaplusplus/chinapp；2025是Fork创建年，原项目现存历史为2023。
- iclasspeople/cnpl、cd37ycs/cnpl同属既有lang-018 CNPL；两仓父项与源项均为Zhou-zhi-peng/cnpl，头提交均为f2a60c0ae7e6264f8a9406e5b8fbda6114b08ccd，完成去重。
- woshishazi250/z-IDE作搜索级原仓简核，保留语法与实现补证项，深入新发现计数仍为2组。
- 后续补证范围包括两条正式项的剩余字段及一条Z++搜索级记录。

## 基线与去重

读取固定研究规范、完整语言目录（86项）、第十五轮研究总报告与搜索记录。GitHub全状态Issues集合返回47项，其中26项是开放Issue，其余为PR记录；全仓Issue评论接口返回83条，其中归属这26项Issue的评论为69条。用于去重的范围覆盖26项Issue正文与69条Issue评论，同时保存PR评论背景。基线原件完整保留。

检索名称、别名、作者与仓库：1556880640-bot、ai-cn、AI-CN、zhixu、知序、iclasspeople、chinapp、china++、chinaplusplus、windworst、cnpl、Zhou-zhi-peng、woshishazi250、Z++。正式目录及Issue／评论中知序与china++完整身份均无命中；CNPL命中lang-018及Issue #1既有完善记录。豫言原条目保持原状。

## 1. 知序（Zhixu）

原仓：https://github.com/1556880640-bot/zhixu
前身：https://github.com/1556880640-bot/ai-cn
固定提交：d85adac01a15af7206ec72eda10d994b36a4b37a。

### 作者、时间、改名与版本

现存三条提交均由1556880640-bot署名，GitHub账号映射相同；自然人姓名与完整团队分工待核实。

- 根提交0e7fe68031318c6a283090f52c38aba2b1bdcabd：2026-05-16T13:10:20Z，parents为空。
- AI-CN建库：2026-05-16T13:32:01Z。
- 中间提交89d30ece9e6d81ff46bcc2398221b9457e3328c8：2026-05-16T13:41:57Z。
- 知序建库：2026-05-16T14:02:29Z。
- 改名提交d85adac01a15af7206ec72eda10d994b36a4b37a：2026-05-16T14:02:56Z，父提交为89d30ece。

改名提交原文明确“AI-CN → 知序 (Zhixu)”，文件差异将ai_cn.py→zhixu.py、ai_cn_utils.py→zhixu_utils.py、.ai_cn→.zx，并新增zx.bat。包字段在同一次提交中从ai-cn 2.0.0改为zhixu 1.0.0。源码版号、Git提交与仓库创建分列；准确首发及包平台发行继续待核。两仓Git refs读取均仅列master，GitHub Releases列表均为空。

固定README与pyproject.toml声明MIT；完整8文件树已读，许可全文、版权主体与授权范围待核实。三次Git提交消息均含“Co-Authored-By: Claude Sonnet 4.6”，按开发记录中的AI协作标记记载；具体工具、模型会话、生成比例及人工复核待核。运行时AI产品功能与开发共同署名分层。

### 连续中文原例

https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/README.md#L31-L44

固定README.md第31—44行，连续14行，逐字提取：
```text
定义 计算平均值(数字列表):
    总 = 0
    循环 数 在 数字列表:
        总 = 总 + 数
    返回 总 / 长度(数字列表)

分数 = [92, 78, 85, 63]
结果 = 计算平均值(分数)
输出(f"平均分: {结果}")

如果 结果 >= 80:
    输出("优秀")
否则:
    输出("继续加油")
```

该片段完整定义并调用平均值函数，随后分支输出；README中代码块注释为demo.zx，实际仓库demo.zx是另一组基础与AI示例，因此出处明确标为README。demo_实用.zx第33—45行另有中文类与过滤循环原例。原代码、作者资料与独立运行结果分别记录。

### 实际实现调用链

1. zhixu.py第649—685行：CLI run→run_file；export与repl分别进入独立函数。
2. 第495—519行：读取UTF-8文件→translate→exec(py_code, exec_globals)。
3. 第443—470行：引号／标点预处理→tokenize→generate_python。
4. 第176—303行：逐字符扫描；第280—294行对完整标识符查KEYWORD_MAP，将中文控制词标成KEYWORD。
5. 第316—435行：按KEYWORD_MAP转换Python文本、保留缩进与换行；使用AI映射词时加入工具库导入。
6. zhixu_utils.py第48—146行：后端检测与分派；Ollama第165—189行、OpenAI第247—272行、HuggingFace第320—377行存在具体推理调用。

语法资格来自定义／返回／如果／循环等实际映射及原例；中文变量名与模型.推理方法是另行保存的标识符／接口能力。

### AI功能实现边界

- Ollama：requests访问本地/api/tags、/api/generate；函数内有流式分支。
- OpenAI兼容API：requests调用/chat/completions；流式路径使用OpenAI客户端。
- HuggingFace：AutoTokenizer／AutoModelForCausalLM加载与generate调用；流式方法转到同一predict路径。
- 模拟模型：返回带“模拟”标记的固定文本。
- RAG：LangChain／Chroma创建向量库；依赖缺失分支写入文件列表索引。功能声明与文件格式覆盖继续核实。
- 微调第529—587行：依赖检测、配置与训练命令提示；另一分支输出模拟完成文本。提示引用的finetune_runner.py和_run_finetune对应来源待核。
- 量化第590—618行：按精度分支打印比例与完成文案；真实量化效果待核。
- 显存优化第759—780行：检测CUDA后打印策略和状态；优化效果待核。
- 嵌入第783—811行：调用Ollama嵌入端点，异常／失败路径返回768项零向量。

这些内容均按固定源码静态阅读，模型请求、训练、服务启动与项目执行待核。标点预转换、字符串边界、入口全局、行号映射、REPL变量持久性及包配置列入后续检查。

### 固定原件
- 知序原仓及当前元数据：https://api.github.com/repos/1556880640-bot/zhixu
- 固定中文语法、连续14行平均值原例：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/README.md#L31-L63
- 固定中文类、函数及循环原例：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/demo_实用.zx#L33-L45
- 固定中文关键字与宿主操作映射：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu.py#L46-L124
- 固定词法扫描与整词关键字识别：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu.py#L176-L303
- 固定词元到Python源码与工具库导入：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu.py#L316-L435
- 固定转译调用链：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu.py#L443-L470
- 固定文件执行与Python exec：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu.py#L495-L519
- 固定CLI入口与三子命令分发：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu.py#L631-L685
- 固定后端检测及模型加载分派：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L48-L146
- 固定Ollama与OpenAI推理适配：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L153-L304
- 固定HuggingFace与模拟回退：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L311-L418
- 固定RAG真实调用与模拟索引分支：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L425-L526
- 固定微调提示与量化状态输出阶段：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L529-L618
- 固定显存状态提示及嵌入模拟回退：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L759-L811
- 固定源码1.0.0、MIT标签与Python版本：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/pyproject.toml#L5-L19
- 固定README许可声明：https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/README.md#L96-L98
- 前身AI-CN源码2.0.0：https://github.com/1556880640-bot/ai-cn/blob/89d30ece9e6d81ff46bcc2398221b9457e3328c8/pyproject.toml#L5-L19
- 改名提交、共同历史及Claude Sonnet 4.6署名：https://github.com/1556880640-bot/zhixu/commit/d85adac01a15af7206ec72eda10d994b36a4b37a
- 现存根提交与AI共同署名：https://github.com/1556880640-bot/zhixu/commit/0e7fe68031318c6a283090f52c38aba2b1bdcabd
- 第二次提交与AI共同署名：https://github.com/1556880640-bot/zhixu/commit/89d30ece9e6d81ff46bcc2398221b9457e3328c8
- 前身AI-CN原仓：https://github.com/1556880640-bot/ai-cn
- 固定完整八文件树：https://api.github.com/repos/1556880640-bot/zhixu/git/trees/d85adac01a15af7206ec72eda10d994b36a4b37a?recursive=1
- Git refs核对：https://api.github.com/repos/1556880640-bot/zhixu/git/refs
- GitHub Releases核对：https://api.github.com/repos/1556880640-bot/zhixu/releases?per_page=100

## 2. china++（chinaplusplus）

原仓：https://github.com/chinaplusplus/chinapp
发现入口：https://github.com/iclasspeople/chinapp
固定提交：dc9dc98cb963cecdd4db1c69da86698207e7ef31。

### 作者、历史与许可

原仓由chinaplusplus组织持有，三条现存提交Git作者为xbw、GitHub映射账号windworst。自然人姓名与完整分工待核。根提交99361dbe21ba782c1e754df3bcf5281ac0ad62e9为2023-04-21T04:33:29Z；原仓创建04:33:43Z；头提交同日11:23:47Z。iclasspeople/chinapp创建2025-04-14T10:08:57Z，GitHub parent和source均指回原仓，头和完整路径／blob SHA一致。

Git refs仅列main，Releases为空。独立版号、准确首次公开、公开许可声明及完整许可文本待核。所读README、三个提交和实现文本的AI开发参与声明待核。此项作为2023历史项目补录，与2026知序分别计入时间层。

### 连续中文原例

https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/main.cpp#L26-L38

固定main.cpp第26—38行，连续13行，是主函数内部完整for宏与条件分支块：
```text
  计次循环(次数, 5) {
    如果(次数==1) {
      打印("苹果\n");
    } 又如(次数==2) {
      打印("梨子\n");
    } 又如(次数==3) {
      打印("香蕉\n");
    } 又如(次数==4) {
      打印("草莓\n");
    } 否则 {
      打印("鸭蛋\n");
    }
  }
```

main.cpp第1—2行引入两个中文头文件，主函数跨第4—41行，第40行返回0。原例保留缩进、花括号、又如关键字和转义，独立编译／输出待核。

### 实现链与分类

- main.cpp→china++/核心.h：第3—18行宏替换整数／返回／如果／否则／又如、三类循环及主函数。
- 输入输出.h第3—5行：引入stdio.h，打印→printf。
- Makefile第9—10行：g++ main.cpp -o main.app。
- Makefile第1—7行：另列amalgamate头文件合并目标。

类型和流程控制宏提供中文语法层；按C++中文关键字宏层／头文件语法实验分类。与YoloLogic等其他中文C++方案的源码继承、作者和设计关系继续待核。项目执行、宏作用域、各编译器兼容性与头文件合并工具安装保持待核。

### 固定原件
- 原仓与组织归属元数据：https://api.github.com/repos/chinaplusplus/chinapp
- 固定原作者README：https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/README.md#L1-L5
- 固定连续13行计次循环与分支原例：https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/main.cpp#L26-L38
- 完整主函数、头文件引用与返回：https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/main.cpp#L1-L41
- 固定中文核心关键字与循环宏：https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/china++/核心.h#L3-L18
- 固定打印宏与C标准库接入：https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/china++/扩展/输入输出.h#L1-L5
- 固定g++构建与头文件合并目标：https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/Makefile#L1-L10
- 2023根提交与GitHub作者映射：https://github.com/chinaplusplus/chinapp/commit/99361dbe21ba782c1e754df3bcf5281ac0ad62e9
- 当前头提交与作者署名：https://github.com/chinaplusplus/chinapp/commit/dc9dc98cb963cecdd4db1c69da86698207e7ef31
- 2025 Fork的明确parent与source元数据：https://api.github.com/repos/iclasspeople/chinapp
- 原仓固定完整树：https://api.github.com/repos/chinaplusplus/chinapp/git/trees/dc9dc98cb963cecdd4db1c69da86698207e7ef31?recursive=1
- Fork同头完整树：https://api.github.com/repos/iclasspeople/chinapp/git/trees/dc9dc98cb963cecdd4db1c69da86698207e7ef31?recursive=1
- Git refs核对：https://api.github.com/repos/chinaplusplus/chinapp/git/refs
- GitHub Releases核对：https://api.github.com/repos/chinaplusplus/chinapp/releases?per_page=100

## 3. 去重与搜索级保留

### CNPL的2025／2026 Fork

iclasspeople/cnpl（建库2025-05-14）与cd37ycs/cnpl（建库2026-01-30）均有GitHub明确Fork关系，parent/source为Zhou-zhi-peng/cnpl。两仓所读头f2a60c0ae7e6264f8a9406e5b8fbda6114b08ccd及83项完整树与既有lang-018固定头对应。按CNPL同源线索归并。
- https://api.github.com/repos/iclasspeople/cnpl
- https://api.github.com/repos/cd37ycs/cnpl
- https://github.com/Zhou-zhi-peng/cnpl

### Z++ IDE

woshishazi250/z-IDE固定b2280f7cc6dd898eb6ba267ca9caef58ae94e69e，建库与根提交均为2026-03-20T07:00:22Z。完整树只有README.md与LICENSE；README介绍中文语言IDE，Apache-2.0全文可读。语言本体、连续中文语法、实现调用链、作者关系及版号待补。记录为搜索级补证，正式／深入新发现计数采用前述2组。
- 固定README简介：https://github.com/woshishazi250/z-IDE/blob/b2280f7cc6dd898eb6ba267ca9caef58ae94e69e/README.md
- 固定两文件树：https://api.github.com/repos/woshishazi250/z-IDE/git/trees/b2280f7cc6dd898eb6ba267ca9caef58ae94e69e?recursive=1
- 原仓元数据：https://api.github.com/repos/woshishazi250/z-IDE
- 固定许可：https://github.com/woshishazi250/z-IDE/blob/b2280f7cc6dd898eb6ba267ca9caef58ae94e69e/LICENSE

## 检索平台、关键词、时窗与遗漏

时间窗以2024-01-01—2026-10-10为主，遇Fork回溯原仓历史。日期过滤为仓库创建日期，项目创制与中文语法引入日期逐项核对。

### GitHub仓库检索

- 查询："中文编程语言" created:2024-01-01..2026-10-10 fork:false；page=1、per_page=100，取得36项。
  - nntandg/PengBooo
  - HeiKe-Tom/CN-Language
  - 52zwbc/zw
  - qbr12/hbr-c.zc
  - qilang-project/qi
  - whitesnowmoon/CN_Interpreter
  - wc772/atlanage
  - 1556880640-bot/ai-cn
  - nekonekods/NyaPlus
  - CLimber-Rong/sitameng
  - Citric1acid/ChineseProgrammingLanguage
  - PythonDeveloper29042/PythonCN
  - 1556880640-bot/zhixu
  - QAZWSX123456-Source/-python-toolbox
  - bikthh/wenyu
  - jinglei88/Yima---Minimalist-Chinese-Programming-Language
  - jiangjun-ling/jiangjunling-lang
  - cnlnr/xiaoyi
  - a737812/yaolang
  - benxiaoniao/JISHI
  - mycplang/cplang
  - 3477856804/coCN-website
  - wwwwyyt/dgy-lang
  - CNplus/CNplus-wiki
  - CNplus/CNplus-lang
  - cnzkai/Zlang
  - LostPEople634/pchinese
  - zf199606/ling-code
  - jzm3/lingyu
  - bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool
  - xxiaoxiong/DaLang
  - 3477856804/coCN
  - woshishazi250/z-IDE
  - oneone1565/LightLang
  - qingsububao/PYCH-Language
  - Xzach88/Longyin-OS
- 查询："中文关键字" created:2024-01-01..2026-10-10 fork:false；page=1、per_page=100，取得6项。
  - YoloLogic/ChinesePlusPlus
  - YoloLogic/LinuxChinesePlusPlus
  - YoloLogic/ChinesePython
  - YoloLogic/LinuxChinesePython
  - coatcn1/Item-Lore-Highlighter
  - HongshouStudio/-

以上搜索用作回查前轮微型仓、已有对象及相关工具；36项与6项为两组查询各自结果，交叉重复另行去重，搜索结果数与语言数分列。搜索只覆盖GitHub名称／描述索引；fork:false对Fork另由前轮给定路径追溯。

### 普通网页精确查找

- "知序" "1556880640" 编程
- "ai-cn" "zhixu" 中文编程
- "chinaplusplus" "chinapp"
- "woshishazi250" "Z++"
- "知序" "中文编程" 2026
- "china++" "chinaplusplus"
- "AI-CN" "中文编程语言"
- site:github.com/1556880640-bot/zhixu

网页精确查询返回零散同名与泛化结果，本轮新增事实均回到原作者GitHub源码和元数据取证。相关的原作者外站发布入口继续待核；搜索索引缺口保留。网页精确查询采用开放日期范围，2026词作为其中一组检索条件。

### 读取限制与解决

GitHub标签端点/tags?per_page=100存在读取限制；/git/refs/tags返回404。随后读取同仓公开/git/refs集合成功，列出唯一默认分支。版本结论依据可读refs及Releases集合，原始失败响应也保留。研究范围为公开资料静态阅读。源码安装、编译及执行结果待核。

GitHub小仓库、未索引外站、动态发布、私有或已删除项目仍有遗漏风险；建库时间、Git作者时间、提交时间、包版号与首次公开时间分别记录。AI共同署名是作者提交记录，具体生成过程待核；模型后端源码、演示文案和独立运行分层。

## 原例与资料核验

两个正式条目的code均由固定源码指定连续行直接提取；知序14行、china++13行，源码字节、空行与缩进保留。39条正式引用分别指向固定源码、Git提交及公开元数据。条目采用既有目录字段，许可和AI事项同步记录于版本与核验说明。所有原始来源完整保留。项目安装、运行、编译与测试均保持待核。

研究资料静态核验确认：两条代码与固定来源指定连续行逐字相等；必需字段、引用格式及可核源码行号范围完整；去重原件再次计得26项Issue与69条Issue评论。

