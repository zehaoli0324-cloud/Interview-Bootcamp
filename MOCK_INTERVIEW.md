# MOCK INTERVIEW — V3 医疗 MLLM 算法岗

> 目标：复刻 60 分钟技术面，不再学习新知识。

## 规则

- 60 分钟；
- 不查资料；
- Coding 不提前提示；
- MLLM/Post-training 先独立回答再追问；
- 结束后按 `RUBRIC.md` V3 总评；
- Mock 1/2 更换题面和模型问题。

---

# 0–5 min：背景与项目

3 分钟讲清一个最能证明“科研判断 + AI 能力”的项目：

1. problem；
2. 你具体做了什么；
3. hardest technical/methodological issue；
4. 怎么验证结果可信；
5. 一次失败/迭代。

追问重点：你本人贡献、是否真实运行、如何避免 benchmark shortcut / circular truth。

---

# 5–35 min：Coding

从已学范围抽 1 道牛客/LeetCode 风格题。

优先池：
- LC1 / LC20 / LC206；
- LC3 / LC33；
- LC102 / LC200 / LC215；
- 状态很好时才抽 LRU / DP / LC25 stretch。

要求：

1. 复述输入输出；
2. 先说最直接方案；
3. 写 Python；
4. 自测 2 个 case；
5. 时间/空间复杂度；
6. 一个 constraint change follow-up。

如果代码错，面试官只给最小失败输入，观察 self-debug。

---

# 35–48 min：MLLM / ViT

随机 1 个主问题 + 2 个 follow-up。

主问题池：
- 图像如何变成 ViT tokens；
- patch size / resolution / token cost；
- self-attention 在视觉中的作用；
- ViT vs CNN；
- vision encoder 如何接入 LLM；
- projector / Q-Former / resampler；
- Detail Caption；
- high-resolution medical image；
- hallucination / grounding。

至少一个 follow-up 必须涉及：
- tensor shape；或
- training objective；或
- compute/latency；或
- medical-specific failure。

---

# 48–56 min：SFT / LoRA / RL

随机：
- pretraining vs SFT；
- LoRA；
- preference data / DPO；
- reward model/verifier；
- PPO vs GRPO 直觉；
- KL；
- reward hacking；
- 医疗 RL reward。

必须追问：

> “你怎么验证这个训练真的让模型变好，而不是 reward/judge 被 hack？”

候选人应把 Medical Eval / Benchmark 优势迁移进回答。

---

# 56–60 min：快速追问 + 反问

快速题二选一：
- dict / heap / BFS 复杂度；
- patch token 数计算；
- LoRA rank 取舍；
- high-resolution token cost；
- hallucination vs factual error。

候选人反问建议：
- 团队医疗 MLLM 当前更核心的是预训练、post-training 还是业务场景模型迭代？
- ViT/视觉 encoder 是自研训练为主还是基于已有 backbone 做领域适配？
- 医疗模型 release gate 最重视哪些 failure slices / safety 指标？

---

# V3 总评

```text
Coding: __/10
MLLM / ViT: __/10
Post-training: __/10
Medical domain / Eval / Communication: __/10

Weighted: __/10
Biggest rejection risk: __
Strongest differentiated signal: __
Verdict: FAIL / BORDERLINE / INTERVIEW-READY
```

权重：
- Coding 45%
- MLLM/ViT 25%
- Post-training 15%
- Medical/Eval/communication 15%

## Interview-ready 参考

- Foundation 已 PASSED；
- Coding ≥7；
- MLLM ≥8；
- Post-training ≥7.5；
- 总体 ≥7.5；
- 不出现核心结构完全空白；
- 能主动用医疗/科研背景补充 failure mode 和验证方案。

Mock 分数只是训练门槛，不代表真实 offer 概率。

---

# Mock 后修补

只回答：

> 如果下一轮真实面试就在明天，我最可能因为什么被淘汰？

只修第一名风险 60–120 分钟，然后进行下一次 Mock。

禁止因为焦虑新增 20 个知识点。