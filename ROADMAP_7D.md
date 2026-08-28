# ROADMAP 7D — 双轨入口

本仓库现在服务两个不同岗位，**不要再用一份路线混练**。

## Track A — A04613A 医疗大模型评测 / 数据工程

主线：

> Python/Engineering → Evaluator → LLM-as-Judge → Data Pipeline → Benchmark → RAG/Agent Eval → System

使用：[`ROADMAP_TRACK_A_7D.md`](./ROADMAP_TRACK_A_7D.md)

训练权重：
- Python Coding + Data Engineering 40%
- Eval / Benchmark / Judge 30%
- LLM App / Agent / RAG 15%
- Medical / Multimodal Eval 10%
- Project communication 5%

Track A 不把 ViT training、Detail Caption 工程、PPO/GRPO 作为 P0。

---

## Track B — A180084A 医疗大模型算法实习

主线：

> Python/Algorithm → ViT → MLLM → Detail Caption/High Resolution → SFT/LoRA → RL

使用：[`ROADMAP_TRACK_B_7D.md`](./ROADMAP_TRACK_B_7D.md)

训练权重：
- Algorithm Coding 45%
- CV / ViT / MLLM 30%
- SFT / LoRA / RL 15%
- Medical / Research / Eval 10%

Track B 不把 Judge calibration、数据 pipeline、RAG/Agent eval 当主线。

---

# Shared Core — 两条轨道共享

以下进度共享，不重复刷：

1. `PYTHON_LEVEL0.md`
2. `LEETCODE_CORE_15.md` 中已真正掌握的模式
3. Python 基础 API / complexity / debugging
4. 医疗领域基本场景理解

如果 LC3 在 Track A 已通过延迟复测成为 MASTERED，Track B 不需要重新从 LC3 教学开始，只需要在 Mock 中回测。

---

# 使用规则

训练开始时必须声明：

```text
Track: A
```

或：

```text
Track: B
```

如果未声明：
- 延续上一轮 active track；
- 如果是新 session，则先询问一次 A/B，不要自行混合。

用户说“两个都练”时：
- 共享 Coding 只练一次；
- 其余时间 A/B 分块；
- 不在同一道题里强行混合 Judge calibration 和 ViT training。

---

# 推荐优先级

如果两个面试时间接近：

1. 先补共享 Python/Coding veto risk；
2. Track A 用其专属优势快速达到稳定通过；
3. Track B 用剩余时间补 ViT/MLLM/SFT/RL 的最低技术生存线。

原则：

> **共享底座，岗位分轨；不能为了一个岗位的短板，破坏另一个岗位本来很强的匹配。**
