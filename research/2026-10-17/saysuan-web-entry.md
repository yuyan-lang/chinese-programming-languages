# 说了算Web入口与结果绑定补证

核验日期：2026-10-17（UTC）。百科基线49da57628c6544f417a144260cd5422d62ce2a9b，103项语言、10项内核。本轮限定Issue #31既有的Web精确覆盖缺口，完善lang-103。

## 固定源码证据

原仓badhope/saysuan固定提交719f1b3db510902527c0ad9cc7d439fad92b16fc。

- [playground.html](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/playground.html)第7行加载Chart.js，第145—651行保存内联脚本。页面的编译器和运行时定义位于该内联脚本中。
- [内联编译规则，第364—438行](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/playground.html#L364-L438)按行匹配中文句式并生成JavaScript。第385—397行的CSV输入采用显式存到名称；筛选、分组和排序统一生成var 结果。分组提取分组列、聚合列与聚合方式。
- [run入口，第520—555行](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/playground.html#L520-L555)读取编辑器文本、调用内联编译函数，再将生成文本交给Function构造器，并传入运行时、内置文件与输出回调。
- [页面内置原例，第174—182行](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/playground.html#L174-L182)在分组、显示和排序中使用结果名称。原例的完整运行结果继续待核。
- [独立compiler-js.js，第112—132行](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/src/compiler-js.js#L112-L132)也将表操作绑定为结果，其分组分支固定使用金额列与总和聚合。该文件与playground.html内联编译器分别记录。
- [runtime-js.js](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/src/runtime-js.js)保存独立运行时模块；页面内联运行时按自身源码范围核验。

## 结论与剩余范围

已有CLI证据使用显式存到或命名话题块绑定。本次补齐Web页面自身的静态生成入口、执行调用链和结果名称。README入门段落中的排序后结果与当前页面绑定的对应、完整句式与标准库双端等价、版本沿革和独立运行继续待核。Issue #31其余发行、首次公开、作者分工及AI细节沿用既有待核范围。

## 检索与核验边界

先读根AGENTS.md、目录树、开放Issue／PR和Issue #31全部既有评论，复核2026-10-15说了算研究及当前lang-103。随后仅读取GitHub原仓上述固定文件；定向词为playground、编译、run、Function、结果、存到、分组和compiler-js。范围限定同一固定快照的Web实现与独立模块，其他分支、历史版本及未公开资料保留遗漏风险。GitCode既有访问限制保持原边界。

证据等级为固定源码静态阅读。本次候选执行、安装、构建和测试均为0；页面实际运行与浏览器渲染均待核。数据对象、对应HTML与本研究记录作资料一致性检查；主例、原有24项引用及其余102项语言保留。目录仍为103项语言、10项内核。
