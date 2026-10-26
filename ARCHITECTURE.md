# maxloop 质量宇宙 · 详细架构与 40 仓命运映射

> 配套 [README.md](./README.md)。本文是「融合概念」的施工蓝图：每个零 star 仓去哪、怎么熔、为什么。

## 1. 内核：maxloop-overlord

四道刹车（R/C/N + 根因闸门）、Oracle Gate + 证据锚点、判别测试（旧红新绿）、逃逸阶梯 + stall guard。**所有融合旗舰共享它作为「质量判据与迭代闭环」**，自己不需要再写一套质量保障。

- 定位：从「一个 skill」升为「任何 agent 任务的质量中台」
- 外接判据可插拔：health 轴（codehealth-loop）、内容达标判据（content-forge）、教学达标判据（video-brief 的「教学式」判据）

## 2. 四大融合旗舰（Convergence Products）

### 2.1 codehealth-loop（✅ 已建成 · 代码健康线）
**模式样板**：maxloop 内核 + 判据插件（judges）+ 收敛协议 + Healer（沙箱验证修复候选，绝不自动改用户代码）。
**已熔**：doctors 8 包核心规则 → 8 个 Python judge（repo/commit/dev/doc/pkg/rel/type/a11y）+ sec/cyc/dup + enghealth（共 12 轴，零依赖离线确定性）；advverify 7 视角、forge-safeguard 护栏为接口预留。
**复用点**：新融合线直接抄这个目录结构与 `run_loop` 收敛逻辑。

### 2.2 bili-ops（🔜 B站线融合）
**锚点**：`bili-subtitle-universal`（12k LOC 油猴脚本，8/10，痛点清晰受众大众）。
**熔入**：
- `bili-subtitle-extractor` = universal 的 CLI/批量孪生版 → 把其批量/CLI 逻辑折叠进 universal 的 `cli/` 模块，extractor 仓库归档弃用（避免两条几乎一样的字幕扒取代码分家）。
- `bilibili-comment-engine`（私有运营工具）→ 作为 bili-ops 的「运营侧」关联项，不公开熔入，仅在 README 交叉引用。
**熔法**：universal 已是成熟产品，不重写；只在仓库内新增 `cli/` 吸收 extractor 的批量能力 + README 加「Unified Bilibili Toolkit」定位。

### 2.3 content-forge（🔜 内容教学线融合）
**主题**：maxloop 驱动的「内容质量门禁」——文本产出先过判据再交付。
**熔入（4 个文本变换产品，共享 maxloop 判据）**：
- `video-brief`：B站视频 → 教学式重写 HTML（教学达标判据 = maxloop 的外部 Oracle）
- `prompt-refiner`：口语 → 提示词（本地零依赖零 Key，受众大）
- `book-dissector`：书籍结构化拆解 CLI（多格式 × 五模板）
- `tech-news-hub`：科技资讯站（8 维深读 + 知识库 + BYOK 助手）
**熔法**：以 `video-brief` 的「教学达标判据」为范式，抽成 maxloop 的可插拔判据；其余三个作为「内容生产模块」挂在同一循环下，统一在交付前跑质量门禁。

### 2.4 study-companion（🔜 学习助手线融合）
**锚点**：`zhihuishu-helper`（10★，智慧树/知到网课助手，自动播放+断点续播+AI 答题）。
**熔入**：
- `tust-classroom`：高校空闲教室查询框架（垂直痛点，有接入体系潜质）
- `live-subtitle`：Windows 本地实时中文字幕（Whisper 本地 + 云端翻译，听障/语言学习刚需）
**熔法**：以 zhihuishu 为锚，tust/live-subtitle 作为「学习场景扩展模块」；不强行合并代码，而是统一品牌 + 共享「学习助手质量门禁」（答题准确率、字幕延迟、查询覆盖率）。

## 3. 全量命运映射（40 仓 · VulnClaw 基准分诊）

| 仓库 | 原 tier | 融合命运 | 说明 |
|---|---|---|---|
| maxloop-overlord | 核心 | **内核** | 质量宇宙唯一内核 |
| novel-smith | 核心 | **锚点保留** | 写作旗舰，已 maxloop 化 |
| zhihuishu-helper | 核心 | **锚点 + study-companion 锚** | 10★ |
| bili-subtitle-universal | 核心 | **锚点 + bili-ops 锚** | 12k LOC |
| advverify | FUSE | 熔入 **codehealth-loop** | AdversarialMatrix 接口 |
| forge-safeguard-20260812 | FUSE | 熔入 **codehealth-loop** | GuardrailLayer 接口 |
| video-brief | FUSE | 熔入 **content-forge** | 教学达标判据范式 |
| live-subtitle | KEEP | 熔入 **study-companion** | 实时字幕模块 |
| prompt-refiner | KEEP | 熔入 **content-forge** | 提示词模块 |
| tust-classroom | KEEP | 熔入 **study-companion** | 教室查询模块 |
| tech-news-hub | KEEP | 熔入 **content-forge** | 资讯模块 |
| book-dissector | KEEP | 熔入 **content-forge** | 书籍拆解模块 |
| bili-subtitle-extractor | KEEP | 熔入 **bili-ops**（折叠进 universal cli） | CLI 孪生 |
| doctors | KEEP | 被 **codehealth-loop** 吸收（保留为 Node 上游参考） | 8 包 monorepo |
| family-showcase | KEEP | **丢弃/归档** | 冗余展示站，已被 codehealth-loop 取代 |
| enghealth | KEEP | **丢弃/归档** | 已被 codehealth-loop EngHealth 轴取代 |
| secscan | ARCHIVE | **丢弃/归档** | 已熔入 codehealth-loop SecScan |
| dupscan | ARCHIVE | **丢弃/归档** | 已熔入 codehealth-loop DupScan |
| cycscan | ARCHIVE | **丢弃/归档** | 已熔入 codehealth-loop CycScan |
| testlite | ARCHIVE | **丢弃/归档** | 已被 codehealth-loop 取代 |
| debtlens | ARCHIVE | **丢弃/归档** | 红海静态扫描 |
| debugdoctor | ARCHIVE | **丢弃/归档** | 红海静态扫描 |
| litdoctor | ARCHIVE | **丢弃/归档** | 红海静态扫描 |
| ghadoctor | ARCHIVE | **丢弃/归档** | 红海静态扫描 |
| awaitscan | ARCHIVE | **丢弃/归档** | 红海静态扫描 |
| chaineye | ARCHIVE | **丢弃/归档** | 红海图谱分析 |
| idiot-index | ARCHIVE | **丢弃/归档** | 红海静态扫描 |
| licguard | ARCHIVE | **丢弃/归档** | 红海静态扫描 |
| forest-focus | ARCHIVE | **丢弃/归档** | 番茄钟红海 |
| floatsnip | ARCHIVE | **丢弃/归档** | 剪贴板红海 |
| recall-cli | ARCHIVE | **丢弃/归档** | 终端补全红海 |
| jpath | ARCHIVE | **丢弃/归档** | jq 替代红海 |
| pagext | ARCHIVE | **丢弃/归档** | readability 红海 |
| track-capped | ARCHIVE | **丢弃/归档** | 内部工具非产品 |
| repodoctor | (漏网叶子) | **丢弃/归档** | doctors 第?轴，已熔入 codehealth-loop RepoDoctor |
| knowledge | PRIVATE | **排除** | 私有知识库 |
| bilibili-comment-engine | PRIVATE | **关联 bili-ops（不公开熔）** | 私有运营 |
| ntr-psychological-therapy | PRIVATE | **排除** | 私有 |
| overlord-loop | PRIVATE | **排除（maxloop 前身）** | 私有研发母体 |
| dsh-memory | INFRA | **排除** | 跨设备记忆同步 |
| huanweide | INFRA | **排除** | Profile 仓库 |

## 4. 执行顺序与门禁

1. **M1（本次）**：本 manifest 立起 + `maxloop-universe` 伞仓库上 GitHub + 实体熔最清晰线（bili-ops：extractor 折叠进 universal）。
2. **M2**：content-forge / study-companion 从「定义」建成「实体旗舰」（复用 codehealth-loop 模式）。
3. **M3**：清理本地重复 checkout（`_work` 重复克隆）、远程归档红海（`gh repo archive`，**需你确认**）、给 4 旗舰统一加 maxloop 质量门禁文档。

## 5. 安全边界（铁律）

- **不擅自删远程仓库**：归档（archive）是 GitHub 原生可逆操作，红海归档等你确认后再 `gh repo archive`；DELETE 一律需你单独说「删除」。
- **Healer 绝不自动改用户代码**：引擎只交付经沙箱验证的修复候选，落地由上层 agent/人执行，二者解耦（继承 forge-safeguard 安全精神）。
- **本地清理均为可逆移动**（移入 `_archive/`），不涉及远程删除。
