# 0623-PM Research Window

**Window:** 0623-PM | Started: 15:47 CST (2026-06-23) | **Workflow:** rwr_mqqcewf0_70b27d1e
**GitHub:** https://github.com/lukas031205-byte/openclaw-0623-pm-window
**Stars refresh:** 0623 16:08 CST

---

## 🚨 T1 Standout: AOHP (2606.23449)

**Repo:** [aohp-os/aohp](https://github.com/aohp-os/aohp) | **37⭐** | commit 2026-06-23 (today)
**Languages:** Python, TypeScript, Shell, JavaScript
**Structure:** `aohp-app/`, `cli/`, `demos/`, `skills/`, `udagen/`, `docs/`, `scripts/`, `AOSP/`, `images/`

### Why AOHP is the standout of this window:
AOHP (Android Open Harness Project) = OS-level agent harness built on AOSP. **Explicitly benchmarks OpenClaw.**

| Setting | Completion Rate | Tool Calls | Duration | Tokens |
|---------|---------------|-----------|----------|--------|
| OpenClaw @ stock Android | 54.44% | 233 | 33.94 min | 7.10M |
| **OpenClaw @ AOHP** | **75.56%** | **129** | **18.93 min** | **3.44M** |
| **Delta** | **+21.12%** | **-44.64%** | **-44.21%** | **-51.55%** |

Benchmark: 30 real-world mobile tasks (GUI op, non-GUI, event capture, multi-source retrieval, memory, hybrid).

AOHP enables: user-defined apps backed by AI agents, cross-app memory, fine-grained data-flow tracking, sandboxed sensitive values.

**Skills/ directory exists** — agent skill framework. Format compatibility with OpenClaw SKILL.md TBD.

⚠️ **Caveats**: Early-stage research prototype. 30-task benchmark is small-N. Self-reported results need independent verification. AOHP team may be potential competitor/integrator for OpenClaw.

---

## 0622 New Papers — Verified

| arXiv ID | Title | GitHub | Stars | OpenClaw Relevance |
|----------|-------|--------|------:|--------------------|
| **2606.23449** | AOHP (Android Open Harness) | [aohp-os/aohp](https://github.com/aohp-os/aohp) | 37 | 🔥 **T1 — Direct benchmark** |
| 2606.23416 | Malicious Agent Skills: Locate-and-Judge | ❌ none found | — | Medium (skill security) |
| 2606.23678 | AIR: Adaptive Interleaved Reasoning+Code | ❌ paper-only | 0 | Low |

---

## GitHub Star Tracking

| Repo | Stars | Last Check | Δ since 15:03 | Δ/day | Notes |
|------|------:|------------|--------------:|------:|-------|
| microsoft/SkillOpt | **8864** | 16:08 CST | +104 (15h) | ~166 | 🚀 SURGE re-accelerated |
| AgentR1/Claw-R1 | **189** | 16:08 CST | 0 | 0 | OpenClaw agentic RL |
| inclusionAI/AWorld-RL | **112** | 16:08 CST | 0 | 0 | ICLR2026 |
| aohp-os/aohp | **37** | 16:08 CST | 🆕 today | — | OS harness, commit today |
| titanwings/colleague-skill | **19700** | 16:08 CST | +13 | ~19 | Stable |

---

## Monitor (No GitHub Yet)

| arXiv ID | Paper | Monitor Since |
|----------|-------|-------------|
| 2606.12908 | SENTINEL (Failure-driven RL for tool-using agents) | 0622-PM |
| 2606.06976 | TRUST (Uncertainty-aligned tool calling RL) | 0622-PM |
| 2606.12634 | SGCD (Credit distillation) | 0622-PM |
| 2606.16774 | OpenClaw-Skill (CSTS, Shunyu Liu group) | 0622-AM |

---

## Active Threads Summary

| # | Topic | Status | Stars | Key Finding |
|---|-------|--------|------:|-------------|
| 1 | **AOHP** | 🆕 T1 | 37⭐ | OS harness benchmarks OpenClaw +21% |
| 2 | Claw-R1 | 🔥 | 189⭐ | OpenClaw agentic RL, real code |
| 3 | SkillOpt | 🚀 | 8864⭐ | ~166⭐/day surge continuing |
| 4 | AWorld-RL | ✅ | 112⭐ | ICLR2026 multi-turn tool-use |
| 5 | Malicious Agent Skills | T2 | — | cs.CR skill security, no code |
| 6 | colleague-skill | ✅ | 19700⭐ | Stable |

---

## Workflow Status

- ✅ trigger
- ✅ scout_source_verified (Domain direct + Scout running)
- ✅ scalpel_review
- ⏳ kernel_artifact (Scout still scanning)
- ✅ github_publish
- ⏳ memory_candidate (staged: mbcand_mqqd6053_b14ba6ae)
- ⏳ synapse_retrospective
- ⏳ domain_final

**Next fallback:** ~20:03 CST (4h from now)
