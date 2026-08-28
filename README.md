# Interview Bootcamp — Dual Track Medical LLM / MLLM

这个仓库现在明确服务两个不同岗位，**共享 Python/Coding 基础，但岗位专项完全分轨。**

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

Track B 不允许用 Benchmark/Eval 强项替代 Coding、ViT/MLLM 或训练基础。

---

# Shared Core — 只学一次

两个岗位共享：

- [`PYTHON_LEVEL0.md`](./PYTHON_LEVEL0.md)：从读题、list/index、for/if/function/dict 起步；
- [`LEETCODE_CORE_15.md`](./LEETCODE_CORE_15.md)：常见 Easy/Medium 算法锚点；
- complexity / debugging / edge cases；
- 医疗场景基本理解。

共享 Coding 状态记录在 [`PROGRESS.md`](./PROGRESS.md)。

**一个模式在 Track A 已经真正 MASTERED，Track B 不重新从头刷，只在 Mock 回测。**

---

# Tutor V4

主协议：[`DEEPSEEK_TUTOR.md`](./DEEPSEEK_TUTOR.md)

虽然保留旧文件名用于兼容，但现在是通用 **Tutor V4**，支持：

1. **岗位路由**：Track A / Track B；
2. **FOUNDATION MODE**：基础 Python/读题不会时先教学；
3. **INTERVIEW MODE**：会基础后按真实面试单题训练；
4. **TEACHING MODE**：只修一个根因；
5. **Counterexample-first debugging**；
6. **Hint 1/2/3 分级**；
7. **Delayed mastery**；
8. **Shared Coding / Track-specific readiness 分开记录**。

训练时直接说：

```text
练 Track A
```

或：

```text
练 Track B
```

然后一次只处理当前一道题/一个概念。

---

# Track A 专项文件

- [`TRACK_A_EVAL_DATA.md`](./TRACK_A_EVAL_DATA.md)：JD → 能力 → 题库 → 通过线
- [`CORE_12.md`](./CORE_12.md)：Evaluator / Judge / Batch / Benchmark / System 核心题
- [`ROADMAP_TRACK_A_7D.md`](./ROADMAP_TRACK_A_7D.md)
- [`MOCK_TRACK_A.md`](./MOCK_TRACK_A.md)

重点：
- medical evaluator coding；
- JSONL / cleaning / aggregation；
- async / retry / resume / idempotency；
- LLM-as-Judge calibration；
- independent truth；
- shortcut / leakage；
- medical safety slices；
- RAG / Agent / tool calling evaluation；
- data provenance / versioning。

---

# Track B 专项文件

- [`TRACK_B_MLLM_ALGO.md`](./TRACK_B_MLLM_ALGO.md)
- [`MLLM_VIT_CORE.md`](./MLLM_VIT_CORE.md)
- [`POSTTRAINING_SFT_RL_CORE.md`](./POSTTRAINING_SFT_RL_CORE.md)
- [`ROADMAP_TRACK_B_7D.md`](./ROADMAP_TRACK_B_7D.md)
- [`MOCK_TRACK_B.md`](./MOCK_TRACK_B.md)

重点：
- data structures / LeetCode；
- patch embedding / attention / ViT；
- vision encoder → projector → LLM；
- LLaVA / Q-Former；
- Detail Caption / high-resolution；
- SFT / LoRA / DPO；
- PPO / GRPO / rollout / KL / reward hacking。

---

# 统一状态与入口

- [`PROGRESS.md`](./PROGRESS.md)：Shared + Track A + Track B 三层状态
- [`SESSION_STATE.md`](./SESSION_STATE.md)：跨 session 恢复
- [`ROADMAP_7D.md`](./ROADMAP_7D.md)：双轨路由
- [`MOCK_INTERVIEW.md`](./MOCK_INTERVIEW.md)：双轨 Mock 路由
- [`START_TUTOR.md`](./START_TUTOR.md)：给其他教练模型的启动 Prompt

---

# 核心原则

> **A04613A 和 A180084A 不是同一个岗位换名字。**

Track A 要证明：

> 我能建设可信、可自动化、可追溯的医疗 LLM 评测与数据系统，并通过分析推动模型迭代。

Track B 要证明：

> 我具备进入医疗多模态模型训练团队的 Coding、ViT/MLLM 与 post-training 技术基础。

因此最终 readiness 必须分别判定，不能互相抵分。
