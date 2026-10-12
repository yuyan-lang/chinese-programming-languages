# 第20轮独立证据复核

结论：两个候选均具备原作者仓库中的中文语法、连续代码示例及对应执行实现，收录证据充分。固定来源与条目草稿核对完成，当前草稿可进入发布流程。

## 范围

- 按百科仓库固定提交 c14ea6d635124e6a938dd4355fc4cd4b96121d7a 的 AGENTS.md 执行：肯定陈述、直接说明事实，证据不足标为“待核实”。
- 来源仅作公开 GitHub 只读核验；未安装、启动或执行候选项目。
- ling-code 固定提交：5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb。
- Smal-lang 固定提交：87bdf15d9d37d55ef08f038bac0fa54cbcb852ef。

## 灵码（zf199606/ling-code）

1. 灵码编译器/ling.js 中 LingTranslator.translate 以连续正则替换处理注释、字面量、中文运算符、插值、语法及标准库名称，生成 JavaScript；普通运行分支通过 new Function 执行生成文本并提供 Node.js 运行时参数。应归类为 JavaScript 实现的中文源码转译系统。
2. 灵码示例/09_斐波那契数列.灵 第4—15行为连续原始片段，包含函数定义、条件、返回、递归调用、区间遍历和打印，足以证明中文控制语法。完整片段保留原注释、标点、缩进和输出文字。
3. ling.js 的 --check 分支只完成 translate 后输出成功信息；实际 JS 语法构造位于普通执行分支。模块导入导出在该转译器中替换为注释。字符串及注释上的全局替换、类型注解移除等应按代码实际边界描述。
4. 版本属于不同部件：最新提交消息 v3.5.1；index.html 标识有工作室 v3.0、状态 v3.5；ling.js 头注释 V0.5、CLI 提示 v0.4；文件名 灵码语言规范_V1.0.md 的正文标题为 V2.0。统一发行版本待核实。
5. 递归树中缺少根许可文件，仓库许可状态待核实。index.html 第4310、4318行的 MIT 字段属于导出的 package.json 模板，其适用对象是生成项目。
6. 仓库账号及固定提交作者为 zf199606；更完整的自然人作者资料待核实。
7. 其他模板存在需要另行验证的语义：02_条件判断.灵 尾部把条件语句用作赋值表达式；05_函数定义与调用.灵 的平方使用 ^，该 CLI 转译器保留此运算符。建议只把示例标为原作者代码摘录，实际执行结果待核实。

来源：[转译器](https://github.com/zf199606/ling-code/blob/5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb/灵码编译器/ling.js)、[斐波那契示例](https://github.com/zf199606/ling-code/blob/5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb/灵码示例/09_斐波那契数列.灵)、[网页实现](https://github.com/zf199606/ling-code/blob/5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb/index.html)、[语言规范](https://github.com/zf199606/ling-code/blob/5654cd1f578eaf642a8f8f0731aa77e5d04a4cbb/灵码语言规范_V1.0.md)。

## Smal-lang

1. main.py 为 Python/PyQt5 IDE 与解释器：按钮回调 run_code 读取编辑区纯文本，调用 SmalInterpreter.execute；execute 使用正则识别顶层循环和等值条件并收集缩进体；execute_line 处理赋值、输出和 QInputDialog 输入；parse_expression 处理变量替换、括号及中文四则词。
2. main.py 的 show_example 三引号文本是连续原始 Smal 示例；取出字符串内容时去掉 Python 容器边界即可，内部空行、四空格循环体和文字完整保留。README 示例带转义痕迹，main.py 是较清晰的取样来源。
3. 循环计数从1开始，循环体由四个空格或制表符识别。顶层条件只匹配“等于”。嵌套控制流的递归执行待核实：循环和条件体逐行交给 execute_line，当前实现覆盖赋值、输出和输入三类。
4. 版本 v2.3.2 同时存在于 README、窗口标题和关于对话框。README 标示 Python 3.6+ 与 PyQt5；兼容性属于项目说明，实际环境运行待核实。
5. 根 LICENSE 确认 MIT，版权署名 Copyright (c) 2025 Smal Smith。固定提交作者为 Smal Smith，仓库账号为 CodeWatcher-Smal。
6. 表达式处理首先移除引号，随后进行变量替换和运算；字符串保护及复杂表达式语义宜按此实现范围描述。

来源：[main.py](https://github.com/CodeWatcher-Smal/Smal-lang/blob/87bdf15d9d37d55ef08f038bac0fa54cbcb852ef/main.py)、[README](https://github.com/CodeWatcher-Smal/Smal-lang/blob/87bdf15d9d37d55ef08f038bac0fa54cbcb852ef/ReadMe.md)、[LICENSE](https://github.com/CodeWatcher-Smal/Smal-lang/blob/87bdf15d9d37d55ef08f038bac0fa54cbcb852ef/LICENSE)。

## 草稿核验结论

- 灵码 code 字段与独立重读原始文件第4—15行逐字符相等，共12行。
- Smal code 字段与独立重读 main.py 的 example_code 三引号字符串值 trimEnd 后逐字符相等，共15行；草稿已经明示末尾换行展示裁剪。
- 灵码设计方案第3行确有2026-07-24及墨灵署名；Rust、AST、WebAssembly路线归于设计资料，已与现有 JavaScript 实现分开。
- 灵码 AI 文件头、盘古模拟注释与 ForgeStencil 参考许可字段已独立重读，草稿的规则/模板及许可边界表述与来源相符。
- 两仓创建时间、根提交时间、根 parents 空数组、fork=false 与当前公开 releases 空列表已分别重读确认。灵码固定树112项与草稿一致。
- 草稿用“待核实”呈现实际执行、兼容性、复杂语义及历史资料缺口，保留两项目的具体实现分类和完整来源链。语言样例、主要技术事实、许可、作者署名及版本边界均通过复核。
