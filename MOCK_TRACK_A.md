# Mock Track A — A04613A 医疗大模型评测 / 数据工程

## 60 min

### 0–5 min 项目
讲一个 Benchmark/Eval/Data 项目：problem → design → truth → verifier → failure → impact。

### 5–30 min Coding / Evaluator Coding
随机：
- Easy/Medium Python；或
- medical evaluator；或
- JSONL/data processing；或
- async batch evaluator。

追问：复杂度、edge case、retry/idempotency、malformed input。

### 30–48 min Eval / Data / System
随机一题：
- model A/B medical comparison；
- LLM-as-Judge calibration；
- medical safety benchmark；
- guideline/drug/literature data pipeline；
- continuous regression system。

### 48–56 min LLM App
RAG / Agent / tool calling / multi-turn 中随机一题，重点问如何评测失败层。

### 56–60 min Medical follow-up
高风险医疗错误、指南一致性、影像/报告一致性。

## Score
- Coding/Engineering 35%
- Eval/Benchmark 30%
- Data/System 20%
- LLM App/Medical 15%

Stable Pass：overall ≥8 且 Coding ≥7.5。
Fatal：truth 循环、judge 未校准当 gold、retry 无幂等、无 provenance、高风险错误被平均分掩盖。
