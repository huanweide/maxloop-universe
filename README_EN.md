**中文** · [README.md](./README.md)

# MaxLoop Quality Universe · Convergence architecture

> Consolidates **40 scattered repositories** into **"1 kernel + 4 fusion flagships + retained anchors + red-ocean discard"**. Every zero-star project gets a clear destination instead of drifting at 0★.

## Overview

The **MaxLoop methodology** (the `maxloop-overlord` repo — the anti-fake-green iteration kernel) is the universe's single kernel. Every other project is sorted by one question — *"can it reuse MaxLoop's convergence brake?"* — into one of four fusion flagships, kept as a retained anchor, or discarded as red-ocean.

One sentence: **MaxLoop (the methodology) is the only kernel; everything else is classified by whether it can reuse the brake.**

---

## Who should read this

- You want the map of the author's project ecosystem and *why* 40 repos were folded into a few.
- You are evaluating the MaxLoop family and want to know which repo is the real engine vs. which are vertical instantiations.
- You maintain many small repos and are thinking about the same convergence problem.

## Who should NOT read this

- You are looking for a runnable tool — this repo is an **architecture document** (see `ARCHITECTURE.md`), not code you install.
- You want a quick start or CLI — those live in the individual flagship repos.

---

## Architecture overview

```
                    ┌─────────────────────────────┐
                    │   maxloop-overlord (kernel)  │
                    │  4 brakes / Oracle Gate /     │
                    │  convergence protocol / anchors│
                    └──────────────┬──────────────┘
                                   │ shared quality criteria + iteration loop
        ┌──────────────┬───────────┴───────────┬──────────────┐
        ▼              ▼                        ▼              ▼
 ┌────────────┐ ┌────────────┐         ┌────────────┐ ┌────────────┐
 │codehealth- │ │  bili-ops  │         │content-    │ │study-      │
 │  loop      │ │(Bilibili)  │         │forge(content)│ │companion   │
 │(code health│ │(anchor uni.)│         │(teaching)  │ │(study aid) │
 └────────────┘ └────────────┘         └────────────┘ └────────────┘
```

---

## Four fusion flagships

| Flagship | Status | Anchor / merged-from | One line |
|---|---|---|---|
| **codehealth-loop** | ✅ built | doctors' 12 axes (8+sec/cyc/dup+enghealth merged) + advverify/forge-safeguard interfaces | Code-health self-healing loop |
| **bili-ops** | 🔜 defining→merge | anchors `bili-subtitle-universal` (12k LOC) + `bili-subtitle-extractor` (CLI twin, folded into cli module) + `bilibili-comment-engine` (private ops) | Unified Bilibili subtitle/ops toolkit |
| **content-forge** | 🔜 defining | `video-brief` + `prompt-refiner` + `book-dissector` + `tech-news-hub`, running MaxLoop's "content quality gate" | Content / teaching-quality loop |
| **study-companion** | 🔜 defining | anchors `zhihuishu-helper` (10★) + `tust-classroom` + `live-subtitle` | Study / teaching-assistant matrix |

---

## Retained anchors (CORE, not merged)

- **novel-smith** — writing flagship, already has built-in MaxLoop-style self-check
- **zhihuishu-helper** — study-companion anchor (10★)
- **bili-subtitle-universal** — bili-ops anchor (12k LOC)

---

## Red-ocean / duplicate → discarded

Pomodoro timers / clipboards / jq replacements / webpage text extraction / terminal completion / archive portals / various single-purpose static-scan leaves — they can't fold into any line, so they are archived locally and, after your confirmation, `gh repo archive`d remotely.

---

## Why this merge (first principles)

1. **Scattered repos each sit at 0★ with no traffic**; folding them into 4 methodology-backed products lets each explain "what problem it solves + its moat".
2. **MaxLoop is a reuse lever** — write the brake once, four lines share it, avoiding re-building quality assurance per project.
3. **Red-ocean tools can't fold into any line** — discard them outright, don't waste maintenance effort.

---

## Details

See [ARCHITECTURE.md](./ARCHITECTURE.md) — includes the full 40-repo fate-mapping table and the concrete merge method for each fusion line.

---

## Roadmap

- [x] Kernel fixed: `maxloop-overlord`
- [x] codehealth-loop flagship built and shipped
- [ ] Define and merge bili-ops
- [ ] Define content-forge
- [ ] Define study-companion

---

## More from huanweide

> A series of open-source efficiency tools; a ⭐ Star helps:

- 📚 Long-form writing — AI novel workshop, local zero-dep rule engine: [novel-smith](https://github.com/huanweide/novel-smith)
- 🎓 Course assistant — Zhihuishu auto-play/continue/AI-answer: [zhihuishu-helper](https://github.com/huanweide/zhihuishu-helper)
- 🎬 Subtitle/video — one-click Bilibili subtitle extraction (zero-key official subtitles): [bili-subtitle-universal](https://github.com/huanweide/bili-subtitle-universal)
- 📺 Live subtitle — real-time subtitles for livestreams/meetings: [live-subtitle](https://github.com/huanweide/live-subtitle)
- ✂️ Video summary — one-click long-video summary: [video-brief](https://github.com/huanweide/video-brief)
- 🖥️ Overview — all the author's open-source projects: [family-showcase](https://github.com/huanweide/family-showcase)
- 🩺 Code health — zero-dep multi-axis static checkup: [doctors](https://github.com/huanweide/doctors)

## License

MIT.
