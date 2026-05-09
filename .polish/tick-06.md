# Tick 6: Survey Cross-Check

**Date**: 2026-05-09 05:49 UTC

## Method
Extracted all arXiv IDs from both `../latex-v2/references.bib` (124 entries, 115 unique arXiv IDs) and `README.md` (111 unique arXiv IDs + 1 HuggingFace link).

## Results

### In README but not in Survey Bib: 4 papers
All are correctly marked 🟡 (pending next survey revision):
- AOPD (2605.06387)
- Near-Policy Distillation (2605.05940)
- OPSD Compresses What RLVR Teaches (2605.06188)
- VISD (2605.06094)

### In Survey Bib but not in README: 8 entries
All are background/infrastructure references, not OPD methods:
- 6 background papers (Hinton 2015, Scaling Laws, Chinchilla, False Promise, PRM, KD Survey)
- 2 infrastructure tools (OpenRLHF, veRL) already linked in Additional Resources

## Conclusion
No gaps that require action. All discrepancies are correctly explained by design choices. Full report written to `.polish/gaps.md`.

## Fixes Applied
None. Documentation-only tick.
