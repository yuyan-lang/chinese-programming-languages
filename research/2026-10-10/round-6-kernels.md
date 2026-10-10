# 第六轮内核资料：NeoAetherOS／na-kernel

核验日期：2026-10-10。研究范围为公开网页、只读 GitHub 内容及 公开网页浏览器中的 Bilibili 原片页面。交付建议：新增 NeoAetherOS／na-kernel 一项，继续保存源码沿革和独立运行的待核实清单。

## 本轮结果

- 新发现项目数：0 项。
- 旧线索核实数：1 项，即 Issue #18 的 NeoAetherOS／na-kernel。
- 旧线索达到目录收录条件：1 项；建议正式条目增加 1 项。
- 已完成去重：现有 DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380 六项，以及 Issue #13 的 KunOS、NeoRunST。
- 主要增量：作者与源码关联、中国工作室公开关系、三个 2025 年原视频地址、可读桌面画面、内核与系统构建分离、根许可证历史。
- 内核固定快照：[2c45649144afa3dd2e32147d7029e354dc9fc518](https://github.com/aether-os-studio/na-kernel/commit/2c45649144afa3dd2e32147d7029e354dc9fc518)，提交时间 2026-08-24T05:49:13Z。

## 1. 作者、社区归属及原视频关联

[2025-05-18 GCC 原片](https://www.bilibili.com/video/BV1f3JGzwE9u/)的简介明确写明 NeoAetherOS 由 [VOID2913](https://space.bilibili.com/3546729567750733) 开发，注明宏内核定位，并列出 github.com/aether-os-studio/naos。

[2025-07-18 桌面原片](https://www.bilibili.com/video/BV1WJu1zzEWn/)由 [XIAOYI80386](https://space.bilibili.com/3537113156946497) 发布。简介直接关联 VOID2913 和同一源码地址。作者说明涉及 Xorg、x86_64、aarch64 与 Linux 系统调用兼容。

[2025-09-26 JVM 原片](https://www.bilibili.com/video/BV1iynGzYE3E/)由 VOID2913 发布，简介报告 Java Hello world 运行进展，页面包含“国产”标签。标准 DOM 元数据 video:release_date 为 2025-09-26T13:45:41.000Z；桌面片为 2025-07-18T11:49:49.000Z。网页在浏览器中会重绘为本地时区显示，公开日期采用上述 UTC 元数据及对应自然日。

[XINGJI Studio 官方成员页](https://www.xingjisoft.com/about/)将 VOID2913 列为 XJ380 副总工程师，并提示 Bilibili 同名账号；同页列出 XIAOYI80386 的 CoolPotOS 开发者角色。[工作室 GitHub 组织主页](https://github.com/xingji-studio)自述所在地为中国，并链接该官网。此处保存公开项目角色和工作室关系。NeoAetherOS 的源码维护组织记录为 aether-os-studio。

[GitHub 固定提交](https://github.com/aether-os-studio/na-kernel/commit/2c45649144afa3dd2e32147d7029e354dc9fc518)关联提交账号 lihanrui2913。条目分别列出该 GitHub 账号和 VOID2913 的公开角色。两账号的直接互链继续待核实。

上述证据支持按作者发布页及公开中国社区关系收录。个人国籍继续按明确的自述证据处理。

## 2. 画面与功能证据分层

- 作者声明：[2025-05-18 视频](https://www.bilibili.com/video/BV1f3JGzwE9u/)说明约 100 个 Linux 系统调用和 GCC、Lua、GNU nano、Bash 等软件进展；数字对应该视频阶段。
- 作者声明：[2025-10-12 README](https://github.com/aether-os-studio/na-kernel/blob/6b18ceb2b95590ac2d5385dd142416dbd1d63ebf/README.md)记述 SMP、ACPI、网络、Linux/POSIX 兼容与 Weston 等软件。
- 作者演示：[桌面原片](https://www.bilibili.com/video/BV1WJu1zzEWn/)01:02 可见青绿色桌面、xeyes 眼睛窗口和终端窗口；字幕将其说明为移植软件在 Xorg 中的表现。
- JVM 原片简介按作者声明记录。具体运行输出、退出状态、拍摄构建和当前源码版本的对应继续待核实。
- 独立运行：待核实。本轮交付覆盖资料、源码静态阅读和原片画面。

## 3. 源码起点、分离与路径沿革

[现存根提交](https://github.com/aether-os-studio/na-kernel/commit/d7d9570a4aaeafae969487ce2cb32e4ab8456f8d)时间为 2025-04-26T01:27:21Z；[当日提交集合](https://api.github.com/repos/aether-os-studio/na-kernel/commits?until=2025-04-27T00:00:00Z&per_page=100)显示其 parents 为空。[根 README](https://github.com/aether-os-studio/na-kernel/blob/d7d9570a4aaeafae969487ce2cb32e4ab8456f8d/README.md)保留 Limine C Template 标题，[根 LICENSE](https://github.com/aether-os-studio/na-kernel/blob/d7d9570a4aaeafae969487ce2cb32e4ab8456f8d/LICENSE)保存 mintsuki and contributors 许可文字。此为当前保留历史的模板起点。

[后续当日 README](https://github.com/aether-os-studio/na-kernel/blob/e50f4a900c945bc9beca21c3e6f8f60a5460ccb5/README.md)使用 Next Aether-OS 名称。[na-kernel 元数据](https://api.github.com/repos/aether-os-studio/na-kernel)中的稳定仓库 ID 为 973050278，created_at 为 2025-04-26T06:33:04Z。仓库创建与本地提交时间分项记录。

2025 年视频引用 aether-os-studio/naos。[2026-03-31 README](https://github.com/aether-os-studio/na-kernel/blob/1d94ef6ca62cf8c09ec3adc64989ca99efd7246b/README.md)的徽章和文档链接同样使用该旧路径，相关提交保存在现内核仓库历史中。

[2026-07-23 提交 85fc8c1](https://github.com/aether-os-studio/na-kernel/commit/85fc8c140c8bc7f5c57dad91e25ac4383cbf56d0)将 README 改为 na-kernel，保留内核和可加载模块，拆分用户态和镜像构建。[当前 naos 元数据](https://api.github.com/repos/aether-os-studio/naos)为独立仓库 ID 1309511798，created_at 为 2026-07-23T04:23:27Z；[根提交](https://github.com/aether-os-studio/naos/commit/6cae733fbef5be83724d15d66cbf36ed1d847ca3)时间为 2026-07-23T04:27:06Z。

[当前系统工程 README](https://github.com/aether-os-studio/naos/blob/20ab03a5a8c4201f1cf2df31ee1aa1ed5204120b/README.md)明确为 na-kernel 提供用户态、initramfs、镜像及 NixOS/Void Linux rootfs 构建。[VOID2913 的 2026-07-25 发布页](https://www.bilibili.com/video/BV15Q3u6UEwD/)标题关联 na-kernel 与 NixOS。

旧 aether-os 阶段代码继承范围、仓库更名操作时间和平台迁移公告继续待核实。2025 年视频的历史源码链接与 2026 年新建同名系统工程分别记录。

## 4. 当前固定源码事实

固定前缀：https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/

- kernel/GNUmakefile：接受 x86_64、aarch64、riscv64、loongarch64；定义 Limine、SBI、laboot、x86_64 Linux boot protocol 条件。编译入口使用 GNU C11、汇编、freestanding 与 nostdlib 等参数。
- kernel/src/init/main.c 78–145 行：启动、页帧、页表、中断、设备、VFS、initramfs、模块链接及任务初始化。
- kernel/src/init/thread.c 36–95 行：PCI、虚拟文件系统、显示、网络初始化，调用 task_execve("/init", ...)。
- kernel/src/task/sched.c：nice 权重、虚拟时间、时间片、截止时间及红黑树队列维护。
- kernel/src/mm/buddy.c：按阶页块、页面状态和每 CPU 页缓存。
- kernel/src/fs/vfs/vfs_init.c：目录项缓存、挂载命名空间、挂载子系统及文件系统类型注册。
- modules/drivers/block/nvme/nvme.c 1–100 行：DMA 缓冲分配、内存屏障及寄存器读写。
- modules/drivers/drm/virtio-gpu/src/lib.rs：no_std Rust 模块，使用 na_std 注册 VirtIO GPU 设备。
- 完整源码树包含 ext、FAT、tmpfs、procfs、sysfs 与各架构目录。

条目把这些事实标为“源码可见”。四架构实际运行支持、调度正确性及兼容程度继续待运行核验。

## 5. 许可证与第三方组件

[根 LICENSE 变更历史](https://api.github.com/repos/aether-os-studio/na-kernel/commits?path=LICENSE&per_page=100)及固定文本记录：

- 2025-04-26：[MIT 许可](https://github.com/aether-os-studio/na-kernel/blob/df1584b26ed66a110fda147075c059374d0ad927/LICENSE)
- 2025-10-03：[Apache-2.0 许可](https://github.com/aether-os-studio/na-kernel/blob/069b73f86bc90a28ba91bb8522738c825adb5141/LICENSE)
- 2025-10-29：提交 6039aa62339c3b4e49e5a3cb13ca292a2db6c970 将根许可更新为 GPLv3
- 当前固定快照：[根 GPLv3 文本](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/LICENSE)

当前源码内附的第三方记录：

- [uACPI MIT](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/src/acpi/LICENSE)
- [lwIP BSD COPYING](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/modules/net/netserver/lwip/COPYING)
- [TinyCrypt／micro-ecc 许可文字](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/src/libs/tinycrypt/LICENSE.txt)
- [libfdt 文件头](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/src/libs/fdt/libfdt.h#L1-L7)标注 GPL-2.0-or-later OR BSD-2-Clause

以上为已读文件的许可记录。完整组件清单、导入提交与历史许可范围继续待核实。核验时 [Releases 集合](https://api.github.com/repos/aether-os-studio/na-kernel/releases?per_page=100)返回空数组；正式版本继续待核实。

## 检索范围与限制

起点为 AGENTS.md、data/kernels.json、Issue #18、Issue #13 及第五轮内核研究记录。执行平台包括 GitHub 仓库内容、提交、树、分支和 Releases API，公开网页检索及 公开网页浏览器中的 Bilibili 原片与作者空间。

关键词包括 NeoAetherOS VOID2913、NeoAetherOS XIAOYI80386、NeoAetherOS github.com、NeoAetherOS 国产、NeoAetherOS BV、lihanrui2913 China、lihanrui2913 VOID、lihanrui2913 Bilibili、aether-os-studio 中国、aether-os-studio aether-os，以及 GitHub 的 user:lihanrui2913、org:aether-os-studio、aether-os fork:true。查询窗口聚焦 2025-04 至 2026-10。

网页搜索首先返回 Bilibili 索引线索。云浏览器成功读取原片页面并核对完整 BV。部分直接网页请求返回缓存缺失，GitHub 插件和浏览器原页提供后续核验。aether-os-studio/aether-os 仓库请求返回 404。现内核仓库的分支集合返回 main。旧阶段仓库内容继续待核实。

Bilibili 自动连播会跳转视频；原片核验使用标题、URL 和播放器时间共同确认。后续已跳转页面的元数据舍弃。有效标准发布时间限定为已经核对原片标题和 URL 的 JVM、桌面两项。GCC 与 2026-07-25 视频保存原始页面显示日期。

本轮将工作集中于 NeoAetherOS 的已知缺口，新增无关候选为 0。旧 Aether-OS 视频仅作同作者历史线索。当前正式候选与已收录六项及 Issue #13 去重。独立构建、下载项目执行、虚拟机与实机运行留待后续授权范围。

