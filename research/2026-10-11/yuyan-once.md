# 豫言资料核验记录

核验日期：2026-10-11。条目：lang-001。源码快照：78f66573f8af7c33747958211aae36a8646e805f，提交时间为2026-10-11T05:09:19Z。本文记录公开文档、源码与发行元数据的读取核验；安装、运行、编译、测试、性能与跨平台行为的独立复现状态为待核实。

## 语言与实现

豫言是面向中文编程的静态类型函数式通用语言，提供参数多态、代数数据类型、模式匹配、递归、闭包、模块及带类型宿主接口。名称与数字使用「」，字符串使用『』；函数、调用、局部绑定与模式匹配分别使用会…而…、于、虑…者…而…、鉴…而…有…或有…。官方自述和核心语法给出这些规则。

当前编译器主体使用豫言实现。编译调度源码组织语法分析、类型检查和擦除、跨模块优化、闭包相关转换；阶段文档列出18个中间边界，以树码保存阶段产物。设计说明以豫汇／WebAssembly为统一执行边界，描述标准Wasm与原生执行路线；快速开始采用Node宿主运行Wasm编译器与豫构，并记录三级自举以及最后两级的逐字节比较。上述自举结果作为作者的构建说明记录。

GADT与简单依值类型由专门技术规范、提案00002实施记录和类型检查源码共同支持。索引定义域为整数、爻、字符串，以及元素仍属于这些定义域的递归列表。源码的依值箭头和隐式值参数分支实际调用定义域检查函数。较早设计说明和简版语法中的类型描述，与2026-10-06实施记录存在时间差；本次类型结论以专门规范和实际实现为依据。技术规范总纲自带兼容基线4cdeca11600fed16338793a494b6eecaae94485a，该基线与本次源码快照分别记录。

## 作者、历史、版本与许可

- GitHub账号UltimatePea关联现有根提交与v0.4发行，源码托管于yuyan-lang组织。作者中文姓名和完整贡献者分工待核实。
- 根提交21e8c83c9ff0ad387603d661c8085edf380d56d0的时间为2021-10-14T18:39:36Z，包含SML解析器及.yulang例程；仓库创建时间为2021-10-15T20:29:09Z。首次对外公开日期待核实。
- 现存最早发行条目v0.1.0alpha1发布于2023-12-21T23:47:27Z；v0.1.0rc1发布于2024-02-03T06:52:43Z，作者将其记为首个可用自举版本。
- v0.3发布于2025-08-31T14:36:13Z，发行说明记载OCaml架构；v0.4发布于2026-09-02T15:06:13Z，标题记载全中文自举回归。版本的历史顺序按发布时间记录。
- continuous-binaries提供滚动Wasm工具链，初次读取时更新时间为2026-10-11T04:58:57Z，2026-10-11T12:53Z复核时更新时间为2026-10-11T12:35:41Z。固定源码快照保持上述提交。VS Code插件package.json版本为0.0.21。
- 根LICENSE为GNU Affero General Public License version 3。第三方组件适用范围以各自许可文件为准。
- 2026-06-17的v0.1.0rc2.0发行说明明确提到借助LLM恢复自举编译器。具体模型、生成代码比例和完整人机分工待核实。

## 官方后续事项

提案00002实施记录在2026-10-06将八步标为已实现，列表数组段原型评测后保留链表表示。官方后续事项包括依值字段在模式中的代换、复杂索引的规约与隐式参数推定、项层隐式值参数的提前检查、复合索引构造器的宿主边界、存在名冲突、覆盖检查补全，以及着色向量的维数索引。完成时间待核实。

## 连续原始例程

以下代码来自固定提交的斐波那契。脚本。豫第1—18行。逐字核对包含空行、缩进、汉字数字与中文标点；末尾文件换行单独处理。代码导入标准库及命令行参数、整数操作模块，递归计算首个命令行参数对应的斐波那契值，再打印结果。其执行依赖仓库包上下文和工具链，独立运行结果待核实。

```yuyan
寻观「标准库」之书。
寻「标准库」之「操作系统」之「命令行参数」之书。
寻「标准库」之「数据结构」之「整数操作」之书。

「斐波那契」乃化「整数」而「整数」也。
「斐波那契」者会「数」而
  若「小于」于「数」于「二」
  则
    「数」
  否则
    「加」
      于（「斐波那契」于（「减」于「数」于「一」））
      于（「斐波那契」于（「减」于「数」于「二」））
也。

「参数」者「整数操作」之「理解整数」于（「第几个」于「零」于（「命令行参数」之「获取参数」于「元」））也。

「打印行」于（「整数表示」于（「斐波那契」于「参数」））。
```

## 原条目完整原文

```json
{
  "id": "lang-001",
  "name": "豫言",
  "description": "使用中文语法的函数式编程语言。",
  "references": [
    {
      "title": "参考资料",
      "url": "https://www.ploc.org.cn/ploc/CNPL-2023.pdf"
    }
  ],
  "status": "有文献"
}
```

## 来源

原始参考资料《2023中文编程语言蓝皮书》链接完整保留。其全文在本次网页读取中超时；当前技术事实由以下原作者公开源码和发行记录支持。

- [参考资料](https://www.ploc.org.cn/ploc/CNPL-2023.pdf)
- [豫言官方公开源码仓库](https://github.com/yuyan-lang/yuyan)
- [固定项目自述：定位、工具链与资料入口](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E8%87%AA%E8%BF%B0.%E6%B1%89%E8%AF%AD.md#L1-L31)
- [固定设计动机：中文表达与豫汇执行边界](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%94%E7%94%A8/%E8%B1%AB%E8%A8%80%E7%BC%96%E8%AF%91%E5%99%A8/%E6%96%87%E6%A1%A3/%E8%AE%BE%E8%AE%A1%E5%8A%A8%E6%9C%BA.%E6%B1%89%E8%AF%AD.md#L1-L23)
- [固定核心语法说明：名称、函数、模块和模式匹配](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%94%E7%94%A8/%E8%B1%AB%E8%A8%80%E7%BC%96%E8%AF%91%E5%99%A8/%E6%96%87%E6%A1%A3/%E8%AF%AD%E8%A8%80%E8%A7%84%E8%8C%83.%E6%B1%89%E8%AF%AD.md)
- [固定原始连续例程：递归斐波那契18行](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%94%E7%94%A8/%E6%80%A7%E8%83%BD%E7%A0%94%E7%A9%B6/%E8%B7%A8%E8%AF%AD%E8%A8%80%E6%AF%94%E8%BE%83/%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91%E3%80%82%E8%84%9A%E6%9C%AC%E3%80%82%E8%B1%AB#L1-L18)
- [固定快速开始：Wasm工具链、包构建与自举流程](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%94%E7%94%A8/%E8%B1%AB%E8%A8%80%E7%BC%96%E8%AF%91%E5%99%A8/%E6%96%87%E6%A1%A3/%E5%BF%AB%E9%80%9F%E5%BC%80%E5%A7%8B.%E6%B1%89%E8%AF%AD.md#L14-L57)
- [固定阶段说明：18个中间边界与树码](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%93/%E7%BC%96%E8%AF%91%E5%99%A8%E6%A0%B8%E5%BF%83/%E6%96%87%E6%A1%A3/%E4%B8%AD%E9%97%B4%E8%AF%AD%E8%A8%80%E4%B8%8E%E9%98%B6%E6%AE%B5%E5%88%86%E7%A6%BB.%E6%B1%89%E8%AF%AD.md#L29-L52)
- [固定编译调度源码](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%93/%E7%BC%96%E8%AF%91%E5%99%A8%E6%A0%B8%E5%BF%83/%E7%BC%96%E8%AF%91%E6%AD%A5%E9%AA%A4/%E6%80%BB%E4%BD%93%E8%BF%87%E7%A8%8B/%E7%BC%96%E8%AF%91%E8%BF%87%E7%A8%8B%E3%80%82%E8%B1%AB#L90-L130)
- [固定类型检查源码：依值箭头与隐式值参数](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%93/%E7%BC%96%E8%AF%91%E5%99%A8%E6%A0%B8%E5%BF%83/%E7%BC%96%E8%AF%91%E6%AD%A5%E9%AA%A4/%E7%B1%BB%E5%9E%8B%E6%A3%80%E6%9F%A5/%E7%B1%BB%E5%9E%8B%E7%B1%BB%E5%9E%8B%E6%A3%80%E6%9F%A5%E3%80%82%E8%B1%AB#L296-L397)
- [固定索引定义域源码](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%93/%E7%BC%96%E8%AF%91%E5%99%A8%E6%A0%B8%E5%BF%83/%E7%BC%96%E8%AF%91%E6%AD%A5%E9%AA%A4/%E7%B1%BB%E5%9E%8B%E6%A3%80%E6%9F%A5/%E4%BE%9D%E5%80%BC%E7%B4%A2%E5%BC%95%E5%AE%9A%E4%B9%89%E5%9F%9F%E3%80%82%E8%B1%AB#L16-L73)
- [固定简单依值类型规则与边界](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%94%E7%94%A8/%E8%B1%AB%E8%A8%80%E7%BC%96%E8%AF%91%E5%99%A8/%E6%96%87%E6%A1%A3/%E8%AF%AD%E8%A8%80%E6%8A%80%E6%9C%AF%E8%A7%84%E8%8C%83/%E4%BE%9D%E5%80%BC%E7%B1%BB%E5%9E%8B.%E6%B1%89%E8%AF%AD.md#L1-L61)
- [固定提案00002实施记录：GADT、依值类型与待办](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E6%8F%90%E6%A1%88/00002-%E5%AE%9E%E6%96%BD%E8%AE%B0%E5%BD%95.%E6%B1%89%E8%AF%AD.md#L5-L18)
- [固定提案00002剩余限制](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E6%8F%90%E6%A1%88/00002-%E5%AE%9E%E6%96%BD%E8%AE%B0%E5%BD%95.%E6%B1%89%E8%AF%AD.md#L139-L157)
- [固定技术规范总纲：兼容基线与新增规则](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%94%E7%94%A8/%E8%B1%AB%E8%A8%80%E7%BC%96%E8%AF%91%E5%99%A8/%E6%96%87%E6%A1%A3/%E8%AF%AD%E8%A8%80%E6%8A%80%E6%9C%AF%E8%A7%84%E8%8C%83/%E6%80%BB%E7%BA%B2.%E6%B1%89%E8%AF%AD.md#L1-L23)
- [固定操作系统目录说明：宿主与系统组件](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E8%B1%AB%E8%A8%80%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F/%E6%80%BB%E8%A7%88.%E6%B1%89%E8%AF%AD.md#L1-L13)
- [固定VS Code插件版本与命令配置](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/%E5%BA%94%E7%94%A8/%E5%BC%80%E5%8F%91%E5%B7%A5%E5%85%B7/yuyan-vscode/package.json#L1-L52)
- [固定AGPLv3许可](https://github.com/yuyan-lang/yuyan/blob/78f66573f8af7c33747958211aae36a8646e805f/LICENSE#L1-L15)
- [历史根提交：UltimatePea与2021-10-14开发记录](https://github.com/yuyan-lang/yuyan/commit/21e8c83c9ff0ad387603d661c8085edf380d56d0)
- [仓库公开元数据：创建日期与归档状态](https://api.github.com/repos/yuyan-lang/yuyan)
- [v0.1.0alpha1：现存最早发行条目](https://github.com/yuyan-lang/yuyan/releases/tag/v0.1.0alpha1)
- [v0.1.0rc1：作者记录首个可用自举版本](https://github.com/yuyan-lang/yuyan/releases/tag/v0.1.0rc1)
- [v0.3：OCaml实现阶段](https://github.com/yuyan-lang/yuyan/releases/tag/v0.3)
- [v0.1.0rc2.0：LLM与恢复自举的作者说明](https://github.com/yuyan-lang/yuyan/releases/tag/v0.1.0rc2.0)
- [v0.4正式发行](https://github.com/yuyan-lang/yuyan/releases/tag/v0.4)
- [持续Wasm工具链发行](https://github.com/yuyan-lang/yuyan/releases/tag/continuous-binaries)


本条按2026-10-11要求完成一次性快照；后续普查沿其他语言与内核项目推进。
