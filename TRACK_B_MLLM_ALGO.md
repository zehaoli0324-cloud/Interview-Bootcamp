# Track B — A180084A 医疗大模型算法实习生

> 岗位：大模型算法实习生（医疗方向）- 搜索  
> 核心定位：**模型训练算法 + CV/ViT/MLLM + SFT/RL + Coding**。

---

# 1. JD 真正要什么

核心职责：

1. 医疗大模型预训练、SFT、强化训练；
2. 对业务模型效果负责；
3. 调研并落地医疗大模型前沿方案。

基本要求中特别强调：

- 优秀 Coding / 数据结构 / 基础算法；
- CV 算法与技术；
- MLLM 模型结构；
- ViT 训练；
- Detail Caption；
- NLP / 大模型训练 / RL 经验优先。

因此面试核心不是“你会不会做 benchmark”，而是：

> **你是否具备进入模型训练团队的算法基础，能理解并实现 MLLM / ViT / post-training 方案。**

---

# 2. 面试训练权重

- **Python / Data Structure / Algorithm Coding：45%**
- **CV / ViT / MLLM：30%**
- **Pretraining / SFT / LoRA / RL：15%**
- **Medical / Research / Evaluation：10%**

---

# 3. Coding 主线

必须通过 `PYTHON_LEVEL0.md` 后进入 `LEETCODE_CORE_15.md`。

## P0

- HashMap；
- Stack；
- Linked List；
- Sliding Window；
- Binary Search；
- Tree BFS；
- Grid DFS/BFS；
- Heap / Top-K；
- Interval；
- LRU。

## P1

- Basic DP；
- Longest Valid Parentheses；
- sqrt binary/Newton；
- k-group linked list stretch。

Track B 对算法的要求高于 Track A：

- Easy 应接近稳定；
- 常见 Medium 应能在 25–35 min 内形成正确实现；
- 需要更强的复杂度、边界与陌生题迁移能力。

---

# 4. CV / ViT / MLLM

主教材：`MLLM_VIT_CORE.md`。

必须能够解释：

- CNN vs ViT inductive bias；
- patch embedding；
- positional embedding；
- self-attention；
- CLS token / pooling；
- ViT pretraining / finetuning；
- vision encoder；
- projector / adapter；
- Q-Former / resampler；
- LLaVA-style architecture；
- visual instruction tuning；
- Detail Caption；
- high-resolution / tiling；
- image token length / compute tradeoff；
- multimodal hallucination；
- grounding；
- medical image/report alignment。

面试不只背概念，还要能做 shape / token 数计算和简单架构设计。

---

# 5. Pretraining / SFT / RL

主教材：`POSTTRAINING_SFT_RL_CORE.md`。

必须理解：

- pretraining objective；
- instruction SFT；
- LoRA / PEFT；
- preference data；
- DPO；
- reward model；
- PPO 基本结构；
- GRPO 基本直觉；
- rollout；
- KL regularization；
- reward hacking；
- offline/online evaluation。

医疗迁移问题：

- reward 如何体现 factuality / safety / guideline consistency；
- 如何避免“为了高 reward 编造指南”；
- 稀有高风险 case 如何进训练；
- preference 数据如何做专家校准。

---

# 6. 最小实践证据

Track B 最好在面试前至少完成一个小实验：

## Option 1 — ViT / CLIP inference

- 加载公开小模型；
- 输入几张图；
- 打印 preprocessing / embedding shape；
- 解释 token 数和输出。

## Option 2 — Tiny LoRA SFT

- 小型开源模型；
- 几十/几百条 toy medical instruction；
- LoRA；
- train/eval split；
- 训练前后 loss / 简单质量对比；
- 说明过拟合风险。

## Option 3 — Small MLLM inference + error analysis

- 选公开 MLLM；
- 5–20 个医学/生物图像样例；
- 记录 hallucination / grounding / detail caption 失败；
- 给出 eval rubric。

重点不是模型规模，而是你能解释完整 pipeline。

---

# 7. Track B 通过线

## Coding
- Foundation 通过；
- Level 1 4/4 PASS；
- Level 2 至少 6/7 PASS；
- LC3 / LC200 / LC215 / LC146 必须稳定；
- 陌生常见 Medium 不空白。

## MLLM
- ViT core ≥8；
- LLaVA-style pipeline 能从 image 到 token 到 LLM 完整说明；
- Detail Caption / high-resolution 能讲目的与 tradeoff；
- medical hallucination 能设计评测。

## Post-training
- SFT / LoRA / DPO / PPO / GRPO 能比较；
- 能解释 reward hacking 和 KL；
- 能给出医疗 reward 设计。

---

# 8. Track B 不应依赖的优势

Benchmark / Agent Eval / 医疗 domain 可以加分，但不能替代：

- Coding；
- ViT / MLLM；
- 模型训练基础。

原则：

> **这是模型算法岗。评测能力能让你更有差异化，但必须先证明你能进入模型训练技术栈。**
