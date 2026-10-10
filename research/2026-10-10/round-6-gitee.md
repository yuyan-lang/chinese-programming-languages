# 第六轮：Gitee／GitCode 三项核验

核验日期：2026-10-10（UTC）。核验窗口约 17:00—17:08。

## 范围与结果

- 基线：先读目标仓库 AGENTS.md、data/languages.json 与 Issue #3 及两条进度评论。目录共51项；Issue原19项中 CP语言、coCN、Atlanage、Citric设计已完成分类收录，余15项。
- 防重：核对51项名称、别名、仓库地址，CNSH、kaisen-wang/dao、衍真三个候选与目录匹配结果为空；“道”额外采用作者限定名称。
- 本轮聚焦：CNSH、道、衍真，共3项。交付2项完整无ID条目、1项待核实记录。
- 研究方式：公开网页、GitHub只读接口和云浏览器；以源代码静态阅读及原始连续中文例程为依据。运行结果、性能和完整高级特性覆盖采用待核实状态。
- 本轮范围遵守豫言排除要求。

## 道：Gitee原始线索经同源GitHub补齐

原始线索：https://gitee.com/kaisen-wang

1. 原作者页显示 Carson、账号 kaisen-wang，并有“道-中文编程语言”项目卡，链接 https://gitee.com/kaisen-wang/dao。
2. Gitee项目显示97次提交，最新完整SHA为 e00a6f4c5e0f67409676ba8f33ef06e737d5c49d，时间属性为2026-07-19 15:38:18 +0800。
3. GitHub同名库 https://github.com/kaisen-wang/dao 的默认分支最新SHA完全相同。GitHub元数据 fork=false，创建时间2026-07-01T06:53:56Z；本轮据跨平台相同提交与标签原始链接合并为一个项目。
4. GitHub递归树368项、truncated=false；默认分支提交列表97项。最早条目 ce196f18011db76c653df9af7b4f3f720c1433ba 的父列表为空，时间2026-02-08T08:34:32Z，仅有文档.md，已读开头的“道（dao）”综合研究报告。
5. v0.1.0 注释标签对象 91123ff7f277f4c612694acfbdfb810f069162e4 的时间为2026-07-01T02:10:18Z，指向60512207b88747542c7618d9c48fdb5c486ee4f8。标签说明直接链接 Gitee v0.1.0 提交历史。包内版本0.1.0；作者署名由LICENSE的Carson与包内“道语言项目组”分别记录。
6. 中文连续原例：源码/examples/斐波那契.道 第3—13行。核查 tokens.py、lexer/readers.py 的KEYWORDS读取、parser/modules/control_flow.py、main.py 和 interpreter/statements/executor.py 第313—440行，形成关键词→解析→求值路径。
7. bytecode/compiler.py 与 vm/core.py 的相关源码可读。JIT _specialize 复制CodeObject指令和常量，条目明确当前行为；优化效果、机器码生成和四范式完整覆盖采用待核实状态。
8. GitHub通用 /tags URL由接口拒绝为不支持路径；随后使用受支持的 /git/refs/tags 和 /git/tags/{sha} 读取公开Git标签。GitHub Releases结果为空。Gitee作者动态显示2026-07-01推送v0.1.0标签。

主要固定来源：
- https://github.com/kaisen-wang/dao/blob/e00a6f4c5e0f67409676ba8f33ef06e737d5c49d/源码/examples/斐波那契.道#L3-L13
- https://github.com/kaisen-wang/dao/blob/e00a6f4c5e0f67409676ba8f33ef06e737d5c49d/源码/main.py
- https://github.com/kaisen-wang/dao/blob/e00a6f4c5e0f67409676ba8f33ef06e737d5c49d/源码/dao/jit/compiler.py
- https://api.github.com/repos/kaisen-wang/dao/git/tags/91123ff7f277f4c612694acfbdfb810f069162e4

## CNSH：固定Gitee源码及v2.2.0发行

原始线索：
- https://gitee.com/uid9622/longhun-cnsh
- https://gitcode.com/UID9622/longhun-cnsh

1. 常规网页抓取对原库返回不可读；云浏览器可以读取Gitee主页、目录和固定blob。
2. 当前main完整SHA为95ef57360c6226f7020cd27f100c4c98fa982775；主页时间属性为2026-10-07 10:20:35 +0800；主页显示42次提交。
3. 原始连续中文代码来自固定 examples/fib.cnsh 第5—12行。头部2026-06-29属于作者代码注记，首次公开日期采用待核实状态。
4. 已读固定 tokens.py、parser.py、cnsh_v21/__init__.py、toolchain.py、pyproject.toml 和README。关键词映射、函数/条件/返回递归下降解析、可选严格类型检查及Interpreter.run入口可直接引用。
5. 解释器正文 interpreter.py 的固定blob页面显示“内容可能含有违规信息”，本轮在此停止对该文件的读取。该文件内部求值实现与完整运行时行为采用待核实状态。
6. 已读取独立 cnsh_v2c/compiler.py 全文与 codegen_c.py 的代码生成路径。编译驱动使用模块加载、审计、语义检查与C代码生成；build中的宿主命令参数包含 -std=c99，编译器选择cc/gcc/clang。
7. 发布包 pyproject.toml 为2.2.0，Python>=3.10；发行说明将独立转C工具自身版本记为2.0.0。Gitee发行列表显示v2.1.1（2026-09-20 03:49）、v2.1.2（2026-09-20 06:16）、v2.2.0（2026-09-22 15:06）。时间按页面显示原样记录。
8. v2.2.0标签指向42583e8a76b62df17006a443e61e12b48bca5dda，与本轮main固定SHA分别记录。
9. 固定README定位longhun-cnsh为对外发布仓，开发主仓链接为 https://gitee.com/uid9622_admin/longhun-system-core，开发版转C路径为packaging/cnsh-v2/。cnsh_v21、cnsh_v2c作为同语言内工具链合并记录。
10. README将Python/JS/Rust/C列为现有转译后端，将C++/Obj-C/Swift列为规划占位。条目对各后端完整覆盖使用待核实状态。作者的16/16、543 passed等测试陈述维持作者陈述层级。
11. GitCode云浏览器主页可见同名介绍和39提交数；提交历史页持续显示空壳。搜索索引仍显示较早v2.1.2状态，形成平台同步与索引时差风险。GitCode README索引的源码地址直接指向Gitee。两平台完整同步关系采用待核实状态。
12. Gitee单独commit详情页重定向登录；已公开的固定blob和发行页继续作为证据，登录动作留给用户决定。

主要固定来源：
- https://gitee.com/uid9622/longhun-cnsh/blob/95ef57360c6226f7020cd27f100c4c98fa982775/examples/fib.cnsh#L5-L12
- https://gitee.com/uid9622/longhun-cnsh/blob/95ef57360c6226f7020cd27f100c4c98fa982775/cnsh_v21/parser.py
- https://gitee.com/uid9622/longhun-cnsh/blob/95ef57360c6226f7020cd27f100c4c98fa982775/cnsh_v21/__init__.py
- https://gitee.com/uid9622/longhun-cnsh/blob/95ef57360c6226f7020cd27f100c4c98fa982775/pyproject.toml
- https://gitee.com/uid9622/longhun-cnsh/blob/95ef57360c6226f7020cd27f100c4c98fa982775/cnsh_v2c/compiler.py
- https://gitee.com/uid9622/longhun-cnsh/releases/tag/v2.2.0

## 衍真：保留待核实

- 来源 https://gitcode.com/nextOS/yzcc 的搜索索引保留长篇编译器设计README、中文变量和斐波那契原例，自述Rust、YIR及nextOS/NAPP目标。
- 索引显示“当前项目代码仓暂无内容”；当前云浏览器原页为404，并显示“页面找不到或无权限”。
- 设计可作为候选类别。原作者身份、固定提交、可靠页面日期、实现路径与版本证据仍须补齐。
- 十例编译成功、seL4能力隔离、NAPP执行及5%性能差异属于该README陈述，保持待核实层级。
- 排除GitCode域名的“衍真 yzcc 2026”和“nextOS yzcc”补充检索结果为空。

## 平台与关键词覆盖

主平台：Gitee、GitCode（当前页面标题为AtomGit）；辅助平台：GitHub、普通搜索引擎。补充时间范围：2024—2026；核心候选沿革检索采用全时段，保留更早提交。

执行过的主要查询：
- site:gitee.com/uid9622/longhun-cnsh CNSH
- site:gitcode.com/UID9622/longhun-cnsh CNSH
- site:gitcode.com/nextOS/yzcc 衍真
- site:gitee.com/kaisen-wang 道 中文编程
- "longhun-cnsh" "github.com"
- "kaisen-wang" "道"
- "衍真" "定义" 编译器
- site:gitcode.com/nextOS/yzcc "如果"
- site:gitcode.com/nextOS/yzcc "2026"
- site:gitee.com 中文编程 "2025" "微型"
- site:gitcode.com 中文编程 "2026" "AI" 语言 解释器
- site:gitee.com "中文编程语言" "2024" "解释器"
- site:gitcode.com "中文编程语言" "2026" -"博客" -"蓝皮书"
- "衍真" "yzcc" "2026" -site:gitcode.com
- "nextOS" "yzcc" -site:gitcode.com -site:blog.gitcode.com

有界扩展检索产生大量教程、翻译文档及一般AI开发工具结果；返回的意语言已存在于Issue #3，CNSH与衍真属于本轮已选候选。新增候选数为0。PyPI的cnsh页面读取失败，相关版本以Gitee固定pyproject和发行页为准。

## 遗漏风险与下一轮入口

- Gitee搜索索引对微型低星项目覆盖有限；常规抓取失败与云浏览器可读状态同时存在。
- GitCode缓存README与实时页面状态存在差异；候选消失、私有化及平台同步均可能造成证据缺口。
- 一些Gitee提交详情要求登录，个别正文有平台限制提示。以当前公开来源为边界继续核验。
- 微型及AI辅助项目可能以博客、单文件、临时账号或非“中文编程”关键词发布；本轮补充查询为有界样本。
- 道与CNSH均有实现文件和原例；本轮的收录结论基于静态证据。测试通过、性能、完整标准库与运行安全仍需独立验证。
- 衍真下一步需要可读原页、作者公开规范或稳定提交，随后按设计／实现证据分类。

