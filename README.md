<a name="readme-top"></a>

<div align="center">
  <a href="https://github.com/nick7nlp/Awesome-LLM-On-Policy-Distillation/stargazers"><img src="https://img.shields.io/github/stars/nick7nlp/Awesome-LLM-On-Policy-Distillation?style=for-the-badge" alt="Stars"></a>
  <a href="https://github.com/nick7nlp/Awesome-LLM-On-Policy-Distillation/network/members"><img src="https://img.shields.io/github/forks/nick7nlp/Awesome-LLM-On-Policy-Distillation?style=for-the-badge" alt="Forks"></a>
  <a href="https://github.com/nick7nlp/Awesome-LLM-On-Policy-Distillation/graphs/contributors"><img src="https://img.shields.io/github/contributors/nick7nlp/Awesome-LLM-On-Policy-Distillation?style=for-the-badge" alt="Contributors"></a>
  <a href="https://github.com/nick7nlp/Awesome-LLM-On-Policy-Distillation/blob/master/LICENSE"><img src="https://img.shields.io/github/license/nick7nlp/Awesome-LLM-On-Policy-Distillation?style=for-the-badge" alt="License"></a>
</div>

<br/>

<h1 align="center">🔥 Awesome LLM On-Policy Distillation</h1>

<p align="center">
  <b>A curated collection of papers and resources on On-Policy Distillation for Large Language Models.</b>
</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a>
  <img src="https://img.shields.io/badge/Papers-94-blue" alt="Papers">
  <img src="https://img.shields.io/badge/Last%20Updated-April%202026-green" alt="Last Updated">
</p>

<p align="center">
  On-policy distillation trains the student on its <b>own</b> generated outputs rather than the teacher's, eliminating exposure bias and enabling learning from self-generated mistakes. This paradigm has become central to modern LLM post-training pipelines.
</p>

<p align="center">
  📖 <b>Survey Paper:</b> <a href="https://arxiv.org/abs/2604.00626">A Survey of On-Policy Distillation for Large Language Models</a>
</p>

<p align="center">
  🟢 = In survey
</p>

<p align="center">
</p>

---

<details>
  <summary>📑 <b>Table of Contents</b></summary>
  <ol>
    <li><a href="#-taxonomy">Taxonomy</a></li>
    <li><a href="#-token-level-on-policy-methods">Token-Level On-Policy Methods</a></li>
    <li><a href="#-sequence-level--hybrid-methods">Sequence-Level & Hybrid Methods</a></li>
    <li><a href="#-black-box-on-policy-distillation">Black-Box On-Policy Distillation</a></li>
    <li><a href="#-self-play--self-distillation">Self-Play & Self-Distillation</a></li>
    <li><a href="#-reasoning-distillation">Reasoning Distillation</a></li>
    <li><a href="#-reward-guided-on-policy-distillation">Reward-Guided On-Policy Distillation</a></li>
    <li><a href="#-industrial-systems--scaling">Industrial Systems & Scaling</a></li>
    <li><a href="#-evaluation--analysis">Evaluation & Analysis</a></li>
    <li><a href="#-open-problems">Open Problems</a></li>
    <li><a href="#-contributing">Contributing</a></li>
    <li><a href="#-citation">Citation</a></li>
  </ol>
</details>

---

## 🗺️ Taxonomy

```
On-Policy Distillation
│
├── 📊 Feedback Signal
│   ├── Logit-Based ─── GKD, MiniLLM, DistiLLM, DSKD, EA-OPD ...
│   ├── Outcome-Based ── RLKD, AlignDistil, KDRL ...
│   └── Self-Play ────── SPIN, OPSD, GATES, SDPO ...
│
├── 🔑 Teacher Access
│   ├── White-Box ────── Full logit access
│   ├── Black-Box ────── API-only
│   └── Self ──────────── No external teacher
│
└── 🔍 Granularity
    ├── Token-Level ──── Per-step divergence
    ├── Sequence-Level ── Trajectory reward
    └── Hybrid ──────── Mixed granularity
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## 🔬 Token-Level On-Policy Methods

> The student generates on-policy; the teacher provides dense token-level logit supervision.

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟢 [TIP: Token Importance in On-Policy Distillation](https://arxiv.org/abs/2604.14084) <br><sub>📐 Qwen3-4B / Llama-3.1-8B / Qwen2.5-1.5B → Qwen3-8B / Llama-70B / Qwen2.5-14B</sub> | 2026 |  |
| 🟢 [Lightning OPD: Efficient Post-Training for Large Reasoning Models with Offline On-Policy Distillation](https://arxiv.org/abs/2604.13010) <br><sub>📐 Qwen3-4B / Qwen3-8B → Qwen3-8B / Qwen3-32B</sub> | 2026 |  |
| 🟢 [SCOPE: Signal-Calibrated On-Policy Distillation Enhancement with Dual-Path Adaptive Weighting](https://arxiv.org/abs/2604.10688) <br><sub>📐 DeepSeek-R1-Distill-Qwen-1.5B / Qwen3-1.7B → SkyWork-OR1-Math-7B / Qwen3-8B</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/machine981/SCOPE) |
| 🟢 [Stable-OPD: Length Inflation and Stabilization Strategies for Large Language Models](https://arxiv.org/abs/2604.08527) <br><sub>📐 Qwen2.5-Math-1.5B/7B → DeepSeek-R1-Distill-7B / OpenThinker3-7B</sub> | 2026 |  |
| 🟢 [HY-Embodied-0.5: Embodied Foundation Models for Real-World Agents](https://arxiv.org/abs/2604.07430) <br><sub>📐 HY-Embodied-0.5 (small) → HY-Embodied (large, internal)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/Tencent-Hunyuan/HY-Embodied) |
| 🟢 [On-Policy Distillation of Language Models for Autonomous Vehicle Motion Planning](https://arxiv.org/abs/2604.07944) <br><sub>📐 Qwen3-1.7B → Qwen3-8B</sub> | 2026 |  |
| 🟢 [DP-OPD: Differentially Private On-Policy Distillation for Language Models](https://arxiv.org/abs/2604.04461) <br><sub>📐 DistilGPT-2 82M → GPT-2 Large 774M (+ DP-SGD)</sub> | 2026 |  |
| 🟢 [VLA-OPD: Bridging Offline SFT and Online RL for Vision-Language-Action Models via On-Policy Distillation](https://arxiv.org/abs/2603.26666) <br><sub>📐 OpenVLA-OPD (7B) → Qwen2.5-VL-72B</sub> | 2026 |  |
| 🟢 [Explain in Your Own Words: Improving Reasoning via Token-Selective Dual Knowledge Distillation](https://arxiv.org/abs/2603.13260) <br><sub>📐 Qwen2.5-1.5B / Gemma-2-2B / Qwen3-1.7B → Qwen2.5-14B / Gemma-2-9B / Qwen3-8B</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/kmswin1/TSD-KD) |
| 🟢 [PACED: Distillation and Self-Distillation at the Frontier of Student Competence](https://arxiv.org/abs/2603.11178) <br><sub>📐 Qwen3-8B → Qwen3-14B; Qwen2.5-Math-7B-Instruct → Self</sub> | 2026 |  |
| 🟢 [Scaling Reasoning Efficiently via Relaxed On-Policy Distillation](https://arxiv.org/abs/2603.11137) <br><sub>📐 DeepSeek-R1-Distill-Qwen-1.5B → SkyWork-OR1-7B/32B</sub> | 2026 |  |
| 🟢 [Entropy-Aware On-Policy Distillation of Language Models](https://arxiv.org/abs/2603.07079) <br><sub>📐 Qwen3-0.6B/1.7B/4B → Qwen3-8B</sub> | 2026 |  |
| 🟢 [X-KD: General Experiential Knowledge Distillation for Large Language Models](https://arxiv.org/abs/2602.12674) <br><sub>📐 T5-Small/Base → T5-Large 780M</sub> | 2026 |  |
| 🟢 [Stable On-Policy Distillation through Adaptive Target Reformulation](https://arxiv.org/abs/2601.07155) <br><sub>📐 Qwen2-0.5B-Instruct → Qwen2-7B-Instruct</sub> | 2026 |  |
| 🟢 [SelecTKD: Selective Token-Weighted Knowledge Distillation for LLMs](https://arxiv.org/abs/2510.24021) <br><sub>📐 Qwen2-1.5B / Gemma-2-2B / Danube2-1.8B → Qwen2-7B / Gemma-2-9B / Mistral-7B</sub> | 2025 |  |
| 🟢 [LLM-Oriented Token-Adaptive Knowledge Distillation](https://arxiv.org/abs/2510.11615) <br><sub>📐 Qwen2-1.5B / OpenLLaMA2-3B → Qwen2-7B / OpenLLaMA2-7B</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/SassyRong/AdaKD) |
| 🟢 [AdaSwitch: Balancing Exploration and Guidance in Knowledge Distillation via Adaptive Switching](https://arxiv.org/abs/2510.07842) <br><sub>📐 Qwen2.5-0.5B / Llama-3.1-1B / Gemma-2B → Qwen2.5-3B / Llama-3.1-3B / Gemma-7B</sub> | 2025 |  |
| 🟢 [ToDi: Token-wise Distillation via Fine-Grained Divergence Control](https://arxiv.org/abs/2505.16297) <br><sub>📐 GPT-2 120M / TinyLLaMA-1.1B → GPT-2 1.5B / LLaMA2-7B</sub> | 2025 |  |
| 🟢 [KETCHUP: K-Step Return Estimation for Sequential Knowledge Distillation](https://arxiv.org/abs/2504.19024) <br><sub>📐 T5-Base 250M → FLAN-T5-XL 3B</sub> | 2025 |  |
| 🟢 [A Dual-Space Framework for General Knowledge Distillation of Large Language Models](https://arxiv.org/abs/2504.11426) <br><sub>📐 GPT-2 120M / TinyLLaMA-1.1B → GPT-2 1.5B / Qwen2-1.5B</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/songmzhang/DSKDv2) |
| 🟢 [DistiLLM-2: A Contrastive Approach Boosts the Distillation of LLMs](https://arxiv.org/abs/2503.07067) <br><sub>📐 Qwen2-1.5B / Gemma-2-2B → Qwen2-7B / Gemma-2-9B</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/jongwooko/distillm-2) |
| 🟢 [Rethinking Kullback-Leibler Divergence in Knowledge Distillation for Large Language Models](https://arxiv.org/abs/2404.02657) <br><sub>📐 GPT-2 120M / TinyLLaMA → GPT-2 1.5B / LLaMA-6.7B</sub> | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/wutaiqiang/LLM_KD_AKL) |
| 🟢 [Revisiting Knowledge Distillation for Autoregressive Language Models](https://arxiv.org/abs/2402.11890) <br><sub>📐 GPT-2 120M / OPT-1.3B → GPT-2 XL / OPT-13B</sub> | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/WHU-ZQH/ATKD) |
| 🟢 [DistiLLM: Towards Streamlined Distillation for Large Language Models](https://arxiv.org/abs/2402.03898) <br><sub>📐 GPT-2 (student) → GPT-2 XL (teacher)</sub> | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/jongwooko/distillm) |
| 🟢 [On-Policy Distillation of Language Models: Learning from Self-Generated Mistakes](https://arxiv.org/abs/2306.13649) <br><sub>📐 T5-Small/Base/Large → T5-XL 3B</sub> | 2024 |  |
| 🟢 [MiniLLM: On-Policy Distillation of Large Language Models](https://arxiv.org/abs/2306.08543) <br><sub>📐 GPT-2 120M–760M → GPT-2 1.5B / GPT-J 6B / OPT-13B</sub> | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/microsoft/LMOps/tree/main/minillm) |
| 🟢 [Distillation of Large Language Models via Concrete Score Matching](https://arxiv.org/abs/2509.25837) <br><sub>📐 GPT-2 0.1B–0.3B → GPT-2 1.5B / OpenLLaMA-7B</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/aailab-kaist/CSD) |
| 🟢 [PromptKD: Distilling Student-Friendly Knowledge for Generative Language Models via Prompt Tuning](https://arxiv.org/abs/2402.12842) <br><sub>📐 GPT-2 120M–760M / OPT/Llama-7B → GPT-2 XL / OPT-13B / Llama-13B</sub> | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/gmkim-ai/PromptKD) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## 🔄 Sequence-Level & Hybrid Methods

> Complete sequence generation + trajectory-level loss, or mixing token and sequence signals.

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟢 [Unifying Group-Relative and Self-Distillation Policy Optimization via Sample Routing](https://arxiv.org/abs/2604.02288) <br><sub>📐 Qwen3-4B / Qwen3-8B → Self (SRPO)</sub> | 2026 |  |
| 🟢 [Fast and Effective On-policy Distillation from Reasoning Prefixes](https://arxiv.org/abs/2602.15260) <br><sub>📐 Qwen3-1.7B / Qwen3-8B → Qwen3-8B (teacher)</sub> | 2026 |  |
| 🟢 [Towards On-Policy SFT: Distribution Discriminant Theory and its Applications in LLM Training](https://arxiv.org/abs/2602.12222) <br><sub>📐 Qwen2.5-7B / DeepSeek-R1-Distill-7B → Self (on-policy SFT)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/zhangmiaosen2000/Towards-On-Policy-SFT) |
| 🟢 [TMS: Trajectory-Mixed Supervision for Reward-Free, On-Policy SFT](https://arxiv.org/abs/2602.03073) <br><sub>📐 Llama-3.1-8B / Qwen2.5-1.5B–7B → LLaMA-3.3-70B</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/UNITES-Lab/tms) |
| 🟢 [Didactic to Constructive: Turning Expert Solutions into Learnable Reasoning](https://arxiv.org/abs/2602.02405) <br><sub>📐 Qwen2.5-7B-Instruct → Self (privileged student)</sub> | 2026 |  |
| 🟢 [CORD: Bridging the Audio-Text Reasoning Gap via Weighted On-policy Cross-modal Distillation](https://arxiv.org/abs/2601.16547) <br><sub>📐 Qwen2-Audio-7B / Step-Audio2-mini → Self (cross-modal)</sub> | 2026 |  |
| 🟢 [Rethinking Large Language Model Distillation: A Constrained Markov Decision Process Perspective](https://arxiv.org/abs/2509.22921) <br><sub>📐 Qwen2.5-1.5B-Math / Llama-3.2-3B → Qwen2.5-7B-Math / Llama-3.2-11B</sub> | 2025 |  |
| 🟢 [SuperCorrect: Advancing Small LLM Reasoning with Thought Template Distillation and Self-Correction](https://arxiv.org/abs/2410.09008) <br><sub>📐 Llama-3-8B / Qwen-7B / DeepSeekMath-7B → larger teacher LLMs (thought template + DPO)</sub> | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/YangLing0818/SuperCorrect-llm) [![Model](https://img.shields.io/badge/Model-🤗-yellow)](https://huggingface.co/BitStarWalkin/SuperCorrect-7B) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## 🌐 Black-Box On-Policy Distillation

> When the teacher is API-only (no logit access).

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟢 [X-OPD: Cross-Modal On-Policy Distillation for Capability Alignment in Speech LLMs](https://arxiv.org/abs/2603.24596) <br><sub>📐 Qwen3-Omni-A3B → Qwen3-A3B-Instruct (text teacher)</sub> | 2026 |  |
| 🟢 [Black-Box On-Policy Distillation of Large Language Models](https://arxiv.org/abs/2511.10643) <br><sub>📐 Llama-3.1-8B / Qwen2.5-3B–14B → GPT-5-Chat (black-box)</sub> | 2025 |  |
| 🟢 [Learning to Reason under Off-Policy Guidance](https://arxiv.org/abs/2504.14945) <br><sub>📐 Qwen2.5-Math-7B → Self; RM: off-policy DeepSeek-R1</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/ElliottYan/LUFFY) |
| 🟢 [Lion: Adversarial Distillation of Proprietary Large Language Models](https://arxiv.org/abs/2305.12870) <br><sub>📐 LLaMA-7B → ChatGPT (adversarial distillation)</sub> | 2023 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/YJiangcm/Lion) |
| 🟢 [ORPO-Distill: Mixed-Policy Preference Optimization for Cross-Architecture LLM Distillation](https://arxiv.org/abs/2509.25100) <br><sub>📐 Various students → InternLM-2.5-7B-Chat</sub> | 2025 |  |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## 🔁 Self-Play & Self-Distillation

> No external teacher; the model improves through self-generated feedback.

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟡 [OPSDL: On-Policy Self-Distillation for Long-Context Language Models](https://arxiv.org/abs/2604.17535) <br><sub>📐 Qwen2.5-Instruct (7B/14B/32B) → Self (short-context as teacher)</sub> | 2026 |  |
| 🟢 [π-Play: Multi-Agent Self-Play via Privileged Self-Distillation without External Data](https://arxiv.org/abs/2604.14054) <br><sub>📐 Qwen3-4B / Qwen3-4B-Instruct / Qwen3-8B → Self (privileged QCP context)</sub> | 2026 |  |
| 🟢 [Self-Distillation Zero: Self-Revision Turns Binary Rewards into Dense Supervision](https://arxiv.org/abs/2604.12002) <br><sub>📐 Qwen3-4B-Instruct / Olmo-3-7B-Instruct → Self</sub> | 2026 |  |
| 🟢 [Self-Distilled RLVR](https://arxiv.org/abs/2604.03128) <br><sub>📐 Qwen3-VL-4B / Qwen3-VL-8B → Self (RLSD)</sub> | 2026 |  |
| 🟢 [Embarrassingly Simple Self-Distillation Improves Code Generation](https://arxiv.org/abs/2604.01193) <br><sub>📐 Llama-3.1-8B / Qwen3-4B–30B-Instruct → Self (SSD, code generation)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/apple/ml-ssd) |
| 🟢 [Why Does Self-Distillation (Sometimes) Degrade the Reasoning Capability of LLMs?](https://arxiv.org/abs/2603.24472) <br><sub>📐 Qwen3-8B / DeepSeek-Distill-7B / Olmo3-7B → Self</sub> | 2026 |  |
| 🟢 [HDPO: Hybrid Distillation Policy Optimization via Privileged Self-Distillation](https://arxiv.org/abs/2603.23871) <br><sub>📐 Qwen2.5-Math-1.5B-Instruct → Self (HDPO)</sub> | 2026 |  |
| 🟢 [Online Experiential Learning for Language Models](https://arxiv.org/abs/2603.16856) <br><sub>📐 Qwen3-1.7B / Qwen3-4B / Qwen3-8B → Self (OEL)</sub> | 2026 |  |
| 🟢 [OpenClaw-RL: Train Any Agent Simply by Talking](https://arxiv.org/abs/2603.10165) | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/Gen-Verse/OpenClaw-RL) |
| 🟢 [On-Policy Self-Distillation for Reasoning Compression](https://arxiv.org/abs/2603.05433) <br><sub>📐 Qwen3-8B / Qwen3-14B → Self (reasoning compression)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/HJSang/OPSD_Reasoning_Compression) |
| 🟢 [GATES: Self-Distillation under Privileged Context with Consensus Gating](https://arxiv.org/abs/2602.20574) <br><sub>📐 Qwen3-4B → Self; oracle: Qwen2.5-32B (privileged gating)</sub> | 2026 |  |
| 🟢 [On-Policy Supervised Fine-Tuning for Efficient Reasoning](https://arxiv.org/abs/2602.13407) <br><sub>📐 DeepSeek-R1-Distill-Qwen-1.5B/7B → Self (on-policy SFT)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/EIT-NLP/On-Policy-SFT) |
| 🟢 [Multi-Token Prediction via Self-Distillation](https://arxiv.org/abs/2602.06019) <br><sub>📐 Llama-3.1-8B → Self (multi-token prediction)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/jwkirchenbauer/mtp-lm) |
| 🟢 [Privileged Information Distillation for Language Models](https://arxiv.org/abs/2602.04942) <br><sub>📐 Qwen3-4B / Qwen3-8B → Self (privileged info, π-Distill)</sub> | 2026 |  |
| 🟢 [Expanding the Capabilities of Reinforcement Learning via Text Feedback](https://arxiv.org/abs/2602.02482) <br><sub>📐 Llama-3.1-8B-Instruct → Qwen3-235B (text feedback RL)</sub> | 2026 |  |
| 🟢 [Reinforcement Learning via Self-Distillation](https://arxiv.org/abs/2601.20802) <br><sub>📐 Qwen3-8B → Self (SDPO, iterative)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/lasgroup/SDPO) |
| 🟢 [Self-Distillation Enables Continual Learning](https://arxiv.org/abs/2601.19897) <br><sub>📐 Qwen2.5-7B-Instruct → Self (continual learning)</sub> | 2026 |  |
| 🟢 [Self-Distilled Reasoner: On-Policy Self-Distillation for Large Language Models](https://arxiv.org/abs/2601.18734) <br><sub>📐 Qwen3-4B / Qwen3-8B → Self (reasoning distillation)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/siyan-zhao/OPSD) |
| 🟢 [Distribution-Aligned Sequence Distillation for Superior Long-CoT Reasoning](https://arxiv.org/abs/2601.09088) <br><sub>📐 Qwen3-4B → gpt-oss-120b / Qwen3-Next-80B-A3B-Thinking (DASD)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/D2I-ai/dasd-thinking) |
| 🟢 [Semantic Soft Bootstrapping: Long Context Reasoning in LLMs without Reinforcement Learning](https://arxiv.org/abs/2512.05105) <br><sub>📐 Qwen2.5-3B-Instruct → Self (soft bootstrapping)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/purbeshmitra/semantic-soft-bootstrapping) |
| 🟢 [Self-Play Fine-Tuning Converts Weak Language Models to Strong Language Models](https://arxiv.org/abs/2401.01335) <br><sub>📐 Zephyr-7B (Mistral-7B) → Self</sub> | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/uclaml/SPIN) [![Model](https://img.shields.io/badge/Model-🤗-yellow)](https://huggingface.co/UCLA-AGI/zephyr-7b-sft-full-SPIN-iter3) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## 🧠 Reasoning Distillation

> Distilling chain-of-thought and step-by-step reasoning capabilities from stronger to weaker models.

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟢 [On-Policy Context Distillation for Language Models](https://arxiv.org/abs/2602.12275) <br><sub>📐 Qwen3-1.7B/4B/8B → Qwen3-8B (thinking, OPCD)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/ZijunSong/On-Policy-Context-Distillation) |
| 🟢 [From Correction to Mastery: Reinforced Distillation of Large Language Model Agents](https://arxiv.org/abs/2509.14257) <br><sub>📐 Qwen2.5-7B / Qwen3-8B → Self (SCoRe, agent)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/modelscope/easydistill) |
| 🟢 [Qwen3 Technical Report](https://arxiv.org/abs/2505.09388) <br><sub>📐 Qwen3 series → Qwen3 (larger, on-policy logit KD)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/QwenLM/Qwen3) [![Model](https://img.shields.io/badge/Model-🤗-yellow)](https://huggingface.co/collections/Qwen/qwen3-67dd247413f0e2e4f653967f) |
| 🟢 [Distilling Step-by-Step! Outperforming Larger Language Models with Less Training Data and Smaller Model Sizes](https://arxiv.org/abs/2305.02301) <br><sub>📐 T5-Small/Base → PaLM-540B (step-by-step rationales)</sub> | 2023 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/google-research/distilling-step-by-step) |

---

## 🎯 Reward-Guided On-Policy Distillation

> Combining on-policy generation with reward models or RL objectives to guide distillation.

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟢 [Skill-SD: Skill-Conditioned Self-Distillation for Multi-turn LLM Agents](https://arxiv.org/abs/2604.10674) <br><sub>📐 Qwen3-4B-Instruct → Self (Skill-SDL)</sub> | 2026 |  |
| 🟢 [Reinforcement-aware Knowledge Distillation for LLM Reasoning](https://arxiv.org/abs/2602.22495) <br><sub>📐 Qwen3-0.6B–8B → Qwen3-8B / Qwen3-32B (RLAD)</sub> | 2026 |  |
| 🟢 [Learning beyond Teacher: Generalized On-Policy Distillation with Reward Extrapolation](https://arxiv.org/abs/2602.12125) <br><sub>📐 Qwen3-4B-Non-Thinking → Self-RL teachers / Qwen3-30B-A3B (G-OPD)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/RUCBM/G-OPD) |
| 🟢 [KEPO: Knowledge-Enhanced Preference Optimization for Reinforcement Learning with Reasoning](https://arxiv.org/abs/2602.00400) <br><sub>📐 Qwen3-VL-2B / Qwen3-VL-8B → Qwen3-VL-32B (KEPO)</sub> | 2026 |  |
| 🟢 [A Note on Hybrid Online Reinforcement and Imitation Learning for LLMs: Formulations and Algorithms](https://arxiv.org/abs/2512.23097) <br><sub>📐 Theoretical (no specific models)</sub> | 2025 |  |
| 🟢 [VOLD: Reasoning Transfer from LLMs to Vision-Language Models via On-Policy Distillation](https://arxiv.org/abs/2510.23497) <br><sub>📐 Qwen2.5-VL-3B → Qwen3-8B (text reasoning teacher)</sub> | 2025 |  |
| 🟢 [ThinkTuning: Instilling Cognitive Reflections without Distillation](https://arxiv.org/abs/2508.07616) <br><sub>📐 Llama-3.2-3B → Self (cognitive reflection, ThinkTuning)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/3rdAT/ThinkTuning) |
| 🟢 [KDRL: Post-Training Reasoning LLMs via Unified Knowledge Distillation and Reinforcement Learning](https://arxiv.org/abs/2506.02208) <br><sub>📐 R1-Distill-Qwen-1.5B → Skywork-OR1-Math-7B (KDRL)</sub> | 2025 |  |
| 🟢 [RLKD: Distilling LLMs' Reasoning via Reinforcement Learning](https://arxiv.org/abs/2505.16142) <br><sub>📐 Qwen2.5-Math-7B / R1-Distill-Qwen-7B → DeepSeek-R1 traces (RLKD)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/xsc1234/RLKD) |
| 🟢 [AlignDistil: Token-Level Language Model Alignment as Adaptive Policy Distillation](https://arxiv.org/abs/2503.02832) <br><sub>📐 Qwen2-1.5B / Qwen2.5-1.5B-Instruct → Self (AlignDistil)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/songmzhang/AlignDistil) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## 🏭 Industrial Systems & Scaling

> Large-scale deployments and system-level applications of on-policy distillation.

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟢 [ORBIT: On-policy Exploration-Exploitation for Controllable Multi-Budget Reasoning](https://arxiv.org/abs/2601.08310) <br><sub>📐 DeepSeek-Distill-Qwen-1.5B / Qwen3-4B-Thinking / Nemotron-7B → Self (multi-teacher OPD fusion)</sub> | 2026 |  |
| 🟢 [HY-Embodied-0.5: Embodied Foundation Models for Real-World Agents](https://arxiv.org/abs/2604.07430) <br><sub>📐 HY-Embodied-0.5 (small) → HY-Embodied (large, internal)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/Tencent-Hunyuan/HY-Embodied) |
| 🟢 [KAT-Coder-V2 Technical Report](https://arxiv.org/abs/2603.27703) <br><sub>📐 KAT-Coder-V2 (proprietary multi-expert pipeline)</sub> | 2026 |  |
| 🟢 [Nemotron-Cascade 2: Post-Training LLMs with Cascade RL and Multi-Domain On-Policy Distillation](https://arxiv.org/abs/2603.19220) <br><sub>📐 Nemotron-Cascade-2-30B-A3B → Self (multi-ckpt MOPD)</sub> | 2026 |  |
| 🟢 [Video-OPD: Efficient Post-Training of Multimodal Large Language Models for Temporal Video Grounding via On-Policy Distillation](https://arxiv.org/abs/2602.02994) <br><sub>📐 Qwen3-VL-8B → Qwen3-VL-32B (Video-OPD)</sub> | 2026 |  |
| 🟢 [OVD: On-policy Verbal Distillation](https://arxiv.org/abs/2601.21968) <br><sub>📐 Qwen2.5-3B / LLaMA-3.2-3B → QwQ-32B (verbal feedback)</sub> | 2026 |  |
| 🟢 [MiMo-V2-Flash Technical Report](https://arxiv.org/abs/2601.02780) <br><sub>📐 MiMo-V2-Flash 309B MoE → Self (multi-teacher MOPD)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/XiaomiMiMo/MiMo-V2-Flash) [![Model](https://img.shields.io/badge/Model-🤗-yellow)](https://huggingface.co/XiaomiMiMo/MiMo-V2-Flash) |
| 🟢 [Retaining by Doing: The Role of On-Policy Data in Mitigating Forgetting](https://arxiv.org/abs/2510.18874) <br><sub>📐 Llama-3.1-8B / Llama-3.2-1B → Llama-3.3-70B</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/princeton-pli/retaining-by-doing) |
| 🟢 [Why Knowledge Distillation Works in Generative Models: A Minimal Working Explanation](https://arxiv.org/abs/2505.13111) <br><sub>📐 SmolLM2-135M → SmolLM2-360M (theory + empirical)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/csm9493/kd-minimal-explanation) |
| 🟢 [Qwen3 Technical Report](https://arxiv.org/abs/2505.09388) <br><sub>📐 Qwen3 series → Qwen3 (larger, on-policy logit KD)</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/QwenLM/Qwen3) [![Model](https://img.shields.io/badge/Model-🤗-yellow)](https://huggingface.co/collections/Qwen/qwen3-67dd247413f0e2e4f653967f) |
| 🟢 [Distillation Scaling Laws](https://arxiv.org/abs/2502.08606) <br><sub>📐 143M–1.4B → 975M–12.6B (scaling law study)</sub> | 2025 |  |
| 🟢 [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948) <br><sub>📐 Qwen2.5-1.5B–32B / Llama-3-8B–70B → DeepSeek-R1 671B</sub> | 2025 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/deepseek-ai/DeepSeek-R1) [![Model](https://img.shields.io/badge/Model-🤗-yellow)](https://huggingface.co/deepseek-ai/DeepSeek-R1) |
| 🟢 [Speculative Knowledge Distillation: Bridging the Teacher-Student Gap Through Interleaved Sampling](https://arxiv.org/abs/2410.11325) <br><sub>📐 Gemma-2B / Qwen-0.5B → Gemma-7B / Qwen-7B</sub> | 2024 |  |
| 🟢 [Gemma 2: Improving Open Language Models at a Practical Size](https://arxiv.org/abs/2408.00118) <br><sub>📐 Gemma-2-2B/9B → Gemma-2-27B (online KD in pre-training)</sub> | 2024 | [![Model](https://img.shields.io/badge/Model-🤗-yellow)](https://huggingface.co/google/gemma-2-27b) |
| 🟢 [DistillSpec: Improving Speculative Decoding via Knowledge Distillation](https://arxiv.org/abs/2310.08461) <br><sub>📐 T5-Small → T5-XL (on-policy KD for speculative decoding)</sub> | 2023 |  |

---

## 📊 Evaluation & Analysis

> Empirical studies, theoretical analysis, and benchmarks for understanding distillation.

| Paper | Date | Resources |
|-------|:----:|:---:|
| 🟡 [The Illusion of Certainty: Decoupling Capability and Calibration in On-Policy Distillation](https://arxiv.org/abs/2604.16830) <br><sub>📐 Qwen2.5-Instruct (3B/7B/32B) → Self (CaOPD, calibration-aware OPD)</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/SalesforceAIResearch/CaOPD) |
| 🟢 [Rethinking On-Policy Distillation of Large Language Models: Phenomenology, Mechanism, and Recipe](https://arxiv.org/abs/2604.13016) <br><sub>📐 Qwen3-1.7B → DeepSeek-R1-Distill-7B / Qwen3-4B etc.</sub> | 2026 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/thunlp/OPD) |
| 🟢 [Revisiting On-Policy Distillation: Empirical Failure Modes and Simple Fixes](https://arxiv.org/abs/2603.25562) <br><sub>📐 Qwen2.5-7B-Instruct → OpenThinker3-7B / GiGPO-Qwen2.5-7B</sub> | 2026 |  |
| 🟢 [Towards Cross-Tokenizer Distillation: the Universal Logit Distillation Loss for LLMs](https://arxiv.org/abs/2402.12030) <br><sub>📐 Various students → Various teachers (cross-tokenizer ULD)</sub> | 2025 |  |
| 🟢 [A Survey on Knowledge Distillation of Large Language Models](https://arxiv.org/abs/2402.13116) | 2024 | [![Code](https://img.shields.io/badge/Code-GitHub-blue)](https://github.com/Tebmer/Awesome-Knowledge-Distillation-of-LLMs) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---
## 🗺️ Open Problems

| # | Problem | Description |
|:-:|---------|-------------|
| 1 | **Scaling Laws** | No equivalent of Chinchilla for OPD; the student rollout cost adds a new compute axis |
| 2 | **Teacher Calibration** | Teacher logits may be miscalibrated on student-generated OOD prefixes |
| 3 | **Dynamic Curriculum** | Principled difficulty scheduling that adapts as the student improves |
| 4 | **Cross-Architecture OPD** | Distilling across model families with different tokenizers |
| 5 | **Agent OPD** | Multi-step, tool-using agents with delayed feedback |
| 6 | **Multimodal OPD** | Extending to vision-language and speech models |
| 7 | **KD-RL Loop** | Principled alternation between distillation and RL phases |
| 8 | **Beyond Benchmarks** | Dynamic adversarial testing for true generalization |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

---

## 🤝 Contributing

We welcome contributions! Please submit a **Pull Request** with:

- 📎 Paper title, arXiv link, and date
- 📝 Brief description of the key contribution
- 📂 Correct category placement

---

## 📄 Citation

If you find this collection helpful, please consider citing our survey:

```bibtex
@article{song2026survey,
  title={A Survey of On-Policy Distillation for Large Language Models},
  author={Song, Mingyang and Zheng, Mao},
  journal={arXiv preprint arXiv:2604.00626},
  year={2026}
}
```

---

<div align="center">

**⭐ If you find this repository useful, please star it! ⭐**

*Last updated: April 2026*

</div>
