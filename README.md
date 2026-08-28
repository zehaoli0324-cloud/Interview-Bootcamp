# Interview Bootcamp — Dual Track Medical LLM / MLLM

这个仓库服务两个不同岗位，**共享 Python/Coding 基础，但岗位专项完全分轨。**

当前教学协议：**Tutor V5 — Pattern-First Python**。

---

## 第一次打开仓库：先看这两个文件

如果题目、缩写和技术名词几乎都没见过，不要硬啃题库：

1. [`ONE_LINE_GLOSSARY.md`](./ONE_LINE_GLOSSARY.md)：一句话扫盲，把 Coding、Eval/Data、RAG/Agent、ViT/MLLM、SFT/RL 和工程术语翻译成人话。
2. [`LEETCODE101_PYTHON_PATTERN_MAP.md`](./LEETCODE101_PYTHON_PATTERN_MAP.md)：把《LeetCode 101》的算法分类方式转成我们的 Python 模式地图。

`ONE_LINE_GLOSSARY.md` 是“名词地图”；`LEETCODE101_PYTHON_PATTERN_MAP.md` 是“算法地图”。

---

# Shared Coding：只用 Python，按 Pattern 学

两个岗位都只使用 **Python 3**。

《LeetCode 101》只作为：

> **算法模式教材 + Transfer/Retest 题池**

不学习 C++ 语法，不要求刷完 101 道题。

新的算法学习闭环：

```text
一句话扫盲
→ 极小例子手推
→ Python mini exercise
→ Core Anchor
→ 说清 pattern / state / invariant
→ 《LeetCode 101》同模式 Transfer Variant
→ 隔 ≥3 个训练单元或下一 session Delayed Retest
→ ≥8 才 MASTERED
```

核心原则：

> **做对一道题，不等于学会一种模式。**

算法优先级见：
- [`LEETCODE101_PYTHON_PATTERN_MAP.md`](./LEETCODE101_PYTHON_PATTERN_MAP.md)
- [`LEETCODE_CORE_15.md`](./LEETCODE_CORE_15.md)

Shared Coding 状态跨 Track 复用。

---

## Track A — A04613A 医疗大模型评测 / 数据工程师

核心：

> **医疗 Eval / Benchmark + Data Engineering + LLM-as-Judge + Agent/RAG + 自动化评测系统**

训练权重：
- Python Coding + Data Engineering：40%
- Eval / Benchmark / LLM-as-Judge：30%
- LLM App / Agent / RAG：15%
- Medical / Multimodal Eval：10%
- Project communication：5%

入口：
- [`TRACK_A_EVAL_DATA.md`](./TRACK_A_EVAL_DATA.md)
- [`ROADMAP_TRACK_A_7D.md`](./ROADMAP_TRACK_A_7D.md)
- [`MOCK_TRACK_A.md`](./MOCK_TRACK_A.md)

Track A 的算法目标：Coding 不成为否决项，并能把同样的 Python 模式迁移到 dedup、aggregation、top-k error、batch queue、logs 等工程问题。

Track A 不把 ViT training、Detail Caption 工程、PPO/GRPO 当 P0。

---

## Track B — A180084A 医疗大模型算法实习生

核心：

> **Algorithm Coding + CV/ViT/MLLM + SFT/LoRA + RL/Post-training**

训练权重：
- Algorithm Coding：45%
- CV / ViT / MLLM：30%
- SFT / LoRA / RL：15%
- Medical / Research / Eval：10%

入口：
- [`TRACK_B_MLLM_ALGO.md`](./TRACK_B_MLLM_ALGO.md)
- [`ROADMAP_TRACK_B_7D.md`](./ROADMAP_TRACK_B_7D.md)
- [`MOCK_TRACK_B.md`](./MOCK_TRACK_B.md)

Track B 的算法目标更高：Easy 稳定、常见 Medium 不空白、能识别模式、解释 complexity/invariant，并通过陌生题面迁移。

Track B 不允许用 Benchmark/Eval 强项替代 Coding、ViT/MLLM 或训练基础。

---

# Shared Core — 只学一次

- [`ONE_LINE_GLOSSARY.md`](./ONE_LINE_GLOSSARY.md)：陌生词一句话解释；
- [`PYTHON_LEVEL0.md`](./PYTHON_LEVEL0.md)：读题、list/index、变量、for/if/function/dict；
- [`LEETCODE101_PYTHON_PATTERN_MAP.md`](./LEETCODE101_PYTHON_PATTERN_MAP.md)：Pattern → Anchor → Transfer → Retest；
- [`LEETCODE_CORE_15.md`](./LEETCODE_CORE_15.md)：最小 Anchor 集；
- complexity / debugging / edge cases；
- 医疗场景基本理解。

一个算法模式在 Track A 已真正 MASTERED，Track B 不重新从头学，只在 Mock/retention 回测。

---

# Tutor V5

主协议：[`DEEPSEEK_TUTOR.md`](./DEEPSEEK_TUTOR.md)

V5 支持：

1. Track A / Track B 岗位路由；
2. FOUNDATION MODE：Python/题意不会时先教学；
3. TEACHING MODE：一次只修一个根因；
4. INTERVIEW MODE：正式单题面试；
5. 陌生术语先一句话扫盲；
6. **Pattern-First**：Anchor 后必须做同模式 Transfer；
7. Counterexample-first debugging；
8. Hint 1/2/3；
9. Delayed mastery；
10. Shared Coding / Track-specific readiness 分开记录。

训练时说：

```text
练 Track A
```

或：

```text
练 Track B
```

然后一次只处理当前题/当前概念。

---

# 《LeetCode 101》怎么用

我们不按书从第 1 页刷到最后，而是在当前模式需要时读取对应章节。

当前高优先级映射：

- 第 3 章：Two Pointers / Sliding Window
- 第 4 章：Binary Search
- 第 5 章：Quickselect / Top-K 思想
- 第 6 章：DFS / BFS
- 第 7 章：只取 Basic DP
- 第 11 章：Stack / Queue / Heap / Hash Table 等数据结构
- 第 13 章：Linked List
- 第 14 章：Tree Traversal

贪心作为 P1；Backtracking、Union-Find、复杂 Graph 等后置。

复杂 DP、数论、位运算大全、MST/最短路、竞赛级 Hard 当前不系统学习。

---

# Track A 专项文件

- [`TRACK_A_EVAL_DATA.md`](./TRACK_A_EVAL_DATA.md)
- [`CORE_12.md`](./CORE_12.md)
- [`ROADMAP_TRACK_A_7D.md`](./ROADMAP_TRACK_A_7D.md)
- [`MOCK_TRACK_A.md`](./MOCK_TRACK_A.md)

重点：medical evaluator coding、JSONL、async/retry/resume/idempotency、Judge calibration、Benchmark、RAG/Agent Eval、provenance/versioning。

---

# Track B 专项文件

- [`TRACK_B_MLLM_ALGO.md`](./TRACK_B_MLLM_ALGO.md)
- [`MLLM_VIT_CORE.md`](./MLLM_VIT_CORE.md)
- [`POSTTRAINING_SFT_RL_CORE.md`](./POSTTRAINING_SFT_RL_CORE.md)
- [`ROADMAP_TRACK_B_7D.md`](./ROADMAP_TRACK_B_7D.md)
- [`MOCK_TRACK_B.md`](./MOCK_TRACK_B.md)

重点：data structures、ViT/MLLM、Detail Caption/high-resolution、SFT/LoRA/DPO、PPO/GRPO/reward hacking。

---

# 统一状态与入口

- [`PROGRESS.md`](./PROGRESS.md)：Shared + Track A + Track B 状态
- [`SESSION_STATE.md`](./SESSION_STATE.md)：跨 session 恢复
- [`ROADMAP_7D.md`](./ROADMAP_7D.md)：双轨路由
- [`MOCK_INTERVIEW.md`](./MOCK_INTERVIEW.md)：双轨 Mock 路由
- [`START_TUTOR.md`](./START_TUTOR.md)：启动 Prompt

---

# 核心原则

> **Python 是语言；Pattern 是算法能力；Track 决定岗位专项。**

最终不是“刷过多少题”，而是面对陌生题时能：

> 读懂输入与约束 → 先给 brute force → 识别底层模式 → 写出可运行 Python → 解释复杂度和边界 → 在新题面再次迁移。
