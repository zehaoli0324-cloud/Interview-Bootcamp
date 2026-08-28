# PROGRESS — V3 Medical MLLM Algorithm Interview

> 只记录会影响下一步训练选择的信息。

## 当前状态

```yaml
current_day: 1
current_mode: FOUNDATION
foundation_status: NOT_PASSED
current_task: Z1
biggest_risk: PYTHON_FOUNDATION
```

---

# Track A — Python Foundation

状态：`NOT_STARTED / LEARNING / PASSED`

- [ ] list / index
- [ ] variable / expression
- [ ] for loop
- [ ] if condition
- [ ] function / return
- [ ] dict key-value
- [ ] Z15 frequency dict independent
- [ ] Z16 last-position dict independent
- [ ] Z17 complement reasoning independent
- [ ] Z18 Two Sum brute force independent

**Foundation Gate：Z15–Z18 至少 3/4 独立完成 + 六个基础概念可解释。**

通过后：

```yaml
foundation_status: PASSED
```

之后不要因为单个语法 bug 把整个训练退回 Level 0。

---

# Track B — Algorithm Coding

状态：`NOT_STARTED / LEARNING / BORDERLINE / PASS_RETEST_DUE / MASTERED`

## Easy / Foundation Algorithm

- [ ] LC1 HashMap
- [ ] LC20 Stack
- [ ] LC165 String parsing
- [ ] LC206 Linked List reverse

## 高频 Medium

- [ ] LC3 Sliding Window
- [ ] LC56 Interval
- [ ] LC102 Tree BFS
- [ ] LC200 Grid DFS/BFS
- [ ] LC215 Heap / Top-K
- [ ] LC33 Binary Search
- [ ] LC146 LRU

## Stretch

- [ ] LC221 Basic DP
- [ ] LC32 Parentheses
- [ ] sqrt Binary Search / Newton
- [ ] LC25 K-group Linked List

Mastery 仍要求延迟无提示复测。

### Coding Retest Queue

| Pattern | First pass | Hints | Earliest retest | Retest | Status |
|---|---:|---:|---|---:|---|
|  |  | 0 | after 3 other units / next session |  |  |

---

# Track C — MLLM / ViT

状态：`NOT_STARTED / LEARNING / PASS / MASTERED`

- [ ] M1 Image → patch tokens
- [ ] M2 Patch embedding
- [ ] M3 Position embedding
- [ ] M4 Self-attention intuition
- [ ] M5 ViT vs CNN
- [ ] M6 Vision encoder → bridge → LLM
- [ ] M7 LLaVA-style alignment / instruction tuning
- [ ] M8 Q-Former / resampler
- [ ] M9 Detail Caption
- [ ] M10 High-resolution / tiling / token cost
- [ ] M11 MLLM hallucination
- [ ] M12 Medical MLLM evaluation

### Practice

- [ ] MX1 patch/token calculation
- [ ] MX3 projector shape walkthrough
- [ ] MX4 detail-caption schema OR MX5 high-res lesion design

MLLM MASTERED：不同上下文/shape/医疗案例迁移后仍 ≥8。

---

# Track D — SFT / LoRA / Preference / RL

- [ ] P1 Pretraining vs SFT
- [ ] P2 LoRA
- [ ] P3 SFT data schema
- [ ] P4 Packing / masking
- [ ] P5 Preference data
- [ ] P6 DPO intuition
- [ ] P7 Reward model / verifier
- [ ] P8 Why RL
- [ ] P9 PPO interview intuition
- [ ] P10 GRPO interview intuition
- [ ] P11 KL
- [ ] P12 Rollout cost

### Practice

- [ ] PX2 Minimal LoRA experiment
- [ ] PX4 Medical RL reward
- [ ] PX5 Reward hacking

---

# Track E — Medical Eval / Benchmark / System

只保持优势，不重复刷熟题。

- [ ] B1 evaluator metrics
- [ ] B2 judge aggregation
- [ ] B3 async/retry/resume
- [ ] C1 medical model comparison
- [ ] C2 shortcut/leakage
- [ ] D1 scalable judge system
- [ ] D2 continuous regression

---

# Attempt Log

| Date | Track | Task | Result/Score | Primary error | Hint | Next |
|---|---|---|---:|---|---:|---|
|  |  |  |  |  | 0 |  |

## Primary Error Types

Coding/Foundation：
- `READING_INPUT`
- `SYNTAX_API`
- `INDEXING`
- `CONTROL_FLOW`
- `PATTERN_RECOGNITION`
- `INVARIANT`
- `IMPLEMENTATION`
- `BOUNDARY`
- `COMPLEXITY`
- `DEBUGGING`
- `EXPLANATION`

MLLM/Post-training：
- `CONCEPT`
- `DATA_FLOW`
- `TENSOR_SHAPE`
- `TRAINING_OBJECTIVE`
- `FAILURE_MODE`
- `TRADEOFF`
- `MEDICAL_TRANSFER`

每个训练单元只记录一个主要根因。

---

# Checkpoint Template

```text
Foundation: ...
Coding: mastered / pass-retest / biggest gap
MLLM: ...
Post-training: ...
Medical Eval: ...
Biggest interview risk: ...
Next priority: ...
```

---

# Final Gate

- [ ] Foundation PASSED
- [ ] Easy Coding 不再因题意/语法崩溃
- [ ] LC3 / LC200 / LC215 至少 PASS
- [ ] MLLM M1–M8 大部分可独立解释
- [ ] Detail Caption / high-resolution / hallucination 可回答
- [ ] SFT / LoRA / DPO / PPO-GRPO 关系不混乱
- [ ] 至少完成 1 个 LoRA 实验设计
- [ ] 至少完成 1 个医疗 RL reward 设计
- [ ] 一轮 60 min Mock 无基础性崩溃