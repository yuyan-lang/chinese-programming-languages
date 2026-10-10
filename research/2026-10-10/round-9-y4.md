# Y4-Lang新发现核验

核验日期：2026-10-10。

## 发现路径与计数

- 新发现1项，中文语法和独立解释器源码已核，建议正式收录1项。
- 检索平台：搜索引擎、V2EX原帖、GitHub原仓；发现入口为分享创造日报2024-06-19页，资料以作者原帖和固定源码为准。
- 检索词：`中文 编程语言 2024 github 自制`、`中文解释器 github 2026`、`中文编程 AI gitee 2026`、`分享一个自娱自乐造的中文脚本语言`。
- 目标时间范围2024—2026；追溯到2023-12-21仓库创建字段、2024-01-16历史根提交及2024-02-01公开发行。
- 已与64项语言目录和本轮开始时14个开放Issue进行名称／仓库去重。

## 固定证据

- 当前master：5efbabf5a3dd49ab2184ee844e6ad4782832caec，作者及提交者日期2024-06-18T10:28:50Z，单根快照。
- v0.0.3标签：3de99aafe3d0219dc2f11f40f2a50968e49a23c9，提交2024-02-01T10:10:58Z，发行2024-02-01T10:16:34Z。
- 标签历史59条，根cd90cba6e5b26a7373068517a72f394b3f13c761，日期2024-01-16T15:37:10Z。
- 当前仓库归档状态为true。原帖由4ra1n发表于2024-06-18，直接链接4ra1n/y4-lang，并说明参考《两周自制脚本语言》。
- 核心语法常量、Rule规则、AST Eval链、主函数及任务池均已阅读；条目保留原快排函数第20—26行。
- README的轻量实现定位与各组件来源分项记录：Go标准库与仓库内包；测试testify；内置saintfish/chardet和mitchellh/gox。

## 来源

- [作者V2EX原帖：中文脚本语言、原仓链接及设计来源](https://v2ex.com/t/1050623)
- [固定README：项目名称、原例和功能说明](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/README.md)
- [中文关键字常量](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/core/const.go)
- [中文语法规则与AST构造](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/core/core_parser.go)
- [解释执行和主函数调用](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/core/interpreter.go)
- [启动语句和任务池调用](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/ast/go_stmt.go)
- [快速排序完整中文原例](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/y4-examples/002.y4)
- [Go版本及测试依赖](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/go.mod)
- [字符编码检测上游说明](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/chardet/README.md)
- [构建工具上游说明](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/gox/README.md)
- [Apache-2.0项目许可证](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/LICENSE)
- [版本记录](https://github.com/4ra1n/y4-lang/blob/5efbabf5a3dd49ab2184ee844e6ad4782832caec/CHANGELOG.md)
- [v0.0.3公开发行](https://github.com/4ra1n/y4-lang/releases/tag/v0.0.3)
- [v0.0.3固定中文关键字表](https://github.com/4ra1n/y4-lang/blob/3de99aafe3d0219dc2f11f40f2a50968e49a23c9/core/const.go)
- [发行标签历史的根提交](https://github.com/4ra1n/y4-lang/commit/cd90cba6e5b26a7373068517a72f394b3f13c761)

## 覆盖风险与后续

V2EX网页直读返回cache miss，搜索索引保留作者帖正文和原仓链接；GitHub原始文件及API可读。社区搜索排序与索引日期影响发现范围。公开发行早于当前默认根提交，后续历史核验应同时保留标签。构建、附件内容和运行行为待独立核实。
