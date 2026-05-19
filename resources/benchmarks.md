# 📊 Benchmarks & Performance

## Commonly Used Benchmarks

### Mathematical Reasoning
| Benchmark | Description | Typical OPD Gain |
|-----------|-------------|-----------------|
| MATH-500 | Competition-level math | +3-8% over SFT |
| AIME 2024/2025 | AMC/AIME problems | +5-15% over SFT |
| GSM8K | Grade school math | +2-5% over SFT |
| HMMT 2025 | Harvard-MIT Math Tournament | Emerging benchmark for frontier reasoning |

### Code Generation
| Benchmark | Description | Typical OPD Gain |
|-----------|-------------|-----------------|
| LiveCodeBench v6 | Real-time coding | +4-10% over SFT |
| HumanEval+ | Function generation | +3-7% over SFT |

### General Reasoning
| Benchmark | Description | Typical OPD Gain |
|-----------|-------------|-----------------|
| MMLU / MMLU-Pro | Broad knowledge | +1-4% over SFT |
| GPQA | Graduate-level reasoning | +3-8% over SFT |

---

## MATH-500 Results

> Key methods compared on MATH-500 (Qwen family students).

| Method | Paper | Student | MATH-500 | Notes |
|--------|-------|---------|:--------:|-------|
| SFT (off-policy) | baseline | Qwen3-4B | 72.4 | Static teacher demonstrations |
| GKD (RKL) | [Agarwal+ 2023](https://arxiv.org/abs/2306.13649) | Qwen3-4B | 76.1 | Canonical on-policy KD |
| MiniLLM (RKL) | [Gu+ 2023](https://arxiv.org/abs/2306.08543) | Qwen3-4B | 75.8 | Reverse-KL mode-seeking |
| OPSD | [Zhao+ 2026](https://arxiv.org/abs/2601.18734) | Qwen3-4B | 78.3 | Privileged oracle answer |
| AKL | [Wen+ 2024](https://arxiv.org/abs/2404.02657) | Qwen3-4B | 77.5 | Adaptive F-KL/R-KL mixing |
| TIP (20% tokens) | [2604.14084](https://arxiv.org/abs/2604.14084) | Qwen3-4B | 79.1 | Top entropy token selection |
| SCOPE | [2604.10688](https://arxiv.org/abs/2604.10688) | Qwen3-4B | 80.2 | Dual-path adaptive + diversity |
| TRACE (harness) | [2605.08741](https://arxiv.org/abs/2605.08741) | Qwen3-8B | 82.6 | +10.83% over OPSD on HMMT |

*Data extracted from SCOPE, TIP, and TRACE paper tables.*

---

## AIME 2024 Results

| Method | Paper | Student | AIME'24 (Pass@1) | Notes |
|--------|-------|---------|:----------------:|-------|
| SFT (off-policy) | baseline | Qwen3-4B | 33.3 | — |
| GKD (RKL) | [Agarwal+ 2023](https://arxiv.org/abs/2306.13649) | Qwen3-4B | 40.0 | — |
| OPSD | [Zhao+ 2026](https://arxiv.org/abs/2601.18734) | Qwen3-4B | 43.3 | — |
| SCOPE | [2604.10688](https://arxiv.org/abs/2604.10688) | Qwen3-4B | 46.7 | — |
| Lightning OPD | [2604.13010](https://arxiv.org/abs/2604.13010) | Qwen3-8B | 69.9 | In ~30 GPU hours |

---

## AIME 2025 Results

| Method | Paper | Student | AIME'25 (Pass@1) | Notes |
|--------|-------|---------|:----------------:|-------|
| OPSD | [Zhao+ 2026](https://arxiv.org/abs/2601.18734) | Qwen3-8B | ~38 | Estimated from paper |
| SCOPE | [2604.10688](https://arxiv.org/abs/2604.10688) | R1-Distill-1.5B | Avg@32 best | Pass@k significantly better |

*Limited data available; AIME 2025 is a newer benchmark.*

---

## LiveCodeBench Results

| Method | Paper | Student | LiveCodeBench v6 | Notes |
|--------|-------|---------|:----------------:|-------|
| SFT baseline | — | Qwen3-8B | ~32 | Off-policy |
| SSD (self-distill) | [Apple 2604.01193](https://arxiv.org/abs/2604.01193) | Qwen3-8B | ~38 | Embarrassingly simple |
| RLKD | [2505.16142](https://arxiv.org/abs/2505.16142) | Qwen2.5-Math-7B | ~35 | RL + distillation |

---

## Diversity (Pass@k) Analysis

> SCOPE (2604.10688) revealed the critical diversity collapse problem.

| Method | Pass@1 | Pass@8 | Pass@64 | Notes |
|--------|:------:|:------:|:-------:|-------|
| Vanilla OPD | **High** | Low | Very Low | Severe diversity collapse |
| SCOPE (dual-path) | Competitive | **High** | **High** | Alleviates collapse |
| GRPO (RL only) | Moderate | Moderate | Moderate | No collapse but lower peak |

---

## Compute Cost Comparison

| Method | Paper | GPU Hours (8B student) | Hardware | Relative to SFT | Notes |
|--------|-------|:----------------------:|:--------:|:----------------:|-------|
| Off-policy SFT | — | ~4h | 8×H100 | 1× | Static data |
| Standard OPD (GKD) | Agarwal+ 2023 | ~16h | 8×H100 | 4× | Full rollout every step |
| Lightning OPD | 2604.13010 | ~4h | 8×H100 | 1× | Teacher consistency + offline |
| TIP (20% tokens) | 2604.14084 | ~8h | 8×H100 | 2× | 47% memory savings |
| DistiLLM (skew-KL) | Jongwoo+ 2024 | ~12h | 8×H100 | 3× | Careful mixing schedule |
| OPSD (self-distill) | Zhao+ 2026 | ~10h | 8×A100 | 2.5× | No external teacher |
| CaOPD | 2604.16830 | ~12h | 8×H100 | 3× | + calibration overhead |

---

## Calibration Results (CaOPD)

> From "The Illusion of Certainty" (2604.16830):

| Model | Accuracy | Confidence | Overconfidence Gap | ECE |
|-------|:--------:|:----------:|:-----------------:|:---:|
| Qwen3-8B (SDFT, before) | 49.1% | 97.2% | +48.1% | 0.486 |
| Qwen3-8B (CaOPD, after) | 50.0% | ~70% | ~20% | 0.266 |

**Key insight:** Standard OPD produces overconfident models. CaOPD reduces ECE by 45%.

---

## Success/Failure Diagnostics (Rethinking OPD)

> From "Rethinking On-Policy Distillation" (2604.13016):

| Metric | Successful OPD | Failed OPD |
|--------|:--------------:|:----------:|
| Top-k overlap (start) | 72% | 72% |
| Top-k overlap (end) | 91% | Stagnant |
| Probability mass on overlap | 97-99% | < 80% |
| Entropy mismatch | Low | High |

**Two necessary conditions for OPD success:**
1. Top-k overlap between student and teacher must increase during training
2. Student must concentrate probability mass on overlap tokens
