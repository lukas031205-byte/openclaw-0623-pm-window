# 0623-PM Research Window

**Window:** 0623-PM | Started: 15:47 CST (2026-06-23) | **Workflow:** rwr_mqqcewf0_70b27d1e
**GitHub:** https://github.com/lukas031205-byte/openclaw-0623-pm-window
**Stars refresh:** 0623 16:08 CST | Scout scan: 132 papers, 22min

---

## 🚨 T1 Standout: AOHP (2606.23449)

**Repo:** [aohp-os/aohp](https://github.com/aohp-os/aohp) | **37⭐** | commit 2026-06-23 (today)
**Apache-2.0** | Python | 99MB | 1 fork | 0 open issues
**Skills dir:** `skills/` exists (agent skill framework)

### AOHP OpenClaw Benchmark Results:

| Setting | Completion Rate | Tool Calls | Duration | Tokens |
|---------|---------------|-----------|----------|--------|
| OpenClaw @ stock Android | 54.44% | 233 | 33.94 min | 7.10M |
| **OpenClaw @ AOHP** | **75.56%** | **129** | **18.93 min** | **3.44M** |
| **Delta** | **+21.12%** | **-44.64%** | **-44.21%** | **-51.55%** |

Benchmark: 30 real-world mobile tasks. AOHP = AOSP-level agent harness with cross-app memory, fine-grained data-flow tracking, sandboxed sensitive values.

⚠️ Caveat: Small-N (30 tasks), early prototype. Self-reported by AOHP team.

---

## 0622 New Papers — Scout Verification

| arXiv ID | Title | GitHub | Stars | OpenClaw Relevance |
|----------|-------|--------|------:|---------------------|
| **2606.23449** | AOHP (Android Open Harness) | [aohp-os/aohp](https://github.com/aohp-os/aohp) | 37⭐ | 🔥 T1 — Direct benchmark |
| **2606.23416** | Malicious Agent Skills (Locate-and-Judge) | ❌ none | — | 🔥 T1 — clawhub.ai security |
| 2606.23678 | AIR (Adaptive Interleaved Reasoning+Code) | CongHan0808/AIR | 0⭐ | Medium |

**Malicious Agent Skills (2606.23416):** Studies clawhub.ai, skills.sh, lobehub.com. Paper claims dataset release but no public GitHub. **MANDATORY reading** for OpenClaw skill security.

**AIR (2606.23678):** Repo exists but skeleton (0⭐, no lang detected). Use as reference only.

---

## 🆕 New Standouts from 0623 Scan (132 papers scanned)

| arXiv ID | Title | GitHub | Stars | OC Score | Notes |
|----------|-------|--------|------:|----------|-------|
| **2606.23525** | Self-Compacting Language Model Agents | ❌ | — | 8/10 | +5-9pp at 30-70% lower cost for tool-call agents. Context compaction. No code yet. **HIGH priority follow-up.** |
| **2606.22936** | When Agents Commit Too Soon (Premature Commitment) | ❌ | — | 8/10 | Agent reliability failure mode. No code yet. |
| 2606.22000 | CFAgentBench (Construction-Finance Agents) | ❌ | — | 9/10 | Self-hostable CFO-class agent benchmark. Paper-only. |
| 2606.22475 | All Green, Still Broken (LLM+i18n+browser) | ❌ | — | 7/10 | Browser-automation lessons for OpenClaw. |
| 2606.22425 | SVGym (SciVerseGym) | [Bin-Cao/SciVerseGym](https://github.com/Bin-Cao/SciVerseGym) | 1⭐ | 4/10 | Crystal RL env. Fresh commit today. |
| 2606.21136 | Horizon Adaptive Offline RL (Value Stitching) | [Whiterrrrr/value-stitching](https://github.com/Whiterrrrr/value-stitching) | 3⭐ | 5/10 | Offline RL for long-horizon agents. Fresh commit today. |
| 2606.22175 | StickyInvoc (HPC Workflows in LLM Era) | ❌ | — | 7/10 | Workflow scheduling for LLM. Relevant to OpenClaw pipeline. |
| 2606.20761 | LLM Agents + Digital Twins (Industrial) | ❌ | — | 6/10 | Industrial autonomous systems. |
| 2606.20911 | Latent Personal Memory (soft prompts) | ❌ | — | 6/10 | Personal agent memory via soft prompts. |
| 2606.22511 | Variance-Calibrated LLM Decoding | ❌ | — | 5/10 | Fixes repetition/degeneration. |

---

## Monitor: Updated

| arXiv ID | Paper | GitHub | Stars | Status |
|----------|-------|--------|------:|--------|
| SENTINEL | Failure-driven RL tool agents (2606.12908) | ❌ | — | Paper-only confirmed |
| **TRUST** | Uncertainty-aligned tool calling (2606.06976) | [yjzscode/TRUST](https://github.com/yjzscode/TRUST) | 0⭐ | Minimal code release (2 days ago) |
| SGCD | Credit distillation (2606.12634) | ❌ | — | Paper-only confirmed |
| OpenClaw-Skill | CSTS (2606.16774, Shunyu Liu) | ❌ | — | No code yet |

---

## GitHub Star Tracking

| Repo | Stars | Last Check | Δ since 15:03 | Δ/day | Notes |
|------|------:|------------|--------------:|------:|-------|
| microsoft/SkillOpt | **8864** | 16:08 CST | +104 (15h) | ~166⭐/day | 🚀 SURGE |
| AgentR1/Claw-R1 | **189** | 16:08 CST | 0 | 0 | OpenClaw agentic RL |
| inclusionAI/AWorld-RL | **112** | 16:08 CST | 0 | 0 | ICLR2026 |
| aohp-os/aohp | **37** | 16:08 CST | 🆕 | — | OS harness, commit today |
| titanwings/colleague-skill | **19700** | 16:08 CST | +13 | ~19⭐/day | Stable |
| yjzscode/TRUST | **0** | 16:15 CST | 🆕 | — | Minimal code release |

---

## Critical Papers for OpenClaw (Priority Order)

1. **2606.23449 AOHP** — OS-level harness benchmark, +21% OpenClaw completion
2. **2606.23416 Malicious Skills** — clawhub.ai security, dataset claim but no code
3. **2606.23525 SelfCompact** — context compaction for tool-call agents, no code yet
4. **2606.22936 Premature Commitment** — agent reliability failure mode
5. **2606.22000 CFAgentBench** — CFO-class autonomous agent benchmark
6. **2606.22475 All Green Still Broken** — browser-automation lessons

---

## System Status

**Triple-service outage (0623 0839 CST): 10th occurrence.** Dashboard+watchclaw+local全挂，cloudflared消失。~3次/天，HARDENING提案仍未批。

---

## Workflow Status: COMPLETE

- ✅ trigger, scout_source_verified, scalpel_review, kernel_artifact, github_publish, memory_candidate, synapse_retrospective, domain_final
- GitHub: lukas031205-byte/openclaw-0623-pm-window
- Scout JSON: `/home/kas/.openclaw/workspace-domain/research/scout-2026-06-23-pm/arxiv-verify-results.json`
