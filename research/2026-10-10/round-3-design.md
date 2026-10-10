# 中文编程语言设计（Citric1acid）核验日志

核验日期：2026-10-10（UTC）。范围：公开网页、GitHub文档和仓库元数据；操作采用只读方式。

## 结论

按一项“实验性中文编程语言设计／规范与例程”收录。中文控制结构、中文成员访问和名称解析规则的证据充分。编译器与解释器处于待实现状态，JavaScript属于可行性文档提出的目标语言。
## 基线与防重

1. 读取百科AGENTS.md，blob ab8038fa86c6ff04320372eea00cee9c5fd54cca，要求公开技术文档使用直接、肯定的陈述，功能状态和资料缺口照实记录。
2. 读取Issue #3正文及全部评论。正文将本项目列为设计型候选；唯一评论记录CP语言、coCN、Atlanage已通过PR #10收录，其余16项继续核查。
3. 读取data/languages.json完整内容，blob be2a07596a68b9570dd3fdc54d2f98b6f519f518，共41条。核对条目名、别名与参考仓库，当前候选作为新增设计型条目处理。

基线链接：
- https://github.com/yuyan-lang/chinese-programming-languages/blob/main/AGENTS.md
- https://github.com/yuyan-lang/chinese-programming-languages/issues/3
- https://github.com/yuyan-lang/chinese-programming-languages/issues/3#issuecomment-6097444847
- https://github.com/yuyan-lang/chinese-programming-languages/blob/main/data/languages.json

## 仓库与时间

- 仓库：https://github.com/Citric1acid/ChineseProgrammingLanguage
- 元数据：https://api.github.com/repos/Citric1acid/ChineseProgrammingLanguage
- 仓库公开，fork=false，archived=false，默认分支main。
- created_at=2026-09-19T14:23:08Z；pushed_at=2026-09-30T03:25:54Z。
- main固定提交：9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e，作者及提交者日期2026-09-30T03:25:29Z，署名Citric1acid。
- 根提交：d4f79c5a01bbd8faff268adcb1317c19bae761cb，日期2026-09-19T14:21:30Z，署名songzigang；根README标注0.1。
- 当前README标注0.1.1。本轮按规范版本记录。
- commits?per_page=100返回两项，根提交parents为空。
- Releases集合返回空数组：https://api.github.com/repos/Citric1acid/ChineseProgrammingLanguage/releases
- 提交日期、建库日期及首次公开日期分别记录；首次对外公开日期待核实。
- 作者使用已验证GitHub账号与提交署名；真实姓名待核实。

## 原始资料与核验要点

- README.md第1—19、189—195行：设计定位、规范版本、语言设计与规范整理状态、编译器和解释器待实现。
  https://github.com/Citric1acid/ChineseProgrammingLanguage/blob/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e/README.md#L1-L19
  https://github.com/Citric1acid/ChineseProgrammingLanguage/blob/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e/README.md#L189-L195
- 语言规则/命名要求和解析规则.md第40—44行：明确关键词列表，包括定义、若、循环、对、的、每个、返回等；“的每个”为连续关键词组合。
  https://github.com/Citric1acid/ChineseProgrammingLanguage/blob/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e/%E8%AF%AD%E8%A8%80%E8%A7%84%E5%88%99/%E5%91%BD%E5%90%8D%E8%A6%81%E6%B1%82%E5%92%8C%E8%A7%A3%E6%9E%90%E8%A7%84%E5%88%99.md#L40-L44
- 语言规则/基础语法.md：条件、循环、遍历、函数定义、类型、异常与模块语法。
  https://github.com/Citric1acid/ChineseProgrammingLanguage/blob/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e/%E8%AF%AD%E8%A8%80%E8%A7%84%E5%88%99/%E5%9F%BA%E7%A1%80%E8%AF%AD%E6%B3%95.md
- 例程/循环：完整读取18行程序。条目code精确截取第10—15行的连续循环体，保留空行与缩进；上下文使用第1—8行的数据与变量初始化。
  https://github.com/Citric1acid/ChineseProgrammingLanguage/blob/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e/%E4%BE%8B%E7%A8%8B/%E5%BE%AA%E7%8E%AF#L10-L15
- 例程/递归函数、例程/高阶函数、例程/高阶运算符：另行读取，核对函数、返回、的成员访问和一元/二元运算符设计。
- 可行性说明.md第1—24行明确为实现方案。全文提出作用域名称收集、最长匹配和表达式归约，并讨论生成JavaScript和运行时函数的方案。
  https://github.com/Citric1acid/ChineseProgrammingLanguage/blob/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e/%E5%8F%AF%E8%A1%8C%E6%80%A7%E8%AF%B4%E6%98%8E.md#L1-L24
- 语言规则/未定内容.md：作者明确列出独立子表达式求值顺序、数值边界、字典遍历顺序、循环闭包绑定等待定事项。
  https://github.com/Citric1acid/ChineseProgrammingLanguage/blob/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e/%E8%AF%AD%E8%A8%80%E8%A7%84%E5%88%99/%E6%9C%AA%E5%AE%9A%E5%86%85%E5%AE%B9.md
- 固定递归树共39项，其中35个文件、4个目录，truncated=false。树包含规则文档、10份文本例程、两张图片及.gitignore。
  https://api.github.com/repos/Citric1acid/ChineseProgrammingLanguage/git/trees/9abac2a8c4ee96b63d4decf8ce11d8f302e10f0e?recursive=1

## 同源与检索记录

- 按现有41条的名称、aliases、references核对。ChineseProgrammingLanguage属于本项目的英文仓库标识，中文条目名采用原README标题。
- README中的项目资料链接指向同一仓库文档与例程。与目录内语言的继承和兼容关系待核实。
- GitHub仓库搜索ChineseProgrammingLanguage in:name，per_page=100，返回本仓库一项。
- 网页检索“Citric1acid” “中文编程”及“ChineseProgrammingLanguage” “Citric1acid”，返回空结果。
- 原仓库网页可读，内容与固定提交README交叉核对一致。
- 作者GitHub主页经网页工具读取返回Cache miss；作者资料使用仓库所有者与提交署名。
- GitHub接口访问/tags端点返回接口范围错误；/git/refs/tags返回404。标签状态保留待核实，版本依据采用已读取README和Releases集合。

## 核验范围

条目明确标为语言设计，工具链和运行能力列为待核实项。语法和实现方案来自作者仓库的固定提交。
