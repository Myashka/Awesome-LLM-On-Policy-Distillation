# Tick 0: Inventory Report

**Date**: 2026-05-09 04:08 UTC

## Paper Count Summary

| Section | Papers |
|---------|:------:|
| §4.1 Fixed Divergence Objectives | 4 |
| §4.2 Adaptive Divergence Objectives | 8 |
| §4.3 RL-Augmented Objectives | 14 |
| §5.1 White-Box Logit Supervision | 8 |
| §5.2 Black-Box and API-Constrained | 7 |
| §5.3.1 Privileged Information | 15 |
| §5.3.2 Self-Play | 6 |
| §5.3.3 External Feedback | 6 |
| §6 Training Dynamics and Efficiency | 13 |
| §7.1 Success Conditions | 3 |
| §7.2 Failure Modes | 3 |
| §7.3 Unified Theory | 3 |
| §8.1 Industrial Deployment | 8 |
| §8.2 Emerging Domains | 13 |
| §8.3 System-Level Integration | 2 |
| **TOTAL** | **113** |

## Badge Verification

- ✅ `Papers-113` badge matches actual count (113 paper rows in taxonomy)
- ✅ `Survey-V2 124 cites` badge matches actual bib count (124 entries in `references.bib`)

## Cross-Reference: README vs Survey Bib

- Unique arXiv IDs in README (all sections): **112** (+ 1 HuggingFace link for DeepSeek-V4)
- Unique arXiv IDs in survey bib: **107**
- Survey bib total entries: **124** (includes non-arXiv references)

### In survey bib but NOT in README (4) — all background references, correctly excluded:
- `2203.15556` — "Training Compute-Optimal Large Language Models" (Chinchilla, background)
- `2305.15717` — "The False Promise of Imitating Proprietary LLMs" (motivation/critique)
- `2305.20050` — "Let's Verify Step by Step" (PRM, background)
- `2402.13116` — "A Survey on Knowledge Distillation of Large Language Models" (related survey)

### In README but NOT in survey bib (9):
- `2604.00626` — The survey paper itself (expected)
- `2605.06387` — AOPD (listed in "Not Yet in Survey" section) ⚠️
- `2605.05940` — Near-Policy Distillation (listed in "Not Yet in Survey" section) ⚠️
- `2605.06188` — OPSD Compresses (listed in "Not Yet in Survey" section) ⚠️
- `2605.06094` — VISD (listed in "Not Yet in Survey" section) ⚠️
- `2605.00642` — GUI-SD (in "Recently Added" as survey-integrated)
- `2605.02943` — TT-OPD (in "Recently Added" as survey-integrated)
- `2605.03677` — Uni-OPD (in "Recently Added" as survey-integrated)
- `2605.05040` — PBSD (in "Recently Added" as survey-integrated)

## Issues Found

### Issue 1: 🟢/🟡 emoji inconsistency (CRITICAL)
4 papers are marked 🟢 in the main taxonomy sections but listed under "Not Yet in Survey":
- AOPD (`2605.06387`) — marked 🟢 in §4.2 (line 291)
- VISD (`2605.06094`) — marked 🟢 in §5.3.1 (line 389) AND §8.2 (line 522)
- Near-Policy (`2605.05940`) — marked 🟢 in §6 (line 444)
- OPSD Compresses (`2605.06188`) — marked 🟢 in §7.1 (line 464)

**Fix**: Change these from 🟢 to 🟡 in the taxonomy sections (they are NOT in the survey bib).

### Issue 2: "118 citations" in Latest Additions header is outdated
Line 151 says "already in Survey V2 (118 citations)" but the survey now has 124 citations.

**Fix**: Update to "124 citations".

### Issue 3: Cross-listed paper counts in badge
VISD appears in both §5.3.1 and §8.2. The 113 badge counts it twice.
This is a design choice (cross-listing is common in awesome lists), but should be documented.

**Status**: Acceptable (cross-listing pattern used for multi-section papers).

### Issue 4: DeepSeek-V4 has no arXiv link
Line 501 links to HuggingFace. This is correct (DeepSeek-V4 tech report was released on HuggingFace, not arXiv).

**Status**: Acceptable.
