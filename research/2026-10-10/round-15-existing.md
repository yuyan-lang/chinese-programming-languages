# 第十五轮：文言与言序既有资料补证

核验日期：2026-10-10。基线：[757ddd0d875cb114b7261e389aa9a8a002f86c80](https://github.com/yuyan-lang/chinese-programming-languages/tree/757ddd0d875cb114b7261e389aa9a8a002f86c80)。本分项处理lang-003文言、lang-007言序两条既有记录。

## 本轮结果

- 完善已有语言2项。新发现、新增正式语言和新增内核均为0。
- 文言简介373字符、其中263个汉字；言序简介381字符、其中285个汉字。
- 结构化JSON原引用共2条，全部保留。原详情页另有3个独立引用URL并入结构化资料，原资料独立引用合计5条全部保留。
- 文言：原JSON1条与原页额外2条，共3条旧引用；新补14条，合计17条。
- 言序：原JSON1条与原页额外1条，共2条旧引用；新补22条，合计24条。
- 两项合计旧引用5条、新补36条、最终41条。以原JSON单独比较为保留2条、增加39条，其中3条属于既有网页引用的结构化归并。
- 原ID与名称保持；原字段继续存在，简介和状态按本轮证据扩写。豫言lang-001沿用基线。
- 固定中文原例分别为文言完整斐波那契11行、言序《初见》连续13行。原代码和旧字段逐字保存在下文。
- 范围为公开网页、GitHub文件、提交、标签及PR元数据静态阅读。项目安装、执行、编译、测试、自举、性能和发行制品运行继续待核实。

## 开轮与已有成果复用

已读取根AGENTS.md、data/languages.json、第十四轮报告、Issue #1及其14条评论。公开写作采用直接肯定陈述，缺口标为待核实。

[Issue #1](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)首条评论已记录[PR #2](https://github.com/yuyan-lang/chinese-programming-languages/pull/2)合并，补充文言、言序与段言详情页。其合并提交为397718f643b8906d399e1cb72e4fa62f64d9dad9，时间2026-10-09。读取两页确认已有语法介绍与短代码，JSON仍保留早期概要。分支集合有enrich-existing-language-pages-20261009；本轮检查开放PR返回0，main仍为给定基线。复用旧页的全部引用及已确认的语法方向，补齐其结构化字段、固定来源与历史。

原文言页独立引用URL：
1. https://github.com/wenyan-lang/wenyan
2. https://github.com/wenyan-lang/wenyan/wiki/Syntax-Cheatsheet
3. https://github.com/wenyan-lang/wenyan/blob/master/examples/fibonacci.wy

原言序页独立引用URL：
1. https://github.com/YanXuLang/yanxu
2. https://yanxu.dev/

## 原结构化对象

```json
[
  {
    "id": "lang-003",
    "name": "文言",
    "description": "采用古汉语风格语法的编程语言。",
    "references": [
      {
        "title": "参考资料",
        "url": "https://github.com/wenyan-lang/wenyan"
      }
    ],
    "status": "有源码"
  },
  {
    "id": "lang-007",
    "name": "言序",
    "description": "现代中文语法编程语言。",
    "references": [
      {
        "title": "参考资料",
        "url": "https://github.com/YanXuLang/yanxu"
      }
    ],
    "status": "待核实"
  }
]
```

## 文言：旧代码原值与新原例

旧代码来自[基线详情页](https://github.com/yuyan-lang/chinese-programming-languages/blob/757ddd0d875cb114b7261e389aa9a8a002f86c80/languages/lang-003.html)。原页说明为“示例摘自或改编自项目官方文档；请参阅下列来源核对对应版本。”原JSON没有code字段。

```text
吾有一數。曰三。名之曰「甲」。
為是「甲」遍。
    吾有一言。曰「「問天地好在。」」。書之。
云云。
```

核对固定README第28—31行可确认相同语句；旧页以四空格缩进，原README使用制表符。本轮展示递归完整文件并保留旧片段于此。

新原例：[examples/fibonacci.wy第1—11行](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/examples/fibonacci.wy#L1-L11)，blob为0236b22e3eff4fb0fd51a7f2c1a68b90c7454fbb。

```text
吾有一術。名之曰「斐波那契」。欲行是術。必先得一數。曰「甲」。乃行是術曰。
	若「甲」等於零者乃得零也
	若「甲」等於一者乃得一也
	減「甲」以一。減「甲」以二。名之曰「乙」。曰「丙」。
	施「斐波那契」於「乙」。名之曰「丁」。
	施「斐波那契」於「丙」。名之曰「戊」。
	加「丁」以「戊」。名之曰「己」。
	乃得「己」。
是謂「斐波那契」之術也。

施「斐波那契」於十二。書之。
```

连续11行含原有空行，函数体前导字符为U+0009；源文件末尾无换行。数据保存原文，不转换简繁与标点。

### 证据分层与版本

- 作者署名：固定LICENSE为Lingdong Huang，package.json为LingDong。作者作品页搜索索引列TypeScript／Dec 2019；当前主页直接抓取只返回页面导航，因此年月同时由Git根历史佐证。
- 历史：GitHub仓库created_at为2019-12-08T20:21:32Z；Git根d58e01c1fcb7ec477345dda88f3686c3502cbe43作者与提交者时间为同日20:22:01Z。查询2019-12-16之前取得38条，parents可追至空数组。根树6项，含example.txt、example.js、parser.js、汉字转换代码。根example.txt有简体中文函数与阶乘／快排例程。首次对外公开时刻继续待核。
- 固定master为97f0a4b8c5a815467c5c2cac08215d722efde208（2023-01-17T00:00:53Z），树191项且truncated=false；仓库pushed_at为2023-10-20T13:39:33Z。分支提交时间、任意引用推送时间与维护计划分别记录。
- 实现：parser.ts第732—787行完整呈现宏展开、分词、ASC、可选strict类型检查、目标代码生成和导入模块递归；transpilers/index.ts注册js/py/rb；execute.ts内置求值路径支持js。源码中三个后端分别存在。编译目标、内置执行目标和独立执行结果分别保存。
- 版本：package.json为0.4.0；src/version.ts读取该版本。GitHub latest为正式v0.3.4，published_at为2020-07-29T05:11:41Z；npm最新版本继续待核。CHANGELOG v0.3.0说明迁移TypeScript。
- 许可：当前MIT署名2019-present Lingdong Huang。根树没有LICENSE；早期许可时间链继续核实。
- AI：读取主要元数据、README、源码结构并检索AI、作者与项目组合；作者其他AI艺术作品及媒体的NLP形容按各自语境处理。文言开发中的模型和工具参与待核实。
- 关系：README明确关联wyg、wenyanizer、第三方JVM编译器与在线IDE。文言Perl沿用目录独立条目的作者和实现边界。

## 言序：旧代码原值与新原例

旧代码来自[基线详情页](https://github.com/yuyan-lang/chinese-programming-languages/blob/757ddd0d875cb114b7261e389aa9a8a002f86c80/languages/lang-007.html)，原JSON没有code字段。原页同样注明“摘自或改编自项目官方文档”。

```text
法 问候（姓名：文）：文 则
    归 「你好，」加 姓名 加「！」；
终

言 问候（「言序」）；
```

该五行可与固定README第31—35行逐字对应。本轮采用源文件中的递归原例，旧例全文继续保存。

新原例：[examples/初见.yx第1—13行](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/examples/%E5%88%9D%E8%A7%81.yx#L1-L13)。

```text
# 言序的第一卷
令 姓名 为 「言序」；
言 「你好，」 加 姓名；

法 斐波那契（数）则
    若 数 小于等于 1 则
        归 数；
    终
    归 斐波那契（数 减 1） 加 斐波那契（数 减 2）；
终

言 「斐波那契之第十数为：」；
言 斐波那契（10）；
```

连续13行保留注释、空行、四空格缩进和全角标点；源文件尾部另有空行。新code精确对应这13行。

### 证据分层与版本

- 作者：根提交和当前提交署名刘秀，PR #8/#9创建账号LiuXiu233。作者博客文章以“我是刘秀”开始并描述创造言序；搜索索引可读，直接文章读取返回Cache miss。博客首页本次可读并列2026-07-14及文章标题；文章URL路径为2026/07/13，正文/索引日期单独记录。
- 历史：当前核心仓库created_at为2026-07-13T18:14:20Z。三页Git历史取得203条，根10174f4ec04629f89adc85467df4281a80aadbcd时间17:49:56Z、标题“拆分言序语言核心”、parents为空；该根Cargo版本0.3.0-alpha.1。拆分意味着需要继续追踪前身资料，当前根日期用于核心仓库历史。
- 关系：根README与Cargo引用YanXuLang/language及总控仓库；下一提交4f90ff09ecdc894123220fb09450936d0cb0760d标题“调整语言主仓库地址”，链接切为YanXuLang/yanxu。当前README分别列言包、言窗、文档、VS Code扩展、言枢和言据；同名排版引擎toolsvip.cn按其服务定位另行排重。
- 源码：lexer.rs第277—329行包含令/定/置/为/言/若/则/终/法/归等实际词元映射；lib.rs parse_named调用扫描、解析、名称解析后得到语句；main.rs第243—305行分别调用Interpreter和字节码编译／Vm；bytecode.rs定义独立指令与Chunk。运行效果继续待核。
- 规范：公开规范1包含词法、对象、模块、执行器及公共格式。执行一致性和权限约束为规范要求，独立安全审计和完整实现验证继续待核。
- 当前快照：5ccfd2503693d0ab7d2ca27dcca525d219e2b16d；作者时间2026-07-20T09:47:05Z，提交者时间09:55:05Z；树376项、truncated=false。pushed_at为2026-08-01T09:40:12Z。
- 发行：v1.1.20正式Release published_at为2026-07-20T10:20:31Z。附注标签7f3433393858bfc40d6784c566ea98d693a943a1时间10:05:43Z，其object指向当前SHA。Cargo、状态页及Release一致。Release说明1.1.18与1.1.19的稳定发行缺口。
- AI：203条提交文本检索AI／人工智能／大模型／Codex／Claude／ChatGPT／GPT-／Co-authored-by，命中两条codex合并记录。PR #8来自codex/yanxu-1-1-7-gui，合并5539eed9ae49bb3afa2c3a3123c478889b66144b保留[codex]标题；PR #9标题带[codex]，合并7d0e8b2b7bdd1125a7d271bce690ab854c79c31c。命名线索支持记录公开开发标记；具体模型、工具交互、文件贡献与比例继续待核。
- 许可：固定MIT，版权2026 Yanxu contributors；依赖及生态仓库许可独立核验。

## 检索日志、时窗与访问结果

核验窗口2026-10-10 21:29—21:35 UTC；来源历史范围文言2019—2023、言序2026-07—2026-10。全网查询未加发布日期过滤以保留早期来源。

1. GitHub百科：AGENTS.md、languages.json、round-14.md、Issue #1及评论、PR #2、两详情页；开放PR查询、全部分支；提交关键词“文言 言序”。确认现有成果与基线。
2. GitHub原仓：README、整树、主分支提交、根提交、包元数据、LICENSE、版本与Release、标签、例程、词表及执行入口；具体文件/行号见条目references。
3. 文言公开查询：“wenyan Lingdong Huang 2019 creator”；“site:lingdong.works 黃令東”；“wenyan-lang AI Lingdong development”。检索到作者作品页与第三方报道，技术结论以原仓为准。
4. 言序公开查询：“言序 YanXuLang 作者 AI 编程语言”；“site:blog.liuxiu.us 言序 AI”；“YanXuLang Codex”；“site:github.com/YanXuLang/yanxu Codex Claude”；“site:yanxu.dev 言序 作者”。检索到作者文章、同名排版引擎与无关工具；按仓库、作者和实现识别对象。
5. GitHub提交查询：“initial”“初始化”“AI”；空查询配升序返回空集，改读分页与截止日期API；历史结论采用完整返回的Git记录。
6. GitHubcontributors端点被工具以INVALID_ARGUMENT拒绝，停止该端点；作者资料沿用已经获取的LICENSE、提交、PR及作者文章。贡献者完整名单继续待核。
7. 文言根提交README和LICENSE返回404，根树确认该阶段只有六项文件。历史程序与JavaScript解析器可见；资料按实有文件保存。
8. yanxu.dev直接抓取返回不可访问；作者文章与About直接访问返回Cache miss，博客首页与搜索索引可读。当前站点可用性、文章原始时区和早期网页归档继续待核。

## 遗漏风险与下一步

- 公开Git提交时间、仓库创建时间与真实首发时间具有不同含义；言序根提交是拆分后的历史起点。
- 文言中文README存在时差；npm发布版本和独立IDE仓库的当前状态继续核实。
- 原作者自然人中文姓名、跨平台身份与完整贡献者名单需要署名互链；本条采用已核实署名。
- Codex分支和PR标记属于开发记录线索，具体AI参与需要更明确原始材料。
- 源码存在、规范规定、作者测试报告、Release上传和独立运行分别记录；执行与性能结论继续待核。
- 多目标文言后端的语义一致性、言序双执行器及权限契约完整性需要独立验证。
- 同名语言、排版服务、早期移仓地址与周边工具以仓库和职责分别识别。
- 本轮原例已固定提交与行号；保留旧例与旧字段，便于后续审阅和追溯。

## 引用索引

### 文言（17条）

1. [参考资料](https://github.com/wenyan-lang/wenyan)
2. [官方语法速查表（原详情页引用）](https://github.com/wenyan-lang/wenyan/wiki/Syntax-Cheatsheet)
3. [官方示例：斐波那契（原详情页引用）](https://github.com/wenyan-lang/wenyan/blob/master/examples/fibonacci.wy)
4. [固定README：语言定位、三目标与工具生态](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/README.md#L23-L121)
5. [固定连续原例：斐波那契完整11行](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/examples/fibonacci.wy#L1-L11)
6. [固定中文关键字与类型、控制及模块词表](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/src/keywords.ts#L3-L119)
7. [固定编译链：宏、词元、抽象语法链、类型检查与转译](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/src/parser.ts#L670-L798)
8. [固定JavaScript、Python、Ruby后端注册](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/src/transpilers/index.ts#L1-L13)
9. [固定JavaScript执行接口与求值](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/src/execute.ts#L4-L60)
10. [固定包元数据：作者、0.4.0与MIT](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/package.json#L1-L12)
11. [固定MIT许可与作者署名](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/LICENSE#L1-L21)
12. [Git历史根提交：2019-12-08](https://github.com/wenyan-lang/wenyan/commit/d58e01c1fcb7ec477345dda88f3686c3502cbe43)
13. [历史根提交中文例程](https://github.com/wenyan-lang/wenyan/blob/d58e01c1fcb7ec477345dda88f3686c3502cbe43/example.txt)
14. [固定变更记录：v0.3.0迁移TypeScript](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/CHANGELOG.md#L38-L67)
15. [GitHub正式发行v0.3.4](https://github.com/wenyan-lang/wenyan/releases/tag/v0.3.4)
16. [原作者作品页：文言与2019年12月](https://lingdong.works/)
17. [固定中文README及资料更新提示](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/README.zh-Hans.md#L1-L11)

### 言序（24条）

1. [参考资料](https://github.com/YanXuLang/yanxu)
2. [项目网站（原详情页引用）](https://yanxu.dev/)
3. [固定README：语言、工具链与生态](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/README.md#L1-L164)
4. [固定连续中文原例：《初见》第1—13行](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/examples/%E5%88%9D%E8%A7%81.yx#L1-L13)
5. [固定中文关键字词法入口](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/src/lexer.rs#L277-L329)
6. [固定解析、名称解析与树解释入口](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/src/lib.rs#L71-L124)
7. [固定命令行树解释、类型检查与字节码VM入口](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/src/main.rs#L243-L305)
8. [固定字节码、指令与Chunk结构](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/src/bytecode.rs#L20-L145)
9. [固定VM执行入口](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/src/vm.rs#L874-L905)
10. [固定Cargo版本、Rust要求和许可](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/Cargo.toml#L1-L13)
11. [固定版本与公共格式状态](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/docs/project/status.md#L1-L45)
12. [固定MIT许可证](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/LICENSE#L1-L21)
13. [正式发行v1.1.20](https://github.com/YanXuLang/yanxu/releases/tag/v1.1.20)
14. [v1.1.20附注标签及对应提交](https://api.github.com/repos/YanXuLang/yanxu/git/tags/7f3433393858bfc40d6784c566ea98d693a943a1)
15. [当前核心仓库根提交：拆分言序语言核心](https://github.com/YanXuLang/yanxu/commit/10174f4ec04629f89adc85467df4281a80aadbcd)
16. [固定早期Cargo：0.3.0-alpha.1与language地址](https://github.com/YanXuLang/yanxu/blob/10174f4ec04629f89adc85467df4281a80aadbcd/Cargo.toml#L1-L12)
17. [固定拆分时README与生态关系](https://github.com/YanXuLang/yanxu/blob/10174f4ec04629f89adc85467df4281a80aadbcd/README.md)
18. [固定主仓库地址调整后的README](https://github.com/YanXuLang/yanxu/blob/4f90ff09ecdc894123220fb09450936d0cb0760d/README.md)
19. [原作者文章：我为什么要创造一门中文编程语言](https://blog.liuxiu.us/2026/07/13/why-i-created-yanxu-chinese-programming-language/)
20. [公开GUI基础设施PR及codex分支](https://github.com/YanXuLang/yanxu/pull/8)
21. [公开[codex]锁文件维护PR](https://github.com/YanXuLang/yanxu/pull/9)
22. [固定语言规范：词法与文法](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/spec/language/v1/lexical-and-grammar.md)
23. [固定语言规范：执行器与兼容性](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/spec/language/v1/execution-and-compatibility.md)
24. [固定语言规范1入口](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/spec/language/v1/README.md)

