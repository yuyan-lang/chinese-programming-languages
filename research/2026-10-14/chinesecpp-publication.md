# ChineseCpp 与 ChineseCplus 前身资料收录

核验日期：2026-10-14。对应 Issue #16 的 ChineseCpp 子项，收录为 lang-101；前身与后续仓库按作者明确链接归并。

## 本次解决的有限范围

原线索只有 ChineseCpp 的两文件仓库。本次沿同作者仓库找到已归档的 -ChineseCplus，README 明确宣布弃用并链接 ChineseCpp。前身 main/cop.h 和 main/main.cpp 提供中文宏层的实际定义和连续原程序，足以完成这一阶段的分类收录。

类别为 C++ 中文关键字与标准库别名宏层。新仓的具体实现、兼容性和正式发行继续待核实。Issue #16 余下 SPCNYY、ChineseJava 保持开放；本次资料分类完成后累计为5/7。

## 固定证据

- [原始待核议题](https://github.com/yuyan-lang/chinese-programming-languages/issues/16)
- [前身README：宏层定位及后续仓库链接](https://github.com/JinSuperOfficial/-ChineseCplus/blob/035a0433eb215d8843774662912a40dd026f4ef4/README.md)
- [固定中文宏定义](https://github.com/JinSuperOfficial/-ChineseCplus/blob/035a0433eb215d8843774662912a40dd026f4ef4/main/cop.h)
- [固定完整原始程序](https://github.com/JinSuperOfficial/-ChineseCplus/blob/035a0433eb215d8843774662912a40dd026f4ef4/main/main.cpp)
- [前身MIT许可正文与版权占位符](https://github.com/JinSuperOfficial/-ChineseCplus/blob/035a0433eb215d8843774662912a40dd026f4ef4/LICENSE.txt)
- [新仓README](https://github.com/JinSuperOfficial/ChineseCpp/blob/739f835d2bb38202ec08c2cbf30793df152abb6a/README.md)
- [新仓MIT许可与署名](https://github.com/JinSuperOfficial/ChineseCpp/blob/739f835d2bb38202ec08c2cbf30793df152abb6a/LICENSE)
- [前身固定源码树](https://github.com/JinSuperOfficial/-ChineseCplus/tree/035a0433eb215d8843774662912a40dd026f4ef4)
- [前身仓库元数据](https://api.github.com/repos/JinSuperOfficial/-ChineseCplus)
- [新仓仓库元数据](https://api.github.com/repos/JinSuperOfficial/ChineseCpp)
- [前身保留提交历史](https://api.github.com/repos/JinSuperOfficial/-ChineseCplus/commits?per_page=100)

前身提交035a0433eb215d8843774662912a40dd026f4ef4，完整树12项且truncated=false；新仓提交739f835d2bb38202ec08c2cbf30793df152abb6a，完整树2项且truncated=false。

main/cop.h blob为20797444c9eaffd1048b1631cfa4853331e00533，定义中文类型、if/for及标准库名称的预处理宏，mian()映射main()，枚举零取值0。main/main.cpp blob为99f9092570eeed6b15a92d85ddcec38846247e64。网页采用第13—16行完整条件语句短引，14个空白分词，保留Tab缩进；完整原程序第3—18行位于源链接，依赖cop.h及外围循环变量。

前身LICENSE.txt含MIT正文与[year]/[fullname]版权占位符；新仓LICENSE含MIT正文及2026 JinSuperOfficial署名。作者与许可字段按阶段保存。

前身创建2026-08-24T06:56:35Z，根提交07ac451765bf2b9644e0e9b66a0cfaa0209842d4记录06:56:03Z；源码加入b3284c6bc82837b65d5b2e9c8004fec403cf9a51记录06:56:26Z；迁移说明记录2026-08-30T03:14:35Z。新仓创建2026-08-30T03:09:52Z，唯一根提交03:09:53Z。上述均为UTC。首次对外公开日期继续待核实。

## 检索与遗漏风险

平台：GitHub原仓、同作者仓库、提交与文件API，辅以网页精确名称检索。关键词：JinSuperOfficial ChineseCpp、ChineseCplus、chinese-OrientedProgramming，以及原Issue中的ChineseJava/SPCNYY名称。时间范围覆盖保留历史2026-08-24至2026-10-14核验日。检索索引、已删除仓库、仓外发行和未公开历史仍有遗漏风险。

SPCNYY本轮沿用既有词元替换实现证据，连续原始用户程序待核。ChineseJava官网读取失败，现存检索结果保留遗漏风险。两项继续开放。与其他作者的Chinese++项目分开记录，源码继承关系待核实。

## 范围与审阅

只新增目录记录、对应静态资料页和本研究记录。既有100项对象完整保留，豫言、内核页面及站点脚本样式保持原样。候选安装、编译、执行、测试和二进制下载均为0。提交前核对27字段结构、原例、固定链接与文案；PR完整diff、适用检查和冲突另行复核。
