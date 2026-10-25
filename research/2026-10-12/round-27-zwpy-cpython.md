# 52zwbc 中文 CPython 关联组核验

核验日期：2026-10-12 UTC。百科基线40962dd4adb9eeed2bc115966572c90ce3500a05，96语言／10内核，既有条目lang-059「zwpy（zw）」。本轮读取AGENTS.md、lang-059全文、Issue #22正文及全部7条评论、既有round7-issue3研究。全部为静态只读核验；本轮执行、安装、构建、测试数量均为0。

## 结论

两仓与zwpy已有明确的作者官网关联和一致的中文关键词表，可补强lang-059的关联实现资料。具体的zwpy发行阶段、.zw启动器和安装包来源对应仍为待核，保持一个关联候选组，语言总数保持96。

1. python313zw和python314zw安装成功页均直接链接https://www.52zwbc.com，并自述「52中文编程」「山东宁阳郭老师」。314另有「修改版本，添加了中文内置函数」说明。该直接链接强化同作者产品资料链。
2. 两仓Parser/pegen.c的35项硬关键字映射表逐项相同；全部35对均出现在zw固定README关键词表。匹配／情形两个软关键字也一致。该结果证明目标语法词表对应。
3. zw固定文档/官网为2026-09-10；两CPython仓库建立于2026-10-05／07。官网页面将下载称为「zwpy中文Python运行环境+VSCode插件」，提供zwpy2_2.exe和zwpy313_2_win7.exe。该页面未给两源码仓库、固定提交、发行标签或附件摘要对应。
4. 两CPython仓库各自从无父提交的根开始；检查到的main历史分别11及22条，二者及zw根提交之间的共享祖先证据为空。导入式历史足以解释未共享Git祖先；代码搬移方向和统一发行阶段仍待作者声明或包级映射。
5. 314精确上游来源已独立确认：中文仓库根提交与官方v3.14.8使用完全相同的Git tree SHA。313精确源码基线继续待核。

## 固定源码和日期

- 313本轮继续采用84fee06c5dd87bc5547d7c715a1e760dc107c720，2026-10-09T10:59:36Z，固定树5495项，truncated=false；当前main为d86f7f472d6158be356f6212f3f2ac655d8fc229，后4条提交说明涉及macOS构建流程，本轮未据此扩大语义核验范围。
- 314采用a14d42425a5f9c845555783e4ed1cadad7b7df43，2026-10-06T23:26:30Z，固定树5787项，truncated=false。
- zw采用36e929a0d4e868a8700f5ec5e7563b541c9518d4；官网采用c8deec64414b6bde6c56a3bb6e1f968895f4e4e0。zw树为2项；官网树为5项。
- 313根160c69ea1fa34727a3ff84eff162bb40fac28439，2026-10-07T01:12:33Z，初始提交已带中文改动。
- 314根6dfb550b45b6e47e4b35403565b2f428ca11541f，2026-10-05T12:47:34Z，自述「Python 3.14.8 source (from CPython v3.14.8, commit 8e6e75d)」。后继cf5b499e587443b700de0c935828776daf30fd39添加打印／如果。

## 源码入口

### 解析器

[313 pegen.c 158—225](https://github.com/52zwbc/python313zw/blob/84fee06c5dd87bc5547d7c715a1e760dc107c720/Parser/pegen.c#L158-L225)和[314 pegen.c 162—231](https://github.com/52zwbc/python314zw/blob/a14d42425a5f9c845555783e4ed1cadad7b7df43/Parser/pegen.c#L162-L231)的_get_keyword_or_name_type先匹配中文UTF-8字节与长度，再查英文KeywordToken，返回同一token类型。成员访问点号后中文名称保留NAME。35对硬关键字覆盖如果／否则如果／否则、遍历／循环条件、函数／类、导入／从、异常处理、逻辑、异步及真假空。

软关键字入口分别在[313 531—535](https://github.com/52zwbc/python313zw/blob/84fee06c5dd87bc5547d7c715a1e760dc107c720/Parser/pegen.c#L531-L535)与[314 537—541](https://github.com/52zwbc/python314zw/blob/a14d42425a5f9c845555783e4ed1cadad7b7df43/Parser/pegen.c#L537-L541)，匹配→match、情形→case。Grammar/python.gram及Lib/keyword.py保持英语词项；中文入口位于解析器token分类层。zw README 90—134包含同一组35+2映射，另列初始化和主程序保护惯用法。完整语义等价与全角标点支持继续待核。

### 内置与导入

[313 site.py 714](https://github.com/52zwbc/python313zw/blob/84fee06c5dd87bc5547d7c715a1e760dc107c720/Lib/site.py#L714)、[314 site.py 720](https://github.com/52zwbc/python314zw/blob/a14d42425a5f9c845555783e4ed1cadad7b7df43/Lib/site.py#L720)在site.main中导入_zh_builtins。该模块将中文别名注册到builtins，包装中文关键字参数，并提供初始化→__init__构造器适配。打印在bltinmodule.c的C内置表注册，313第3210行，314第3484行；有中文参数包装和文档。

314 [Lib/_zh_stdlib.py](https://github.com/52zwbc/python314zw/blob/a14d42425a5f9c845555783e4ed1cadad7b7df43/Lib/_zh_stdlib.py)在import后给常用英文标准库模块添加中文属性，install插入MetaPathFinder。313明确暂不加载_zh_stdlib，另有[Lib/_zh_builtins.py 209—239](https://github.com/52zwbc/python313zw/blob/84fee06c5dd87bc5547d7c715a1e760dc107c720/Lib/_zh_builtins.py#L209-L239)把import 库映射到Lib/ku.py，后者包装pip命令。本轮未执行这些命令。

PC/launcher.c与Modules/main.c的限定检查未发现zwpy名称或.zw专用启动器映射。该结果只覆盖所检查文件。

### 连续原例

[314 test_zh.py 1—24](https://github.com/52zwbc/python314zw/blob/a14d42425a5f9c845555783e4ed1cadad7b7df43/test_zh.py#L1-L24)是作者中文冒烟原例。连续原文中的首段：

```python
打印("你好，中文Python!")

如果 True:
    打印("如果 True 分支 OK")
else:
    打印("不应该到这里")
```

同文件另含elif、打印sep/end和中文如果三元表达式。313 test_zh.py沿用该原例并增加库导入断言。本轮按作者源码中的测试定义记录；运行通过情况待核。

## 明确官网链接与关系缺口

- [313 Default.wxl 109](https://github.com/52zwbc/python313zw/blob/84fee06c5dd87bc5547d7c715a1e760dc107c720/Tools/msi/bundle/Default.wxl#L109)及[314 Default.wxl 110—129](https://github.com/52zwbc/python314zw/blob/a14d42425a5f9c845555783e4ed1cadad7b7df43/Tools/msi/bundle/Default.wxl#L110-L129)是直接的产品内官网链接。此处作者自称郭老师；实名继续待核。
- 两仓Tools/msi/bundle/xcx.jpg共享blob bdcbf59767c955e2db907736bfc3dddb90c246cc，为额外共享安装资源证据。官网xcx.jpg为不同blob。
- [官网固定下载说明281—297](https://github.com/52zwbc/52zwbc.github.io/blob/c8deec64414b6bde6c56a3bb6e1f968895f4e4e0/index.html#L281-L297)与两个仓库发行资产名不同；官网资产未有可比摘要。作者站点的早期安装包与后来的源码发行之间仍缺桥接证据。
- 精确完成条件：取得作者明确说明哪个zwpy发行由这两库哪个commit构建，或取得插件／启动器源码中的明确运行时版本与分发引用，或取得官网安装包清单与发布摘要的一致映射。当前证据支持“同作者、官网直链、词表一致的关联实现”。

## CPython上游固定关系

[官方v3.14.8 tag对象](https://api.github.com/repos/python/cpython/git/tags/992560c2cc62d47b308cec662feb485456847931)指向8e6e75d9102e39bed2a2b279203a396741180f12，提交时间2026-09-30T17:55:09Z，tree为5c846838d075d0d44c37549e11cdc334fbef2054。

[314导入根提交](https://api.github.com/repos/52zwbc/python314zw/git/commits/6dfb550b45b6e47e4b35403565b2f428ca11541f)的tree也为5c846838d075d0d44c37549e11cdc334fbef2054。完全相同的Git tree提供原始文件快照一致证据；中文库从独立根导入该快照，再提交中文修改。

[官方v3.13.16 tag对象](https://api.github.com/repos/python/cpython/git/tags/3b55c23ff4a6aa32f77be661802a3978d7324f88)指向cbc944f4bc59639a444dd971c737788ba2283a91，tag时间2026-09-30T18:57:39Z。313中文库根已含定制代码；该官方标签存在与自标版本一致，精确初始源码来源尚缺基线对照。patches-win7/README声明使用PythonVista对应版本补丁，范围仅按原作者声明记录，未扩查第三方仓库。

## 发行与许可

- 313 v3.13.16-zh2及v3.13.16-win7-5均固定到84fee06…。前者2026-10-09T11:14:37Z发布，API当时显示102项附件；后者2026-10-09T11:17:24Z发布，2项附件。例：python-3.13.16-amd64v1.exe，API摘要sha256:2a1dc616f7535ed7afa127a7ad5ce8ef05e5be69b8aef074ee8cd5cf999ded92。
- 314 v3.14.8-zh8及v3.14.8-win7-3均固定到a14d424…。前者2026-10-06T23:44:05Z发布，API当时显示105项附件；后者2026-10-06T23:57:08Z发布，2项附件。附件列表记录到公开元数据；可用性、实际内容及与官网包的对应继续待核。
- 两仓README.rst与Include/patchlevel.h自标3.13.16／3.14.8。独立核验官方标签后，官方版本存在已经有来源；自定义中文发行仍按各自zh／win7标签记录。
- 两仓根LICENSE包含PSF License Version 2及历史许可条款。此事实适用于所见源码许可文本；zw/zwpy文档、配套插件和完整安装包的许可范围继续待核。
- Release列表与matching-refs/tags接口均可用；普通/tags接口返回404，本轮采用matching-refs明确核对，避免将404当成无标签。

## 产出与停止条件

建议只补强lang-059的implementation、relations、version、status、verification_notes与references，保留现有分类及原例。Issue #22的52zwbc组继续待核，计数保持8/10已分类、2组待核。

证据档案：zwpy-cpython-evidence.json包含限定源码全文、元数据、发行与上游证据；本文件给出可公开引用的固定链接。具体包级关系缺口已经确定，达到本轮有界研究停止条件。


## 检索与覆盖

本轮沿Issue22既有线索定向读取GitHub：52zwbc/python313zw、python314zw、zw、zwpy、52zwbc.github.io，以及python/cpython的两个指定上游标签和对应提交。重点版本范围2026年9—10月，核验日2026-10-12。名称排重采用zw、zwpy、zwpython、python313zw、python314zw；限定检索词包括_get_keyword_or_name_type、_zh_builtins、_zh_stdlib、.zw、zwpy和52zwbc.com。研究覆盖所列固定文件、保留提交和发行元数据；原始二进制附件、完整插件、站外发布及后续提交语义留有遗漏风险。

## 主审复核

主审独立读取314导入根、官方v3.14.8标签对象和目标commit，确认完整tree SHA一致。现有11项引用和原始中文主例逐项保留，新增18项引用，共29项；原95个其他语言条目保持原样。已有正式条目完善1项，新发现、新增正式语言与内核均为0，目录96语言／10内核。Issue22继续按8/10已分类、2组待核保存。

独立复核确认35+2词表、官网互链、发行与许可文本；“zw与zwpy两文档仓库”的发行状态与两CPython源码仓库发行状态分别表述。
