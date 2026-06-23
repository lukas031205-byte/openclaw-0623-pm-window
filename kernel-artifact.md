# Kernel Artifact: 0623-PM Window Consolidated Findings

**Window:** 2026-06-23 20:03 CST | **Model:** MiniMax (Copilot blocked) | **Status:** COMPLETE

## T1 Findings (Verified, Actionable)

### 1. MacAgentBench: OpenClaw Scores 73.7% — External Validation! 🔥
- **Repo:** [JetAstra/MacAgentBench](https://github.com/JetAstra/MacAgentBench) (43⭐, MIT, updated 2026-06-23)
- **Benchmark:** 676 tasks, 25 macOS apps, 3 agent frameworks
- **Result:** OpenClaw (73.7%) > Agent-S3 (66.9%) > Baseline (39.2%)
- **Config:** openclaw.json shows real deployment config (feishu, apple-notes, sherpa-ONNX-TTS)
- **Relevance:** First external benchmark confirming OpenClaw as top-tier agent framework
- **KAS use:** PhD application — strong evidence of OpenClaw's competitiveness

### 2. AOHP Skills: OpenClaw SKILL.md Format Confirmed as Open Standard
- **Repo:** [aohp-os/aohp](https://github.com/aohp-os/aohp) (37⭐, Apache-2.0)
- **Claim:** skills/ directory explicitly "AgentSkills-compatible SKILL.md folders (OpenClaw-style)"
- **Format verified:** `metadata: {"openclaw":{"emoji":"👆","requires":{"bins":["aohp"]},"os":["linux"]}}`
- **AOHP result:** OpenClaw on AOSP: 54.44% → 75.56% (+21pp) via OS-level harness
- **Relevance:** Validates SKILL.md as an adopted open format

### 3. 2606.20363: SKILL.md Auto-Generation (Paper-Only)
- **Paper:** "Automating SKILL.md Generation for Computer-Using Agents via Interaction Trajectory Mining"
- **Method:** Segments GUI trajectories → clusters → trains skill-aware policy
- **Finding:** GRPO only 18.5%→20.5% on skill steps; current methods insufficient for cross-domain improvement
- **GitHub:** None (paper-only, negative result)
- **Relevance:** SKILL.md authoring is still a human-in-the-loop process

### 4. 2606.23416: Malicious Agent Skills (Paper-Only, Critical Read)
- **Topic:** Skill marketplace attack surface — prompt injection defenses don't transfer because skill IS instruction
- **Action:** Add `skill_audit.py` to verify third-party SKILL.md before loading
- **GitHub:** None (paper-only)
- **Relevance:** Security roadmap for OpenClaw skill marketplace

## T2 Findings (Fresh, 0-4⭐, Worth Watching)

| Paper | Repo | Stars | Key Relevance |
|-------|------|------:|---------------|
| JetAstra/MacAgentBench | MacAgentBench | 43⭐ | OpenClaw benchmark validation |
| 2606.22557 | (checking) | — | OpenClaw mentioned in paper |
| 2606.23127 AFTER | (checking) | — | 22 skills × 6 roles benchmark |
| 2606.22953 | (checking) | — | Plan persistence failure evidence |
| 2606.22528 | (checking) | — | Context compaction safety (Governance Decay) |

## InStreet Engineering Insights (0623-AM)

**Top applicable patterns for OpenClaw:**
1. **@派蒙's 4-state wait model** → Map to triple-service health checks
2. **@Void's per-rule activation policy** → TTL + trigger conditions in SKILL.md
3. **@KKClaw's cold-start audit** → 204 signals → 7 rules, 89% coverage
4. **@垂涎各位已久's memory compression** → 50KB → 8KB validates compaction approach

## Action Items for Next Window

1. **GitHub publish:** Push consolidated standouts to `lukas031205-byte/openclaw-0623-pm-window`
2. **Nova ideation:** MacAgentBench integration ideas for KAS
3. **arXiv rescan:** 2026-06-24 AM (to catch papers published 2026-06-23 US Eastern)
4. **Memory candidates:** Commit AOHP + MacAgentBench findings to memory
