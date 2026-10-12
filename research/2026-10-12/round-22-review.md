# CN Language独立静态复核

日期：2026-10-12 UTC。结论：通过，支持按一项语言／Python中文关键词转译层收录。主要事实通过核验；两项措辞完善已纳入发布稿。

## 范围与方法

独立读取条目草稿、研究报告、百科基线574d50b435fe327f9111abf02c696344f62ea3ae的AGENTS.md与data/languages.json、Issue #3正文及全部8条评论；通过GitHub只读接口重新取得固定源码、完整树、提交、仓库元数据、发行和标签。候选源码只作文本读取与字符比较；候选安装、执行和远程写入均为0。

## 已通过的重点核验

1. **21行中文原例**：heikeling固定6540faf32f98712931028a7014c5ea3c2eef0629的main.pyw第513—533行，去code.insert及三引号外壳、将CRLF规范为LF后，与JSON的code字段逐字符相等。共21行，9个制表符缩进行，中文／英文标点保留。HeiKe-Tom固定ae2fdc7cf47e83fca1f450012be590876a794764的CN-Language/main.pyw相同原例逐行相等。
2. **转换与执行链**：第165—170行读取编辑器文本并经code.txt重新读入codes；第172—243行逐项codes.replace；第248—250行写new.py并exec(codes)。第137—164行确有中文Python包装函数。F5入口另存一组转换并exec；按钮和菜单绑定yx，F5绑定yxf5。Cnexe.py另读code.txt并在第111行exec(codes)。随机.py调用random.randint。研究中的转译层分类成立。
3. **边界说明**：条件循环分支检测“条件循环”而替换“弹出”为while、按钮路径额外列表／画布／监听规则、exec前计时终点、原仓导入Wdata及依赖文件待补，以及副本translator的URL/url大小写差异均由源码复核。运行状态继续待独立核验。
4. **源码关系**：原仓完整树24项、副本37项，二者truncated=false。副本CN-Language/前缀下恰有20个与原仓同路径对应、同SHA的blob，含LICENSE、Cnexe.py、ku.py、随机.py及main.cn。main.pyw各699行正文，恰7处逐行差异：两处联系字段、URL变量大小写、启动请求地址、窗口标题、窗口大小、作者主页地址。内嵌猜拳程序及中文转换链逐行一致。
5. **fork关系**：tomkiyang元数据fork=true，parent与source均为heikeling/CN-Language，main提交为6540faf32f98712931028a7014c5ea3c2eef0629。HeiKe-Tom元数据fork=false；两个维护账号ID不同。条目将技术同源与自然人／授权关系分别记载，证据边界妥当。
6. **日期与提交署名**：原仓六条提交作者名均为heikeling；根提交ad38c862e03692902e1aa65a95e7723446806612记录2022-11-03T12:53:05Z，最新固定提交记录2022-11-20T04:56:56Z。副本八条提交，根提交c0e9b5ac1c33fb347d7f0be5b90b0f9e95cbd024记录2024-01-11T07:33:15Z，最新记录2024-01-14T09:54:15Z。创建日期与首次公开日区分合适。
7. **2024发行和标签**：v1.0.0 published_at为2024-01-12T07:25:51Z，标签为commit 2043485553dfae2d750ed9054ff7c28e22dcbe74；v1.0.1 published_at为2024-01-14T09:47:35Z，标签为commit 7ba2af7cc7dcf4599cd1ae2e3d3f85c1e047e72d。各有Portable.exe、Setup.exe、zip三件资产。v1.0.1发行正文明确要求联网。当前源码快照与发行标签分开写正确，二进制内容和行为待核。
8. **许可证**：固定原仓根LICENSE为Apache License Version 2.0全文，附录保留Copyright [yyyy] [name of copyright owner]。副本CN-Language/LICENSE与其同blob 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64。原仓元数据Apache-2.0、副本根级license=null属实。新增文件、发行资产和依赖范围继续逐项待核的措辞准确；占位符是许可全文附录模板，许可适用范围按文件与作者说明核实。
9. **基线与计数**：固定百科data/languages.json有94项，lang-095空闲。精确候选名称与账号的既有条目匹配数为0。宽泛不区分大小写子串检索会命中lang-072的“PyCn Language”，该名称归属不同项目。Issue最新评论明确11/19组、余8组及94语言／9内核；完成CN Language这一组后12/19、余7组、95语言的算术正确。
10. **CN_Interpreter分类**：固定树确为单项README.md，truncated=false，blob c3f61d4f94d5b8cdf7aca61651dc0cce38bb5afb。固定README为指令／语境／释义设计讨论，包含“机器开机”讨论句；三条提交及首末提交时间与研究稿一致。保留构想待核、继续寻找正式规范／用户程序／实现的分类合理。

## 已采用的完善

- code_context补充“换行统一为LF”，明确提取变换；原代码保持一致。
- verification_notes明确为“HeiKe-Tom副本的错误翻译函数”。原仓使用小写url，副本改成大写URL后仍用小写url。

## 继续待核

首次公开日、三个账号的自然人关系、账号迁移／授权沿革、AI开发参与、完整运行表现、网络服务可用性、打包资产内容、独立语言语义版本与各资产许可适用范围继续待核。结论范围为上述静态证据。

## 主要一手证据

- https://github.com/yuyan-lang/chinese-programming-languages/blob/574d50b435fe327f9111abf02c696344f62ea3ae/AGENTS.md
- https://github.com/yuyan-lang/chinese-programming-languages/blob/574d50b435fe327f9111abf02c696344f62ea3ae/data/languages.json
- https://github.com/yuyan-lang/chinese-programming-languages/issues/3#issuecomment-6116655862
- https://github.com/heikeling/CN-Language/blob/6540faf32f98712931028a7014c5ea3c2eef0629/main.pyw#L513-L533
- https://github.com/heikeling/CN-Language/blob/6540faf32f98712931028a7014c5ea3c2eef0629/main.pyw#L165-L250
- https://github.com/HeiKe-Tom/CN-Language/blob/ae2fdc7cf47e83fca1f450012be590876a794764/CN-Language/main.pyw
- https://api.github.com/repos/heikeling/CN-Language/git/trees/6540faf32f98712931028a7014c5ea3c2eef0629?recursive=1
- https://api.github.com/repos/HeiKe-Tom/CN-Language/git/trees/ae2fdc7cf47e83fca1f450012be590876a794764?recursive=1
- https://api.github.com/repos/tomkiyang/CN-Language
- https://api.github.com/repos/tomkiyang/CN-Language/branches/main
- https://api.github.com/repos/HeiKe-Tom/CN-Language/releases
- https://api.github.com/repos/HeiKe-Tom/CN-Language/git/refs/tags
- https://github.com/heikeling/CN-Language/blob/6540faf32f98712931028a7014c5ea3c2eef0629/LICENSE
- https://github.com/whitesnowmoon/CN_Interpreter/blob/4c07321166a4a697fe6c7ca3c717e7e07abca2fa/README.md
