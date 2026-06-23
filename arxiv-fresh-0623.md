# Fresh arXiv cs.AI Scan — 0623 (Afternoon/Evening UTC)

**Date:** 2026-06-23 | **Window:** 0623-PM autonomous run
**Time:** 20:05 CST (12:05 UTC) | **Scout:** Subagent session 6f8fda4f
**Baseline:** Prior 0623-PM scout captured 132 papers through 2606.23680 (16:08 CST).
**Method:** Fresh query of arXiv API `https://export.arxiv.org/api/query` for `cat:cs.AI`, max_results=200, sorted by submittedDate desc.

---

## ⚠️ Freshness Note

**No cs.AI papers dated 0623 in arXiv listing yet.** The most recent papers in the feed are dated 0622 (last batch 17:59 UTC). arXiv's cs.AI listing is updated in waves, with US-Eastern evening submissions appearing in the feed ~04:00–10:00 UTC the next day. Current UTC time is 12:05 on 0623 — the first 0623-dated batch should appear by ~14:00 UTC.

This scan therefore captures: **(a) papers published after 0623-PM's 2606.23680 cutoff, dated 0622, AND (b) 0621 papers with high OpenClaw relevance missed in earlier passes.**

---

## 🆕 Newly Discovered / High-OpenClaw-Relevance Papers (0622, post-prior-scan)

### T1 — Directly applicable to OpenClaw skill/security design

#### 🔥 2606.23449 — AOHP: An Open-Source OS-Level Agent Harness for Personalized, Efficient and Secure Interaction
**Dated:** 0622 (matches Task 2 investigation)
**Core claim:** AOHP = AOSP-level agent harness; benchmarked OpenClaw agent: completion 54.44% → **75.56%** (+21pp), tool calls 233 → 129, tokens 7.10M → 3.44M (–51.55%).
**Why it matters:** First external benchmark showing OS-level harness design moves the needle for OpenClaw agents. Cross-app memory, fine-grained data-flow tracking, sandboxed sensitive values.
**Code:** [aohp-os/aohp](https://github.com/aohp-os/aohp) 37⭐ Apache-2.0 (already verified in 0623-PM window).
**Status:** **T1 ACTIONABLE** — already documented in 0623-PM window README. The companion paper confirms the SKILL.md format compatibility (Task 2).

#### 🔥 2606.23416 — Detecting Malicious Agent Skills in the Wild using Attention
**Dated:** 0622
**Core claim:** Skill marketplaces (clawhub.ai, skills.sh, lobehub.com) are an attack surface. Prompt-injection defenses don't transfer because a skill *is* an instruction. Proposes attention-based detection.
**Why it matters:** 🔥 **CRITICAL for OpenClaw skill ecosystem.** OpenClaw has its own skill marketplace direction; this paper is the first systematic study of skill-level security.
**Code:** No GitHub (paper-only); dataset claim but no public release.
**Status:** **T1 MANDATORY READ.** Suggests adding `skill_audit.py` to verify third-party SKILL.md files before loading.

### T2 — Skill/agent system architecture papers

#### 2606.23127 — Managing Procedural Memory in LLM Agents: Control, Adaptation, and Evaluation (AFTER benchmark)
**Dated:** 0622
**Core claim:** AFTER = 382 realistic enterprise tasks × 22 procedural skills × 6 roles. Procedural memory (skill transfer) helps but is uneven across tasks/roles/models. Controlled settings: local improvement, cross-task transfer, cross-role transfer, cross-model generalization.
**Why it matters:** First real benchmark for skill transfer. Directly applicable to our SKILL.md portability work.
**Code:** Need to check for AFTER repo.

#### 2606.22678 — RigorBench: Benchmarking Engineering Process Discipline in Autonomous AI Coding Agents
**Dated:** 0621
**Core claim:** Agentic coding harnesses like **Agent-Skills, Superpowers, Agent-Rigor** are being deployed. Benchmarks should evaluate engineering process discipline, not just outcome correctness. An agent that arrives at correct solution via reckless trial-and-error is fundamentally less reliable.
**Why it matters:** Names "Agent-Skills" as a category alongside Superpowers and Agent-Rigor. Suggests OpenClaw's skill system is in a competitive space. Calls for process-grade evaluation.
**Code:** Need to check for RigorBench repo.

#### 2606.22613 — SkillAudit: From Fixed-Suite Benchmarking to Skill-Centered Assessment
**Dated:** 0621
**Core claim:** Skill marketplaces need a way to judge whether a skill is worth deploying. Fixed-task suites conflate skill's marginal contribution with backbone strength. End-to-end framework: skill-centered assessment.
**Why it matters:** Companion piece to 2606.23416. Different angle: not malicious-skill detection but skill-quality measurement. Could inform OpenClaw skill marketplace curation.
**Code:** Need to check for SkillAudit repo.

#### 2606.20363 — Automating SKILL.md Generation for Computer-Using Agents via Interaction Trajectory Mining
**Dated:** 0618
**Core claim:** Mines interaction trajectories to auto-generate SKILL.md files. **This is the only paper with "SKILL.md" in the title.**
**Why it matters:** Highest direct relevance to our SKILL.md investigation. If method is reproducible, it could 10× our skill authoring throughput.
**Code:** Need to check for SKILL-gen repo. **HIGH PRIORITY** to verify.

#### 2606.22557 — MacAgentBench: Benchmarking AI Agents on Real-World macOS Desktop
**Dated:** 0621
**Core claim:** 676 tasks × 25 macOS apps × ~60% multi-app. **Description explicitly mentions "OpenClaw on Mac Mini for always-on automation"** as a deployment example.
**Why it matters:** First paper that cites OpenClaw by name as a deployed CUA in a benchmark study. Validates OpenClaw's positioning.
**Code:** Need to check for MacAgentBench repo.

### T2 — Agent reliability / context management

#### 2606.22528 — Governance Decay: How Context Compaction Silently Erases Safety Constraints
**Dated:** 0621
**Core claim:** Context compaction (summarization, eviction) is a safety-critical failure surface. Constraints visible while in-context get silently removed by compaction. Introduces `ConstraintRot` benchmark.
**Why it matters:** OpenClaw already uses context-compaction patterns. This paper formalizes the safety failure mode. Could influence future SOUL.md design.
**Code:** Need to check for ConstraintRot repo.

#### 2606.22953 — Plans Don't Persist: Why Context Management Is Load Bearing for LLM Agents
**Dated:** 0622
**Core claim:** Plans written early, used for many steps, evicted first. Replay-pairing diagnostic measures hidden-state cosine distance. On Llama-3.1-70B, plan signal spikes to 0.453 one step after plan, falls 4.1× in a single action-observation.
**Why it matters:** Direct evidence for plan persistence in long-horizon agents. Suggests implementing `plan_persistence.py` for OpenClaw.
**Code:** Need to check.

#### 2606.22936 — When Agents Commit Too Soon: Diagnosing Premature Commitment in LLM Agents
**Dated:** 0622 (already in prior scout list)
**Why re-listed:** Worth flagging again — agent settles on one reading of evidence early and defends it. Failure mode for autonomous research agents like Scout. Worth a follow-up Scalpel review.

### T3 — Memory and routing

#### 2606.22844 — RaMem: Contextual Reinstatement for Long-term Agentic Memory
**Dated:** 0622
**Core claim:** Identifies "context collapse" — memories lose surrounding context needed to judge whether they apply. Proposes Contextual Reinstatement.
**Why it matters:** Directly relevant to our `memory_bridge_search` design. Adding reinstatement context could improve recall precision.

#### 2606.23195 — Memory Contagion: Cross-Temporal Propagation of Evaluator Bias via Agent Memory
**Dated:** 0622
**Core claim:** When agents are trained/guided by biased evaluators, their experiences become biased; when these trajectories are stored and consolidated into memory, the bias propagates.
**Why it matters:** ⚠️ Should we audit our own memory candidates for evaluator bias? Could feed into Synapse retrospective.

#### 2606.22902 — Agent-as-a-Router: Agentic Model Routing for Coding Tasks
**Dated:** 0622
**Core claim:** Routing tasks to the most suitable LLM. Augmenting vanilla LLM router with performance statistics at task-dimension level yields +15.3% relative gain.
**Why it matters:** OpenClaw's `model routing` could leverage this. We currently use single model; routing by task type (research vs coding vs chat) might help cost/quality.

#### 2606.23608 — Causal Discovery in the Era of Agents
**Dated:** 0622
**Core claim:** Argues agents should *inspect data, retrieve context, explain method assumptions* but NOT supply edges in causal discovery.
**Why it matters:** Methodological guardrail. Agents as reasoning partners, not as ground truth.

### T3 — Engineering scaffolding

#### 2606.22883 — CLI-Universe: Towards Verifiable Task Synthesis Engine for Terminal Agents
**Dated:** 0622
**Core claim:** Synthesizes terminal-agent tasks via multi-dimensional capability sampling. Generates higher-quality tasks than retrofit pipelines.
**Why it matters:** Could feed OpenClaw's terminal-task generation for self-improvement.

#### 2606.23075 — Safety in Self-Evolving LLM Agent Systems: Threats, Amplification, and Case Studies
**Dated:** 0622
**Core claim:** MLAS matrix = 5 modules × 5 lifecycle stages for analyzing self-evolving agent threats.
**Why it matters:** Threat model for self-evolving agents. OpenClaw memory candidate commit is a form of self-evolution.

---

## 📊 Summary Counts

| Tier | New (post-prior-cutoff) | Already in prior | Action needed |
|------|-------------------------|-----------------|----------------|
| T1 | 23449, 23416 | — | Verify GitHub, prioritize |
| T2 | 23127, 22678, 22613, 20363, 22557, 22528, 22953 | 22936 | Verify repos, deep-read |
| T3 | 22844, 23195, 22902, 23608, 22883, 23075 | — | Background reads |

---

## 🎯 Recommended Next Actions

1. **Verify GitHub for:** 2606.20363 (SKILL.md generation), 2606.23127 (AFTER), 2606.22678 (RigorBench), 2606.22613 (SkillAudit), 2606.22557 (MacAgentBench). These are the highest-leverage T1/T2 candidates.
2. **Deep-read 2606.23416** (Malicious Agent Skills) — paper-only but mandatory for OpenClaw skill security roadmap.
3. **Schedule Scalpel review** on 2606.23449 (AOHP) benchmark claims — small-N caveat, self-reported.
4. **Nova ideation** on 2606.22528 (Governance Decay) + 2606.22953 (Plans Don't Persist) — both feed into SOUL.md/Context-management design.
5. **Add `skill_audit.py` to OpenClaw** roadmap — informed by 2606.23416 + 2606.22613.

---

## Limitations

- **0623-dated papers:** None yet in arXiv cs.AI feed (timing). Recommend re-scan at 14:00 UTC or 22:00 CST.
- **0622-dated overlap:** Several papers (22936, 23449, 23416) were already partially captured by prior 0623-PM scout but their abstracts are included here for completeness with cross-references.
- **No code-availability filter:** Paper-only candidates are flagged but not excluded; prioritize repos where they exist.