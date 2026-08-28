# Track B 7D — A180084A 医疗大模型算法实习生

> 目标：Coding 达标 + 建立可面试的 ViT/MLLM/Post-training 技术骨架。
>
> Coding 全程使用 Python，并按 `LEETCODE101_PYTHON_PATTERN_MAP.md` 的 **Pattern → Anchor → Transfer → Retest** 机制训练。

## Track B Coding 原则

Track B 不以“刷题数量”衡量进度，而以模式迁移能力衡量：

```text
Pattern 扫盲
→ Python mini exercise
→ Core Anchor
→ 同模式不同题面 Transfer
→ timed Delayed Retest
```

相较 Track A：
- Transfer 更多；
- timed 更严格；
- complexity / invariant / boundary 要求更高；
- 常见 Medium 不能完全空白。

---

## Day 1 — Python Foundation + HashMap Pattern + ViT 入门

### Shared Coding
- `PYTHON_LEVEL0.md`
- list/index/变量/for/if/function/dict
- HashMap Pattern：以前见过吗？
- Anchor：LC1 Two Sum，从 brute force 到 dict

### Track B
- patch embedding / token count / positional embedding

结束：
- 能解释 `value -> index`；
- 能手写/补全 LC1 主逻辑；
- 能解释 image → patches → tokens。

---

## Day 2 — Stack / Linked List Pattern + Self-Attention / ViT

### Shared Coding
- Stack Pattern：最近一个未解决状态
- Anchor：LC20
- Transfer：Min Stack 或简化嵌套结构题
- Linked List Pattern：`prev / cur / next`
- Anchor：LC206

### Track B
- self-attention / QKV / multi-head
- CNN vs ViT
- ViT pretraining vs finetuning

结束：
- Stack 至少 Anchor PASS；
- LC206 能手推；
- ViT core ≥7.5。

---

## Day 3 — Sliding Window / Binary Search Pattern + MLLM 架构

### Shared Coding
- Sliding Window：LC3 Anchor
- Transfer：同模式不同题面
- Binary Search：sqrt / LC33 选 Anchor
- 手推 left/mid/right 与区间 invariant

### Track B
- vision encoder / projector / LLM
- LLaVA-style pipeline
- Q-Former / resampler 的作用
- shape / hidden-size 计算

结束：
- LC3 ≥8 或 Transfer ≥7.5；
- Binary Search 不再靠死背模板；
- MLLM pipeline 能闭卷讲。

---

## Day 4 — BFS/DFS / Heap Pattern + Detail Caption / High Resolution

### Shared Coding
- BFS：LC102 Anchor
- DFS/Grid：LC200 Anchor
- Transfer：Max Area of Island / shortest-layer 简化题
- Heap/Top-K：LC215 Anchor
- Transfer：Top K Frequent

### Track B
- Detail Caption 为什么重要
- high-resolution / tiling / token budget trade-off
- hallucination / grounding

结束：
- LC200 或 LC215 ≥8；
- 至少一个 BFS/DFS Transfer 可独立完成；
- MLLM 专项 ≥8。

---

## Day 5 — Sorting/Interval / LRU + SFT / LoRA

### Shared Coding
- Sorting + Interval：LC56 Anchor
- Transfer：Non-overlapping Intervals / scheduling-like 题
- LRU：先画 HashMap + Doubly Linked List，再写 Python

### Track B
- pretraining vs SFT
- LoRA / PEFT
- instruction data / train-eval split
- 小型 LoRA experiment 设计

结束：
- Interval pattern ≥7.5；
- LC146 至少能讲完整流程；
- SFT/LoRA ≥8。

---

## Day 6 — Pattern Retest + Basic DP + Preference / RL

### Shared Coding
- 选择 2–3 个 `RETEST_DUE` pattern 做 timed Delayed Retest
- 不告诉 pattern
- 新增 Basic DP：LC221 或基础 DP mini lesson
- 若前面 Coding 仍不稳定，DP 可降级为只理解 state definition

### Track B
- DPO / reward model / PPO / GRPO
- rollout / KL / reward hacking
- 医疗 reward design

结束：
- 至少 2 个核心 pattern 达到 MASTERED；
- Mixed Coding 平均 ≥7.5；
- Post-training ≥7.5。

---

## Day 7 — Track B Full Mock ×2

每轮 60 min：
- 30 min LeetCode/牛客 Coding
- 15 min ViT/MLLM
- 10 min SFT/RL
- 5 min 医疗/科研项目

Coding 规则：
- 不重复原 Anchor 原题；
- 优先抽已学 pattern 的陌生表面；
- 必须先解释 brute force / pattern / complexity，再完成 Python；
- 题目难度以 Easy/常见 Medium 为主，不用竞赛 Hard 证明实力。

通过线：
- Coding ≥7.5
- MLLM ≥7.5
- Post-training ≥7
- Overall ≥7.5
- 至少 3 个 P0 pattern 有 Transfer 通过
- 至少 2 个 pattern 完成 delayed retest
- 不允许基础 shape、ViT、LLaVA pipeline 完全答不上

---

## Track B 不做

- 不把 Benchmark 设计当主要复习内容
- 不花大量时间在 RAG/Agent 平台工程
- 不深挖数据标注运营流程
- 不系统刷竞赛级 Hard
- 不为了“刷完《LeetCode 101》”牺牲 ViT/MLLM/Post-training 时间
