# Changelog

All notable additions to this collection are documented here.

## [2026-06-03]
### Added
- **TRB** (2605.31159) added to §6 Training Efficiency and Stabilization and Pending Papers. Trust-region behavior blending for OPD rollout warmup; annealed student-centered KL trust region improves early on-policy prefixes while keeping the reverse-KL distillation loss unchanged.

## [2026-05-30]
### Added
- **SOD** (2605.07725) added to Hall of Fame **🚀 Frontier (2025–2026)** subsection alongside OPSD / AlignDistil / Rethinking-OPD / SCOPE / SDZero. Step-level divergence reweighting for tool-integrated reasoning agents, surfacing the step-granularity unit that sits between token-level (TIP / SCOPE) and trajectory-level (TCOD) weighting.
- Daily pipeline cron added **2605.28791** (Skill-Conditioned Gated Self-Distillation for LLM Reasoning) to §5.3.1 (commit 9047e7c). Paper count badge: 175 → 176.

## [2026-05-29]
### Changed
- **Agentic OPD navigation references**: TCOD → SOD in 3 navigational locations (Trends takeaway #4, `resources/method-comparison.md` decision tree, `resources/reading-order.md` Level 4). SOD (2605.07725) is the more representative agentic OPD method now (step-level divergence reweighting for tool-integrated reasoning, +20.86% over the second-best baseline). TCOD's own paper entry, codebase row, the §6 dynamics toolbox listing in Quick-Start (where TCOD remains the §6.2 Curriculum representative), and historical changelog references are kept intact; only the high-level agentic-OPD pointers are updated.

### Reviewed (no list change)
- Reviewed 3 candidate papers from 5/27-5/28 daily-pipeline against the 5/15 inclusion scope (text/language model output only). All 3 had not entered the Awesome list, so no removal was needed; recording the boundary review here for completeness.
  - **AnyFlow** (2605.13724) — video diffusion (Wan2.1-14B + VBench), out of scope.
  - **Adversarial Dual OPD from Expressive Flow-based Teacher** (2605.27095) — embodied control, flow-matching policy teacher (no LLM backbone), out of scope.
  - **SERL** (2605.19447) — 5/27 commit message labelled it as "+OPD" but `paper_notes.json` had no entry; 5/28 three-condition review judged it RL-only (GRPO + env feedback reweighting, no teacher distill term). Stub added to `paper_notes.json` referencing `papers-meta/excluded-papers.md`.

## [2026-05-28]
### Removed
- **ThinkTuning** (2508.07616) — full-corpus audit reclassification. Paper's own title declares "without Distillation"; teacher provides text hints (opinions / reasons / phrases) appended to a fraction of student rollouts, not logit distributions. Loss is GRPO with Advantage-Aware Shaping on hint-augmented data — no KL-to-teacher term. Closer to teacher-augmented RL than distillation. Removed from Awesome List, V4 references.bib, paper_notes.json, INDEX.md; PDF moved to `pdfs/.trash-2026-05-28-thinktuning/`. Logged in `papers-meta/excluded-papers.md`.
- Paper count badge: 176 → 175

## [2026-05-17]
### Changed
- Removed 3 non-OPD papers: HPD (off-policy), Distillation Traps (analysis), VPG-EA (variational inference)
- Updated Key Takeaways with accurate pair statistics (83 models, 753 pairs)
- Regenerated heatmap: 83 models, 753 pairs, 148 OPD papers
- Fixed paper count badge (154)

## [2026-05-16]
### Added
- Batch: TGPO, EGRSD, MOPD, GEAR, RWOPD, DAgger-LLM, Prefix-Teach
- VPD, HyperEyes, Shadow Mask Distillation, UniSD, ProteinOPD, TRACE, TTS, Safactory
- AOPD, NPD, OPSD-post-RL, VISD

## [2026-05-08 polish v2]
### Added
- MiniPLM (§5.1) — Pre-training KD via difference sampling
- Visual upgrades: Mermaid evolution timeline, taxonomy mindmap
- Hall of Fame section with recommended reading orders by background

### Changed
- Paper count: 108 → 109 (107 arXiv + 2 tech reports)
- "Related Surveys" row: 108 methods → 109 methods

## [2026-05-08]
### Added
- PBSD (§5.3.1 + §4.3) — Preference-based self-distillation with DPO-style reward-regularized KL objective; first to replace pure KL with preference gap in OPD
- TT-OPD (§5.3.1 + §7.2 + §8.2) — Turn-level truncated OPD for medical agents; EMA teacher + outcome-privileged hints; first systematic agentic-OPD stability study
- Delta-KD (§5.1) — Base-to-Instruct delta signal isolation for white-box logit distillation
- TAID (§5.1) — Temporally adaptive interpolated distillation (2024)

### Changed
- Reclassified Latest Additions spotlight tags to match survey V2 fine-grained sections: CoPD §5.3.2→§5.3.3 (external feedback, mutual teacher), MAD-OPD §5.3.3→§5.1+§6.1+§8.2 (multi-teacher white-box), Uni-OPD §6→§6.2, PRISM §6→§6.2, PAINT §6.2→§5.3.2+§6.2.
- Paper count badge: 104 → 108.
- "Related Surveys" row: `104 methods across 13 subcategories` → `108 methods across 13 subcategories`.

## [2026-05-07]
### Added
- DeepSeek-V4 Technical Report (§7.1) — Multi-domain OPD consolidation via reverse-KL
- CaOPD (§7.2) — Discovers miscalibration scaling law in OPD
- OPSDL (§5.3.1) — Short-context as privileged teacher for long-context

## [2026-05-06]
### Added  
- Uni-OPD (§4.2) — Dual-perspective recipe unifying student exploration + teacher reliability
- MAD-OPD (§4.1) — Multi-agent debate for confidence-weighted OPD

## [2026-05-04]
### Added
- GUI-SD (§5.1) — Visual privileged context for GUI grounding
- MSD (§5.1) — Multilingual self-distillation for safety alignment

## [2026-05-01]
### Added
- TCOD (§4.2) — Temporal curriculum for multi-turn agent OPD
- PRISM (§4.2) — Pre-alignment via black-box OPD for multimodal RL
- PAINT (§4.2) — Partial-solution adaptive interpolated training
- CoPD (§5.3) — Co-evolving policy distillation
- IRIS (§5.2) — Interpolative Rényi iterative self-play

## [2026-04-26]
### Added
- π-Play (§5.1/§5.2) — Multi-agent self-play via privileged self-distillation
- ORBIT (§7.1) — Multi-teacher OPD fusion for controllable reasoning
- SCOPE (§4.2) — Dual-path adaptive weighting, reveals diversity collapse
- TIP (§4.2) — Token importance via 2D classification
- Lightning OPD (§4.2) — Teacher consistency + offline OPD 4x speedup

## [2026-04-24]
### Added
- Rethinking OPD (§6) — Two necessary conditions for OPD to work
- SDZero (§5.3) — Self-revision turns binary rewards into dense supervision

## [2026-04-20]
### Added
- Stable-OPD (§4.2) — Length inflation and stabilization strategies
- HY-Embodied-0.5 (§7.3) — Embodied foundation models for real-world agents
- DP-OPD (§7.3) — Differentially private on-policy distillation

## [2026-04-15]
### Added
- SRPO (§5.3) — Unifying group-relative and self-distillation policy optimization
- AKL (§4.1) — Rethinking Kullback-Leibler divergence (Adaptive KL)

## [2026-04-13]
### Added
- Initial creation of the Awesome LLM On-Policy Distillation list!
- A Survey of On-Policy Distillation for Large Language Models (§1)
- Foundational papers: GKD, MiniLLM, Lion, Distilling Step-by-Step.
