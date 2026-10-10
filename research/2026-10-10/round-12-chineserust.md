# 第十二轮：Issue #22 中文Rust设计短核验

核验日期：2026-10-10（UTC）。百科基线：[9776f45bed00a6f1c9a594eb8142dd5b4428095d](https://github.com/yuyan-lang/chinese-programming-languages/tree/9776f45bed00a6f1c9a594eb8142dd5b4428095d)。本支线范围为Issue #22的一项既有候选。

## 结论

中文Rust编程语法设计与Rust转译继续保留为待核实候选，本轮正式新增0项。项目阶段核明为“中文→Rust转译设计与部分基础模块原型”。下一步关键证据是作者发布的连续中文用户程序原例，以及相应转译实现。

读取了百科固定[AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/AGENTS.md)、[Issue #22原文](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)及5条评论。[第十一轮状态](https://github.com/yuyan-lang/chinese-programming-languages/issues/22#issuecomment-6101471141)为初始10组累计分类7组，XuYu、中文Rust设计、52zwbc中文CPython关联组3组继续核实。本轮维持这一分类计数。

## 1. 连续中文原例核验

原仓固定提交：[4605fee9402c9ad6fe6e06771b6d2443105eada8](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/tree/4605fee9402c9ad6fe6e06771b6d2443105eada8)。完整递归树为81项，truncated=false；其中51个文件、30个目录。本轮读取50个非空文件，另1个“ZhongComputeRust/中文Rust编程语法设计与Rust转译.md”的树元数据大小为0字节。

[根README](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/README.md)为579行、29946字节的需求与映射规范。7个围栏代码块均标记plantuml，分别位于67—89、149—166、209—226、275—294、339—358、393—406、511—526行。正文包含函数、让、可变、如果、返回等关键词映射，类型映射，以及借用等语法片段；这些材料的内容层级为规则、表格、流程和片段。连续中文用户程序原例继续待核实。

当前51文件的构成为README、15个Cargo.toml、34个Rust源码文件和1个空设计文档。Rust源文件中的汉字用于映射表、注释、诊断文本和CLI提示；它们提供实现证据。用户中文程序的定义与调用连续原例仍待作者资料。

本轮还核对当前主分支的5次提交历史：

- [fd99a1de…根提交](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/commit/fd99a1de560a478f65276c3429b68bd71f02540c)：初始README为标题与项目说明两行
- [4a387265…README修订](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4a387265dd10fac5dd791bf4bac2d5d5708ebf8e/README.md)：仍为两行标题与说明
- [bd8ebc34…工作区上传](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/commit/bd8ebc340636968c96200795525a374fbe88b6db)：上传Rust工作区及Compute文件
- [75b72589…删除Compute](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/commit/75b725895c34321b8bd670679160ff3973d803e8)：删除74行NumPy／Matplotlib演示；其执行语法为import、def、return、for等Python英文语法，汉字为注释、说明及显示文本
- [4605fee9…需求README修订](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/commit/4605fee9402c9ad6fe6e06771b6d2443105eada8)：形成当前需求说明

核验结论限定于上述固定树及已核历史。其他作者发布渠道的连续原例待核实。正式条目code字段保持空缺。

## 2. 实际实现阶段

[工作区清单](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/Cargo.toml#L1-L18)列14个crate。cn_types及cn_config含具体数据结构和函数体：

- [builtin_mappings.rs](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_config/src/builtin_mappings.rs#L15-L127)构造33项关键词、27项类型名、4项所有权语法映射
- [MappingRegistry](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_types/src/mapping_registry.rs#L27-L83)实现注册、冲突检查及反向索引
- [MappingQuery](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_config/src/mapping_query.rs#L27-L61)实现正反向查询
- [pipeline_types.rs](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_types/src/pipeline_types.rs#L8-L87)定义Token、中文AST、Rust AST及指纹结构；相关源码还定义诊断、源位置与源码映射数据

12个其余crate的lib.rs共声明51个外部模块。对照完整固定树，这51个模块的对应源码文件为缺失状态。典型证据为[cn_lexer两条声明](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_lexer/src/lib.rs#L1-L2)、[cn_parser两条声明](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_parser/src/lib.rs#L1-L2)、[cn_codegen五条声明](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_codegen/src/lib.rs#L1-L5)。cn_mapper的10项声明也属于这一阶段。[CLI main](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_cli/src/main.rs#L1-L6)执行内容为打印版本横幅并返回。

配置层有明确的阶段界限：

- [load_from_str第22—27行](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_config/src/mapping_registry.rs#L22-L27)解析TOML文本后建立固定1.0内置注册表；输入解析结果保存在_parsed变量
- [第34—36行](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_config/src/mapping_registry.rs#L34-L36)将热加载回调注册标为后续实现
- [第162—169行](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_config/src/mapping_registry.rs#L162-L169)的向后兼容检查保留后续实现注释并直接返回Ok

因此，需求中性能、LSP、增量转译、语法糖、完整Rust语义映射及诊断回传按设计目标记录；端到端可用性继续待核实。本次核验采用公开静态文本，独立构建和执行结果待核实。

## 3. 同项目命名、作者与日期

根README标题为“中文Rust编程语法设计与Rust转译”。ZhongComputeRust为承载上述14个crate的同仓工作区目录。[cn_cli/Cargo.toml第7—9行](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_cli/Cargo.toml#L7-L9)将二进制命名为cn_transpiler。三种名称按同一项目组保存，ZhongComputeRust的正式语言名地位待作者说明。

仓库维护账号及5次提交的作者署名为bo333。真实姓名及其他作者待核实。时间分别记录：

- 仓库created_at：2026-07-03T03:40:07Z
- 根提交作者及提交时间：2026-07-03T03:40:08Z
- 工作区上传：2026-07-03T05:31:02Z
- 固定头提交：2026-07-03T05:36:32Z

[仓库元数据](https://api.github.com/repos/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool)和上述固定提交支持各自日期。准确首次公开时间待核实。AI参与范围待原作者资料。

## 4. 版本与许可

[workspace.package](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/Cargo.toml#L20-L24)声明version=0.1.0、edition=2021、rust-version=1.70.0、license=MIT。[CLI入口](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_cli/src/main.rs#L3-L6)横幅也使用v0.1.0。内置关键词[条目版本](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/ZhongComputeRust/crates/cn_config/src/builtin_mappings.rs#L53-L62)为1.0；它属于映射规范字段。README中的v1.0／v1.2出现在假设的异常场景说明，按示意文字保存。

[公开release列表](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/releases)本次API查询返回空数组。初次tags端点读取失败；随后[标签引用端点](https://api.github.com/repos/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/git/matching-refs/tags/)成功返回空数组。正式版号和发行日期待核实。

MIT可确认到workspace.package声明层级。14个子包的Cargo.toml均未填写license或license.workspace字段，固定树的许可证正文与版权署名待补，GitHub license元数据为null。整体及各包授权适用范围继续待核实。

## 后续最小补证

优先获取作者的连续中文程序原例及固定来源，再结合补全的词法、解析、语义映射与生成源码核定收录阶段。当前固定树与历史已提供原例缺口的明确边界；重复读取同一需求映射表的价值较低。Issue #22保持开放，本候选计数为1组。

