# 说了算固定原例与CLI实现补证

核验日期：2026-10-15（UTC）。百科基线9f43243e4cb70445deec21627b01ef0b45a681a3，102项语言、10项内核。沿Issue #31已有说了算线索取得GitHub公开副本，拟收录lang-103，目录成为103／10。

## 原始证据与收录范围

[GitHub公开项目](https://github.com/badhope/saysuan)固定头719f1b3db510902527c0ad9cc7d439fad92b16fc，完整递归树truncated=false。其头提交与Issue #31先前保存的GitCode头相同。[固定发布指南](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/发布指南.md)直接链接GitCode badhope/saysuan，并记载该仓已推送。跨平台账号关系复用[10月14日补证](https://github.com/yuyan-lang/chinese-programming-languages/issues/31#issuecomment-6163790501)与[固定个人README](https://github.com/badhope/badhope/blob/067b65180fb3a4ede505c19f76db722fb6817a41/README.md#L42-L54)。同一快照关系与持续同步分别核实。

收录类别为中文数据分析DSL与Python转译实现。以固定.suan原文件、词法／表达式处理和CLI调用链确认中文语法与实现层次；Web路线及双端覆盖表按文档说明保存。

## 连续原例

[demo.suan第11—14行](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/demo.suan#L11-L14)，blob fe8d613ca76074c6ecb3b6b1316958f748a7167e。四句组成完整的定义、乘法与输出序列；20个空白分词，逐字保留换行：

```text
设 「单价」 为 5 块 5 角
设 「数量」 为 10 个
算 「货款」 = 「单价」 乘 「数量」
显示 「货款」
```

完整demo另含CSV读取、显式结果名筛选与分组汇总。[门店月报原文件](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/例子/门店月报.suan)使用命名话题块、时间筛选、汇总、排序和导出。原例输出与独立运行结果继续待核。

## 调用链及文档边界

- [saysuan.js](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/saysuan.js)分派文件、单句及REPL入口。
- [cli.js](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/src/cli.js)读取源文件、调用编译、写入.py，并按参数决定Python调用。所有流程仅作静态阅读。
- [tokenizer.js](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/src/tokenizer.js)识别名字、文本、量词及中文运算词；[types.js](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/src/types.js)提供量词运算规则。compiler.js表达式引擎调用分词并按优先级递归处理。
- [顶层表操作规则](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/src/compiler.js#L94-L108)使用显式存到目标；[生成分支](https://github.com/badhope/saysuan/blob/719f1b3db510902527c0ad9cc7d439fad92b16fc/src/compiler.js#L865-L906)以该目标登记变量并生成pandas筛选、聚合、排序。话题块以块名绑定结果。
- README入门片段使用省略存到的句式和排序后结果名称。本条示例选用完整demo中的算术原段。README片段的端别与实际运行对应继续待核。
- SPEC将函数、异常、文件读写、模块、一册列为CLI已覆盖、Web待补。标准库函数双端对齐为作者文档范围，全部句式的端间等价继续待核。
- README要求Node.js≥18；package.json列Node≥14。实际最低兼容版本继续待核。README测试总数与CHANGELOG通过声明按作者自述保存。

## 日期、作者、许可与AI

GitHub元数据：创建2026-10-14T08:47:28Z，推送2026-10-14T09:07:24Z。保留历史共12提交，根529192c6fbc9a07afd7d45a5a5dba9a5267e6fb4无父提交，时间2026-09-29T10:57:13Z；头时间2026-10-09T07:58:26Z。CHANGELOG另将v0.1.0记为2026-09-28，v1.0.0／v1.1.0记为2026-10-09。首次对外公开时刻继续待核。

package.json与compiler.js自标1.1.0，SPEC自标v1.1.0。2026-10-15 GitHub releases集合为空；GitCode既有v0.9.0侧栏记录及发行正文、绝对时间、附件对应继续待核。GitHub标签端点本次工具不支持，标签状态保持待核。

LICENSE为MIT全文，版权署名2026 badhope。历史根与早期提交作者为x1882，后续为badhope；两署名关系与分工待核。发布指南说明AI协作过程台账保留在本地，具体模型、比例和人工复核待核。

## 检索与有限核验

已读AGENTS、当前目录树、全部开放Issue／PR正文、最新研究及Issue #31评论。04:30 UTC之后的提交、Issue更新、Issue评论及PR评论接口均返回空集合。当前27个开放Issue及PR #62按各自范围保留。

复用10月14日跨账号证据后，以saysuan及三个已关联GitHub账号作一次定向仓库检索，返回badhope/saysuan；后续仅阅读该项目固定原件。GitCode此前访问频次／登录限制保持原边界。索引覆盖、保留历史与首次公开之间的区别、持续同步及Web端覆盖构成本轮局限。

## 提交范围与收尾条件

仅新增lang-103对象、对应静态详情页和本研究记录。既有102个对象逐项保持相同，豫言条目与10项内核保持原样；旧详情页、脚本、样式及PR #62保持原状。提交前核对27字段、103个唯一ID、原例20词与固定blob、全部引用及JSON／HTML一致性。完整远端diff、CI和冲突状态由PR复核。

本次候选程序执行、安装、构建和测试均为0。Issue #31可记录连续原例、CLI源码、许可与同一快照证据已经补齐。其剩余的Web精确覆盖、发行和首次公开、x1882分工、AI细节及独立运行继续待核；LightLang相关残余字段沿用既有记录。建议合并后留言关联PR并保留Issue开放。
