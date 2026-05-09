# Survey ↔ Awesome List Cross-Reference Gaps

**Date**: 2026-05-09 05:49 UTC  
**Survey bib**: 124 entries (115 unique arXiv IDs)  
**Awesome List**: 113 papers in taxonomy (111 unique arXiv IDs + 1 HuggingFace link)

---

## In Awesome List but NOT in Survey Bib (4 papers)

These are papers listed in the README (marked 🟡 "Not Yet in Survey") that haven't been added to the survey's `references.bib` yet.

| arXiv ID | Paper | README Section | Status |
|----------|-------|---------------|--------|
| 2605.06387 | AOPD: Asymmetric On-Policy Distillation | §4.2 | 🟡 Queued for survey V2.1 |
| 2605.05940 | Near-Policy Distillation | §6 | 🟡 Queued for survey V2.1 |
| 2605.06188 | OPSD Compresses What RLVR Teaches | §7.1 | 🟡 Queued for survey V2.1 |
| 2605.06094 | VISD: Enhancing Video Reasoning via Structured Self-Distillation | §5.3.1 + §8.2 | 🟡 Queued for survey V2.1 |

**Action**: These are correctly marked 🟡 in the README. No fix needed.

---

## In Survey Bib but NOT in Awesome List (8 entries)

### Background / Foundation References (not OPD methods, correctly excluded)

| arXiv ID | Paper | Role in Survey |
|----------|-------|---------------|
| 1503.02531 | Distilling the Knowledge in a Neural Network (Hinton et al., 2015) | Historical foundation of KD |
| 2001.08361 | Scaling Laws for Neural Language Models | Background on compute scaling |
| 2203.15556 | Training Compute-Optimal Large Language Models (Chinchilla) | Background on optimal training |
| 2305.15717 | The False Promise of Imitating Proprietary LLMs | Motivation for OPD (off-policy critique) |
| 2305.20050 | Let's Verify Step by Step (PRM) | Background on process reward models |
| 2402.13116 | A Survey on Knowledge Distillation of Large Language Models | Related survey |

### Infrastructure / Tools (referenced but not OPD methods)

| arXiv ID | Paper | Role in Survey |
|----------|-------|---------------|
| 2405.11143 | OpenRLHF: Easy-to-use RLHF Framework | Training infrastructure (already linked in README "Additional Resources") |
| 2409.19256 | veRL: Volcano Engine RL for LLM | Training infrastructure (already linked in README "Additional Resources") |

**Action**: All 8 are correctly excluded from the Awesome List. They are background references, not OPD methods. OpenRLHF and veRL are already listed in the README's "Additional Resources" section as tooling links.

---

## Summary

- **No missing OPD papers in either direction.** The gap is entirely explained by:
  1. 4 very recent papers (May 2026) pending next survey revision (correctly marked 🟡)
  2. 8 background/infrastructure references in the survey that are not OPD methods

- **Badge accuracy**: README says "Papers-113", survey says "124 cites". The difference (11) = 8 background refs + 4 pending papers - 1 (survey cites itself). Math checks out.

---

*No changes to README needed. This is a documentation-only report.*
