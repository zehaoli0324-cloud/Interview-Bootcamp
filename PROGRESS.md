# PROGRESS — Dual-Track Interview Bootcamp V5

> Shared Coding 进度只记录一次；Track A / B 专项能力分别记录。

```yaml
active_track: SHARED   # SHARED / A / B
foundation_status: LEARNING
shared_coding_phase: PATTERN_FOUNDATION
current_pattern: HASHMAP
current_pattern_stage: ANCHOR_LEARNING
```

---

# 1. Shared Foundation

## Python Level 0
- [x] list / index
- [x] variable / assignment
- [x] for / range
- [x] if / comparison
- [x] function / return
- [x] dict
- [ ] set
- [x] can read a simple input/output example with guidance
- [x] can hand-trace a tiny loop/dict example
- [x] understands `len()` and `range()`
- [x] understands function parameters vs values created inside a loop

Foundation Exit Gate：`PYTHON_LEVEL0.md` Z15–Z18 至少 3/4 独立完成。

当前判断：
- 基础概念已经建立；
- 仍需一次更独立的 mini coding gate；
- 不需要重新从 list/index 开始教学。

---

# 2. Shared Coding Pattern Mastery

V5 状态：

`NOT_STARTED → LEARNING → ANCHOR_PASS → TRANSFER_PASS → RETEST_DUE → MASTERED`

## P0 Pattern Map

| Pattern | Anchor | Stage | Notes |
|---|---|---|---|
| HashMap | LC1 Two Sum | ANCHOR_LEARNING | 已理解 `need`、`seen[value]=index`、先查再存；在大量教学提示下完整写出函数，尚未形成独立 mastery evidence |
| Stack | LC20 | NOT_STARTED |  |
| Two Pointers | book/variant | NOT_STARTED |  |
| Sliding Window | LC3 | NOT_STARTED |  |
| Sorting + Interval | LC56 | NOT_STARTED |  |
| Binary Search | LC33 / sqrt | NOT_STARTED |  |
| BFS | LC102 | NOT_STARTED |  |
| DFS | LC200 | NOT_STARTED |  |
| Heap / Top-K | LC215 | NOT_STARTED |  |
| Linked List | LC206 | NOT_STARTED |  |

## P1

| Pattern | Anchor | Stage |
|---|---|---|
| Basic DP | LC221 | NOT_STARTED |
| Tree Traversal | LC102/variants | NOT_STARTED |
| Greedy | book/interval variants | NOT_STARTED |

MASTERED 必须：
1. Anchor ≥8；
2. 同模式不同题面 Transfer；
3. 隔 ≥3 个其他训练单元或下一 session；
4. 不透露 pattern、无 Hint 2/3 的 Delayed Retest ≥8。

---

# 3. Current HashMap Learning Evidence

已经能解释：
- `nums[i]` 是按当前 index 取值；
- `for i in range(len(nums))` 让 `i` 依次走过位置；
- `target` 来自函数参数；
- `x = nums[i]` 是当前值；
- `need = target - x` 是当前所缺的配对值；
- `if need in seen` 是检查以前是否见过；
- `seen[x] = i` 保存 `value -> index`；
- 先查再存可以避免同一个位置和自己配对；
- 两个不同位置的相同值可以合法配对。

已完成：
- 多轮 tiny trace；
- 从函数头继续写出完整 Two Sum HashMap 主体。

尚未完成：
- 无逐行提示的正式闭卷 Anchor；
- HashMap Transfer；
- Delayed Retest；
- complexity 独立解释。

下一步：

```text
先做一个很小的独立函数调用/mini gate
→ 再做 LC1 clean retry
→ Anchor ≥8 后进入 HashMap Transfer
```

---

# 4. Track A — A04613A Eval / Data

## Coding / Engineering
- [ ] B1 medical evaluator
- [ ] B2 judge aggregation
- [ ] B3 async batch evaluator
- [ ] JSONL cleaning / dedup
- [ ] grouped metrics
- [ ] retry / checkpoint / idempotency

## Eval / Benchmark
- [ ] medical A/B comparison
- [ ] LLM-as-Judge calibration
- [ ] medical safety benchmark
- [ ] shortcut / leakage audit
- [ ] multi-turn / Agent evaluation

## Data / LLM System
- [ ] medical data pipeline
- [ ] synthetic data QC
- [ ] provenance / versioning
- [ ] RAG evaluation
- [ ] tool calling / Agent trajectory

### Track A Mock
```yaml
track_a:
  coding_engineering: null
  eval_benchmark: null
  data_system: null
  llm_app_medical: null
  overall: null
  verdict: NOT_RUN
```

---

# 5. Track B — A180084A MLLM Algorithm

## MLLM / ViT
- [ ] patch embedding / token count
- [ ] positional embedding
- [ ] self-attention / QKV
- [ ] CNN vs ViT
- [ ] ViT training / finetuning
- [ ] vision encoder → projector → LLM
- [ ] Q-Former / resampler
- [ ] Detail Caption
- [ ] high-resolution / tiling
- [ ] hallucination / grounding

## Post-training
- [ ] pretraining vs SFT
- [ ] LoRA / PEFT
- [ ] preference data / DPO
- [ ] reward model
- [ ] PPO basics
- [ ] GRPO basics
- [ ] rollout / KL
- [ ] reward hacking
- [ ] medical reward design

### Track B Mock
```yaml
track_b:
  coding: null
  vit_mllm: null
  post_training: null
  medical_research: null
  overall: null
  verdict: NOT_RUN
```

---

# 6. Attempt Log

| Date | Track | Pattern/Skill | Stage | Score | Primary error | Hint | Next |
|---|---|---|---|---:|---|---:|---|
| 2026-08-28 | SHARED | HashMap / Two Sum | ANCHOR_LEARNING | teaching | code-vs-value / state timing | guided | clean retry |

Primary error only one per formal attempt:
- SYNTAX_API
- READING_COMPREHENSION
- PATTERN_RECOGNITION
- INVARIANT
- IMPLEMENTATION
- BOUNDARY
- COMPLEXITY
- DEBUGGING
- EVAL_REASONING
- DATA_ENGINEERING
- MLLM_CONCEPT
- TRAINING_CONCEPT

---

# 7. Retest Queue

| Shared/Track | Pattern/Skill | Anchor score | Transfer | Earliest delayed retest | Retest | Status |
|---|---|---:|---|---|---:|---|
| SHARED | HashMap | not formally scored | pending | after transfer + spacing |  | ANCHOR_LEARNING |

---

# 8. Current Session

```yaml
active_track: SHARED
mode: FOUNDATION_TO_PATTERN
current_skill: HashMap_TwoSum
current_stage: ANCHOR_LEARNING
biggest_risk: "can understand code line-by-line but still needs practice converting concrete values into reusable code rules"
next_priority: "clean mini coding gate, then independent HashMap anchor retry"
```

原则：

> **Python 是语言；Pattern 是算法能力；Track A/B 分开判岗位 readiness。**
