# Track A 7D — A04613A 医疗大模型评测 / 数据工程

> 目标：Coding 不挂 + Eval/Data/System 成为主优势。

## Day 1 — Python Foundation + Evaluator 基础
- `PYTHON_LEVEL0.md`：list/index/for/if/function/dict
- Two Sum 暴力解理解即可，能写基础循环
- B1 medical evaluator：TP/FP/FN、micro P/R/F1
- 结束：能读懂 JSON-like record，写简单函数

## Day 2 — HashMap / Sliding Window + 数据清洗
- LC1 / LC3 基础
- JSONL parse / malformed / dedup / latest timestamp
- Data quality：schema / duplicate / missing / provenance
- 结束：一题 Easy ≥8；数据清洗题 ≥8

## Day 3 — BFS/DFS + LLM-as-Judge
- LC102 / LC200 选主线
- Judge aggregation / disagreement
- Judge calibration：expert agreement / bias / drift
- 医疗 high-risk slices
- 结束：Coding ≥7.5；Judge 设计 ≥8

## Day 4 — Heap / Binary Search + Async Evaluation
- LC215 / LC33
- B3 async evaluator：concurrency / timeout / retry / resume
- idempotency / checkpoint / run_id / version
- 结束：B3 ≥7.5，不允许“失败从头重跑”

## Day 5 — Benchmark / RAG / Agent Eval
- C1 A/B medical model comparison
- C2 shortcut / leakage audit
- RAG：retrieval recall / citation faithfulness / answer correctness
- Agent：tool selection / args / observation use / trajectory / final answer
- 结束：C1/C2 ≥8

## Day 6 — Data Pipeline + Mixed Coding
- guideline / drug label / literature pipeline
- source authority / temporal validity / conflict / contamination
- 1 道随机 Easy/Medium Coding
- 1 道 evaluator/data coding
- 结束：能完整讲 `source → parse → QC → version → eval`

## Day 7 — Track A Full Mock ×2
每轮 60 min：
- 25 min Coding / evaluator coding
- 20 min Eval/Benchmark/Data/System
- 10 min LLM App/Agent/RAG
- 5 min 项目/医疗追问

通过线：
- Coding ≥7.5
- Eval/Data ≥8
- Overall ≥8
- 无 truth 循环 / judge 未校准 / retry 无幂等 / provenance 缺失等致命问题

## Track A 不做
- 不系统学 ViT training recipe
- 不系统刷 LC Hard
- 不学 RL 数学推导
- 不做 CV 算法大全
