# ⚡ Method Quick-Reference Matrix

At-a-glance comparison of key OPD methods. Use this to pick the right method for your use case.

## Teacher-Guided Methods

| Method | Divergence | Token Selection | Speed | Best For | Key Insight |
|--------|-----------|-----------------|-------|----------|-------------|
| **GKD** | RKL/FKL/JSD | All tokens | 1× | General purpose | On-policy sampling + configurable divergence |
| **MiniLLM** | RKL | All tokens | 1× | Math/Code | Policy gradient interpretation of RKL |
| **DistiLLM** | Skewed KL | All tokens | 1.5× | Stability | Streaming + adaptive skew prevents collapse |
| **AKL** | Adaptive FKL↔RKL | All tokens | 1× | Mixed tasks | Token-level divergence switching |
| **TIP** | RKL | Top 20-50% | 2× | Compute-limited | Only high-entropy tokens need KD |
| **SCOPE** | Dual-path (RKL+FKL) | Adaptive | 1× | Pass@k matters | Fixes diversity collapse |
| **Lightning OPD** | RKL | All tokens | **4×** | Speed priority | Offline — no live teacher needed |
| **TAID** | Adaptive | Curriculum | 1× | Large gap | Progressive capacity-aware scheduling |

## Self-Distillation Methods

| Method | Signal Source | Needs Teacher? | Best For | Key Insight |
|--------|-------------|----------------|----------|-------------|
| **OPSD** | Privileged context | ❌ | Math reasoning | Student's own oracle as teacher |
| **SDZero** | Binary reward → dense | ❌ | No reward model | Converts pass/fail into token-level signal |
| **SDPO** | Text feedback | ❌ | Multi-step | Tokenized feedback as distillation target |
| **SPIN** | Self vs human | ❌ | Alignment | Iterative self-play against human references |
| **On-Policy SFT** | Self-filter | ❌ | Quick setup | Simple: generate, filter correct, retrain |

## Decision Quick-Reference

```
What's your bottleneck?
│
├── Compute → Lightning OPD (offline, 4x faster) or TIP (20% tokens)
├── No teacher → OPSD / SDZero / On-Policy SFT
├── Diversity matters → SCOPE (dual-path) or AKL (adaptive)
├── Multi-turn / Agent → TCOD (temporal curriculum)
├── Cross-architecture → ULD / DSKD (representation alignment)
└── Production at scale → Follow DeepSeek-V4 recipe (RKL + multi-domain)
```

## Compute Budget Guide

| Budget | Recommended Pipeline |
|--------|---------------------|
| **Low** (< 50 GPU-hrs) | Lightning OPD or TIP with 20% tokens |
| **Medium** (50-200 GPU-hrs) | Standard GKD/MiniLLM with full training |
| **High** (200+ GPU-hrs) | Multi-stage: SFT → OPD → RL fine-tune |
| **Huge** (1000+ GPU-hrs) | DeepSeek-V4 style: domain experts → OPD consolidation |
