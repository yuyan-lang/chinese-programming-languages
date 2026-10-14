# 墨言项目文档语法收录

整理及存档复核日期：2026-10-14。原始README和src目录读取日期：2026-10-13。对应Issue #26，收录为lang-102。

## 有限收录范围

本条目以GitCode moyan_lang/moyan_compiler的项目文档与连续中文原例为依据，类别为中文编程语言（项目文档语法核验）。资料来自2026-10-13原页读取记录，2026-10-14复核本仓Issue存档并转录。固定文件逐字对应、Rust实现正文、发行与作者沿革继续由Issue #26跟踪。

项目发布组织为“墨言编程语言”（moyan_lang），所见master头提交关联账号amor2022。原作者身份与团队分工待核实。moyanv2名称及skywalk163所列同名墨言的关系待核实。

## 原例与证据层级

[2026-10-13原始读取存档](https://github.com/yuyan-lang/chinese-programming-languages/issues/26#issuecomment-6151455940)保存README的完整你好世界原例。目录与资料页采用相同连续13行（包含空行），15个空白分词，保留四空格缩进。

```text
篇章 你好世界

引言
    注：添加常量
    恒有 问好 者，为 「你好，墨言！」。
毕

正文
    书 问好。
毕

结语
毕
```

篇章、引言、正文、结语、恒有与书依据此原例记录。README中的递归下降、AST解释执行、VM字节码、原生可执行文件输出及AI开发范围分别归属于作者说明。src目录条目及main.rs、lib.rs等文件名按既有观察记录；词法、语法与执行代码正文待核实。独立运行验证为0。

所见master头为11e0367837834df1f2fb5655a494b4fda9cdec3d；README页面最后修改字段为411b21edf03f03a53d062975d9a96fcf7a4fa47c。两项为页面所示版本定位信息，动态README正文与固定SHA文件的逐字对应待核实。代码来源字段保留动态master路径，并将commit与blob字段的核验缺口显式记录。

README声明MIT License；完整许可正文、版权署名及适用范围待核实。v0.1.0与2025-12-16来自根页侧栏，发行正文、附件、时区和首次公开日期待核实。仓库创建、推送及提交时间字段保持待核实。

## 原始来源与存档

- [墨言原始项目](https://gitcode.com/moyan_lang/moyan_compiler)
- [原始README（动态分支）](https://gitcode.com/moyan_lang/moyan_compiler/blob/master/README.md)
- [2026-10-13原例、目录和访问记录存档](https://github.com/yuyan-lang/chinese-programming-languages/issues/26#issuecomment-6151455940)
- [所见master头提交](https://gitcode.com/moyan_lang/moyan_compiler/commit/11e0367837834df1f2fb5655a494b4fda9cdec3d?ref=master)
- [README页面标注的最后修改提交](https://gitcode.com/moyan_lang/moyan_compiler/commit/411b21edf03f03a53d062975d9a96fcf7a4fa47c?ref=master)
- [原始src文件目录](https://gitcode.com/moyan_lang/moyan_compiler/tree/master/src)
- [v0.1.0发行入口（正文待核实）](https://gitcode.com/moyan_lang/moyan_compiler/releases/v0.1.0)
- [待核议题与剩余缺口](https://github.com/yuyan-lang/chinese-programming-languages/issues/26)

## 检索范围与访问限制

平台：GitCode原项目和本仓GitHub研究记录、议题存档。名称与路径：墨言、Moyan、moyan_lang/moyan_compiler、README.md、src、v0.1.0。时间范围覆盖2026-10-10原始线索、2026-10-13原页补证至2026-10-14存档整理；2025-12-16作为侧栏版本日期保存。本轮沿用已有成果，新增平台搜索为0。

2026-10-13读取Cargo.toml时原站提示访问频次限制与登录要求，后续请求停止。本轮直接复核公开GitHub存档。动态分支变动、固定正文缺口、发行加载外壳、同名项目和未公开历史构成遗漏风险。

## 资料范围与审阅

仅新增lang-102目录对象、静态资料页及本研究记录。既有101项完整保留。豫言、内核、脚本与样式保持原样。安装、构建、测试、候选执行及二进制下载均为0。提交前核对27字段结构、转录原例、链接及事实限定；完整PR差异、适用检查及冲突由合并前审阅核实。Issue #26保持开放，下一步限于固定原例、lexer→parser→执行入口及发行和作者身份对应。
