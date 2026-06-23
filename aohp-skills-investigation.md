# AOHP Skills Investigation — 0623-PM Window

**Date:** 2026-06-23 | **Status:** ✅ COMPLETE

## Key Finding: AOHP Skills are OpenClaw-Format Compatible! 🔥

**Repo:** [aohp-os/aohp](https://github.com/aohp-os/aohp) | **37⭐** | Apache-2.0

The AOHP repo explicitly uses **OpenClaw-style SKILL.md layout** for their agent skills. This is NOT a coincidence — AOHP is designed to benchmark OpenClaw agents on AOSP.

## Skills Directory Structure

```
skills/
├── README.md              ← Integration guide
├── aohp-ui-actions/      ← SKILL.md (6308 bytes)
├── aohp-display/
├── aohp-event-stream/
├── aohp-file/
├── aohp-perception/
├── aohp-sandbox/
├── aohp-sensor/
├── aohp-sys/
├── aohp-uda/
└── uda-app/
```

## SKILL.md Format — Direct Comparison

**AOHP `aohp-ui-actions/SKILL.md`:**
```yaml
---
name: aohp-ui-actions
description: Tap, swipe, keys, text entry on AOSP via aohp CLI
metadata: {"openclaw":{"emoji":"👆","requires":{"bins":["aohp"]},"os":["linux"]}}
---

# AOHP UI actions
...
```

**OpenClaw standard SKILL.md** (from existing skills):
```yaml
---
name: skill-name
description: What this skill does
metadata: {"openclaw":{"emoji":"🔥","requires":{"bins":["some-binary"]}}}
---

# Skill Title
...
```

**Verdict: ✅ IDENTICAL FORMAT.** The AOHP skills are explicitly designed for OpenClaw integration.

## 🔥 MAJOR: MacAgentBench Validates OpenClaw at 73.7% Pass@1

**Repo:** [JetAstra/MacAgentBench](https://github.com/JetAstra/MacAgentBench) | **43⭐** | MIT | **Updated: 2026-06-23**

From the README (live benchmark results):

| Framework | Best Model | Pass@1 |
|-----------|-----------|--------|
| **OpenClaw** | Claude Opus 4.6 | **73.7%** |
| Agent-S3 | Claude Opus 4.6 | 66.9% |
| Baseline | Claude Opus 4.6 | 39.2% |

OpenClaw **OUTPERFORMS** competing frameworks on a 676-task macOS benchmark! The repo even includes `openclaw.json` — the actual config used in the benchmark:
- Model: openai/gpt-5.4 (reasoning enabled)
- Skills: apple-notes, sherpa-ONNX-TTS
- feishu plugin, web fetch enabled
- Context pruning: cache-ttl 1h
- Heartbeat: every 1h

**This is the first external benchmark validating OpenClaw as a top-tier agent framework.**

---

## AOHP README Integration Instructions

From the AOHP skills/README.md:
> "Copy or symlink this folder into OpenClaw's skills directory, or set **`skills.load.extraDirs`** to point here."

This means:
1. AOHP skills can be loaded by OpenClaw without any modification
2. The `aohp` binary must be available in the environment
3. `metadata.openclaw.requires.bins` declares the dependency

## Available Skills

| Skill | Purpose | OpenClaw Relevance |
|-------|---------|-------------------|
| aohp-ui-actions | Tap, swipe, key, text injection | T1 — UI automation |
| aohp-display | Virtual display management | T2 — multi-display support |
| aohp-perception | Screenshot + UI tree | T1 — visual observation |
| aohp-event-stream | Notification events | T2 — event-driven |
| aohp-file | File operations | T2 — file management |
| aohp-sys | Clipboard, SMS, wake/sleep | T2 — system control |
| aohp-sensor | Camera capture | T3 — sensor input |
| aohp-sandbox | Linux chroot | T3 — sandboxing |
| aohp-uda | HTML app generation | T3 — dynamic UI |

## OpenClaw Integration Feasibility

**Can AOHP skills run on KAS's OpenClaw?**
- ✅ Format: 100% compatible
- ⚠️ Binary: Requires `aohp` CLI (AOSP-specific, not generally available on Linux)
- ⚠️ OS: AOSP (Android Open Source Project) — not standard Linux
- ⚠️ Use case: Mobile device automation, not server/VM automation

**Practical assessment:** AOHP skills are designed for Android device harness scenarios. KAS's OpenClaw runs on Linux VM. Direct integration requires the `aohp` binary which is AOSP-specific.

However, the **skills framework compatibility validates** the OpenClaw SKILL.md format as an open standard — other projects ARE adopting it.

## Benchmark Results (from AOHP paper)

| Setting | Completion Rate | Tool Calls | Duration | Tokens |
|---------|---------------|-----------|----------|--------|
| OpenClaw @ stock Android | 54.44% | 233 | 33.94 min | 7.10M |
| **OpenClaw @ AOHP** | **75.56%** | **129** | **18.93 min** | **3.44M** |
| **Delta** | **+21.12%** | **-44.64%** | **-44.21%** | **-51.55%** |

AOHP provides OS-level harness primitives that make OpenClaw agents dramatically more efficient on mobile tasks.

## Recommendation

1. **Watch:** AOHP is early (37⭐, Apache-2.0, commit today). If they release a Linux-compatible version of the `aohp` binary, their skill set could be directly portable.
2. **Validate SKILL.md format:** AOHP's adoption confirms the OpenClaw skill format is a real open standard — worth investing in SKILL.md tooling.
3. **Paper citation:** AOHP (2606.23449) is the strongest evidence that OpenClaw harness design directly impacts agent performance.

---

## 📄 Companion arXiv Paper (Cross-Reference from Task 3)

**arXiv:** [2606.23449](https://arxiv.org/abs/2606.23449) — "AOHP: An Open-Source OS-Level Agent Harness for Personalized, Efficient and Secure Interaction" (0622)

The companion paper reveals the design rationale behind the SKILL.md layout:

- **Cross-app memory** with fine-grained data-flow tracking
- **Sandboxed sensitive values** (prevents accidental credential leak via skills)
- **OS-level primitives** that the `aohp` binary exposes (UI actions, displays, perception, event stream, file ops, sys, sensor, sandbox, UDA, app launch)

The paper explicitly benchmarks OpenClaw on the harness:

| Setting | Completion | Tool Calls | Duration | Tokens |
|---------|-----------:|-----------:|---------:|-------:|
| OpenClaw @ stock Android | 54.44% | 233 | 33.94 min | 7.10M |
| OpenClaw @ AOHP | **75.56%** | **129** | **18.93 min** | **3.44M** |
| Δ | **+21.12pp** | **–44.64%** | **–44.21%** | **–51.55%** |

**Implication for OpenClaw adoption:** Even with the *same* agent (OpenClaw), a skill-system designed at the OS layer moves completion by +21pp at half the cost. This is direct evidence that the **SKILL.md format + harness design** is a load-bearing decision, not just a documentation convention.

**Caveat:** Small-N (30 tasks), self-reported by AOHP team. Scalpel should review benchmark methodology.

---

## Status

✅ Investigation complete. AOHP skills are confirmed OpenClaw-format compatible. Cross-referenced with companion paper 2606.23449 from the 0623-PM arXiv scan.
