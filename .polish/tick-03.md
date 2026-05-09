# Tick 3: Title Accuracy Verification

**Date**: 2026-05-09 04:56 UTC

## Method
Fetched arXiv pages for 15 papers spread across §4, §5, §6, §7, §8, Hall of Fame. Compared `<title>` tag from arXiv against README title text.

## Papers Checked (15)

| arXiv ID | Status | Notes |
|----------|--------|-------|
| 2402.03898 | ✅ Match | DistiLLM title correct |
| 2601.07155 | ✅ Match | |
| 2404.02657 | ✅ Match | |
| 2602.12125 | ✅ Match | |
| 2602.12674 | ⚠️ Acceptable | arXiv uses LaTeX `$\mathcal{X}$-KD`, README renders as "X-KD" (markdown limitation) |
| 2605.01347 | ❌ **Fixed** | README had "Multi-Agent Debate-driven On-Policy Distillation", actual title is "MAD-OPD: Breaking the Ceiling in On-Policy Distillation via Multi-Agent Debate" |
| 2306.08543 | ❌ **Fixed** | README had "MiniLLM: **Knowledge** Distillation of Large Language Models", actual is "MiniLLM: **On-Policy** Distillation of Large Language Models" |
| 2509.14526 | ✅ Match | |
| 2602.02405 | ✅ Match | |
| 2605.05040 | ✅ Match | |
| 2603.11178 | ❌ **Fixed** | README had "PACED: Distillation and Self-Distillation at...", actual is "PACED: Distillation and **On-Policy** Self-Distillation at..." |
| 2604.27083 | ✅ Match | |
| 2505.13111 | ✅ Match | |
| 2604.16830 | ✅ Match | |
| 2501.12948 | ✅ Match | |

## Fixes Applied (3 title corrections)

1. **2605.01347 (MAD-OPD)** — Updated title in both §5.1 table and Latest Additions section to match actual arXiv title
2. **2306.08543 (MiniLLM)** — Changed "Knowledge Distillation" → "On-Policy Distillation" in §5.1 table entry
3. **2603.11178 (PACED)** — Added missing "On-Policy" to title in §6 table entry

## Notes
- The MiniLLM title error was significant (wrong keyword: "Knowledge" vs "On-Policy")
- MAD-OPD appears to have been renamed on arXiv since initial listing
- The X-KD LaTeX rendering (`$\mathcal{X}$`) is a known markdown limitation, left as "X-KD"
