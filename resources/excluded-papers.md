# Excluded Papers (Initially Surveyed but Removed)

> Papers that were initially included as 🟡 placeholders during deep-read sweeps,
> then removed after V3 schema-based classification revealed they don't satisfy
> OPD's defining criterion (student rollout during training, with concurrent teacher signal).
>
> Kept here for **transparency** so reviewers can see we considered them.

## OPD Inclusion Criterion (recap)

A paper is OPD if **all three** hold:
1. Training-time student rollouts (not pre-collected datasets)
2. Concurrent teacher supervision (logits / preferences / rewards) on those rollouts
3. Per-step or per-iter weight updates from those signals

Methods that fail any of (1–3) — even if they call themselves "self-distillation",
"online distillation", or "on-policy SFT" — are **not** OPD.

---

## Removed in 2026-05-28

| arXiv | Title | Reason | Verdict |
|-------|-------|--------|---------|
| [2605.16826](https://arxiv.org/abs/2605.16826) | Decoupling KL and Trajectories: A Unified Perspective for SFT, DAgger, Offline RL, and OPD in LLM Distillation | Theoretical framework unifying SFT/DAgger/Offline-RL/OPD; not a new method per se. Belongs in §7.3 unified perspectives review, not main paper list. | `analysis` |
| [2605.16865](https://arxiv.org/abs/2605.16865) | MIXSD: Mixed Contextual Self-Distillation for Knowledge Injection | MIXSD generates mixed self-distillation targets offline (one-time preprocessing) before training. Off-policy by definition — fails OPD criterion. | `no` |


### Detailed reasoning

#### [2605.16826](https://arxiv.org/abs/2605.16826) — Decoupling KL and Trajectories: A Unified Perspective for SFT, DAgger, Offline RL, and OPD in LLM Distillation

- **Verdict**: `is_opd = "analysis"`
- **V3 classifier reasoning**: The paper's core contribution is a theoretical framework unifying four distillation objectives and empirical analysis of their tradeoffs, rather than proposing a single new OPD method.
- **Removal cause**: Theoretical framework unifying SFT/DAgger/Offline-RL/OPD; not a new method per se. Belongs in §7.3 unified perspectives review, not main paper list.

#### [2605.16865](https://arxiv.org/abs/2605.16865) — MIXSD: Mixed Contextual Self-Distillation for Knowledge Injection

- **Verdict**: `is_opd = "no"`
- **V3 classifier reasoning**: MIXSD generates mixed supervision targets offline (one-time preprocessing) from the base model before training, not during the training loop; it is off-policy self-distillation for knowledge injection, not on-policy distillation.
- **Removal cause**: MIXSD generates mixed self-distillation targets offline (one-time preprocessing) before training. Off-policy by definition — fails OPD criterion.

---

## See also

- [README.md §🤔 Why On-Policy?](../README.md#-why-on-policy--the-core-problem) — full inclusion criterion
- [README.md §❓ FAQ](../README.md#-faq) — common edge cases

If you believe a paper here was removed in error, please open an issue with:
1. The paper's ICML/NeurIPS/arXiv link
2. Concrete pointer to where in the paper it satisfies criteria (1)–(3) above
3. Quoted text from the paper supporting that claim
