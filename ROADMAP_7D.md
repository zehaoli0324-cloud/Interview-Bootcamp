# ROADMAP 7D — Medical MLLM Algorithm Interview V3

> 默认每天 6–8 小时。如果只有 3–4 小时，保留每一天的 P0，不扩题。
>
> 默认权重：Coding 50% / MLLM 25% / Post-training 15% / Medical Eval 10%。

---

# Day 1 — 从看懂代码到 Two Sum

## P0：Python Foundation（3–4 h）

使用 `PYTHON_LEVEL0.md`。

只学：
- list / index；
- variable；
- `for`；
- `if`；
- function / return；
- dict。

顺序：

`Z1–Z4 → Z5–Z9 → Z10–Z14 → Z15–Z18`

不要机械全做；会的跳过。

## 核心结果

必须做到：
- 看懂输入输出；
- 能自己 trace 两层循环；
- 能写 Two Sum 暴力版；
- 理解 `target - x` 是“补数”。

如果 Z15–Z18 至少 3/4 独立完成，立刻标 `FOUNDATION_PASSED`。

## MLLM 插针（60–90 min）

只学 M1/M2：
- 图像如何变成 patch tokens；
- patch embedding。

完成 MX1：224/16 的 patch 数量计算。

## Day 1 Exit

- Foundation Gate 通过，或明确只剩 1–2 个语法点；
- Two Sum 暴力版能独立解释；
- 知道 ViT 会把图像切成 tokens。

---

# Day 2 — Easy Coding + ViT 基础

## Coding P0（3 h）

从 `LEETCODE_CORE_15.md`：

1. LC1 HashMap 版本；
2. LC20 Stack；
3. LC206 Reverse Linked List。

LC165 如果时间够再做。

规则：
- 先允许 brute force；
- 再问如何优化；
- 每题必须自己给 2 个测试。

## Python micro repair

只有出现具体 API/语法错误时补 5–10 min，不回去重刷 Level 0。

## MLLM（2 h）

M3–M5：
- position embedding；
- self-attention 直觉；
- ViT vs CNN。

必须会回答：
- patch 变小为什么 token 数增加；
- 高分辨率为什么贵。

## Day 2 Exit

- 至少 2 道 Easy ≥7.5；
- LC1 必须能解释 dict 里存什么；
- 能画最简 ViT 数据流。

---

# Day 3 — Sliding Window / Binary Search + MLLM 架构

## Coding（3 h）

P0：
- LC3 Sliding Window；
- LC33 Binary Search。

P1：
- LC56 Interval merge。

目标不是一次写对所有 Medium，而是：
- 能先给 brute force；
- 能说清 invariant；
- 能跟随最小反例 debug。

## MLLM（2–2.5 h）

M6–M8：
- vision encoder → visual features；
- projector / adapter；
- LLM token space；
- LLaVA 两阶段直觉；
- Q-Former/resampler。

完成 MX3 shape walkthrough：

`[B,576,1024] → projector → [B,576,4096]`

## Post-training 预热（45 min）

P1：Pretraining vs SFT。

## Day 3 Exit

- LC3/LC33 至少一题 PASS；
- 能画 image → encoder → projector → LLM；
- 能解释 projector 为什么需要。

---

# Day 4 — BFS/DFS/Heap + Detail Caption / High Resolution

## Coding（3 h）

P0：
- LC102 Tree BFS；
- LC200 Grid DFS/BFS；
- LC215 Top-K Heap。

LC200 是重点。

必须会：
- visited 什么时候标；
- DFS vs BFS；
- heap 为什么是 O(n log k)。

## MLLM（2 h）

M9–M12：
- Detail Caption；
- high-resolution / tile / multi-scale；
- hallucination；
- medical MLLM evaluation。

完成二选一：
- MX4 医疗 Detail Caption schema；
- MX5 小病灶高分辨率方案。

## Medical Eval（45 min）

用 `CORE_12.md` 的 C1，只回答“医疗 MLLM 如何可信比较两个模型”，限制 15 min。

## Day 4 Exit

- LC200 ≥7.5；
- LC215 至少能独立写 heap 版；
- 能解释为何小病灶对 resize 敏感；
- 能列出医疗 MLLM hallucination 的 3+ 来源。

---

# Day 5 — LRU / Coding 强化 + SFT / LoRA

## Coding（3 h）

- LC146 LRU；
- 回测当前最弱的一个模式；
- 如果 LC206 已稳定，再尝试 LC25 分段思想；否则不做 LC25。

LRU 最低要求：
- 能解释 HashMap + Doubly Linked List；
- 能画 get/put/update/evict 数据流。

## Post-training（2.5 h）

P1–P4：
- Pretraining vs SFT；
- LoRA；
- SFT data schema；
- packing / masking。

完成 PX2：最小 LoRA 实验设计。

不要求真正写 trainer，但必须回答：
- baseline；
- train/val/test；
- overfit；
- eval slices；
- regression。

## Day 5 Exit

- LRU 能完整解释，最好 ≥7；
- LoRA 能解释低秩增量直觉；
- 能设计一个小型医疗 SFT/LoRA 实验。

---

# Day 6 — Mixed Coding + Preference / RL

今天开始打乱专题。

## Coding Mock A（45 min）

随机已学模式，隐藏标签。

## MLLM Follow-up（45 min）

随机 M1–M12，必须包含一个 shape / failure / medical transfer 追问。

## Coding Mock B（45 min）

换一个模式。

## Post-training（2–2.5 h）

P5–P12：
- preference data；
- DPO；
- reward model/verifier；
- PPO 直觉；
- GRPO 直觉；
- KL；
- rollout cost。

重点不是公式，而是 training signal 和 failure mode。

完成：
- PX4 医疗 RL reward；
- PX5 reward hacking 案例。

## Medical Eval / System（45 min）

C2 或 D1 二选一。

## Day 6 Exit

- 两道陌生 Coding 至少一题 ≥7.5；
- MLLM 随机问答 ≥8；
- 能说清 SFT / DPO / PPO/GRPO 分别在解决什么问题；
- 能主动提 reward hacking。

---

# Day 7 — 两轮全真技术面

不新增知识。

## Mock 1（60 min）

建议结构：

- 5 min：项目/科研背景；
- 30 min：牛客/LeetCode 风格 Coding；
- 15 min：MLLM/ViT；
- 7 min：SFT/RL；
- 3 min：候选人反问。

## Repair（90–120 min）

只修一个最大淘汰风险。

排序优先级：

1. Coding 基础崩溃；
2. MLLM 完全空白；
3. Post-training 机制混乱；
4. 表达问题；
5. 已经较强的医疗/Eval。

## Mock 2（60 min）

换 Coding 模式和 MLLM 问题。

---

# 最终 Gate

## Coding

- Foundation 已通过；
- Easy 可独立；
- LC3 / LC200 / LC215 至少 PASS；
- Binary Search / Stack / Linked List 至少不空白；
- 陌生 Medium 能从 brute force 开始。

## MLLM

- ViT 核心结构可解释；
- image → vision encoder → bridge → LLM 可画；
- Detail Caption / high-resolution / hallucination 能回答；
- 至少 2 个迁移小题 ≥8。

## Post-training

- SFT / LoRA / preference / DPO / PPO/GRPO 的关系不混乱；
- 能设计最小实验；
- 能讨论 reward hacking / safety。

## 综合

Mock 2：
- Coding ≥7；
- MLLM ≥8；
- Post-training ≥7.5；
- 无“完全看不懂题面”的基础性崩溃。

---

# 一周明确不学

- Hot100 全套；
- LeetCode Hard 题海；
- DP 大全；
- 线段树/红黑树；
- CNN/ViT 所有论文谱系；
- PPO/GRPO 完整数学推导；
- 从零搭大型训练基础设施；
- 医学百科背诵。

**目标是跨过真实面试门槛，不是七天完成计算机本科 + MLLM 博士训练。**