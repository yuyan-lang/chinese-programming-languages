# LightLang 1.0.0清单与自举链资料更新

核验日期：2026-10-20（UTC）。关联[Issue #31](https://github.com/yuyan-lang/chinese-programming-languages/issues/31#issuecomment-6286331351)。

## 范围

完善既有lang-083，目录保持103项语言、10项内核。保留原例、同源沿革及历史引用。豫言条目、其他项目与开放PR #62、#76保持原样。

## 固定证据

- [2026-10-13固定编译器清单：1.0.0与nlightc](https://github.com/oneone1565/LightLang/blob/458b31a7f01d4c6aeed6b387b47a04a8d994c772/lightc/Cargo.toml)
- [固定自举脚本：分阶段编译、Rust运行时链接与IR比较](https://github.com/oneone1565/LightLang/blob/458b31a7f01d4c6aeed6b387b47a04a8d994c772/scripts/bootstrap.sh)
- [固定自举阶段文档：作者测试声明及后续目标](https://github.com/oneone1565/LightLang/blob/458b31a7f01d4c6aeed6b387b47a04a8d994c772/docs/bootstrap.md)
- [2026-10-13快照提交与时间](https://github.com/oneone1565/LightLang/commit/458b31a7f01d4c6aeed6b387b47a04a8d994c772)

2026-10-13固定快照458b31a7f01d4c6aeed6b387b47a04a8d994c772的lightc/Cargo.toml标为1.0.0，编译器二进制名为nlightc。此前2026-09-27快照的五个Cargo组件清单为0.2.1。历史标签0.2.0指向d507d3a03a993d3613f51e5fafee4ab9944a34e0，其lightc清单为0.2.0。2026-10-20读取GitHub发行集合返回空数组；1.0.0的正式发行日期、附件及GitCode发行对应待核实。

2026-09-27固定快照的Rust前端实现中文词法、缩进解析、AST和类型推导，生成LLVM IR后通过Clang链接Rust运行时；light与lightGo分别提供会话重编和FFI构建入口。2026-10-13快照的scripts/bootstrap.sh先以Cargo构建Rust参考编译器及运行时，再由nlightc编译bootstrap/lc.light，逐级生成stage2.ll与stage3.ll并以cmp逐字节比较。各代链接target/release/libnlightrt.a，比较成功后编译运行中文打印冒烟程序。docs/bootstrap.md记录作者的IR定点一致测试声明，后续目标包括运行时存活计数、页面元素和REPL移植。上述调用链已经静态核验；独立构建、自举复现及完整语义覆盖待核实。

## 核验与后续

本轮先读AGENTS.md、目录、全部开放Issue与PR集合、相关研究日志及Issue #31评论。采用GitHub原仓固定文件与此前已归档补证；检索词为既有项目名LightLang、bootstrap、版本1.0.0。关注2026-09至2026-10版本演变。独立构建、测试、候选执行与桌面操作均为0；更新仅限公开资料。

JSON与HTML同步版本、实现、自举证据和核验日期；旧中文原例及其固定出处保持。GitHub发行集合读取为空，正式发行日期与代码清单版本分开记录。GitCode访问边界继续遵守，未索引发行物、平台不同步和阶段文档计数存在遗漏风险。平台同步、最早公开、AI参与、与光明的沿革及独立运行仍按已有缺口保留，Issue #31继续开放。
