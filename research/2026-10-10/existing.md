# 第二轮已有条目核验日志

核验日期：2026-10-10 UTC。仅对 lang-004 凹语言、lang-005 洛书、lang-013 中蟒提案。没有修改远端仓库，没有安装、编译、运行任何项目代码。没有研究豫言或访问 yuyan-cloud。

## 可直接采用的结论

1. 凹语言有独立中文语法模式，证据超过“支持中文变量名”：.wz 文件分派到 w2parser；中文 token 表含引入、函数、如果、循环、完毕；官方固定提交有连续中文程序。中文和英文模式属于同一工具链，不应重复计语言。
2. 洛书原 GitHub 链接是可读的 2022 年源码快照，不能作当前实现依据。官方 Gitee README 已说明 C99 嵌入式解释器；本次所能核对的程序和 C++ 编译器/LVM必须注明历史版本。当前 Gitee源码正文未能读取，所以不宣称新版兼容旧示例。
3. 中蟒原 SourceForge 项目资料尚可读，确认中文化的对象包括保留关键字与内置类型；但官网与源代码浏览失败。本轮只更新能由原始公告确认的历史事实，不提供虚构代码或伪造 commit。这条仍是部分完成。

## 起始数据与输出

- 原始数据：https://github.com/yuyan-lang/chinese-programming-languages/blob/main/data/languages.json
- 读取到文件 blob SHA：0bc05f2923b04a3698f4194bedca2e8a17f37165
- 保留三个原 id 与名称及原参考链接，完善全文对象。
- 更新对象：round2-existing.json（UTF-8 JSON 数组）。
- 所有 description 约 260—285 中文字符。未为了凑字数补无来源的技术结论。
- 中蟒没有 code/code_source 属性，code_context 和 verification_notes 明示缺口；不要把缺口写成已验证示例。

## 凹语言：证据链

固定仓库提交：
https://github.com/wa-lang/wa/commit/68289efad08785938a1ea5225c23d0fcbf5bb9cb
master 提交时间：2026-04-27T08:18:19Z。
仓库创建：2022-07-20T03:22:58Z；pushed_at：2026-04-30T10:43:49Z；archived=false。
pushed_at 不当作默认分支最近提交日期。

读取文件（均为上述 commit）：
- README.md：明确 GitCode 为 canonical repository、GitHub 为 mirror；英文/中文双前端架构。
- README-zh.md：中文例子、工程试用定位、贡献者；“例子: 凹语言(中文版)”代码块作为 code。
- internal/parser/interface.go：ParseFile 对 .wz 调用 w2parser.ParseFile；ParseDir 拒绝同一包混合 .wa/.wz。
- internal/token/const_wz.go：独立中文关键字、类型、内置操作常量。
- waroot/hello.wz：额外实读的中文样例，含如果/空/整型等，未用于拼接示例。
- internal/version/version.go：const Version = "v1.9.0"。
- waroot/changelog.md：v0.6.0（2023-04-13）增加中文语法；v1.3.0（2025-11-01）中文版正式上线；v1.7.0原生龙芯64；v1.8.0原生X64。
- GitHub releases/latest：返回v1.8.0、published_at 2026-03-02T09:49:41Z。未把开发分支v1.9.0当成正式发行。
- 源码树已读取，truncated=false；只检查路径及相关文件，未执行。

原始官网补充：
- https://wa-lang.org/community/ ：2019立项、2022年7月开源、工程试用。
- https://wa-lang.org/smalltalk/st0089.html ：开发组2025-10-23自述中文语法沿革；提到2022开源时已内置中文关键字，区别于2025新版。
- https://wa-lang.org/smalltalk/st0031.html ：官方站刊载由柴树杉、丁尔男等署名的开源周年材料，说明创始成员与来源。
- https://wa-lang.org/smalltalk/st0032.html ：官方周年直播逐字稿补充作者身份和前端源自Go的背景。
- https://wa-lang.org/talks/wa-gallery/notes.html ：柴树杉自称联合发起人。

代码摘录：
- README-zh.md第129—135行。
- 完整连续7行程序；以原文本直接抽取，未翻译关键词、未拼接其他段落，制表符保留。
- 固定链接：https://github.com/wa-lang/wa/blob/68289efad08785938a1ea5225c23d0fcbf5bb9cb/README-zh.md

注意边界：
- “全自主研发”是项目对其代码生成器/运行时的说明，不是整个仓库无第三方代码的证明；parser/interface.go保留Go Authors版权。
- 官网/README架构图不代表每个CPU后端已独立运行验证；README特别写RISC-V未真机测试。
- 未实读GitCode最新提交，不把GitHub日期扩成整个项目最后活动。
- 更早项目发起叙述有2018年底/2019立项之别，正文用官网简史的2019立项，不发明日级首发。

## 洛书：证据链

固定仓库提交：
https://github.com/chen-chaochen/losulang/commit/3510b5ee974461533bc325202ea587090e52c934
master 提交时间：2022-09-25T09:31:17Z；署名陈朝臣。
仓库创建：2022-09-27T09:17:03Z；pushed_at：2022-09-27T09:18:35Z；archived=false。
不能将仓库迁入GitHub的创建日当首发日。

读取文件（均为上述 commit）：
- README.md：C++11历史实现、洛书指令语言/语法前端、Gitee lpk链接、1.0 LTS和河图。
- 洛书示例代码/你好世界.losu：中文加载、导入、对象声明、方法定义，原始示例。
- src/bin/Compiler/losuc_main.cpp：lsc实例和compile入口；该文件中文提示存在编码乱码，所以不从乱码猜测语义。
- src/bin/Compiler/losuc_compiler.cpp：lsc声明。
- src/bin/LVM/losu.cpp：ls_vm、.lsc路径、hostfile；原始版权自称Chen-chaochen。
- 源码树完整返回，含release/losu1.0和release/losu1.0.1；只读取必要内容。

官方后续资料：
- https://gitee.com/chen-chaochen/lpk 可读。
  README说明C99可编译内核，面向Windows/Linux/RTOS，链接官网losu.tech，并链接24.1.4阶段版本公告。
  当前页面含MIT版权2020—2024；不得以版权开始年当首发。
  页面展示head链接6e71f05d4eb4c5e69cab67abea06d893f4497ac5及preversion树873134edec6bacb1b5fdd75a954caf0af7a3cef1；相应正文无法读取，未把这两个hash作为代码来源。
- https://gitee.com/chen-chaochen/lpk/releases/tag/1.6.8 可读。
  发布者陈朝臣，页面日期2023-08-05 00:22（时区不明），版本1.6.8、代号破晓。示例使用英文def/import，未拿来声称中文版关键字。
- https://losu.tech/ 和 https://losu.tech/wiki/readme.md 返回502。
- Gitee raw readme、blob readme、losu及losu_core目录、head commit与preversion树读取失败（Cache miss或不可访问）。
- 未绕过登录或验证码，未下载发行包。

代码摘录：
- 洛书示例代码/你好世界.losu第19—22行，连续方法定义。
- 原始CRLF保留；依赖同文件前面的加载/导入/实例化；不是自足完整程序，也不是经新版验证的示例。
- https://github.com/chen-chaochen/losulang/blob/3510b5ee974461533bc325202ea587090e52c934/%E6%B4%9B%E4%B9%A6%E7%A4%BA%E4%BE%8B%E4%BB%A3%E7%A0%81/%E4%BD%A0%E5%A5%BD%E4%B8%96%E7%95%8C.losu

待核实：
首发日期、当前完整中文语法、C++到C99迁移过程、当前最新稳定版本、历史/新版兼容性。不能将河图全部语法自动当成洛书本体语法，也不另行录入本轮研究范围之外的新条目。

## 中蟒：证据链与未完成项

原SourceForge：
- https://sourceforge.net/projects/chinesepython/ ：中文化关键字和内置类型；维护账号glace；注册2002-04-10；分类Interpreters；语言C/Python；Beta；页面Last Update 2013-04-02。
- https://sourceforge.net/p/chinesepython/news/ ：
  - 2002-05-06迁到cosoft.org.cn的开发者公告。
  - 2002-06-11“chinesepython 3.14 released.”列翻译、名字统一、字符串hash等变更。
  - 2002-08-06取得chinesepython.org域名，网站将迁移；CVS/下载留SourceForge。
  - 2003-06-28 Windows补丁0-3.14，修复IDLE与小问题。
  - 2003-07-24发布2.1.3-0.4，改用Python2.1.3基线并改进GB编码。
- https://sourceforge.net/projects/chinesepython/files/chinesepython/ ：
  0-3（2002-04-21）、0-3.1（2002-04-28）、0-3.14（2002-06-11）、2.1.3-0.4（2003-07-24）目录。
  不同缓存页的“Download Latest Version”提示不一致，因此以版本目录及作者公告确认历史版本，不抄该自动提示。
- http://www.chinesepython.org/english/english.html 超时。
- http://chinesepython.sourceforge.net/ 不可访问。
- SourceForge Code入口、glace个人页、具体新闻与发行版本子目录读取失败。

代码缺口：
没有取得原始源码文件、可验证commit或源码包校验值；不引用转载的“回答=读入/如/写”示例，也不把近年ChinesePython同名仓库作为中蟒。保留具体拼写与实施机制待核验。
实名不得从零散第三方叙述猜测；只记录原项目维护账号glace。

## 搜索日志（用于发现原始入口，搜索片段不自动作为证据）

执行过的查询：
- 中蟒 ChinesePython 劉鑫
- 中蟒 chinese python 2002 作者
- "中蟒" "作者"
- "ChinesePython" sourceforge
- "ChinesePython" "website"
- site:wa-lang.org "柴树杉" "2019"
- site:wa-lang.org "中文版" "2025" "11"
- site:chinesepython.org "中蟒"
- site:github.com "chinesepython2.1.3"
- "洛书" "github" "losu_core"
- site:losu.tech "中文" "若"
- "ChinesePython" "glace" "name"
- "中蟒" "劉"
- "chinesepython.org" "glace"
- "ChinesePython" "Cheng"
- "中蟒" "2002" "開發"
- "chinesepython.sourceforge.net"

其中针对姓名的查询没有取得原作者身份依据，完全未用于author字段。
检索出现的百科、新闻转载、聚合站、现代同名项目仅是搜索结果，没有作为本轮事实来源。
GitHub仓库搜索chinesepython、losu、洛书未定位新的可证实原始镜像；没有将那些同名结果纳入。
尝试GitHub fetch搜索仓库REST URL两次，因工具仅允许特定搜索endpoint返回INVALID_ARGUMENT；改用正式search_repositories只读工具，非权限规避。

## 交付前QA

- 三个对象只保留lang-004/lang-005/lang-013；没有覆盖其他条目。
- 所有确定代码逐字来自已读取的固定提交文件。
- 所有日期区分项目首发、仓库创建、提交、推送及网页“更新”。
- 当前与历史实现状态区分，未声称性能或测试已实测。
- 中蟒是部分补充，必须在汇总中明确尚缺原始代码证据。

