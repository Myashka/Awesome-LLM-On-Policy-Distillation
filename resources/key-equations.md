# 📐 Key Equations

Quick reference for the core loss functions and formulations in OPD.

## Divergence Objectives

### Forward KL (Mode-Covering)
$$\mathcal{L}_{\text{FKL}} = \mathbb{E}_{y \sim p_S} \left[ \sum_t p_T(y_t | y_{<t}, x) \log \frac{p_T(y_t | y_{<t}, x)}{p_S(y_t | y_{<t}, x)} \right]$$

### Reverse KL (Mode-Seeking) — Default for OPD
$$\mathcal{L}_{\text{RKL}} = \mathbb{E}_{y \sim p_S} \left[ \sum_t p_S(y_t | y_{<t}, x) \log \frac{p_S(y_t | y_{<t}, x)}{p_T(y_t | y_{<t}, x)} \right]$$

### Adaptive KL (AKL)
Blends Forward KL and Reverse KL dynamically based on token-level difficulty or entropy to balance mode-seeking and mode-covering behavior.
$$\mathcal{L}_{\text{AKL}} = \alpha_t \mathcal{L}_{\text{FKL}} + (1 - \alpha_t) \mathcal{L}_{\text{RKL}}$$

### GKD Generalized Divergence
Generalized Knowledge Distillation allows interpolation between different divergences by tuning a parameter $\beta$. When $\beta \to 1$, it aligns with Reverse KL; when $\beta \to 0$, it aligns with Forward KL; and intermediate values align with Jensen-Shannon Divergence (JSD).

## Token Selection

### TIP Soft-OR Score
Used to filter and retain only the most important tokens (often top 20-50%) based on token-level importance scores, saving computation and memory.

## Self-Distillation

### OPSD Loss
On-Policy Self-Distillation typically leverages privileged information or longer reasoning traces from the student itself to act as the "teacher" signal, matching the distribution of the less-privileged generation path to the privileged one.
