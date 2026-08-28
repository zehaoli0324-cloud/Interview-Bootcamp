# PROGRESS — Dual-Track Interview Bootcamp

> Shared Coding 进度只记录一次；Track A / B 专项能力分别记录。

```yaml
active_track: A   # A or B
foundation_status: LEARNING
shared_coding_phase: FOUNDATION
```

---

# 1. Shared Foundation

## Python Level 0
- [ ] list / index
- [ ] variable / assignment
- [ ] for / range
- [ ] if / comparison
- [ ] function / return
- [ ] dict / set
- [ ] can read simple LeetCode statement
- [ ] can hand-trace a tiny example

Foundation Exit Gate：`PYTHON_LEVEL0.md` Z15–Z18 至少 3/4 独立完成。

---

# 2. Shared Coding Mastery

状态：`NOT_STARTED → LEARNING → BORDERLINE → PASS/RETEST-DUE → MASTERED`

## Level 1
- [ ] LC1 HashMap
- [ ] LC20 Stack
- [ ] LC165 String parsing
- [ ] LC206 Linked List

## Level 2
- [ ] LC3 Sliding Window
- [ ] LC56 Interval
- [ ] LC102 Tree BFS
- [ ] LC200 Grid DFS/BFS
- [ ] LC215 Heap / Top-K
- [ ] LC33 Binary Search
- [ ] LC146 LRU

## Level 3
- [ ] LC221 Basic DP
- [ ] LC32 Parentheses
- [ ] sqrt Binary/Newton
- [ ] LC25 K-group linked list

MASTERED：首次无强提示 ≥8 → 隔至少 3 道其他题或下一 session → 无提示变式再次 ≥8。

---

# 3. Track A — A04613A Eval / Data

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

# 4. Track B — A180084A MLLM Algorithm

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

# 5. Attempt Log

| Date | Track | Skill/Problem | Score | Primary error | Hint | Next |
|---|---|---|---:|---|---:|---|
|  |  |  |  |  | 0 |  |

Primary error only one:
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

# 6. Retest Queue

| Shared/Track | Skill | First score | Earliest retest | Retest | Status |
|---|---|---:|---|---:|---|
|  |  |  |  |  |  |

---

# 7. Current Session

```yaml
active_track: A
mode: FOUNDATION
current_skill: list_index
questions_completed: 0
biggest_risk: ""
next_priority: ""
```

原则：

> Track A 和 Track B 分开判定岗位 readiness；只有 Shared Foundation/Coding 可以互相复用。
