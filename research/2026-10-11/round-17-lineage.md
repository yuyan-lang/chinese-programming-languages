# 第十七轮：Chinese++分叉与中文C#编辑器入口去重

核验日期：2026-10-11。目标仓基线：565357c62953e94ea6824b32e801e82622278861，语言目录90项。研究范围为Afiredream/ChinesePlusPlusCompiler及HongshouStudio/-两项，采用GitHub只读元数据、固定文件和提交比较。

## 结果与计数

- 真正新发现项目0项，正式新增0项。
- Afiredream/ChinesePlusPlusCompiler属于既有lang-046 Chinese++，已在目录关系字段及Issue #11第四轮评论记载。此次补齐分叉头、祖先比较、例程blob与日期边界。
- HongshouStudio/-已在第十六轮搜索日志列出。本轮确认其公开Git仓为空，保留一项旧搜索入口的补证记录，正式名称及实现继续待核实。

## 基线与去重范围

已读根AGENTS.md、当前完整data/languages.json（90项）、根目录和递归树、第十六轮总日志、微型语言发现日志相关搜索记录，以及Issue #16和#11正文与全部评论（分别2条、4条）。根AGENTS要求公开技术文档采用肯定陈述，缺口如实标注待核实。

目录中的lang-046已记载Afiredream分叉元数据和YoloLogic同源关系。Issue #11评论明确“Afiredream仓库按同源分叉处理”：
https://github.com/yuyan-lang/chinese-programming-languages/issues/11#issuecomment-6099595783

Issue #16评论已记载ChinesePython和ChineseTypeScript收录，以及ChineseJava继续待核；本轮沿用其项目身份：
https://github.com/yuyan-lang/chinese-programming-languages/issues/16#issuecomment-6099860042

第十六轮“中文关键字”查询结果已有HongshouStudio/-：
https://github.com/yuyan-lang/chinese-programming-languages/blob/565357c62953e94ea6824b32e801e82622278861/research/2026-10-10/round-16-discovery.md

## 1. Afiredream/ChinesePlusPlusCompiler：既有Chinese++分叉

### 身份、固定提交及日期

原仓：https://github.com/Afiredream/ChinesePlusPlusCompiler
GitHub元数据fork=true，parent.full_name与source.full_name均为YoloLogic/ChinesePlusPlus。
默认分支为“主线分支”，分支端点固定头为62a9384017ee397e6cc5cd71988fdc527880a8a6，提交作者及提交者均为YoloLogic，GitHub身份映射同为YoloLogic。

- 分叉仓创建：2026-10-08T14:28:37Z。
- pushed_at：2026-10-08T14:29:04Z。
- 分叉头提交：2026-10-06T02:28:39Z。
- 取得提交列表共13项，署名均为YoloLogic；根提交74a1b1973eeb6f2ad085ec65c2b86cf56085dea6的author时间2026-09-26T20:55:49Z、committer时间21:26:06Z。
- 分叉创建时间用于标记复制入口；语言首发沿用lang-046的原项目来源。
- 上游固定8a528b432a6df276dbe095a97adc868ae4831eac与分叉头比较返回ahead_by=6、behind_by=0，merge_base为分叉头。由此确认分叉头处在既有上游历史链内。

比较证据：
https://api.github.com/repos/YoloLogic/ChinesePlusPlus/compare/62a9384017ee397e6cc5cd71988fdc527880a8a6...8a528b432a6df276dbe095a97adc868ae4831eac

### 原始示例与实现分类

固定vscode-kit/示例.cpp的blob为1b99ebc8355aa6edaa670745f75c4843c42747da，与当前lang-046原例的blob一致。第23—28行连续原文：

```cpp
双精度 合计(常量 std::vector<商品>& 货物) {
    双精度 和 = 0;
    对于 (常量 自动& 件 : 货物)      // 对于 = for，自动 = auto
        和 += 件.单价();
    返回 和;                        // 返回 = return
}
```

来源：https://github.com/Afiredream/ChinesePlusPlusCompiler/blob/62a9384017ee397e6cc5cd71988fdc527880a8a6/vscode-kit/%E7%A4%BA%E4%BE%8B.cpp#L23-L28

函数依赖同文件前文商品类型与vector导入，原例展示中文类型、循环和返回关键字与英文C++库名混用。采用既有分类“Clang/LLVM中文C/C++工具链／中文关键字扩展”。分叉固定树提供Windows工具链二进制、库头、配置和脚本，README将底本记为LLVM/Clang 24.0.0git。核心词元注册及中文诊断的补丁证据沿用lang-046已核验官方Linux平台线，分叉仓的克隆行为和现有文件足以完成同源归档。

README声称编译运行通过；本轮完成静态读取，独立构建、执行、运行结果、兼容性及发布包可重建性继续待核实。

### 版本与许可分层

分叉README下载入口指向上游Chinese++-0.2-win64.zip；分叉Releases返回空数组。根NOTICE版本字段仍保留“Chinese++ <版本号>”占位。读取tags端点收到工具400“not an allowed public GitHub repository or search endpoint”，tag列表状态继续待核实，Releases空数组不外推到tag为空。

固定LICENSE.TXT含Apache License v2.0 with LLVM Exceptions全文，NOTICE将其适用范围表述为LLVM派生内容。当前上游lang-046中v0.3的项目自定义许可按版本与组件单独记录。分叉历史快照的许可材料、后续上游许可及具体原创文件授权范围分别处理。

固定NOTICE另保留早期发行叙述，其“compiler-rt”说明与当前固定树lib/clang/24/lib/windows下可见运行库及README状态存在时间层差异；因此采用实际文件树和对应版本材料分层，旧NOTICE用于记录许可声明与历史说明。

来源：
- https://github.com/Afiredream/ChinesePlusPlusCompiler/blob/62a9384017ee397e6cc5cd71988fdc527880a8a6/README.md
- https://github.com/Afiredream/ChinesePlusPlusCompiler/blob/62a9384017ee397e6cc5cd71988fdc527880a8a6/LICENSE.TXT
- https://github.com/Afiredream/ChinesePlusPlusCompiler/blob/62a9384017ee397e6cc5cd71988fdc527880a8a6/NOTICE.txt
- https://api.github.com/repos/Afiredream/ChinesePlusPlusCompiler
- https://api.github.com/repos/Afiredream/ChinesePlusPlusCompiler/branches/%E4%B8%BB%E7%BA%BF%E5%88%86%E6%94%AF
- https://api.github.com/repos/Afiredream/ChinesePlusPlusCompiler/git/trees/62a9384017ee397e6cc5cd71988fdc527880a8a6?recursive=1

## 2. HongshouStudio/-：旧搜索入口，公开空仓

原仓：https://github.com/HongshouStudio/-

2026-10-11读取的原始仓库描述为：“一款用于中文编程的代码编辑器，第一个版本是基于C#语法而来的编辑器，可编译运行基于中文关键字映射的C#代码”。

GitHub创建时间为2026-09-28T06:50:18Z，updated_at与pushed_at均为当日06:50:19Z。fork=false，size=0，language=null，license=null，default_branch=main。元数据标示的默认分支名与实际分支列表分别记录。

进一步只读核验：
- contents：404，原文“This repository is empty.”
- commits：409，原文“Git Repository is empty.”
- branches：空数组
- releases：空数组

这些响应支持“当前公开Git仓为空”的限定结论。当前证据仅达作者描述层；正式项目名、中文关键字映射内容、原始用户程序、C#编译调用、首版发行及许可均待核实。作者账号记录为HongshouStudio，自然人或组织身份待核实。正式语言计数维持0，后续清单作为旧搜索级候选的补证保留。

## 访问与证据边界

“主线”分支树查询初次返回无可用树，随后按实际默认名“主线分支”和固定提交取得完整树。分支名按仓库原文保留。公开仓库API及固定文本为本轮证据，网页索引名称用于发现，创建日期用于定位仓库。安装、下载执行、编译、远端写入及第三方联系均未进行。



## 既有条目补充
lang-046保留全部原字段、中文原例与15条旧引用，补充祖先比较和固定分叉示例2条来源。其他平台版本与实现核验日期继续按原2026-10-10快照说明，2026-10-11只增补分叉关系。
