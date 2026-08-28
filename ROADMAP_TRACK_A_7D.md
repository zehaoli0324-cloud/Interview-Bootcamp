# Track A 7D — A04613A 医疗大模型评测 / 数据工程

> 目标：Coding 不挂 + Eval/Data/System 成为主优势。
>
> Coding 全程使用 Python，并按 `LEETCODE101_PYTHON_PATTERN_MAP.md` 的 **Pattern → Anchor → Transfer → Retest** 机制训练。

## Track A Coding 原则

每个算法日不是“刷若干题”，而是：

```text
一个 Pattern 人话解释
→ Python mini exercise
→ Core Anchor
→ 一个同模式 Transfer（优先业务改写或《LeetCode 101》变式）
→ 之后再 Delayed Retest
```

Track A 更看重：
- 能不能稳定写 Python；
- 能不能把算法模式迁移到 evaluator / data / batch / logs；
- 不要求系统刷 Hard。

---

## Day 1 — Python Foundation + HashMap Pattern + Evaluator 基础

### Shared Coding
- `PYTHON_LEVEL0.md`：list/index/变量/for/if/function/dict
- HashMap 一句话：把“以前见过的信息”存起来，以后快速查
- Anchor：LC1 Two Sum，从 brute force 到 dict
- 若 Foundation 尚未通过：不急着做 Transfer

### Track A
- B1 medical evaluator：TP/FP/FN、micro P/R/F1
- 能读懂 JSON-like record，写简单函数

结束条件：
- 能解释 `value -> index`；
- 能写/补全 LC1 主逻辑；
- 能读简单 evaluator record。

---

## Day 2 — HashMap Transfer + Sliding Window + 数据清洗

### Shared Coding
- LC1 同模式 Transfer：不同题面，仍需 dict/seen/last-seen
- 新 Pattern：Sliding Window
- Anchor：LC3
- 极小手推：left/right 如何变化

### Track A
- JSONL parse / malformed / dedup / latest timestamp
- Data quality：schema / duplicate / missing / provenance

业务迁移：
- 用 dict 做 dedup；
- 用窗口思路理解连续日志/时间段统计。

结束：
- 至少 1 个 HashMap Transfer ≥7.5；
- 数据清洗题 ≥8。

---

## Day 3 — BFS/DFS Pattern + LLM-as-Judge

### Shared Coding
- BFS 一句话：像水波一样一层层扩散
- DFS 一句话：沿一条路走到底再回来
- Anchor：LC102 / LC200 选主线
- Transfer：Max Area of Island / connected-component 简化题

### Track A
- Judge aggregation / disagreement
- Judge calibration：expert agreement / bias / drift
- 医疗 high-risk slices

结束：
- BFS/DFS 至少一个 Anchor ≥7.5；
- 能区分 stack/queue；
- Judge 设计 ≥8。

---

## Day 4 — Heap / Binary Search Pattern + Async Evaluation

### Shared Coding
- Heap/Top-K：只维护最重要的 K 个
- Anchor：LC215
- Transfer：Top K Frequent 或 top-k error categories
- Binary Search：每次安全排除一半
- Anchor/mini：sqrt 或 LC33，根据当日状态选择

### Track A
- B3 async evaluator：concurrency / timeout / retry / resume
- idempotency / checkpoint / run_id / version

结束：
- Heap/Top-K 能用 Python `heapq` 解释；
- B3 ≥7.5；
- 不允许“失败从头重跑”。

---

## Day 5 — Sorting/Interval Pattern + Benchmark / RAG / Agent Eval

### Shared Coding
- Sorting + Interval：先排序，让关系变得局部可处理
- Anchor：LC56
- Transfer：Non-overlapping Intervals / scheduling-like 题

### Track A
- A/B medical model comparison
- shortcut / leakage audit
- RAG：retrieval recall / citation faithfulness / answer correctness
- Agent：tool selection / args / observation use / trajectory / final answer

结束：
- Interval pattern 能解释为什么先排序；
- Benchmark 设计 ≥8。

---

## Day 6 — Retention + Data Pipeline + Mixed Coding

### Shared Coding
- 从前 5 天选择 2 个 `RETEST_DUE` pattern
- 不告诉 pattern，做 Delayed Retest
- 至少一个题面改成 Track A 业务形式：dedup / logs / queue / top-k / interval

### Track A
- guideline / drug label / literature pipeline
- source authority / temporal validity / conflict / contamination
- evaluator/data coding

结束：
- 至少 1–2 个核心 pattern 达到 MASTERED 条件；
- 能完整讲 `source → parse → QC → version → eval`。

---

## Day 7 — Track A Full Mock ×2

每轮 60 min：
- 25 min Coding / evaluator coding
- 20 min Eval/Benchmark/Data/System
- 10 min LLM App/Agent/RAG
- 5 min 项目/医疗追问

Coding 题：
- 不告诉 pattern；
- 优先抽已学 pattern 的陌生表面；
- 不重复原 Anchor 原题。

通过线：
- Coding ≥7.5
- Eval/Data ≥8
- Overall ≥8
- 至少 2 个共享 Coding pattern 已通过 delayed retest
- 无 truth 循环 / judge 未校准 / retry 无幂等 / provenance 缺失等致命问题

---

## Track A 不做

- 不系统学 ViT training recipe
- 不系统刷 LC Hard
- 不学 RL 数学推导
- 不做 CV 算法大全
- 不因为《LeetCode 101》有某章就把所有章节塞进一周
