# 0623-PM Research Window

**Window:** 0623-PM | Started: 15:47 CST (2026-06-23)
**Workflow:** rwr_mqqcewf0_70b27d1e

---

## 🚨 Top Standout: AOHP (2606.23449) — T1 PRIORITY

**GitHub:** [aohp-os/aohp](https://github.com/aohp-os/aohp) | **37⭐** | Last commit: 2026-06-23

### What is it?
AOHP (Android Open Harness Project) — OS-level agent harness built on AOSP. Treats AI agents as first-class OS actors. Redesigns Android as an agent-native operating environment.

### Why it matters for OpenClaw:
**AOHP explicitly benchmarks OpenClaw** as the agent system running on top of the OS.

| Setting | Completion Rate | Tool Calls | Duration | Tokens |
|---------|---------------|-----------|----------|--------|
| OpenClaw @ stock Android | 54.44% | 233 | 33.94 min | 7.10M |
| **OpenClaw @ AOHP** | **75.56%** | **129** | **18.93 min** | **3.44M** |
| **Delta** | **+21.12%** | **-44.64%** | **-44.21%** | **-51.55%** |

AOHP provides: adaptive UI, OS-managed cross-app memory, fine-grained data-flow tracking, sandboxed sensitive values. OpenClaw runs on AOHP with 44% fewer tool calls and 21% higher task completion.

### Code:
- Languages: Python, TypeScript, Shell, JavaScript
- Structure: `aohp-app/`, `cli/`, `demos/`, `skills/`, `udagen/`
- Skills/ dir = agent skill framework (directly relevant to OpenClaw SKILL.md ecosystem)

### OpenClaw Integration Opportunity:
AOHP could be the reference OS-level harness for OpenClaw agent optimization. Skills/ format compatibility with OpenClaw's SKILL.md should be verified.

---

## 0622 New Papers Verification

| arXiv ID | Title | GitHub | Stars | OpenClaw Relevance | Notes |
|----------|-------|--------|------:|-------------------|-------|
| **2606.23449** | AOHP (Android Open Harness) | aohp-os/aohp | 37 | 🔥 **HIGH — Direct benchmark** | OS-level harness, OpenClaw tested |
| 2606.23416 | Malicious Agent Skills (Locate-and-Judge) | ❌ none found | — | Medium (skill security) | cs.CR, attention-based detection |
| 2606.23678 | AIR (Adaptive Interleaved Reasoning+Code) | ❌ none | 0 | Low | Paper-only, 0⭐ |

---

## GitHub Stars (Live — 0623 15:47 CST)

| Repo | Stars | Δsince 0623-AM | Δ/day | Status |
|------|------:|----------------|-------|--------|
| microsoft/SkillOpt | **8864** | +104 (15h) | ~+166/day | 🚀 SURGE |
| AgentR1/Claw-R1 | **189** | 0 | 0 | 🔥 OpenClaw RL |
| inclusionAI/AWorld-RL | **112** | 0 | 0 | ✅ ICLR2026 |
| aohp-os/aohp | **37** | 🆕 | — | 🚨 TODAY'S COMMIT |
| titanwings/colleague-skill | **19700** | +13 | steady | ✅ |

---

## Monitor: No GitHub Yet

| arXiv ID | Paper | Status |
|----------|-------|--------|
| 2606.12908 | SENTINEL (Failure-driven RL for tool-using agents) | No GitHub |
| 2606.06976 | TRUST (Uncertainty-aligned tool calling RL) | No GitHub |
| 2606.12634 | SGCD (Credit distillation) | No GitHub |

---

## Active Threads (Updated)

1. **AOHP** 🆕 — **37⭐**, aohp-os/aohp, OS-level harness, **OpenClaw benchmarked on it**. T1 priority.
2. **Claw-R1** — 189⭐, AgentR1/Claw-R1, OpenClaw agentic RL middleware
3. **SkillOpt** — 8864⭐, SURGE continuing (~166/day)
4. **AWorld-RL/RODS** — 112⭐, ICLR2026, multi-turn tool-use + RL
5. Malicious Agent Skills — skill security, T2
6. SENTINEL/TRUST/SGCD — monitor for GitHub
7. OpenClaw-Skill (2606.16774) — CSTS by Shunyu Liu group, no code yet
8. Skill-to-LoRA (2606.16769) — SKILL.md → LoRA, no code yet

---

## Scalpel Falsification (Domain direct)

- **AOHP OpenClaw benchmark**: Data from official GitHub README. Numbers are from AOHP's own evaluation. Verify independently if possible.
- **AOHP skills/**: Format unknown — needs compatibility check with OpenClaw SKILL.md
- **AOHP maturity**: Early-stage research prototype, not production-ready
- **Malicious Agent Skills paper**: No GitHub — paper-only. Claims unverified independently.

---

## Notes for Next Window

- **AOHP is the standout** — explicit OpenClaw benchmark + real code + active development
- AOHP skills/ directory may be SKILL.md-compatible — mini-project opportunity
- Need to verify AOHP's skills format vs OpenClaw's SKILL.md
- Triple-service outage: 10th occurrence at 0839 CST, hardening still pending
