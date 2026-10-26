# maxloop 质量宇宙 · 融合大架构

> 把 40 个散仓收敛成 **「1 内核 + 4 融合旗舰 + 保留锚点 + 红海丢弃」**。
> 每个零 star 项目都有明确归宿，而不是各自 0★ 漂着。

## 一句话

**maxloop-overlord**（防假绿迭代内核）是质量宇宙的唯一内核；其余项目按「能否复用 maxloop 刹车」分进 4 条融合旗舰，或作为保留锚点，红海工具直接丢弃。

## 架构总览

```
                    ┌─────────────────────────────┐
                    │   maxloop-overlord (内核)    │
                    │  四道刹车 / Oracle Gate /     │
                    │  收敛协议 / 证据锚点          │
                    └──────────────┬──────────────┘
                                   │ 共享质量判据 + 迭代闭环
        ┌──────────────┬───────────┴───────────┬──────────────┐
        ▼              ▼                        ▼              ▼
 ┌────────────┐ ┌────────────┐         ┌────────────┐ ┌────────────┐
 │codehealth- │ │  bili-ops  │         │content-    │ │study-      │
 │  loop      │ │(B站线)     │         │forge(内容) │ │companion   │
 │(代码健康✅) │ │(锚universal)│         │(教学线)   │ │(学习助手)  │
 └────────────┘ └────────────┘         └────────────┘ └────────────┘
```

## 四大融合旗舰

| 旗舰 | 状态 | 锚点 / 熔入来源 | 一句话 |
|---|---|---|---|
| **codehealth-loop** | ✅ 已建成 | doctors 12 轴（已熔 8+sec/cyc/dup+enghealth）+ advverify/forge-safeguard 接口 | 代码健康自愈闭环 |
| **bili-ops** | 🔜 定义→熔 | 锚 `bili-subtitle-universal`（12k LOC）+ `bili-subtitle-extractor`（CLI 孪生，折叠进 cli 模块）+ `bilibili-comment-engine`（私有运营） | B站字幕/运营统一工具箱 |
| **content-forge** | 🔜 定义 | `video-brief` + `prompt-refiner` + `book-dissector` + `tech-news-hub`，统一跑 maxloop「内容质量门禁」 | 内容/教学质量闭环 |
| **study-companion** | 🔜 定义 | 锚 `zhihuishu-helper`（10★）+ `tust-classroom` + `live-subtitle` | 学习/教学助手矩阵 |

## 保留锚点（CORE，不熔）

- **novel-smith** — 写作旗舰，已内建 maxloop 式自检
- **zhihuishu-helper** — study-companion 锚点（10★）
- **bili-subtitle-universal** — bili-ops 锚点（12k LOC）

## 红海 / 重复 → 丢弃（用不上的不管）

番茄钟 / 剪贴板 / jq 替代 / 网页正文提取 / 终端补全 / 归档门户 / 各种单一静态扫描叶子 —— 熔不进任何线，本地归档、远程待你确认后 `gh repo archive`。

## 为什么这样熔（第一性原理）

1. **散仓各自 0★ 没流量**；熔成 4 个有方法论的产品，每个都能讲清「解决什么 + 护城河」。
2. **maxloop 是复用杠杆**——一次写好刹车，4 条线共用，避免每个项目重写质量保障。
3. **红海工具熔不进任何线**——直接丢弃，不浪费维护精力。

## 详情

见 [ARCHITECTURE.md](./ARCHITECTURE.md) —— 含 40 仓全量命运映射表与每条融合线的具体熔法。
