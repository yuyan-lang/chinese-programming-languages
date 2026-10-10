# 周蟒与草蟒资料核验

核验日期：2026-10-10（UTC）。本轮完善 lang-014 周蟒与 lang-015 草蟒，采用原作者文档、代码和发行资料。运行核验为待核实项。

## 周蟒：来源链

### 原作者及迁移链

原汇总入口：https://github.com/program-in-chinese/overview
其周蟒链接指向Google Code Archive。
作者现存仓库：https://github.com/gasolin/zhpy
README明确写明Migrated from code.google.com/p/zhpy。

源码固定提交：
https://github.com/gasolin/zhpy/commit/f4d932a5ab810158ef4e4113df337cbf7d83817a
提交时间：2020-02-27T09:11:33Z。
提交内容：合并README示例文本修正。
仓库创建：2015-08-08T12:08:11Z；推送：2020-02-27T09:11:35Z；archived=false。
来源：https://api.github.com/repos/gasolin/zhpy
源码树完整返回，truncated=false。

官方文档固定wiki分支提交：
https://github.com/gasolin/zhpy/commit/88e11bf44394260e35c2739ed7e01d3181cb639d
时间：2015-08-08T12:11:07Z。
历史与命名：
https://github.com/gasolin/zhpy/blob/88e11bf44394260e35c2739ed7e01d3181cb639d/AboutZhpy.md

AboutZhpy记载：
- 2006-12-22的python-cn讨论引出HYRY中文字串替换脚本。
- gasolin将该脚本视为0.1原型。
- 2007-08-09发布0.2，加入内建繁简关键字和可安装工具。
- 中文名周蟒来自zhpy读音，命名说明明确提及中蟒。
- 历史实现采用pyparsing转换后由Python执行。
原型的独立公开日期仍待核实；2006-12-22仅作为讨论日期记录。

### 作者、版本与实现

以下路径均相对于源码固定提交f4d932a5ab810158ef4e4113df337cbf7d83817a：
- zhpy2/AUTHORS.txt：Fred Lin、HERY、Jiahwa Huang、renhbo。
- zhpy2/zhpy/release.py：author Fred Lin、version 1.7.4、Python 2使用说明。
- zhpy3/release.py：version 3.0.0a1，明确zhpy3为zhpy后继路线。
- CHANGELOG.txt：0.2日期2007-08-09；0.2从HYRY脚本重构；1.1加入由Python生成繁简中文源码的命令。
- zhpy2/zhpy/zhpy.py：pyparsing词语识别、关键字查表、中文标识符编码、convertor、zh_exec及try_run中的exec。
- zhpy2/zhpy/plugcn.py第34—93行：定义、导入、返回、如果、取、在、当等简体词条。
- zhpy3/core.py：tokenize.generate_tokens及NAME词元转换。
- zhpy3/twpy.py：untokenize、compile、runpy执行流程。
- zhpy3/examples/hello/hello.twpy：另有面向Python 3的带括号印出示例，只作两路线核对。

AUTHORS的HERY与历史文档及源码中的HYRY存在拼写差异，条目按来源说明。

发行记录：
- https://pypi.org/project/zhpy/ ：0.2为2007-08-09；1.7.4为2015-10-23，列Python 2要求。
- https://pypi.org/project/zhpy3/ ：3.0.0a1为2011-06-25，标Alpha。
- https://api.github.com/repos/gasolin/zhpy/releases ：空数组。

PyPI日期与源码版本同时核对。仓库创建日期按迁移时间记录；当前维护计划与现代环境兼容性为待核实。

### 原文程序

https://github.com/gasolin/zhpy/blob/f4d932a5ab810158ef4e4113df337cbf7d83817a/zhpy2/examples/hello/hello.twpy#L3-L7

第3—7行连续摘录，包含中文函数定义、循环与调用。
保留原始3格和7格缩进。
文件blob SHA：69ddc37a87c8a90cb2129e7529706c800929c12e。
条目的code直接由已读取文件截取；字符串结尾匹配检查通过。
该示例属于zhpy2历史路线，执行验证为待核实。

## 草蟒：来源链

### 原作者与项目入口

原汇总入口：https://github.com/yiung/china-programming-languages
其草蟒链接指向：
https://gitee.com/laowu2019_admin/cpython

作者主页：
https://gitee.com/laowu2019_admin
公开简介自称草蟒（Python汉化版）中文编程语言开发者，显示名称草蟒老吴。
原目录中的实名吴胜金属于发现线索；本轮原作者材料仅证实草蟒老吴及Laowu Grasspy署名，实名列待核实。

当前核验源码分支：
https://gitee.com/laowu2019_admin/cpython/tree/zwpython3.10
分支头：aa81cfdecfe8d93b58c2942ec13a8bba1908a5ef。
页面末次提交说明为调整随机范围数参数。
页面时间元素title：2022-06-06 12:07:02 +0800，换算UTC为2022-06-06T04:07:02Z。
上述日期为该分支头提交日期。

### 中文版本与实际语法

中文说明：
https://gitee.com/laowu2019_admin/cpython/blob/zwpython3.10/README.zh.md
所见文件末次提交链接：
https://gitee.com/laowu2019_admin/cpython/commit/63df03cbc19df16b86c56211874f795887360dc0

已读取事实：
- 标题草蟒（Python中文版）3.10.1。
- Windows+Visual Studio构建说明。
- 作者自述在统信UOS家庭版编译成功。
- Linux说明记录unicodedata.so构建顺序问题及准备方法。
- macOS部分为作者提供的构建建议，作者说明自己缺少Mac设备。正文将macOS实际支持列为待核实。
- 说明提供关键字、内置函数等定制入口。

语法文件：
https://gitee.com/laowu2019_admin/cpython/blob/zwpython3.10/Grammar/python.gram
文件末次提交链接：
https://gitee.com/laowu2019_admin/cpython/commit/87c1395dc3d9ed9e22a9e201d4b3ed6dc07fd633
提交说明：语法汉化。
浏览器读取pre.textContent，共1063行。

关键定位：
- 第70—88行：返回、导入、套路、如果、类、取、只要等语句分派。
- 第138行：import/导入对应_PyAST_Import。
- 第182行：while/只要对应_PyAST_While。
- 第186—188行：for/取及in/于循环规则。
- 第392行：return/返回对应_PyAST_Return。
- 第404—408行：def/套路函数规则。
这些事实确认中文控制结构进入CPython语法与AST构造层。

C实现目录：
https://gitee.com/laowu2019_admin/cpython/tree/zwpython3.10/Parser
可见parser.c、pegen.c、tokenizer.c等文件。
parser.c页面显示1.43MB及同名语法汉化提交，正文因文件大小而折叠。正文实现结论以已完整读取的PEG规则和中文构建说明为证据。

本轮引用Gitee可读分支链接，记录所见分支头与文件末次提交号。固定提交页面内容复核为待核实。

### 历史版本

https://gitee.com/laowu2019_admin/grasspy380
README记3.8.0 take 4源码及基于Python 3.8.0。
项目简介明确该仓库为存档状态，3.10.x长期维护版本及其他版本资料见作者名下相应仓库。
此说明用于解释3.8.0与后续cpython中文分支的项目关系。

### 中文库与原文程序

https://pypi.org/project/grasspy-wordcloud/
作者署名Laowu Grasspy，维护账号laowu2020。
Homepage链接到：
https://gitee.com/laowu2019_admin/zwwordcloud
版本0.0.1，PyPI日期2022-04-17，Requires Python >=3.10。
“使用说明”提供导入结巴、导入词云、中文字符串分词及词云对象操作。
条目代码选取该代码块开头六行连续原文，保留原有空行和标点。
该片段是分词准备部分，依赖草蟒与配套中文库；运行结果待核实。
代码来源为作者发布说明，源码包的本地内容核验属于后续工作。
PyPI公开列出的源包SHA256：
177051086a60cfc3f984aa6c12546a5f9fe68fd0d3f31d6595fbfe01e20e5acc
该校验值仅记录页面公布内容。

https://pypi.org/project/grasspy-jieba/
作者、维护账号及Gitee归属一致；说明给出中文导入示例。
0.0.1为2022-04-16，0.0.2为2022-04-17。

https://pypi.org/project/grasspy-bs4
作者Laowu Grasspy、维护账号laowu2020。
0.1.4112发布于2023-04-06。
此日期用于证明配套库的发布活动，语言内核的版本与维护状态单独记录。

作者Gitee主页列出autopunc：
用于中文输入法下将用户输入的中文标点自动调整为英文标点。
因此它属于编辑器辅助组件，相关名称统一记入生态关系说明。

### 早期公开视频

https://www.bilibili.com/video/BV1GJ411J7Df/
标题：草蟒(Python汉化版)中文编程入门视频。
发布账号：laowu2017；页面标记原创，简介介绍Python汉化的草蟒。
页面显示：2020-01-15 00:35:58。
meta video:release_date：2020-01-14T16:35:58.000Z。
以北京时间2020-01-15说明至少已存在公开介绍；首发日期仍为待核实。
本轮核验标题、简介、原创标记与日期；原文程序采用PyPI文本来源。

## 获取情况与资料边界

- GitHub接口读取周蟒源码与官方文档成功。
- 网页检索工具读取Gitee中文README与子目录返回不可访问；云端浏览器能正常只读访问上述中文README、PEG文件、主页、分支日期和作者页。
- Gitee分支头commit详情页转到登录页；公开分支首页时间提示仍可读取，登录步骤留空。
- 草蟒网站源码库docsite目录显示“内容可能含有违规信息”；该目录的受限内容保留待核实。
- https://pypi.org/project/grasspy-modules/ 在云端浏览器明确返回404。
- 原官网域名由历史README识别，当前站点内容与所有权保留待核实，条目使用已核验的原作者仓库和PyPI资料。
- 发现过GitHub laowu2019/cpython，这是python/cpython的fork，所读GitHub分支列表仅有上游分支。Gitee已核实的中文源码是本轮实现依据。
- 百科、聚合列表及转载用作入口发现。技术结论来自作者源码、官方历史文档与作者发布包说明。
- 中文样例、实现路径、发行记录均为静态核验。首发缺口、当前维护计划、环境兼容性与执行结果分别明示。

## 检索方法、关键词与时间范围

检索平台：通用网页搜索及页面读取、GitHub仓库搜索与文件接口、Gitee公开网页、PyPI作者发布页面、Bilibili公开页面。Gitee与Bilibili的网页工具结果不完整时，使用云端浏览器只读核对公开页面。

本轮检索执行日期为2026-10-10 UTC。查询未设发布日期过滤，目的是同时覆盖项目早期资料及现存资料。最终采用的时间证据范围：周蟒原型讨论始于2006年底，0.2发布于2007年，发行记录到2015年，所读仓库头到2020年；草蟒已核验的公开视频为2020年，内核分支头为2022年，配套库发行记录到2023年。该范围表示所取证据的日期，项目更早与更晚活动均可能存在。

真实使用过的通用网页查询包括：
- 周蟒 语言 源码 中文 Python
- 草蟒 语言 作者 源码 Python
- 草蟒 grasspy 吴胜金 官网
- 草蟒 grasspy gitee github laowu
- "草蟒" "官网"
- "草蟒" "吴胜金"
- "草蟒" "grasspy.com"
- "草蟒" "编程" "吴胜金"
- "grasspy" "官网"
- "grasspy" github
- "草蟒" 编程 语言
- "grasspy" "中文"
- "草蟒" site:oschina.net/news
- "草蟒" "http"
- "草蟒" "www" "官网"
- "grasspy" "README.zh.md"
- grasspy.org
- grasspy.cn
- 草蟒 官网 3.10
- "grasspy.cn" python
- "草蟒" "grasspy.cn"
- "草蟒" "README.zh"
- 草蟒 site:gitee.com/laowu2019_admin
- grasspy-modules pypi 2019
- grasspy 草蟒 教程
- site:zhpy.blogspot.com "中蟒"
- site:gitee.com/laowu2019_admin "吴胜金"
- site:pypi.org/project/grasspy-modules "2020"

真实使用过的GitHub仓库查询：
- zhpy
- grasspy
- 草蟒
- cpython user:laowu2019
- user:laowu2019

资料覆盖与遗漏风险：
- 周蟒原Google Code入口由原目录及作者README确认；本轮采用作者迁移至GitHub的源码和wiki。原Google Code各时期tag、发行包及讨论档案的完整覆盖仍待核实。0.2发布与0.1原型分开表述。
- zhpy.blogspot.com的年度归档检索曾返回内容片段，直接页面读取出现Cache miss；相关技术与日期结论以已读作者仓库和PyPI记录为依据。更早讨论线程本轮只通过作者历史文档定位，独立读取待核实。
- 草蟒旧官网域名由作者README确认。本轮原官网当前内容和历史网页存档缺少可用原证，因此首发日、长期维护承诺延续情况及最新版均保留待核实。
- Gitee公开分支及文件页可读，固定commit详情页转到登录页，固定commit的blob网页工具读取失败。正文明确使用分支链接及当次可见commit元数据；分支内容今后可能变化。
- 草蟒网站源码库docsite目录有平台限制提示，相关内容核验停留在限制处。公开内核仓库与PyPI包形成独立证据链。
- PyPI所读页面只覆盖选定配套库，整个草蟒生态的最新活动仍可能存在其他发布入口。库版本与内核版本分别记录。
- 通用搜索结果包含同名无关项目，中文名称与grasspy短词也会触发近似词结果；原作者归属、项目说明及实际中文代码用于筛选。
- 语言运行、安装包完整性、构建可复现性和现代平台兼容性均属于后续核验范围。


