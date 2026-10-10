# 语程同名线索：作者署名、发布范围与原例

核验日期：2026-10-10（UTC）。对应[Issue #4](https://github.com/yuyan-lang/chinese-programming-languages/issues/4)。沿用第四轮同名仓库线索，本轮新增项目计数为0。

## 固定资料

- 仓库：[yucheng-lang/yucheng](https://github.com/yucheng-lang/yucheng)，创建时间2026-05-18T05:02:00Z。
- 默认分支固定提交：a5de19574471ea41d0c399b06f6958ae8a746d64，2026-05-19T08:05:54Z。
- [版权声明](https://github.com/yucheng-lang/yucheng/blob/a5de19574471ea41d0c399b06f6958ae8a746d64/语程中文语言版权声明.txt)署名“A米空”，声明保留所有权利。公开文档与程序的再利用范围需按该声明核对。
- [README](https://github.com/yucheng-lang/yucheng/blob/a5de19574471ea41d0c399b06f6958ae8a746d64/README.md)使用语程、YuCheng、YuProg及YCC名称，文档版本v0.4.1；[函数原例](https://github.com/yucheng-lang/yucheng/blob/a5de19574471ea41d0c399b06f6958ae8a746d64/示例/函数与递归.程#L27-L30)文件首行标注v0.4.0。
- 当前可见11次提交；最早提交[366a3ddf2aedec00e03e08d3d009115e975da597](https://github.com/yucheng-lang/yucheng/commit/366a3ddf2aedec00e03e08d3d009115e975da597)，时间2026-05-18T05:04:49Z，包含参考手册与简介两份文档。首次公开日期继续待核实。

## 逐字中文短例

固定函数示例第27—30行：

```text
函程 阶乘(n):
    如果 n <= 1:
        返回 1
    返回 n * 阶乘(n - 1)
```

该原例直接提供中文函数、条件与返回语法。文档说明动态类型、缩进推断、可选“结束”、.程后缀与库导入。具体执行行为留待独立核实。

## 实现与发行证据等级

递归文件树返回269项，truncated=false，含261个文件及35个GUI组件库文件。公开范围包含中文程序、参考文档、VS Code插件及Windows/Linux/macOS文件名的二进制运行入口。Rust 2021、clap、GTK4、Cocoa及独立程序编译能力来自作者说明；Rust解析器源码、构建工程及发行二进制对应关系待核实。GitHub Releases接口本轮返回空集合。当前维护计划待核实。

## 同名关系与下一步

[B站语程原片](https://www.bilibili.com/video/BV1EgKZ6VED9/)发布账号为旭猜囱，原标题以易语言格式描述语法。该视频与A米空署名仓库的公开互链、版本及身份对应继续待核实。本轮将取得的原始署名和语法保存到既有线索，正式目录计数保持原样。

## 检索记录与遗漏风险

平台：GitHub仓库/API、Bilibili原片网页和公开网页搜索。

关键词：`"语程" "旭猜囱"`、`"yucheng-lang" "语程"`、`"YuCheng" "YuProg" 编程`、`"语程" "A米空"`、`"语程" "229305405"`、`"旭猜囱" "语程" "米"`。时间范围：2026年线索及仓库完整可见历史。

原BV网页请求返回内部错误，作者GitHub主页直连返回缓存缺失；仓库、固定文件、提交与完整文件树可读。精确搜索出现较多汉字表噪声，搜索命中情况按本轮检索范围记录。作者主页、视频评论互链与其他发布平台存在遗漏风险。本轮采用静态来源核验。
