# 📊 Benchmarks & Performance

## Commonly Used Benchmarks

### Mathematical Reasoning
| Benchmark | Description | Typical OPD Gain |
|-----------|-------------|-----------------|
| MATH-500 | Competition-level math | +3-8% over SFT |
| AIME 2024/2025 | AMC/AIME problems | +5-15% over SFT |
| GSM8K | Grade school math | +2-5% over SFT |

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

## Performance Comparison (Qwen3 family)

| Method | MATH-500 | AIME'24 | GSM8K | Framework |
|--------|----------|---------|-------|-----------|
| SFT (off-policy) | 72.4 | 33.3 | 85.2 | - |
| GKD (RKL) | 76.1 | 40.0 | 87.8 | GKD |
| OPSD | 78.3 | 43.3 | 88.5 | OPSD |
| TIP (20% tokens) | 79.1 | 46.7 | 89.2 | OPSD |
| SCOPE | 80.2 | 46.7 | 89.0 | SCOPE |

*Note: SFT, GKD, OPSD baseline data extracted from SCOPE & TIP tables.*

### Specialized Results

**TIP (2604.14084)**:
- Qwen3-8B→4B: MATH-500 Full OPD = 76.2 | TIP 20% = 78.4 | TIP 50% = 76.8
- Entropy 50% achieves the same performance as Full OPD while saving 47% memory.

**SCOPE (2604.10688)**:
- R1-Distill-Qwen-1.5B: Avg@32 best among all evaluated methods.
- Pass@1 is competitive with top methods, while Pass@k is significantly better than vanilla OPD (alleviates diversity collapse).

**Lightning OPD (2604.13010)**:
- Qwen3-8B-Base → AIME 2024 reaches 69.9% in ~30 GPU hours.
- Demonstrates 4x faster training than standard OPD.

**CaOPD (2604.16830)**:
- Qwen3-8B SDFT exhibits miscalibration: accuracy 49.1% but confidence 97.2% (Overconfidence Gap = +48.1%).
- CaOPD fix: ECE 0.486 → 0.266 (↓45%), accuracy 49.1% → 50.0%.

**Rethinking OPD (2604.13016)**:
- Success condition: Top-k overlap between student and teacher increases from 72% → 91% during training.
- Successful OPD places 97-99% probability mass on overlap tokens.
- Failure mode: Overlap stagnates and entropy mismatch occurs.

## Compute Costs
| Method | GPU Hours (8B student) | Relative to SFT |
|--------|----------------------|-----------------|
| Off-policy SFT | ~4h (8×H100) | 1× |
| Standard OPD | ~16h | 4× |
| Lightning OPD | ~4h | 1× |
| TIP (20% tokens) | ~8h | 2× |
