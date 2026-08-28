# Track A — A04613A 医疗大模型评测 / 数据工程师

> 岗位：大模型评测/数据工程师（医疗方向）- 小荷健康  
> 核心定位：**评测方法 + 数据工程 + LLM 应用系统 + 医疗场景**，不是模型训练算法岗。

---

# 1. JD 真正要什么

这个岗位的四个核心产出是：

1. 医疗大模型端到端评测、效果分析、问题归因；
2. 自动化评测基建 / 评测 Agent / LLM-as-Judge；
3. 医疗训练/评测/知识库数据建设与质量控制；
4. 医疗 Benchmark / 专项评测，并通过分析推动模型迭代。

因此它最看重的是：

> **能不能把一个“模型效果问题”拆成可测量能力 → 构造可靠数据 → 自动化跑评测 → 分析失败 → 形成可执行改进。**

---

# 2. 面试训练权重

建议训练权重：

- **Python Coding + Data Engineering：40%**
- **Eval / Benchmark / LLM-as-Judge：30%**
- **LLM Application / Agent / RAG / Tool Calling：15%**
- **Medical AI + Multimodal Evaluation：10%**
- **Communication / Project Defense：5%**

注意：

- 这里的 Coding 目标是“良好的编码与工程基础”，不是竞赛算法画像；
- LeetCode Easy / 常见 Medium 仍必须过，因为技术面会现场写代码；
- 但不应为了这个岗位投入大量时间到 LC25、复杂 DP、CV 训练细节。

---

# 3. Coding 主线

## P0 — 必须稳定

来自 `PYTHON_LEVEL0.md` 与 `LEETCODE_CORE_15.md`：

- list / dict / set / tuple；
- for / while / if / function；
- JSON / JSONL parsing；
- HashMap；
- Stack；
- Sliding Window；
- Sorting / Interval；
- BFS / DFS；
- Heap / Top-K；
- Binary Search；
- 基础 linked list。

## P0 — 岗位专属 Evaluator/Data Coding

来自 `CORE_12.md`：

- B1 医疗问答 micro precision/recall/F1 evaluator；
- B2 多 Judge aggregation / disagreement；
- B3 async batch evaluator：concurrency / timeout / retry / resume / idempotency。

额外必须能写：

### A-D1 JSONL 清洗

输入一批医疗问答 JSONL：
- 跳过 malformed 行但记录错误；
- 按 `(sample_id, model_version)` 去重；
- 保留最新 timestamp；
- 输出 clean / rejected 两份数据。

### A-D2 分组统计

给定 sample-level eval records：
- 按 specialty / risk_level / model_version 分组；
- 输出 count / mean / pass_rate；
- 处理 missing slice；
- 不能让空组除零。

### A-D3 Retryable Batch Runner

实现一个最小 batch runner：
- bounded concurrency；
- timeout；
- retry with backoff；
- SUCCESS / RETRYABLE_FAILED / FATAL_FAILED；
- rerun 跳过 SUCCESS；
- 每个结果可追溯 run_id / evaluator_version。

---

# 4. Eval / Benchmark 核心题

## A-E1 医疗 LLM A/B 对比

设计一个可信实验，比较模型 A/B 在医疗问答中的表现。

必须覆盖：
- task taxonomy / slices；
- independent truth；
- factuality / diagnosis rationality / guideline consistency / safety；
- LLM-as-Judge calibration；
- expert adjudication；
- paired comparison / confidence interval；
- high-risk slice；
- error taxonomy；
- regression set。

## A-E2 LLM-as-Judge 校准

给 100 条专家标注回答和一个 Judge：
- 如何测 agreement？
- 如何发现 leniency / position / verbosity bias？
- ordinal score 应该怎么看一致性？
- 哪些错误必须人工 adjudicate？
- Judge 升级后如何回归？

## A-E3 医疗安全专项评测

针对：
- 错误用药；
- 禁忌证；
- 急危重症漏识别；
- 伪造指南/文献；
- 过度自信。

设计专项 benchmark + severity-weighted reporting。

## A-E4 Benchmark shortcut / leakage

必须区分：
- contamination；
- template leakage；
- answer distribution shortcut；
- metadata shortcut；
- judge leakage。

并设计 naive baseline / counterfactual / held-out / ablation。

## A-E5 多轮与 Agent Eval

评估一个医疗 Agent：
- 是否正确调用工具；
- 参数是否正确；
- 是否在不该调用时乱调；
- observation 是否被正确利用；
- 多轮状态是否保持；
- final answer 是否与 tool evidence 一致。

---

# 5. Data Engineering 核心题

## A-DATA1 医疗数据 pipeline

从指南 / 药品说明书 / 医学文献构建评测集：

`source → parse → normalize → deduplicate → chunk/structure → annotate → QC → version → publish`

要主动讲：
- provenance；
- document/version/date；
- conflicting sources；
- stale knowledge；
- PHI/privacy；
- train/eval contamination。

## A-DATA2 Synthetic Data

什么时候适合合成？

必须讲：
- seed source；
- task template；
- generation；
- rule/model/human QC；
- diversity；
- distribution drift；
- avoid self-training circularity。

## A-DATA3 数据质量

至少考虑：
- schema validity；
- duplicate；
- label consistency；
- source authority；
- temporal validity；
- difficulty；
- slice balance；
- leakage；
- annotation agreement。

---

# 6. LLM Application / Agent / RAG

必须能解释并设计：

- Prompt baseline；
- RAG pipeline；
- retrieval recall vs answer correctness；
- chunking / reranking；
- tool calling schema；
- function call error；
- Agent trajectory evaluation；
- hallucination after retrieval；
- citation faithfulness；
- offline eval vs online metric。

重点不是“会调 API”，而是：

> **知道系统每一层会怎样失败，以及如何单独测。**

---

# 7. Medical / Multimodal 在 Track A 的深度

需要：
- 医学问答；
- 临床诊疗；
- 指南；
- 药品；
- 报告解读；
- 医学影像理解的评测维度；
- 多模态模型 hallucination / grounding / report consistency。

不要求把以下内容作为 Track A 主战场：
- ViT 训练配方；
- projector 架构细节；
- high-resolution tiling 工程；
- PPO / GRPO 数学推导。

这些属于 Track B。

---

# 8. Track A 通过线

## Coding
- Python Foundation 通过；
- Easy 可独立完成；
- 常见 Medium 能形成正确主解；
- B1/B2 至少 8/10；
- B3 至少 7.5/10。

## Eval / Data
- C1/C2 ≥8；
- 能独立设计 LLM-as-Judge calibration；
- 能解释 independent truth / leakage / shortcut；
- 能设计医疗数据 pipeline 与 QC；
- 能从 aggregate score 下钻到 failure slices。

## System
- retry / timeout / idempotency / checkpoint / provenance 不遗漏；
- 能设计 sample-level state 与版本追踪。

## Medical
- 能给出至少 3 类医疗高风险错误及对应评测方案。

---

# 9. Track A 不需要过度准备

不作为 P0：
- LC25；
- 系统性 DP 题库；
- CV 算法大全；
- ViT pretraining recipe；
- 深度 RL 数学推导；
- CUDA / distributed training。

原则：

> **这个岗位要的是“能建设可信医疗模型评测与数据系统的研发工程师”，不是训练 foundation model 的标准算法研究员。**
