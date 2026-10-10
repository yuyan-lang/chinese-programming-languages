# 第七轮：文语与灵语既有条目复核

核验日期：2026-10-10（UTC）。资料库起点为697f78bd2d10a85a0c0c8cce9444bf03bdbf415a。起始读取根AGENTS.md、data/languages.json中的lang-019／lang-020、对应两张HTML页面及round-6.md。

本组完善已有条目2项，新增项目0项。两项简介分别为341和369个字符。保留原有全部6条参考链接，补充具体实现、连续原例、原始元数据、作者署名、版本、发行和许可。研究采用普通网页及GitHub只读接口；交付内容为资料对象与本日志。

## 一、文语 lang-019

### 固定来源与原始元数据

[仓库元数据](https://api.github.com/repos/bikthh/wenyu)本轮返回：

- full_name：bikthh/wenyu
- description：全新中文编程语言，对标go语言
- default_branch：main；language：JavaScript
- fork：false；archived：false；stargazers_count：1
- created_at：2026-07-14T07:47:51Z
- pushed_at：2026-07-26T06:22:33Z
- updated_at：2026-08-21T01:59:50Z
- license：null

[main引用](https://api.github.com/repos/bikthh/wenyu/git/refs/heads/main)仍指向旧核验提交c550aa8b80e6682914164d89b497c05f9e3d760b，继续采用该快照。[核验提交](https://github.com/bikthh/wenyu/commit/c550aa8b80e6682914164d89b497c05f9e3d760b)署名孙川，作者时间为2026-07-15T04:28:56Z、提交者时间为04:41:50Z。最后推送时间与源码提交时间分别记录。

[现存根提交](https://github.com/bikthh/wenyu/commit/bbeaab28b54cf6fe836379950aed7f9a6abbd781)的parents数组为空，署名sunchuan，作者与提交者时间均为2026-07-14T09:14:44Z，消息使用“文语 v3.0”。本轮完整提交集合返回8条，包含孙川署名及Gitee提交者记录。仓库账号bikthh与提交姓名对应关系、Gitee原始仓库同源关系及首次对外公开时点待核实。

### 版本、发行和许可

- [README](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/README.md)标题为v3.1。
- [package.json](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/package.json)的version为3.0.0，bin入口为launcher.js。
- [main.js](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/main.js#L16-L63)中的VERSION为3.0.0；[launcher.js](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/launcher.js#L59-L61)输出v3.0。
- [GitHub Releases](https://api.github.com/repos/bikthh/wenyu/releases)与[标签引用集合](https://api.github.com/repos/bikthh/wenyu/git/matching-refs/tags)均返回空数组。正式发行物待核实。
- README第182—184行声明MIT License。[固定递归树](https://api.github.com/repos/bikthh/wenyu/git/trees/c550aa8b80e6682914164d89b497c05f9e3d760b?recursive=1)返回完整列表。独立许可证正文和版权授权范围待补核实；元数据license=null与README声明分别保留。

### 实现链与宣传边界

1. [main.js第30—55行](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/main.js#L30-L55)建立Lexer和Parser，调用parseProgram，编译为CodeObject，再await VM.run。launcher.js第79—95行采用同一链路。evaluator.js作为另一组求值源码保存；默认入口采用Compiler／VM。
2. [lexer.js第126—145行](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/lexer.js#L126-L145)先读取完整标识符，再调用lookupKeyword精确查询。[token.js](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/token.js)保存关键字表。README架构图的“Trie最长匹配”与当前实现的对应性待核实。
3. [parser.js](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/parser.js)登记前缀／中缀表达式函数，并按优先级循环解析；[compiler.js](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/compiler.js)生成指令、常量及名称；[VM第212—235行](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/vm.js#L212-L235)按调用帧取指并等待Promise。main.js注释中的TypeChecker阶段与实际runSource调用路径分别识别。
4. [channel.js](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/channel.js)以buffer、senders、receivers数组和Promise实现缓冲与等待，select先尝试就绪项，再用Promise.race等待，并设30秒超时；中文发送、接收、关闭方法位于第211—220行。compiler.js第311—363行生成SELECT_WAIT；vm.js第469—543行接入Channel.select。这些是通道及选择语句的具体静态路径。
5. 启动链路待核实点：token.js定义SPAWN并映射“启动”；vm.js第420—427行包含OP.SPAWN到spawn的分派。parser.js及compiler.js全文的SPAWN字符串命中数均为0。[coroutine.js第151—179行](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/coroutine.js#L151-L179)以setImmediate调度，第170行调用ready.vm._doCallWithEnv；vm.js全文该方法名命中数为0。公开稿保留通道、选择及调度源码事实，并将完整启动接入列为待核实。
6. [VM第749—783行](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/vm.js#L749-L783)把AI映射至stdlib/ai.js并包装JS导出函数。[stdlib/ai.js](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/stdlib/ai.js)导入Node http／https，以httpRequest和httpRequestStream发请求，chat分别选择OpenAI兼容、Anthropic messages和本地Ollama chat。默认服务商为Agnes，AI_API_KEY用于Agnes；其他服务商另读相应环境变量或设置密钥接口。图像及向量采用OpenAI兼容路径。模型字符串、服务商名称和“AI原生”按源码配置或设计描述记录；实际模型、接口兼容及服务效果待核实。

### 连续中文原例

采用[examples/fibonacci.wy第4—9行](https://github.com/bikthh/wenyu/blob/c550aa8b80e6682914164d89b497c05f9e3d760b/examples/fibonacci.wy#L4-L9)。code与返回源码的连续子串相符，保留缩进和换行。这是完整的递归函数定义，展示“函数”“如果”“返回”；调用语句位于原文件后段。旧README AI示例来源链接完整保留。研究阶段为静态原文核对。

### 同源和设计关系

README明确描述Go风格并发与Python风格简洁。文语有自己的JavaScript编译链，文语和文言分别按各自仓库记录。源码继承、兼容性、.wy后缀设计关系及Gitee对应仓库继续待核实。

## 二、灵语 lang-020

### 固定来源与原始元数据

[仓库元数据](https://api.github.com/repos/jzm3/lingyu)本轮返回：

- full_name：jzm3/lingyu
- description：lingyu 灵语 · 中文编程语言 — 关键字/内置/模块/方法全中文，token 级脂译为真 Python，跑在 CPython 上，100% 兼容 Python 3.x
- default_branch：main；language：Python
- fork：false；archived：false；stargazers_count：0
- created_at：2026-09-02T02:24:37Z
- pushed_at：2026-09-02T04:46:12Z
- updated_at：2026-09-02T04:45:49Z
- license.key：agpl-3.0；license.spdx_id：AGPL-3.0

[main引用](https://api.github.com/repos/jzm3/lingyu/git/refs/heads/main)仍为旧快照fc24eeb21478bf60bf2184c8db02446c473b7980。[该提交](https://github.com/jzm3/lingyu/commit/fc24eeb21478bf60bf2184c8db02446c473b7980)的parents数组为空，署名jzm，作者及提交者时间均为2026-09-02T04:45:29Z。README和源码版权署名Copyright (C) 2026 jzm，与Git提交署名相互支持。更早公开记录待核实。

### 发行、工具版本和许可

[正式发行v1.0.0](https://github.com/jzm3/lingyu/releases/tag/v1.0.0)由jzm3发布，draft=false、prerelease=false，published_at为2026-09-02T08:17:14Z，updated_at为08:30:17Z。附件名称及元数据：

- lingyu_Desktop_Studio-setup-windows-64x.exe；application/x-msdownload；170795175字节。
- lingyu_Desktop_Studio_No_installation_required-windows-64x.zip；application/x-zip-compressed；254488420字节。

[附注标签833d3bef](https://api.github.com/repos/jzm3/lingyu/git/tags/833d3bef1ca4a6ceedbb701fba4e142d467ab60c)的tagger为jzm，时间2026-09-02T04:46:07Z，目标为同一fc24eeb2提交。README、[__init__.py](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/__init__.py)和[pyproject.toml](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/pyproject.toml)均为1.0.0；README的桌面工作室v2按工具版本说明记录。

[LICENSE](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/LICENSE)为GNU AGPL Version 3正文。源码SPDX为AGPL-3.0，pyproject.toml的license.text为AGPL-3.0-or-later，两处原始写法均保留。Python要求以pyproject.toml的>=3.11为准。

### token转译、字符串和库映射边界

1. [__main__.py](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/__main__.py)处理源码、文件、标准输入、REPL和导出选项。[compiler.py第98—101行](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/compiler.py#L98-L101)调用translate再compile；第17—37行临时绑定主模块并exec；第240—292行处理.灵文件、*_gen.py及缓存。
2. [translate.py第71—257行](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/translate.py#L71-L257)对纯ASCII源直接返回，其余调用tokenize.generate_tokens。全角归一化限定NAME／NUMBER／OP／ERRORTOKEN，普通字符串和注释保持内容。替换按原行列回填，保留行结构。
3. [f-string辅助函数第302—396行](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/translate.py#L302-L396)处理普通引号f-string花括号中的表达式；表达式按NAME词元替换，字符串词元保留。第388—389行对三引号形式返回None。公开稿将普通字符串保留和f-string辅助翻译分别表达；复杂嵌套及Python版本差异的实际效果待核实。
4. [keywords.py](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/keywords.py)分列KEYWORDS、DUNDERS、DUNDER_METHODS、BUILTINS、MODULES、MODULES_MEMBERS及METHODS。MODULES只在导入语境映射，例如“导入 数学”按规则建立import math as 数学形式的中文绑定。已知模块点访问查该模块成员表，其他名称查合并表和唯一成员表。GLOBAL_MEMBERS按中文名跨表出现次数筛选；方法表含追加、值列表、大写、读、写等。
5. translate.py第83—90及261—299行以显式导入检测控制“参数”到argv的映射。名称转换采用词表和有限上下文状态；任意名称、作用域和第三方API的完整兼容性继续逐项核实。
6. [importer.py](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/importer.py)为.灵文件注册finder／loader，读取源文件并translate、compile、exec。[cnlib.py第260—329行](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/cnlib.py#L260-L329)识别LIB_CN中文库名，用importlib装载相应模块，复制命名空间并恢复包装模块身份，再按词表getattr／setattr添加存在的中文属性。[i18n.py](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/lingyu/i18n.py)提供类属性别名注入及对象代理。覆盖范围以词表和实际模块／类为界。
7. README的“100%兼容”、测试通过数量和约1.0x性能为作者说明。独立运行、性能、第三方包版本适配和桌面附件效果属于后续验证范围。

### 连续中文原例

采用[README第52—55行](https://github.com/jzm3/lingyu/blob/fc24eeb21478bf60bf2184c8db02446c473b7980/README.md#L52-L55)，补齐旧条目摘录后面的递归返回分支。code为README原文连续子串，相同函数也见examples/hello.灵。原例展示中文定义、条件、返回及递归；本轮为静态原文核对。

### 同源关系

灵语复用Python标准库tokenize、compile／exec和importlib。灵库、桌面工作室位于同仓库。README及发行页均指向pylingyu.com；本轮直接读取官网返回访问错误，官网内容及在线运行效果待核实。与灵码、其他同名项目的作者和源码关系继续待核实。

## 三、检索与访问记录

- 时间：2026-10-10 17:32—17:38 UTC，普通网页和GitHub只读资料。
- GitHub覆盖：仓库元数据、固定README、递归树、原始源码、提交集合、根提交、分支引用、发行集合、标签引用及附注标签对象。
- 搜索词：“文语” “bikthh” “孙川”；“文语” “gitee.com” “WenYu”；“灵语” “jzm” “pylingyu.com”。本轮查询均返回空结果，相关同源关系维持待核实。
- 通用GitHub抓取工具对/repos/.../tags返回INVALID_ARGUMENT；受支持的git/matching-refs/tags只读接口取得标签引用，作为接口路径适配记录。
- 官网https://pylingyu.com的公开网页读取返回访问错误。
- 两段中文代码通过原文连续子串核对；原ID及原参考链接完整保留，新增code_context与仓库时间字段。
- 所有功能判断来自静态源文件和公开元数据。构建、安装、项目测试、二进制执行、桌面操作和外部AI服务请求属于后续独立验证范围。

## 四、建议汇入范围

资料对象用于更新data/languages.json的lang-019和lang-020，再按现有模板同步两张详情页。目录条目数保持原值。豫言排除约束保持。参考总数为文语17项、灵语16项。

