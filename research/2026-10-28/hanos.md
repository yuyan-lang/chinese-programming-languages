# HanOS：按中国关联、国籍待核实完成收录

核验日期：2026-10-28（UTC）。百科基线为 `f6e83511d97bdf78b68b6665fb58bbde74b96c36`，114项语言、24项内核。本轮用户明确批准仅对 HanOS 采用“中国关联、国籍待核实”的收录范围。贡献分支为 `contrib/hanos-20261028`。

已完整阅读根AGENTS.md、当前目录、第15轮研究与45项来源候选、2026-10-25／28相关台账，以及本轮快照中的#46正文与全部4条评论。当前checkout没有`.agents/skills`目录。开放PR仅#62与#76；取消合并与草稿边界保持原有状态，Safari待批与B站风控入口未操作。

结果：新增 `data/kernels.json` 的 `hanos` 对象及 `内核/hanos.html`，38项来源。既有24项对象、全部语言与旧研究文件保持原样；索引和总台账由汇总任务更新。本条目的作者所在地、中文文档与国籍分别记录，这一批准适用于HanOS本项目。

## 实际中国关联与原作者发布链

[GitHub公开作者API](https://api.github.com/users/jjwang)由汇总任务本轮直接读取，HTTP200，响应Date为 **Wed, 28 Oct 2026 09:19:40 GMT**，核验完成时间09:20:34Z。公开字段为 `login=jjwang`、`id=1480750`、`name=JW`、`location=Beijing, China`、`blog=''`、`bio=null`。原始响应1304字节，SHA-256为 `ebe01997feea3807348ac4cb5d708961a77a9c296ac0de97fe4a20f2dcd44243`。缓存字段为public max-age=60／s-maxage=60，Last-Modified为2026-10-26T23:32:39Z。

所在地字段作为作者自述的中国关联，国籍待核实。[当前根MIT许可](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/LICENSE)署名JW, HanOS developer。[中文README](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/README.zh-cn.md)和技术文档分别是项目公开文档事实。

本轮重新打开两条OSDev原帖，直接正文可读：[2021公告](https://forum.osdev.org/viewtopic.php?p=337922)由junjie发布并直链jjwang/HanOS；[2026年HD520帖](https://forum.osdev.org/viewtopic.php?p=354923)同样直接给出原仓。项目发布关系依据这些直接链接记录。此前中文Wiki讨论中的native Chinese speaker属于zhang3的发言；本条目未据该引文判断HanOS作者身份或国籍。

## 当前固定源码与自身内核链

当前mainline固定为 [`b449b6fe`](https://github.com/jjwang/HanOS/commit/b449b6fed18ac820cd20fa3a7f519056e59a2867)，提交时间 **2026-10-26T12:10:55Z**。完整树308项，truncated=false。旧 `089ce1cd`（2026-10-10）、`c4572824`（2026-10-18）留在既有研究，按各自历史阶段引用。

| 环节 | 当前直接依据 | 核对结果 |
| --- | --- | --- |
| 引导与链接 | [内核规则](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/GNUmakefile)、[链接脚本](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/linker.ld) | C／GNU11与x86汇编，freestanding／nostdlib，独立hanos.elf、ELF64 x86-64与kmain入口。 |
| 内核入口 | [kmain](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/kmain.c#L277-L495) | 读取Limine信息，自行初始化IDT／GDT、物理与虚拟内存、APIC／SMP、系统调用及调度。 |
| 内存 | [vmm](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/mm/vmm.c#L318-L435)、[buddy](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/mm/buddy.c)、[memobj](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/mm/memobj.c) | 建立PML4映射与CR3，伙伴分配物理页，共享内存对象按用户权限映射。 |
| 调度与用户进程 | [调度切换](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/proc/sched.c#L174-L286)、[ELF装载接入](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/proc/sched.c#L834-L900) | 每CPU运行队列、到期睡眠者唤醒、TSS／系统调用栈更新与地址空间切换；sched_execve创建PROC_USER_MODE并装载ELF。 |
| IPC与权限 | [endpoint](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/ipc/ipc.c)、[句柄](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/ipc/object.c)、[路由](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/router/router.c) | 有锁消息队列与等待键；句柄槽／代数／权限检查；临时应答endpoint及服务对象转移。 |
| 中断服务 | [IRQ对象](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/ipc/irq.c) | 绑定中断线到endpoint，以IRQ_NOTIFY_TAG传递通知。 |
| 用户服务 | [VFS适配](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/srv/vfs_srv.c#L42-L120)、[用户构建](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/userspace/GNUmakefile#L77-L83) | /bin/vfs由用户进程装载，授予endpoint及只读initrd；block、fat32、ext2、console、input、net、pipe、process、tty等分别构建。 |
| 接口层 | [编号](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/include/syscall_nr.h)、[分派](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/proc/syscall.c#L3976-L4098) | 对应调用沿用Linux x86-64编号，HanOS扩展位于0x400以上，musl链接用户态。 |

作者将其定位为混合微内核；上述具体代码提供自身内核、IPC与用户服务分工依据。内核保留引导与部分设备驱动，严格隔离、ABI完整性及实际运行分别待核。源码静态可见、作者硬件测试声明与独立运行按不同层级保存。

## 当前与历史文档阶段

- **FAT32**：当前README仍称只读；[当前源码](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/userspace/servers/fat32.c#L1289-L1388)已有FAT_CREATE／WRITE／TRUNC／UNLINK分派。[10月23日作者记录](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/attic/2026/2026-10-23-fat32-write-and-vfs-persistence-zh.md)说明8.3名称写入及VFS的ext2 `/.vfs-store`持久化。条目保留文档／源码分层，正确性和恢复覆盖待核。
- **线程**：[musl说明](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/3rdparty/musl/README.md)保留CLONE_VM限制；[当前k_clone](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/proc/syscall.c#L2101-L2142)与process_clone已有共享地址空间线程路径。完整pthread／信号运行待核。
- **服务恢复**：设计文档局限段保留停域描述；[svc_monitor](https://github.com/jjwang/HanOS/blob/b449b6fed18ac820cd20fa3a7f519056e59a2867/kernel/srv/svc_monitor.c)已有服务下线后重启回调。内部状态恢复按具体实现与运行覆盖待核。
- **Limine**：当前根规则选择v8.x-binary；内核规则要求随仓limine.h，缺失时报告错误。旧089ce研究中的trunk头文件下载是历史事实，条目分别记录。musl1.2.5与libvterm0.3.3位于当前3rdparty移植说明，精确上游SHA与完整分发许可另行待核。

根MIT许可与基础VERSION 0.1.2已直接核对。version.sh文本追加构建日期YYMMDD；本轮没有执行该脚本。

## 上游与同名边界

2021年OSDev完整对话中，ToaruOS作者指明早期cmos与键盘文件来源；junjie回应已删除相关代码、将按许可调整，并记述受到ToaruOS启发。条目按历史对话保存，当前精确继承文件和许可保留继续待核。

HanOS-rs沿用2026-10-13评论已核的 `a39ea39c` Rust裸机启动原型；当前C版的继承／重写关系待核。2007—2008年其他作者同名HanOS单独消歧。9月30日作者原帖记述HD520实机、Ubuntu光标及AI辅助调试；本轮读取文本，未新增图像观察或运行验证。完整许可、AI工具／模型／比例及人工复核范围保留字段。

## 最终处理与评论草稿

作者公开所在地提供实际中国关联，用户已批准以这一有限范围收录本项目；当前核心源码与原作者发布链充分，合理收录分类工作完成。**建议资料PR经独立审阅并合并后，给#46关联证据与PR链接并关闭。** 完整历史、精确ToaruOS／HanOS-rs关系、全部许可及独立运行继续作为条目待核字段。

> 按本轮已确认的“中国关联、国籍待核实”范围完成HanOS收录。2026-10-28作者公开API为jjwang／JW，location自述Beijing, China（HTTP200，Date 09:19:40 GMT），所在地与国籍分别记录；中文文档及OSDev原作者发帖直链建立项目发布关系。当前mainline固定b449b6fe（2026-10-26T12:10:55Z），已静态核对独立ELF／Limine入口、内存与调度、句柄endpoint IPC、IRQ消息和用户态服务启动链。条目区分当前FAT写入与旧只读描述、线程与musl说明、服务重启及随仓limine.h阶段。ToaruOS精确继承、HanOS-rs和其他同名项目、完整许可、AI范围及独立运行继续列为条目待核。收录分类已完成；本轮候选安装、构建、启动、挂载和执行均为0。

## 原件摘要与检查

[hanos-evidence.json](hanos-evidence.json)复制本轮作者API回执，列固定源码URL、缓存路径及缓存文本SHA-256；缓存位于 `/tmp/hanos-read-20261028/`，仅供静态阅读。完整固定提交URL是技术陈述的版本基准。

交付检查覆盖JSON、唯一id、旧24对象比较、source_ids闭合、HTML来源标题／锚点和本地文件链接、diff空白；当前内核数组25项，索引及总台账留汇总任务统一更新。本组不push、创建PR、评论、关闭或合并，不手动触发部署。所有候选安装、构建、启动、挂载、测试与执行均为0。
