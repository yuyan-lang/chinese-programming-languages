# 剩余语言候选：原例定位与脑语言范围分类

核验日期：2026-10-28。基线4e00d5240ff5ca99c745c2b00179c11e42bef800，110项语言、20项内核；范围为Issue #16、#22、#40、#43。本轮先读取四项议题正文、全部评论、AGENTS.md及相关研究和目录；checkout与工作区根下的.agents/skills目录缺省。

本轮建议关闭#43：已核发布物按词表、输入工具、JavaScript教学手册和中文函数别名／JSON组合平台完成范围分类，语言目录新增0项。#16、#22和#40保留具体原例缺口。data/languages.json、全部详情页、既有对象、字段、原例和引用保持原样。候选安装、构建、测试及程序执行均为0。

机器可读固定提交、blob、尝试结果与边界见[mixed-scope-evidence.json](mixed-scope-evidence.json)。本记录仅限所列固定发布物及页面观察，其他版本与未来新增实现按新原件评估。

## 结果表

| 议题 | 已完成对象 | 本轮实际路径与结论 | 剩余实质事项 | 建议 |
| --- | --- | --- | --- | --- |
| #16，7组 | ChinesePython lang-047、ChineseTypeScript lang-048、Sheng lang-049、子语lang-051、ChineseCpp lang-101；ChineseJava按占位计划完成当前阶段分类 | SPCNYY两份安装脚本的7个内嵌模块、GUI写入点、所有字符串和历史根README逐项静态阅读；仍未取得作者连续中文用户程序 | SPCNYY原作者.spc原例；ChineseJava未来形成实际语法时再评估 | 保持开放；本轮不追加同状态轮询评论 |
| #22，10组 | 太和lang-062、ChineseToyLang lang-063、pchinese lang-065、MiniLang lang-066、zhsc-compiler lang-069、chinalang lang-070、PyCn lang-072、XuYu lang-096 | 中文Rust完整5提交树及34份Rust源码核对；文档为映射／需求，历史Compute为英文Python演示 | 中文Rust作者连续中文程序；52zwbc关联组沿用PR #62取消边界 | 保持开放；本轮不追加同状态轮询评论 |
| #40，2组 | 玄lang-105已收录 | Lua正常公开Git传输连接重置；独立分支树及树元数据入口未返回可核材料 | lyzavng/lua原作者连续中文程序 | 保持开放；访问失败作为本地证据记录 |
| #43，1组 | 已核词表、输入工具、函数API和JSON组合平台 | 新读作者关联2500js手册，36项单字标签配标准JS例程；源码直接调用JavaScript Function构造器。dshjs固定CLI、注册器、测试及作者v1.5.1原文支持统一命名与接口分类 | 当前范围分类完成；独立汉字控制语法若另行发布，依据新材料重新评估 | 本轮研究合并后关闭；正式语言目录新增0项 |

## #16：检查SPCNYY内嵌用户程序的可能位置

原仓[xs-smz/spcnyy-](https://github.com/xs-smz/spcnyy-)保留两次提交：根2b99fb85eaf91284d5d0bd0aa047772db41dd75c（2026-08-15T16:43:42Z），源码上传2d9087cade68fff2c966a7bf057141935b439ec0（2026-08-15T16:46:47Z）。根README的blob 6a82887a001c9d1ceb8ef33831f4d7a1746e7edf与当前一致，内容为名称与“用中文来写的编译器”简介。

本轮读取固定[Shell完整脚本](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh)、[PowerShell完整脚本](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/windows_spcnyy.ps1)、[setup/pipe](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/pipe)及根README。Shell与PowerShell分别为blob bd896ef420a1e7a2040e5bdd8ad87d24d53b51fa、7e4abde4fb89966bf8f5826d4a6c1e080172357f。

两份脚本均内嵌main.py、launcher.py、login.py、recharge.py、ai.py、language.py、editor.py七模块。静态提取七组正文，统一展示换行后逐字符比较全部一致。将模块作为文本交给Python ast.parse只做语法树阅读，检查所有字符串常量、多行汉字文本与GUI写入点；此操作未导入或执行候选模块。

| 原始位置（Shell行号） | 内容层级 | 原例定位结果 |
| --- | --- | --- |
| L270—284，ai.py的debug提示 | 自述用户以中文写代码、目标Python，含映射表插值与`{code}`槽 | “用户代码”来自调用参数；提示正文给出检查规则 |
| L289—311，language.py | 中文／拼音到Python关键词及标点映射、循环正则 | 映射和转换实现；连续用户程序待补 |
| L433、L468，学习窗口 | 欢迎语和对话已清空文字 | GUI提示 |
| L503、L508—519，词库与编辑器映射 | 拼音补全词、中文关键字表 | 编辑辅助数据 |
| L536、L551—560，编辑区insert | 标点转换、缩进或用户选择的补全词 | 插入点内容来自输入或映射 |
| L563—578，新建与打开 | 新建清空缓冲区；打开读取外部.spc | 新建路径原例缺省；外部用户文件内容待补 |
| L684，生成关键字.json | 三个拼音映射词 | 配置数据 |
| setup/pipe全文 | chmod与启动命令两行 | 安装入口说明 |

PowerShell对应提示词L317—332、新建／打开L612—626及词库L739提供同一语义。七模块中的多行中文字符串集中于AI提示规则、学习欢迎、清空消息和对话标签；当前公开两次历史内仍缺作者连续中文用户程序。该结论限定于所列原始文件，未推定作者其他渠道或未公开例程的存在状态。

本轮证实本次指定的内嵌示例定位路径仍留下同一实质缺口。五组已收录及ChineseJava占位计划分类沿用2026-10-25记录，当前核验任务集中于SPCNYY原例。#16保持开放；这次负向定位结果保存在研究记录，无需再向远端发布相同待核状态。

## #22：中文Rust的测试、文档和删除历史

固定[4605fee9402c9ad6fe6e06771b6d2443105eada8完整树](https://api.github.com/repos/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/git/trees/4605fee9402c9ad6fe6e06771b6d2443105eada8?recursive=1)共81项、51文件，truncated=false。本轮逐一核对默认分支保留5次提交的完整递归树，并阅读全部34份Rust源文件。完整历史的路径／blob比对表明：工作区上传后Rust文件blob均保持一致；后续差异集中于README修订与删除Compute。

| 固定提交 | 时间（UTC） | 文件及原例核验 |
| --- | --- | --- |
| fd99a1de560a478f65276c3429b68bd71f02540c | 2026-07-03T03:40:08Z | 仅初始README两行，blob 1fb49e19ce568c3f0d625a730aaef1588d940b72 |
| 4a387265dd10fac5dd791bf4bac2d5d5708ebf8e | 2026-07-03T03:42:14Z | 仅修订README两行，blob bc890404156d0a9d959b27b0598d88fa6c45e9d5 |
| bd8ebc340636968c96200795525a374fbe88b6db | 2026-07-03T05:31:02Z | 加入Rust工作区及Compute |
| 75b725895c34321b8bd670679160ff3973d803e8 | 2026-07-03T05:34:31Z | 删除Compute |
| 4605fee9402c9ad6fe6e06771b6d2443105eada8 | 2026-07-03T05:36:32Z | README改为需求、映射和PlantUML流程文档，blob dc4e9ec235d2e9db1f6f4dfae6ff364c5c71d3c5 |

当前全树中的文档为根README与0字节的同名设计文档；tests、examples和中文程序文件路径缺省。34份Rust源码中`#[test]`和`cfg(test)`注解均为0处，汉字文本用于映射条目、诊断、注释与CLI横幅。README的7个围栏均为PlantUML，词表和规则片段按设计资料保存。

历史删除的[ZhongComputeRust/Compute](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/bd8ebc340636968c96200795525a374fbe88b6db/ZhongComputeRust/Compute)已取得正文，blob 1aa3ccadef0d3c923c6b23b5938e1e89f4f36163。它使用Python import、def、return、for等语法调用NumPy与Matplotlib，中文位于注释、文档和显示文字，按Python演示记录。

此前cn_types／cn_config映射基础实现及其他crate外部模块缺口继续适用。现有固定资料支持“中文→Rust设计与部分基础模块原型”，作者写成的连续中文用户程序仍待补；本轮不将词表拼接成程序。#22中其余八组按现有条目完成分类。52zwbc中文CPython关联组继续遵守PR #62已取消合并的边界；本轮未读取其PR差异、未复制资料入条目、未执行任何PR操作。#22保持开放。

## #40：Lua独立公开源路径及访问结果

玄lang-105已通过PR #79完成收录，本轮沿用该完成结论。Lua lyzavng/lua沿用固定c0e0b83f7bd323bac7e0326886652075d85d55db的中文词法、解析与VM静态证据，待补原作者连续中文程序。

本轮尝试正常公开Git路径`git ls-remote https://gitee.com/lyzavng/lua.git HEAD 'refs/heads/*'`，用于先识别分支，再定位tests／例程路径。该操作退出128，原因是`Recv failure: Connection reset by peer`；公开分支列表与Git对象均未取得。独立公开develop、feature树页及固定树元数据URL通过网页工具均未成功读取：

- [develop公开树](https://gitee.com/lyzavng/lua/tree/develop)
- [feature公开树](https://gitee.com/lyzavng/lua/tree/feature)
- [固定树元数据入口](https://gitee.com/api/v5/repos/lyzavng/lua/git/trees/c0e0b83f7bd323bac7e0326886652075d85d55db?recursive=1)

本轮未读取此前被平台屏蔽的README正文，也未通过其他副本读取该被屏蔽内容。正常独立源码路径的访问失败只表示本次缺少可核材料，原作者测试和其他分支中的程序状态保持待核。#40继续开放，访问结果留在本地研究记录。

## #43：按作者发布物完成范围分类

### 新原件：2500js交互式手册

[dshjs固定README L9—15](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/README.md#L9-L15)直接链接http://2500js.com，称其为单字学习JavaScript入口。2026-10-28直接HTTP读取该站成功200，页面题名“JS 关键字交互式手册”，源文件26695字节，SHA256为baefe5161c47face536ab07186f634cb6b10745a32791e97ac193f345a635e88。网页工具对该站未能读取，公开HTTP原件成功；本轮仅读源码，页面脚本与运行按钮均未执行。

源文件L90—134定义36条数据项，包含单字标签、中文解释、英文名称、语法和代码。函对应function、返对应return、如对应if等；实际示例使用JavaScript关键字，可配中文标识符。L254—261将数据中的代码放入Monaco JavaScript编辑器，L271—292读取编辑器文本并直接调用标准Function构造器：

```javascript
const 运行函数 = new Function('console', 代码);
运行函数(模拟控制台);
```

该源码链支持“带单字标签和中文解释的JavaScript交互教学手册”分类。该页面的已核运行路径直接使用JavaScript解析与执行机制。

[2500.ai](https://2500.ai/)直接网页及HTTP读取本轮超时；搜索索引标题为“2500单字统一命名”，摘要涉及编程语言统一与AI提示词快捷字。这部分只记为索引资料；本轮分类采用已读取的2500js原件、作者文章及固定源码。

### 既有原件复核：编辑工具与JSON组合平台

本轮重新读取[naoyuyan/naoyuyan固定脑语言说明](https://github.com/naoyuyan/naoyuyan/blob/986be50b55d60ce9e5869c9e6d0edc80dbed629f/%E8%84%91%E8%AF%AD%E8%A8%80%E8%AF%B4%E6%98%8E)，blob ca7faf763fd6a3b241c20251dd48a0fbc3d4fdd0。说明将2500汉字用于封装现有语言常用函数，并记录旧名与Web应用方向。完整规范版本沿革按既有研究分层保存。

[固定html/asi2500.html](https://github.com/naoyuyan/naoyuyan/blob/986be50b55d60ce9e5869c9e6d0edc80dbed629f/html/asi2500.html)，blob ff886b61b73b3c6a483e788e6bccef68e8b11244：L316—339保存单字到JS代码片段映射，L500—513按长按状态选择片段后调用Monaco executeEdits，L516—529将编辑区内容设置为预览innerHTML。当前固定材料支持中文单字代码输入工具分类。

[2500ai/dshjs固定82b1d5029a7d7acbd58633e106fd6165b0f1841d](https://github.com/2500ai/dshjs/tree/82b1d5029a7d7acbd58633e106fd6165b0f1841d)，提交日期2026-08-23T19:40:46Z；本轮完整树和头保持该版本。已读：

- [README L77—115](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/README.md#L77-L115)：单字作为函数别名，组合采用JSON；目标是逐步将词表映射为可调用函数。
- [bin/dsh.js L147—173](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/bin/dsh.js#L147-L173)：fn入口解析JSON参数再call；compose入口解析定义与输入再compose；内联、@文件及stdin三条数据路径均调用JSON.parse。对应blob ea4f6ba6ec342cb5a5d6c2fd45201e816cdee2e4。
- [src/fn/registry.js](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/src/fn/registry.js)，blob 52ce39f453cec2768ca63f7036bc5e853b323e9b：register将原名及中文别名注册到Map，call执行atom.run，runCompose处理pipe、map、if和parallel容器。
- [test/fn.test.js L50—69](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/test/fn.test.js#L50-L69)，blob 517cb7e1f69339980b519ede77bc4d278caa934c：单字“读”作为reg.call的字符串参数，组合测试使用JavaScript对象与英文结构键。测试正文属于作者源码证据；本轮执行0次。

此前已核46个函数原子、2500词表与产品版本／MIT声明继续按原始范围保存。2022词表、2025输入工具、2026接口词表和dshjs在本研究组内分层，各自发布日期、作者署名与AI声明归属保持原记录。

### 作者文档与最终范围

[作者《脑语言2500单字v1.5.1》原文](https://blog.csdn.net/weixin_44191690/article/details/165245036)本轮网页工具可读。正文将其解释为统一命名和接口，按100类、每类25个汉字组织，直接链接2500ai/dshjs。文末署名齐庄／2026.09.13，页面发布字段2026-09-19 01:39:31，两项日期继续分别记录。其统一命名与接口定位与本轮静态实现证据一致。

当前可核发布物的分类为：单字词汇规范、代码输入工具、JavaScript教学手册、中文函数API与JSON组合平台。它们作为关联工具研究资料保存，本轮正式中文语法语言目录增量0。#43的候选范围核验可以完成并关闭；无需把独立汉字语法实现设为这些已核工具的持续补证任务。此结论限定于已列原件，作者其他渠道或未来新增的中文语法及实现按新来源重新评估。

## 发布建议与评论草稿

#16、#22和#40本轮为定向静态定位或访问结果，没有新增可进入目录的程序实证；保留开放，研究报告关联本轮PR即可，避免再发送同状态轮询评论。各对象的最小后续材料已经在结果表逐项列明。PR #62保持取消合并边界。

#43在本轮研究合并后可使用以下评论并关闭：

> 本轮按原作者发布物完成范围分类，研究记录随本次PR合并。作者关联的2500js原件提供36项单字标签／中文解释配JavaScript例程，运行入口直接使用JavaScript Function构造器；固定dshjs 82b1d502的CLI通过JSON.parse读取参数与组合定义，再进入中文函数别名注册器及pipe／map／if／parallel组合器。结合作者v1.5.1原文的统一命名与接口说明，当前已核范围为词表、代码输入工具、JavaScript教学手册、中文函数API与JSON组合平台，作为关联工具研究资料保存，正式语言目录新增0项。本候选范围核验完成，关闭本Issue。以后取得作者新增的中文控制语法程序或其他实现原件时，可按新材料重新评估。

发布时由root补入本轮PR与固定研究记录链接。此工作树不向远端写入。

## 验证、限制与交付

本轮新增两份研究文件；全部110项语言与20项内核对象、详情页及历史引用保持一致。JSON研究记录可解析，固定URL／提交／blob与本地静态材料对应，git diff --check通过。候选安装、构建、测试、程序执行、部署操作和外部写入均为0。

公开网页的动态内容、搜索索引、网络超时与Git连接重置分别记录。SPCNYY与中文Rust的原例结论限定于已核固定树／历史。Lua未取得的新分支与程序正文保持待核。2500.ai正文读取结果为超时；2500js公开原件、固定Git源码与作者CSDN正文支撑#43结论。没有自动批准审查拒绝；Lua操作为网络失败，PR #62合并为用户已取消且未尝试的操作。
