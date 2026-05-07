# Contributing to Awesome LLM On-Policy Distillation

Thanks for your interest in contributing! This repository tracks the rapidly growing field of on-policy distillation for LLMs.

## How to Add a Paper

1. **Fork** this repository
2. **Add** your paper to the correct section in `README.md`
3. **Submit** a Pull Request using the template below

### Paper Entry Format

```markdown
| 🟢 [Paper Title](https://arxiv.org/abs/XXXX.XXXXX) <br><sub>📐 Teacher → Student (key technique or finding)</sub> | Year | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/...) |
```

### PR Template

Please include:
- **Paper:** Title + arXiv link
- **Date:** Publication date
- **Category:** Which section it belongs to (§4.1, §4.2, §5.1, etc.)
- **Key Contribution:** One-line summary
- **Models:** Teacher → Student configuration
- **Code:** GitHub link (if available)

## Inclusion Criteria

### ✅ Include if:
- The method has an **explicit on-policy sampling component** (student generates rollouts during training)
- It provides **direct insights for OPD** practitioners (analysis papers, failure modes, theoretical foundations)
- It's a **hybrid method** that combines on-policy and off-policy elements
- It's a **tech report** from a major lab describing OPD usage (even without arXiv)

### ❌ Exclude if:
- Pure off-policy SFT (training only on static teacher demonstrations)
- Pure RL without any distillation signal (vanilla PPO/GRPO without KL to teacher)
- Non-LLM domains (vision-only, speech-only without language component)
- Retrieval/embedding models that use "distillation" in name only

## Categories

| Section | Focus |
|---------|-------|
| §4.1 | Divergence/loss function design (KL variants, score matching) |
| §4.2 | Training dynamics (weighting, curriculum, stability, efficiency) |
| §4.3 | Cross-architecture alignment (different tokenizers, model families) |
| §4.4 | Black-box / information-constrained distillation |
| §4.5 | RL-augmented, reward-guided, beyond distribution matching |
| §5.1 | Self-distillation via privileged information |
| §5.2 | Self-play and iterative self-improvement |
| §5.3 | External feedback (reward models, verifiers) |
| §6 | Theory, analysis, failure modes |
| §7.1 | Industrial deployment and tech reports |
| §7.2 | System optimization (speculative decoding, efficiency) |
| §7.3 | Emerging domains (vision-language, embodied, audio) |

## Other Ways to Contribute

- 🐛 **Fix bugs**: Broken links, wrong categories, incorrect descriptions
- 📊 **Add data**: Benchmark results, compute costs, reproduction tips
- 🛠️ **Add code**: New implementations or reproduction repositories
- 📝 **Improve writing**: Clearer descriptions, better organization

## Code of Conduct

Be respectful. Give credit where due. When in doubt about categorization, open an issue for discussion.
