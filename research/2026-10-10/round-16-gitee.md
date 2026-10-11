# 第16轮：Gitee汉源码分类核验与E#新线索

核验日期：2026-10-10。百科基线：yuyan-lang/chinese-programming-languages@93815086f1778802ea57ddeeec8ad717e355814f。

## 结果与计数

- 正式语言新增0项。
- 前轮初筛转首次源码深核1项：汉源码。已核分类为CPython中文内置函数／方法别名扩展。中文专用语法资格继续待核实。
- 真正新发现并深入待核1项：E#（DCOSA/ESharp）。已读固定中文关键词规范、当前源码入口、历史发行、许可和旧入口；按设计与运行平台原型保留。
- 本分项深入对象共2项，其中旧初筛推进1项、新发现1项。两项均作为后续补证对象，正式语言数增量为0。
- 组织页搜索命中的CH-VM和易深IDE仅作为E#关系背景；本轮独立新增对象计数采用E#。
- 两项原作者AI开发声明待核实，发现数量与AI生成项目数量分别记录。

## 去重与读取范围

已读取固定研究规范、完整86项语言目录及第十五轮发现记录。通过GitHub只读接口读取26项开放Issue正文及对应全部69条评论。研究基线另含9内核及0开放PR。

名称、别名、作者和原仓URL逐项比较：汉源码、lglCode、liu-guanglin、ESharp、dcosa/esharp、CH-VM、易深在目录、开放Issue正文及评论中均无独立对象命中。汉源码已在第15轮发现日志作为组织索引初筛记录，本轮单列前轮初筛转深核。E#字符串在部分既有代码URL片段中形成字符级误命中，名称／别名／作者／原仓核对将这些命中判作URL片段背景。

本分项围绕Gitee公开网页和GitHub只读来源开展静态研究。项目安装、运行、编译和测试结果继续待核。

## 1. 汉源码：已核为CPython中文API扩展

原仓：https://gitee.com/liu-guanglin/lglCode

固定快照：562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8。

### 身份、历史与版本

原仓位于Gitee中源组织liu-guanglin，介绍署名刘光林，所读提交账号为liu-guanglin_admin。第15轮索引描述采用“中文编程的壳”和逐步替代Python的目标。本轮实际读取根README、cpython子树、作者必读信息以及中文API原例。

作者必读信息第6—7行记录2025-09-21准备源码与环境、基于CPython 3.14进行修改。相同固定快照cpython子树README的渲染标题为“This is Python version 3.15.0 alpha 0”。两项文字分别保存；准确上游版本及基线提交待核实。

内置函数.py文件页最近修改时间为2025-09-22 23:36 +08:00，根README文件页为2025-09-24 15:53 +08:00。作者工作笔记、文件修改时间及准确首次公开日期分开记录。原仓页列33次提交、1分支、0标签和暂无发行版；汉源码独立版本编号待核实。

作者关注索引将liu-guanglin_admin的同名项目标为中源/汉源码的fork，按同一来源链处理。确切跨仓同步状态与完整继承链继续核实。

### 实际中文层与实现依据

固定cpython/Python/bltinmodule.c：
- 第3343—3397行显示builtin_methods表；
- 第3354行直接注册“设置断点”到builtin_breakpoint；
- 第3360、3366行直接注册“信息列表”“获取属性”；
- 第3376行将“迭代器”注册到builtin_iter；
- 第3381、3383、3385行注册“最大”“最小”“下个元素”；
- 第3397行将“局部字典”注册到builtin_vars；
- 第3413—3418行的builtinsmodule结构引用builtin_methods。

上述中文字符串属于内置方法注册。源码中其他映射如print→打印、pow→幂次方以宏使用和中文注释呈现；宏内部及完整对象方法注册链列为后续字段核验。

作者必读信息第34—75行提供内置函数映射；第77—100行说明Objects/unicodeobject.c的unicode_methods对应str方法别名，包括格式化、编码、替换、分隔、拼接、小写字母等。str对象方法.py的连续源码确实使用这些中文方法名。该文件第230—233行使用英文if搭配中文方法与打印调用，原文为：

```python
用户输入1 = "Python"
if 用户输入1.小写字母() == "python":
   打印("匹配成功！")
打印("-----------------")
```

代表性连续程序取内置函数.py第209—216行，共8行，原缩进3个空格：

```python
# 创建一个列表
列表1 = [1, 2, 3]
# 使用iter()函数获取迭代器
它 = 迭代器(列表1)
# 使用for循环遍历迭代器
for i in 它:
   打印(i)
打印("------------\n")
```

两个片段按固定页面LC行号读取textContent，保留标点和缩进。它们用于证明中文API使用和当前控制结构形态；执行效果待核实。

固定cpython/Lib/keyword.py共64行，开头明确注明由Grammar/python.gram生成；kwlist包含35项英文Python关键词，softkwlist为_、case、match、type。原例中for、if、def保留英文结构。当前分类以CPython中文内置函数／方法别名扩展记录，中文专用语法的原件和解析路径继续待核实。

### 许可与AI

固定cpython/LICENSE共277行，第62—70行说明PSF License Version 2、文档例程双许可PSF v2／Zero-Clause BSD及部分组件的独立许可。Gitee根级提示LICENSE声明缺口，CPython子树许可正文与汉源码新增改动的许可边界分别记录。

项目AI参与待核实。Gitee页面的AI队友属于平台通用入口；模型、工具、人机分工及源码生成比例需要作者专门材料。

### 访问限制与收束

commits/master历史列表转向登录页，读取止于公开状态。Grammar/python.gram已由固定Grammar目录定位，浏览器导航及随后DOM提取出现协议超时，文件内容待核实。研究转向已公开可读的Lib/keyword.py及连续原例，收束中文API分类。时间和许可证正文继续保留原始证据。

主要来源：
- 原作者仓库：https://gitee.com/liu-guanglin/lglCode
- 固定内置方法注册表：https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/cpython/Python/bltinmodule.c
- 固定作者工作笔记与映射说明：https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/%E5%BF%85%E8%AF%BB%E4%BF%A1%E6%81%AF.txt
- 固定中文API连续原例：https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/%E5%86%85%E7%BD%AE%E5%87%BD%E6%95%B0.py
- 固定字符串中文API例程：https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/str%E5%AF%B9%E8%B1%A1%E6%96%B9%E6%B3%95.py
- 固定Python关键字列表：https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/cpython/Lib/keyword.py
- 固定README与构建说明：https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/README.md
- 固定CPython子树与README版本：https://gitee.com/liu-guanglin/lglCode/tree/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/cpython
- 固定CPython许可正文：https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/cpython/LICENSE
- 作者关注索引的fork关系：https://gitee.com/liu-guanglin_admin/watched?sort=watches.created_at+desc

## 2. E#：本轮真正新发现的设计阶段候选

原仓：https://gitee.com/dcosa/esharp

当前固定快照：55503b2e623e3093d9c6423b63aa6b006adaaf32。
0.1.0-end.preview快照：c090f0d80ca5fb6855513b906cb6a321db52903c。

### 发现及身份

公开网页搜索定位DCOSA组织页，组织页直接链接E#、CH-VM和易深IDE。E#原仓README写基于CH-VM的中文编程语言，原仓提交与发行署名云之梦歌。组织页自述成立于2020-05-19，此日期仅用于组织背景。

当前头提交页面时间2023-06-02 19:46:11 +0800。原仓页列10次提交、1分支、1标签、1发行、0 Stars。首次公开日期、自然人姓名、团队分工及维护安排待核实。

### 中文规范与实现阶段

固定E#规范.md为464 Bytes，给出58项词表，类型和控制关键字包括字节型、整数型、文本型、如果、否则、循环、返回；声明包括变量、常量、类、模块、函数、过程、导入；另有中文逻辑和位运算词。

当前固定树中：
- src目录含main.c，文件页显示0 Bytes及空文件；
- test/main.c共6行，主体为int main(int argc, char *argv[]) { return 0; }；
- include目录含dtype.h，共220行，内容为C数据类型、平台和导出宏、字符串与容器结构等。

规范词表已经核实。连续E#程序、中文词法／语法前端及可执行调用链继续待核实。当前按中文关键词设计与运行平台原型处理，正式新增计数为0。

### 历史发行的重要边界

发行页0.1.0-end.preview显示2023-06-02 08:27，作者云之梦歌，提交c090f0d80ca5fb6855513b906cb6a321db52903c，说明为“结构重构备份”。

该固定旧树保留AsmCompiler、ESRuntime、ESLibraries/escore、ESIL.md、msvc等目录。README描述.esb二进制、.esl库以及导出_es_LibraryMain的DLL，并设计常量池、资源段、导入导出段和元数据段。读取旧AsmCompiler/main.c及旧test/main.c，二者均保留6行的C占位入口，返回0。

旧发行包含更丰富的运行平台目录，当前master处于不同结构。完整旧ESRuntime实现与CH-VM关系继续待核实；发行标签和设计目录按版本证据保存。

### 许可与AI

固定根LICENSE为LGPL Version 3完整165行，Gitee项目界面标LGPL-3.0。项目具体版权署名、组件许可范围及AI开发参与声明待核实。

主要来源：
- DCOSA组织原页：https://gitee.com/dcosa
- E#原仓与当前README：https://gitee.com/dcosa/esharp
- 固定58项中文词表：https://gitee.com/dcosa/esharp/blob/55503b2e623e3093d9c6423b63aa6b006adaaf32/E%23%E8%A7%84%E8%8C%83.md
- 当前空语言入口：https://gitee.com/dcosa/esharp/blob/55503b2e623e3093d9c6423b63aa6b006adaaf32/src/main.c
- 当前C测试占位入口：https://gitee.com/dcosa/esharp/blob/55503b2e623e3093d9c6423b63aa6b006adaaf32/test/main.c
- 当前C类型定义：https://gitee.com/dcosa/esharp/blob/55503b2e623e3093d9c6423b63aa6b006adaaf32/include/dtype.h
- 固定LGPLv3正文：https://gitee.com/dcosa/esharp/blob/55503b2e623e3093d9c6423b63aa6b006adaaf32/LICENSE
- 0.1.0-end.preview发行页：https://gitee.com/dcosa/esharp/releases/tag/0.1.0-end.preview
- 历史发行树与README设计：https://gitee.com/dcosa/esharp/tree/c090f0d80ca5fb6855513b906cb6a321db52903c
- 历史汇编器占位入口：https://gitee.com/dcosa/esharp/blob/c090f0d80ca5fb6855513b906cb6a321db52903c/AsmCompiler/main.c
- 历史测试占位入口：https://gitee.com/dcosa/esharp/blob/c090f0d80ca5fb6855513b906cb6a321db52903c/test/main.c

## 检索记录与风险

主要查询：
- "汉源码" "刘光林"
- "lglCode"
- site:gitee.com "中文编程语言" "微型"
- site:gitee.com "中文编程" "2025" "解释器"及已知对象排除词
- site:gitee.com "中文编程语言" "如果" "返回"
- site:gitee.com "编程语言" "中文关键字" "2026"
- site:gitee.com "中文编程语言" "轻量"
- site:gitee.com "中文" "语言" "解释器" "玩具"

搜索结果混入普通中文软件、仓库关注页、既有洛书和RexLang线索；相关结果按初筛背景保存。候选范围为汉源码和E#共2项。

风险：
- 中文API别名、中文关键词设计与完成的中文语法前端分别核验。
- 仓库目录和发行标签用于版本识别，运行效果继续待核实。
- 组织成立、文件修改、发行和项目首发时间分别记录。
- 原作者声明、C源码直接注册与运行结果采用不同证据层级。
- 搜索覆盖描述本轮查询范围，平台整体项目覆盖率待核实。
- 历史登录限制和浏览器协议超时各自记录，源码缺口按具体文件标注。


资料核验范围包括完整271行内置函数原例及58项E#规范词表。
