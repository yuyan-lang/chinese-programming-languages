# 言语言关联设计资料补证

核验日期：2026-10-14（UTC）。百科基线3eebd22c6b0916a09da77a5ae4a96f8088f37543，102项语言、10项内核。本次沿Issue #5旧线索，补充lang-078的关联设计说明与固定引用。正式目录计数保持102／10。

已读AGENTS.md、当前语言目录、开放Issues与PR列表、Issue #5全部评论及相关研究日志。复用[2026-10-13补证评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/5#issuecomment-6157057564)和[第十四轮研究](../2026-10-10/round-14-yan-log.md)。

## 原始来源与证据范围

原仓固定提交：815353dfe80dbae46ac2e0dabe5e9f447559bb78。

- [综合设计比较与取舍，L62—89](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/.dumate/inbox/design.md#L62-L89)，blob a8952c0a35845c1af18df6b445b3c831bfa1cc61。文档开头说明综合三组项目设计；取舍列表属于该综合设计方案。比较表分别记录三组设计特征，现行言实现的功能覆盖沿原条目单独核验。
- [文言心工程设计及AST原例，L55—74](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/docs/design.md#L55-L74)，blob 282fc1d551e195ce57cfd08af90267f6aa292daa。文件开头明确命名文言心并说明后期开发规范；短例“列1 2 3，皆乘2。”用于解释列表、管道和高阶映射的AST构造。
- [Python转译设计中的入口，L899—1011](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/docs/solution-python-transpile.md#L899-L1011)及[阶乘原例，L1072—1082](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/docs/solution-python-transpile.md#L1072-L1082)，blob a2f1ae910b2fbfdceb5d263af9e3ed7b7fdcb8d1。文档标题使用言语言，入口示意和交互文案使用言叶，阶乘例标作examples/factorial.yanya。以设计文档原例为证据层级。
- [文件路径历史](https://api.github.com/repos/skywalk163/yan/commits?path=docs/solution-python-transpile.md&sha=815353dfe80dbae46ac2e0dabe5e9f447559bb78&per_page=10)返回6025186f109976e73730560d438f94d4984a0f45，提交时间2026-06-02T10:06:29Z，消息add base modules。该记录限定为此路径的提交历史，首次公开时间继续待核。

## 发布范围与剩余问题

本次更新data/languages.json中lang-078的介绍、关系说明、核验说明、核验日期和引用，并同步详情页。原有中文主例、实现、版本、作者、许可及其他条目均沿用既有资料。

关联设计材料与中文原例已定位，可作为本项文档补证发布。各名称的独立版本、正式改名、实现继承、发行兼容性与原例运行结果继续待核。段言／光明既有谱系材料保持原有范围；Hanyu、无极与Wxe等Issue #5其他子项继续保留。Issue #5保持开放。

## 检索与读取限制

采用GitHub公开只读接口和网页工具。核对当前目录、固定原文件及路径历史；仓内关键词Hanyu、无极用于复用前序证据。网页精确检索zhf888/wuji、104977727与无极、hanyu-lang与lin8092未取得可推进的原始中文程序证据。无极CSDN原页与Gitee原仓直接读取失败，Hanyu PyPI直接读取返回Cache miss。访问结果限定于本次工具与可见范围。

本次选用已取得固定原件的关联设计资料完成有限补证。搜索索引覆盖、仓外材料、删除历史和未明确的名称沿革仍存在遗漏风险。源码片段与示例仅作静态阅读；执行、安装、构建和测试均为0。文档功能说明、固定源码实现与独立运行结果分层保存。

## 静态核验

核对JSON可解析、条目数102、唯一变更条目lang-078、其余101项逐项保持相同。对照JSON与HTML中的说明和新增引用，阅读完整提交diff。仓库当前树提供静态网页与JSON；适用远端检查在PR中记录。
