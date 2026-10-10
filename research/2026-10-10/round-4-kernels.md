# 第四轮内核核验：KunOS

核验日期：2026-10-10；研究时段：16:00–16:08 UTC。正式内核目录保持 5 项，KunOS 通过 [Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13) 继续跟进。

开工前已读取根目录 AGENTS.md、data/kernels.json、research/2026-10-10/kernels.md、round-3-kernels.md 及 Issue #13 现存评论，核对 DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel 五项。公开文本采用直接事实陈述，资料缺口标为待核实。

## 本轮进展

### XKFS 源码与原片对应

固定快照为 [bf1a46593a12365afc7d7fef45518339d7ab0af1](https://github.com/hellopgrmm/KunOS/commit/bf1a46593a12365afc7d7fef45518339d7ab0af1)，提交时间 2026-09-26T12:32:01Z。

- [BINARY/fileman.asm](https://github.com/hellopgrmm/KunOS/blob/bf1a46593a12365afc7d7fef45518339d7ab0af1/BINARY/fileman.asm) 包含 Bascella File Manager(XKFS)、第二软盘 BIOS 读写、超级块、15 个文件表项、创建/读取/目录操作。freesq 扫描各文件结束扇区；fwrite 更新文件表与超级块后写入内容。
- [BK/kernel.asm](https://github.com/hellopgrmm/KunOS/blob/bf1a46593a12365afc7d7fef45518339d7ab0af1/BK/kernel.asm#L342-L348) 的 fm 分派装入应用并远调用 0x0000:0x9E02，与文件管理器入口一致。
- [原作者视频](https://www.bilibili.com/video/BV1Gkho6fEcd/) 01:40 显示同名 XKFS 文件管理器，以及 Create a file、Read a file、Show files、Quit 四项菜单。作者置顶评论说明超级块、空表项和按最大结束扇区安排数据的过程。
- 01:40 放大画面可读 QEMU 参数：-fda IMAGES\\kun.img -fdb empty.img。源码 driven=0x01 对应第二软盘。
- [build.bat](https://github.com/hellopgrmm/KunOS/blob/bf1a46593a12365afc7d7fef45518339d7ab0af1/build.bat) 生成 IMAGES/ikun.img，启动参数指定该第一软盘。
- 已建立菜单、入口及功能实现对应。视频 kun.img、仓库 ikun.img 的二进制一致性，以及第二软盘 empty.img 的制作和初始化步骤待核实。
- 固定 runprog 读取 3 个扇区，fileman.asm 按 6×512 字节填充。实际装入范围、初始化接入、输入边界和持久化行为属于后续独立运行核验项。

[提交记录](https://api.github.com/repos/hellopgrmm/KunOS/commits?per_page=100) 显示，2026-09-26 依次新增 fileman.asm、接入内核、更新镜像、修改 README。内核 info 字符串仍列 KunOS version 2.1 及 2026/8/28 日期。各字段按源码快照和作者录屏分别保存。

### 授权与归属

[固定 README](https://github.com/hellopgrmm/KunOS/blob/bf1a46593a12365afc7d7fef45518339d7ab0af1/README.md) 明确允许下载代码、修改、分发，可记录为“README 自定义授权声明”。[仓库元数据](https://api.github.com/repos/hellopgrmm/KunOS) 的 license 字段为 null。[完整源码树](https://api.github.com/repos/hellopgrmm/KunOS/git/trees/bf1a46593a12365afc7d7fef45518339d7ab0af1?recursive=1) 包含随附 nasm.exe。标准许可证标识、完整条款及随附组件许可归属待核实。

原视频简介关联 hellopgrmm/KunOS；[作者 Bilibili 主页](https://space.bilibili.com/3494379228498773/) 关联 hellopgrmm.github.io，固定内核也列出同一网站。作者 GitHub 档案、Bilibili 主页、个人网站和网站介绍完成核对。中国开发者公开归属依据继续待核实。

### 较早公开记录

同一作者 [2026-07-30 视频](https://www.bilibili.com/video/BV1oN3866EY1/) 属于同一汇编合集，简介列出 boot.asm 与 kernel.asm，可补为较早公开演示。最早公开日期继续待核实。

[作者关联个人网站](https://owllyug.github.io/) 另将 2024 年初的同名 KunOS 介绍为网页模拟项目。该阶段与 2026 年汇编系统按各自来源保存。主页历史文章 cv42229549 的正文读取结果为页面外壳，其版本关系待核实。

## 教学引导辅助线索

KunOS 原片相关推荐指向 [LiDonghan 的 2026-06-11 演示](https://www.bilibili.com/video/BV1ZDEi6UErg/)。作者明确说明代码由 DeepSeek 提供；简介展示 NASM 引导扇区、BIOS INT 10h 文本输出、停驻循环和 0xaa55 签名。01:14 原片显示实体显示器上的 Hello 文本。

此项保存为 AI 辅助 BIOS 教学引导示例。本轮新内核项目数为 0。中国开发者公开归属、许可证、项目定位及版本对应待核实。

## 检索范围与遗漏风险

平台：只读 GitHub 仓库/提交/内容 API、公开网页搜索、Bilibili 原视频/主页/置顶评论/相关推荐、作者网站。视频核对采用原片画面与公开页面。

实际关键词：`"hellopgrmm" KunOS`、`"KunOS" XKFS`、`"hellopgrmm" "中国"`、`"hellopgrmm" "China"`、`"小猫头鹰Owl-" "KunOS"`、`"BV1Gkho6fEcd"`、`site:github.com/hellopgrmm "KunOS"`、`"owllyug"`、`"KunOS" "国产"`、`"hellopgrmm" "关于"`，另对作者别名和排除同名赛车项目的组合进行检索。

时间重点：2026-07-30 较早演示、2026-09-19 仓库创建、2026-09-26 XKFS 发布与提交；2024 年网站项目仅用于沿革边界，教学线索为 2026-06-11。

精确名称搜索召回有限，部分结果为同名赛车项目、猫头鹰词义页面及自动生成聚合文。技术结论采用原作者材料和固定源码。Bilibili 未登录页面展示部分置顶评论，并提示登录查看完整评论。专栏正文读取失败；GitHub tags URL 请求返回工具不支持错误。正式版本采用成功读取的 Releases 集合、提交和源码字符串。本轮 Releases 集合为空数组。

页面本地化时间出现小时偏移，视频日期保存稳定的年月日，提交时间采用 UTC。独立编译、虚拟机及实机运行保持待核实。本轮完成只读研究与资料整理。

