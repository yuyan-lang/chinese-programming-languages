# CN Language与CN_Interpreter定向研究

核验日期：2026-10-12（UTC）。百科基线574d50b435fe327f9111abf02c696344f62ea3ae，94语言／9内核。只读GitHub与普通网页研究；范围为Issue #3两组旧候选。

## 结果

CN Language具备原作者仓库、连续21行中文原例、字符串转译及Python exec实现链。建议一项收录，编号lang-095。完整条目含28项引用。CN_Interpreter保持中文语言构想待核状态。此批若合并，Issue #3可由11/19增至12/19组完成分类，余7组；百科95语言／9内核。

## 先读与去重

已读根AGENTS.md、基线data/languages.json、Issue #3正文及全部8条评论、第八轮与第二十轮日志；名称／别名／URL搜索显示现有94条内上述账号／项目匹配0条。原始Issue第六、七项对应本轮两组。写作用肯定事实陈述，资料缺口标待核。

- https://github.com/yuyan-lang/chinese-programming-languages/issues/3
- https://github.com/yuyan-lang/chinese-programming-languages/issues/3#issuecomment-6116655862
- https://github.com/yuyan-lang/chinese-programming-languages/blob/574d50b435fe327f9111abf02c696344f62ea3ae/research/2026-10-10/round-8-issue3.md
- https://github.com/yuyan-lang/chinese-programming-languages/blob/574d50b435fe327f9111abf02c696344f62ea3ae/research/2026-10-11/round-20.md

## CN Language关系链

1. heikeling/CN-Language，仓库ID561322911，账号ID110018283，fork=false。建库2022-11-03T12:53:04Z，根提交ad38c862e03692902e1aa65a95e7723446806612为12:53:05Z。六条保留提交均署名heikeling，当前main=6540faf32f98712931028a7014c5ea3c2eef0629（2022-11-20T04:56:56Z）。完整树24项，truncated=false，Releases空集合。
2. tomkiyang/CN-Language，仓库ID979920995，建库2025-05-08T09:25:43Z。API明确fork=true，parent/source均为heikeling/CN-Language。当前main与原仓同hash，完整树24项同内容。计为fork关系。
3. HeiKe-Tom/CN-Language，仓库ID741825989，账号ID140880011，fork=false。建库2024-01-11T07:32:07Z，根提交c0e9b5ac1c33fb347d7f0be5b90b0f9e95cbd024（当日07:33:15Z），八条提交，当前main=ae2fdc7cf47e83fca1f450012be590876a794764（2024-01-14T09:54:15Z）。完整树37项，truncated=false。源码位于CN-Language子目录。
4. 两仓对应路径20个blob相同，包括Cnexe.py、LICENSE、ku.py、main.cn、随机.py等。main.pyw均699行正文，逐行比较仅7行变化：作者联系信息两处、错误翻译URL变量大小写、启动请求地址、窗口标题、窗口大小与作者主页URL。中文转换与内嵌猜拳原例逐行一致。可将Chinese Code Studio按源码副本／同语言配套发行记载。
5. 账号ID和仓库ID分别保留；账号迁移、共同作者、授权沿革与自然人对应关系待核。作者私人联系字段仅用于比较，交付条目省去号码。

固定树：
- https://github.com/heikeling/CN-Language/tree/6540faf32f98712931028a7014c5ea3c2eef0629
- https://github.com/tomkiyang/CN-Language/tree/6540faf32f98712931028a7014c5ea3c2eef0629
- https://github.com/HeiKe-Tom/CN-Language/tree/ae2fdc7cf47e83fca1f450012be590876a794764

元数据：
- https://api.github.com/repos/heikeling/CN-Language
- https://api.github.com/repos/tomkiyang/CN-Language
- https://api.github.com/repos/HeiKe-Tom/CN-Language

### 中文原例与实现

主例原仓main.pyw第513—533行，cq函数传入code.insert的三引号字符串。去调用外壳保留完整连续21行、制表符和全角／半角标点。包含从／导入库、如果／否则如果、和、打印及询问。
https://github.com/heikeling/CN-Language/blob/6540faf32f98712931028a7014c5ea3c2eef0629/main.pyw#L513-L533

yx第165—170行从编辑器取文本，经code.txt读写进入codes；第172—243行顺序str.replace，第248—250行写new.py并exec。中文输入输出与类型函数在137—164行。F5的yxf5重复另一组转换和exec。Cnexe.py也读取code.txt并替换执行。编译exe按钮在394—400行复制Cnexe.exe和code.txt。随机.py包装random.randint。以上均为静态阅读事实。

重要边界：
- 条件循环分支检测“条件循环”后替换“弹出”为while。
- 替换对整段字符串进行；字面量与注释边界、复杂语义待核。
- 按钮与F5规则集合有差异，按钮另含列表、画布、监听。
- 计时结束点位于exec之前。
- 原仓main.pyw导入Wdata，完整树内依赖待补；2024副本含Wdata.py。
- 2024副本错误翻译函数定义大写URL，调用小写url；错误处理待核。
- main.cn UTF-8读取出现替代字符，主例采用UTF-8源码嵌入程序。
- 项目安装、执行、网络调用、发行二进制均保留独立验证状态。

### 版本与许可

原仓Releases空。2024副本有：
- v1.0.0：2024-01-12T07:25:51Z，标签2043485553dfae2d750ed9054ff7c28e22dcbe74。
- v1.0.1：2024-01-14T09:47:35Z，标签7ba2af7cc7dcf4599cd1ae2e3d3f85c1e047e72d；其发布标签与当前源码快照分别记录。发行说明自述从此版开始需要联网。
- 两版各有Portable.exe、Setup.exe及.zip资产，静态记录发行页即可；内容与运行待核。
- 原仓LICENSE与副本CN-Language/LICENSE blob=261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64，Apache 2.0全文，附录权利人／年份仍为占位符。原仓元数据Apache-2.0；副本根级license=null，文件位于子目录。新增文件、资产及依赖许可范围待核。
- AI开发参与待核。错误翻译接口的用途按源码记载。

## CN_Interpreter待核更新

2026-10-12复核：
- main保持4c07321166a4a697fe6c7ca3c717e7e07abca2fa。
- 完整树1项README.md，truncated=false，blob=c3f61d4f94d5b8cdf7aca61651dc0cce38bb5afb。
- 三条提交，根1c13f1e8d402645f69ee3c98fce48c3dac95c000（2025-05-06T06:21:11Z），最新2025-05-06T07:11:08Z。作者whitesnowmoon，建库同根提交时间。
- README阐述指令型／语境型／释义型设计方向；“机器开机”为设计讨论例句。
- 分支集合main，Releases空，许可元数据null。Git refs/tags端点返回404，标签状态仅记录此次读取结果。
- 正式语法规范、连续用户程序、解析执行实现、版本与许可正文继续待核。
- README提及未来AI指令场景；AI参与开发待核。

原始入口与固定证据：
- https://github.com/whitesnowmoon/CN_Interpreter
- https://github.com/whitesnowmoon/CN_Interpreter/blob/4c07321166a4a697fe6c7ca3c717e7e07abca2fa/README.md
- https://api.github.com/repos/whitesnowmoon/CN_Interpreter/git/trees/4c07321166a4a697fe6c7ca3c717e7e07abca2fa?recursive=1
- https://github.com/whitesnowmoon/CN_Interpreter/commit/1c13f1e8d402645f69ee3c98fce48c3dac95c000
- https://github.com/whitesnowmoon/CN_Interpreter/commit/4c07321166a4a697fe6c7ca3c717e7e07abca2fa
- https://api.github.com/repos/whitesnowmoon/CN_Interpreter
- https://api.github.com/repos/whitesnowmoon/CN_Interpreter/releases

## 检索与遗漏风险

02:29—02:32 UTC普通网页精确查询：
- "CN_Interpreter" "whitesnowmoon"
- "CN-Language" "HeiKe-Tom"
- "CN-Language" "tomkiyang"

搜索结果主要为无关词项，项目事实以GitHub原仓、完整树、固定文件、提交与发行为依据。原始中文代码与实现位于嵌套目录／IDE内嵌字符串，README单页不足以覆盖资料。heikeling仓库通过fork元数据确认原始来源，属于既有CN Language组的关系核验。这两组定向核验新增独立候选0项。

## 独立复核

已复核21行字符串提取、原仓与副本实现及7处差异、fork来源、许可、发行与编号。发布稿补明换行统一为LF及错误翻译函数所属副本。详见[复核记录](round-22-review.md)。


## 同批发现检索

2026-10-12 UTC通过公开搜索引擎查询Bilibili视频、中文技术社区及个人内核线索，侧重2024—2026：
- `site.bilibili.com/video "中文" "自制编程语言" "2026"`
- `site.bilibili.com/video "AI" "中文解释器"`
- `site.bilibili.com/video "自制内核" "2026"`
- `"嘉豪TV之ai自创编程语言"`
- `"TAOBOXOS" 内核`

### Tao范围核验

作者原帖 https://ruby-china.org/topics/44641 ，Patamon于2026-08-05介绍Ruby/Racc和Coding Agent生成parser.y。原仓 https://github.com/gotogems/taoism ，固定d5e5ad15b3526de7f1c6e1e1650a196acbb9187d，2026-08-06T15:28:54Z。

lexer.rb第3—21行定义17个英文关键词，第252—264行限定ASCII标识符；parser.y及site/src/pages/docs/syntax.mdx对应上述语法。本轮按英文关键词语言分类，中文语法目录收录计数0。
- https://github.com/gotogems/taoism/blob/d5e5ad15b3526de7f1c6e1e1650a196acbb9187d/lib/taoism/lexer.rb
- https://github.com/gotogems/taoism/blob/d5e5ad15b3526de7f1c6e1e1650a196acbb9187d/lib/taoism/parser.y

### B站标题级线索

索引 https://search.bilibili.com/all?keyword=%E7%BC%96%E7%A8%8B%EF%BC%9F 返回“嘉豪TV之ai自创编程语言”，上传者XXHZAXX，显示05-08、03:32。原BV、年份、语言名称、中文语法、实现与AI参与均待核。直接打开索引返回导航，标题与账号精确搜索仅得索引。

补查关键词："XXHZAXX" "编程语言"；"嘉豪TV" "ai" "编程"；"XXHZAXX" "自创"；"嘉豪TV之ai自创编程语言" "BV"；该标题及账号分别附site:bilibili.com/video/；"嘉豪" "自创编程语言"。该标题作为发现线索保留，正式目录计数0。

### 内核发现范围

TAOBOXOS在 https://post.smzdm.com/p/ad79d8zx/ 及 https://post.smzdm.com/p/arzr3xlg/ 的二手聚合资料中出现，原始发布及项目自身内核实现待核实。聚合描述仅作发现入口，内核目录收录计数0。MimicryOS与Causenix的归属定向复核另保存于research/2026-10-11/round-21-kernel-attribution.md。

上述检索结果混入站外结果、旧资料与AI聚合页面；B站原视频、简介、评论和低关注项目仍存在覆盖缺口。本轮定向核实CN Language1项，原CN_Interpreter与两项内核归属继续待核，标题级发现线索1项。
