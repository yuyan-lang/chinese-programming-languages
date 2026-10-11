# DaLang（大雄语 / DxLang）独立证据复核

复核日期：2026-10-11。固定提交：fa7b3d0202861ed15a58ae861582e89f704175a7。已读 yuyan-lang/chinese-programming-languages 的 AGENTS.md。采用普通GitHub接口读取固定来源，完成静态核对；独立运行结果待核实。

## 结论

满足独立条目基本证据要求：存在实际中文关键字、完整词法分析器、递归下降解析器、AST 数据结构及树遍历解释执行器；固定树包含七个 .dx 示例。名称建议“大雄语（DxLang）”；DaLang 是仓库名称，DxRuntime 是运行时名称。

## 实现证据

- [main.py](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/main.py#L31-L49)：run_code 明确依次调用 DxLexer(source).tokenize()、DxParser(tokens).parse()、vm.run(ast)。
- [dx_lexer.py](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/src/dx_lexer.py#L22-L41)：大雄启动、大雄结束、设、为、印、取、若、则、不然若、否则、当、循、在、函、归、中断、跳过、雄选、情况、默认、尼古守护、捕获、结束、全局等进入关键字表；真、假、空由专门字面量分支处理。
- [dx_parser.py](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/src/dx_parser.py#L94-L160)：程序边界、语句分派、变量定义均有具体解析逻辑；条件与循环见 L238-L292；函数定义见 L298-L311。
- [dx_vm.py](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/src/dx_vm.py#L81-L135)：类文档明确“树遍历解释器（Tree-walking Interpreter）”，run/execute 直接遍历 AST。
- [dx_vm.py](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/src/dx_vm.py#L280-L289)：函数保存定义时作用域，返回使用 DxReturnSignal；[函数调用](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/src/dx_vm.py#L338-L398) 创建局部 Scope，并绑定参数。
- [dx_std.py](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/src/dx_std.py#L539-L605)：中文函数注册表包含 范围、追加、排序、读文件、写文件等。语法关键字和中文内置函数宜分别描述。

## 可直接引用的连续上游样例

[examples/fibonacci.dx L15-L29](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/examples/fibonacci.dx#L15-L29) 是完整迭代函数的连续原文；L30 为空行。它是函数节选，完整文件在 L4 和 L48 使用程序边界。源码如下：

```text
函 斐波那契迭代(n) {
    若 n <= 1 则
        归 n
    结束
    设 雄_a 为 0
    设 雄_b 为 1
    设 雄_i 为 2
    当 雄_i <= n 则
        设 雄_c 为 雄_a + 雄_b
        雄_a = 雄_b
        雄_b = 雄_c
        雄_i += 1
    结束
    归 雄_b
}
```

此样例清楚体现 函、若…则…结束、归、设…为、当…则…结束，并同时保留符号运算。运行结果未实测，正文应采用“上游样例展示”或“源码实现”表述。

## 日期、作者、许可和版本

- [仓库元数据](https://api.github.com/repos/xxiaoxiong/DaLang)：created_at=2026-03-29T01:47:04Z；公开项目，fork=false；license=null。
- [固定初始提交](https://github.com/xxiaoxiong/DaLang/commit/fa7b3d0202861ed15a58ae861582e89f704175a7)：作者与提交时间均为 2026-03-29T01:47:45Z，提交说明 init，parents=[]。日期适宜写“当前可见初始提交日期”；首次公开发布时点仍待核实。
- 作者关联：GitHub xxiaoxiong；提交署名 Nicholas-Xiong；main.py 横幅及 dx_std.py L14 自述“尼古拉斯大雄”。
- 完整固定树无许可文件；许可授权范围待核实。宜写“公开源代码”。
- main.py 横幅和 dx_std.py L13 自标 v1.0.0。releases 接口返回空数组。v1.0.0 可以标为“源码内版本标识”；正式版本发布时间待核实。
- tags 查询被 GitHub fetch URL 支持范围限制，标签情况未核实。勿声称“无标签”。
- [设计文档](https://github.com/xxiaoxiong/DaLang/blob/fa7b3d0202861ed15a58ae861582e89f704175a7/%E5%A4%A7%E9%9B%84%E8%AF%AD%EF%BC%88DxLang%EF%BC%89%E9%9C%80%E6%B1%82%E4%B8%8E%E8%AE%BE%E8%AE%A1%E6%96%87%E6%A1%A3.md) L639 提示“文档部分内容可能由 AI 生成”，可保留出处说明。

## 必须避免的误述

1. 实际架构按 AST 树遍历解释器表述。设计文档“栈式虚拟机”属于设计文本措辞，直接执行路径由源码证实。
2. 实际逻辑运算符是 &&、||、!；parser L415-L427 与 L481-L493。文档的“且、或、非”不应写作已实现关键字。
3. 雄_ 为文档和示例中的命名约定；词法器、变量定义及赋值逻辑未强制此前缀。
4. typed input 后缀 整数/浮点/字符串：parser L230 要求 TT_KEYWORD，lexer 的 KEYWORDS 缺少这三个词。此功能不宜直接标为完整可用。
5. parse() 在“大雄结束”后直接返回，未执行 EOF expect；只描述程序边界即可。
6. 技术、作者、日期、授权的证据彼此独立。fork=false 只说明 GitHub 仓库关系；与其他中文语言的派生关系待核实。

