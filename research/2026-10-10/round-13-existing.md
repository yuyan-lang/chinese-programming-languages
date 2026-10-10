# 第十三轮：完善Y++／YStudio与ikdxhz中文Python

核验日期：2026-10-10（UTC）。百科基线为[65e45d07d80a36412625665931ce4a4402641480](https://github.com/yuyan-lang/chinese-programming-languages/tree/65e45d07d80a36412625665931ce4a4402641480)。

## 范围与结果

本分项完善lang-031、lang-032两项。原ID及两对象已有字段保留；原10条参考的标题、URL和顺序逐项保留，新增11条参考，共21条。两个description分别为319、358个Unicode字符。代码分别升级为8行事件处理原例和17行README完整代码块，替代关系写入code_source_detail与verification_notes。

开工已读：
- 基线[AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/65e45d07d80a36412625665931ce4a4402641480/AGENTS.md)
- 基线[data/languages.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/65e45d07d80a36412625665931ce4a4402641480/data/languages.json)及两完整对象
- 上轮[round-12.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/65e45d07d80a36412625665931ce4a4402641480/research/2026-10-10/round-12.md)
- [Issue #1正文与全部12条评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)，含上轮完善NyaPlus／Nuzo的结果

本分项沿用76项语言、8项内核的开轮基线，新增计数为0。采用GitHub只读API、公开网页及搜索索引进行静态研究；项目独立构建运行保持待验证。

## lang-031：Y++／YStudio

### 作者、归属及时间

[官网“关于与联系”](https://www.yddphp.cn/index.html)明确列出个人开发维护者“一点滴”，并说明其为Y++语言与YStudio IDE作者。[语言基础](https://www.yddphp.cn/docs/language.html)同样署名一点滴，明确产品品牌Y++／y++和IDE名称YStudio。两者以同一语言项目记录；YSS保存为配套样式系统。

[BV1tSNq6AE7g](https://www.bilibili.com/video/BV1tSNq6AE7g/)原视频的公开索引可读标题“Y++高级界面〖3〗标签组件”、账号“一点滴-侠之大者”及2026-07-15 10:46:10。此日期仅作为这条教程视频的发布时间。首个语言公开、官网上线及YStudio 2.2正式发行日期继续待核实。

精确搜索另命中基础课程第1课“IDE界面”的B站搜索页缓存，页面仅写“03-29”，精确BV及完整年份待核实。该线索保存在检索结果中，公开条目仍采用已核原片的完整日期；更早历史继续待核实。

### 中文语法与代码替代

[语言基础](https://www.yddphp.cn/docs/language.html)可核中文基本类型、真／假、函数、返回、如果／否则、循环、当、遍历、选择／分支以及尝试／捕获；源码使用大括号，函数式命令带括号，中文标识符与控件属性可直接出现。

新的code取自[官网“语言一眼能看懂”](https://www.yddphp.cn/index.html)的完整8行事件代码块，含原始“// 事件里写中文逻辑”注释及按钮保存事件。其中文语法包括函数、如果、返回与信息框命令；文本框1、标签状态依赖对应窗口XML。这是完整连续事件片段，配套完整工程与运行结果待核实。

原code为“整数 n = 0”，出处是language.html §3.1基本类型表。新示例替代该单行展示；原参考标题与URL均保留，原例内容和来源也在verification_notes、code_source_detail.replaces中说明。

[图片支持库](https://www.yddphp.cn/docs/image-support.html)还提供按钮打开、条件返回、图片读写与变换的连续原例。本轮使用官网较短事件块作为主展示，图片页继续承担实际库调用语法与底层实现说明证据。

### 实现与边界

[官网](https://www.yddphp.cn/index.html)说明MSVC工具链输出Windows x86／x64原生程序。工程由.ysproj组织，.yc保存事件及业务逻辑，.yt保存类型，.ypp保存类，.yp保存API声明，.xml保存布局，.yss保存样式。编译器本体实现语言、词法／语法前端及中间表示仍待核实。

[DLL/API文档](https://www.yddphp.cn/docs/dllapi.html)说明LoadLibrary与GetProcAddress的导出解析；[指针边界手册](https://www.yddphp.cn/docs/dll-pointers.html)区分声明自动编组、DLL辅助命令及低层地址操作。[图片支持库](https://www.yddphp.cn/docs/image-support.html)说明底层为Windows WIC和Direct2D／DirectWrite。上述均按作者文档说明记录，运行验证继续待核实。

类型宽度存在待核项：[language.html](https://www.yddphp.cn/docs/language.html)将整数列为32位，[第三方DLL指南§4.2](https://www.yddphp.cn/docs/third-party-dll.html)说明部分整数参数常为8字节。目标架构、文档版本及ABI对应关系需要原始编译器或作者进一步明确，条目已显式记入verification_notes。

### 版本、分发、许可及AI

官网公开索引显示2.2.0.0／v2.2，路线区说明当前v2.2可用。下载区同时显示两个IDE安装包和通用编译器为“待发布”，并说明编译器与IDE分开分发。此次按“索引观察到的下载区状态”记录，实际可取得的发行物、分发更新时间与校验信息待核实。旧status中笼统的安装包已提供表述已调整。

源码公开位置、开源许可证、软件使用授权条款、独立语言版本号与首次正式发行日期继续待核实。阅读范围覆盖官网、语言基础、库文档和原片索引；AI参与项目开发的明确作者声明以及AI在执行链中的具体角色继续待核实。文档面向生成／修改代码的说明可作为使用场景信息。version、status和verification_notes均包含这些可在详情页显示的结论。

### 可达性

官网四个既有原页的直接open均返回Cache miss；同源官方索引可读正文，索引显示抓取约在核验前两周。B站原片直接open返回工具不可达，原片公开索引可读，抓取约在核验前三周。本轮使用这些允许读取的公开索引，保留抓取延迟。网站实时内容、影片逐帧演示、评论和安装体验继续待核实。

## lang-032：ikdxhz/chinese-python

全部源码与README固定在[ba31921bd379ca1d72f437a3f01528aaa2fe2a57](https://github.com/ikdxhz/chinese-python/tree/ba31921bd379ca1d72f437a3f01528aaa2fe2a57)。

### 作者及分层时间线

作者账号ikdxhz由README联系方式、GitHub提交及MIT版权行共同支持。仓库[元数据](https://api.github.com/repos/ikdxhz/chinese-python)为：
- created_at：2025-06-22T14:17:18Z
- pushed_at：2025-06-24T12:29:02Z
- default_branch：main
- archived：false；disabled：false；fork：false
- updated_at：2026-08-17T01:04:54Z，此字段按仓库元数据记录；源码维护日期采用提交与pushed_at

[根提交](https://api.github.com/repos/ikdxhz/chinese-python/git/trees/3d8d62f9b5a7c98bab40d52ec8faee564811e05f?recursive=1)时间2025-06-22T14:17:18Z，目录仅含LICENSE。[紧接的首次上传提交5fac2bf](https://github.com/ikdxhz/chinese-python/commit/5fac2bf57b13d8e224eec44d30dc6bf16db596bb)时间2025-06-22T14:19:36Z，新增README、mapping.py、chinese_python.py、GUI和长代码示例。

[当前README“最近更新”](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/README.md#最近更新)自署“2024年6月24日更新”，包含在线版本发布说明。该日期按作者自署文档日期保留；当前可追溯源码链来自2025年6月。两者历史关系、首发材料与最早公开日期继续待核实。

只读提交列表共有12条，首条为2025-06-22根提交，最新ba31921为2025-06-24T12:29:02Z。当前根与上传历史足以区分建库和首次代码入库时间；公开可见性的历史变更另待核实。

### 中文原例与分类

[README L129–L145](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/README.md#L129-L145)的“代码示例”完整连续块已逐字转录。共17行，含全角打印括号、计算平方函数、对于循环和如果／否则分支，具有真正中文关键字。原2行“定义／返回”函数在完整例子中原样保留，来源固定SHA保持一致。

分类沿用“Python中文关键字转换层；教学工具”。作者README“工作原理与技术局限”将核心机制说明为预定义映射和文本转换。条目直接介绍确定性转换与Python执行关系。桌面和浏览器分别属于同一项目的两个转换实现。

### 实际执行链

固定树共7个文件，相关文件完整读取：

1. [mapping.py](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/mapping.py)：translate_to_python位于L1109起；先以正则提取三引号、普通字符串和注释，并用变量占位处理部分赋值、形参及循环变量位置。映射键按词长排序，关键词替换采用正则边界，再转换中文标点，最后恢复占位内容。
2. [chinese_python.py](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/chinese_python.py)：读取UTF-8 .cnpy，显示转换结果，以exec和包含Python内置项的全局字典执行；交互模式累积多行，共用namespace，以“执行()”触发代码块执行。
3. [chinese_python_gui.py](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/chinese_python_gui.py)：Tkinter界面，调用mapping.translate_to_python，显示转换结果，并有exec执行路径。
4. [index.html](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/index.html)：独立JavaScript映射及translateToPython，使用字符串／注释占位、词长排序、正则替换和标点转换；页面引用CodeMirror 5.65.3与Pyodide 0.23.4，L888调用pyodide.runPython(pythonCode)。这些版本属于界面与运行依赖。

静态检查发现同名映射键存在覆盖。桌面“方法”最终值method、“数组”最终值array、“输出”值return；浏览器相应值为def、list、print。桌面变量保护和浏览器替换逻辑分别实现。上述具体差异写入verification_notes，兼容性和示例执行结果继续待核实。Python源文件中的字符串／标点规则、复杂表达式、循环中断与GUI线程行为的完整审计继续待核实。

### 版本、许可与AI依据

[README](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/README.md)徽章自署1.0；[命令行源文件](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/chinese_python.py)交互横幅及帮助文本自署v0.1。这两项按文件层级并列，正式版本对应关系待核实。

[正式发行列表](https://api.github.com/repos/ikdxhz/chinese-python/releases)返回[]；[标签引用列表](https://api.github.com/repos/ikdxhz/chinese-python/git/matching-refs/tags/)返回[]。[固定LICENSE](https://github.com/ikdxhz/chinese-python/blob/ba31921bd379ca1d72f437a3f01528aaa2fe2a57/LICENSE)为MIT，版权行是2025 ikdxhz，根树与当前树LICENSE blob相同。许可和发行结论写入version、status。

AI依据来自README“学习方法”“如何使用AI助手解决问题”：建议把用户程序及报错交给ChatGPT、Claude等外部助手求解释或修正。这是教学排错建议。已读执行链为静态映射及Python执行，项目编写阶段的AI参与比例、所用模型与作者开发声明待核实。此分层写入verification_notes。

### 访问记录

GitHub文件、仓库元数据、提交历史、Releases与Git引用只读端点成功。普通/tags端点被连接器判为不支持，网页tags页面返回Cache miss；使用工具说明支持的Git标签引用GET取得空数组。此为公开元数据接口的格式选择，访问权限保持不变。根提交README读取返回404，随后根目录树证实仅有LICENSE，时间分层按该树与第一次源码上传记录。

## 检索覆盖与遗漏风险

实际关键词分组：
- 站内：site:yddphp.cn/docs/language.html；image-support.html；dll-pointers.html；YStudio 2.2；MSVC；C++；Qt；许可／开源／AI／人工智能／Claude／ChatGPT
- 历史：BV1tSNq6AE7g；“Y++”＋“一点滴”＋2025／2026；“Y++基础课程”＋“IDE界面”；“一点滴-侠之大者”＋“IDE界面”＋“BV”
- GitHub：固定README、映射、CLI、GUI、HTML、LICENSE，递归固定树、根树、首次上传提交、全部12条提交、仓库元数据、Releases和标签引用

Y++资料依赖索引缓存、缺少可固定的源码版本；B站日期只核已读原片，早期第1课BV与年份待核。中文Python的仓库时间、文档自署时间及正式发行层级分别保存。两项目独立构建与运行均待核实。

## 审阅检查与后续

已静态检查：
- lang-031／lang-032及全部原字段保留
- 原10条参考标题、URL、顺序逐项相同
- 新增11条参考，指向本轮实际阅读来源
- description长度319／358字符
- 中文原例8／17行，来源与替代说明齐全；中文Python旧2行原例包含于新块中
- version／status／verification_notes可承载许可、发行及AI分层
- JSON可序列化，两对象ID唯一

后续优先事项：Y++真实发行包与许可、编译器源码和ABI宽度、基础课程第1课原片及首发历史；中文Python自署2024日期的历史资料、同名映射差异及实际程序运行。Issue #1仍有其余薄条目与历史待核字段，保持开放。
