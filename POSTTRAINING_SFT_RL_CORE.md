# POST-TRAINING CORE — SFT / LoRA / Preference / RL

> 目标：达到“能解释、能设计最小实验、能识别失败模式”的面试水平。
>
> 一周内不追求从零实现 PPO/GRPO trainer，也不背大量公式。

## 通过线

- P1–P8 能口述；
- P9–P12 至少完成 2 个设计题；
- 能讲清 pretraining → SFT → preference/RL 的关系；
- 能解释 LoRA 为什么省参数；
- 能说明医疗模型 reward / safety 为什么难。

---

# Part A — Pretraining / SFT / LoRA

## P1. Pretraining 和 SFT 有什么区别？

### Pretraining
目标通常是大规模 next-token prediction / multimodal alignment，获得通用表示与生成能力。

### SFT
使用高质量 instruction-response / demonstration 数据，把模型行为往目标任务和交互格式上拉。

必须能回答：
- SFT 为什么不是简单“让模型记答案”？
- 数据质量和覆盖度为什么重要？
- SFT 太窄可能有什么问题？

## P2. Full fine-tuning vs LoRA

理解 LoRA：

> 不直接更新整个大权重矩阵，而学习低秩增量 `ΔW ≈ BA`。

需要知道：
- 可训练参数显著下降；
- 显存/存储更友好；
- rank r 控制表达能力和成本；
- inference 时可以 merge 或保留 adapter。

追问：
- rank 越大一定越好吗？
- 哪些层加 LoRA？
- 医疗小数据为什么容易 overfit？

## P3. 一个最小 SFT 数据样本长什么样？

至少理解：

```text
system / instruction / context / response
```

医疗任务要额外考虑：
- evidence；
- uncertainty；
- refusal / escalation；
- patient privacy；
- guideline provenance。

## P4. 数据 packing / masking 的意义

理解：
- padding 浪费；
- packing 提高 token 利用率；
- loss mask 决定哪些 token 参与监督；
- chat template 错位会造成训练/推理不一致。

---

# Part B — Preference Learning

## P5. Preference data 是什么？

典型形式：

```text
prompt + chosen + rejected
```

来源可能包括：
- 人工专家比较；
- 规则/verifier；
- 模型辅助标注后人工审核；
- 在线/业务反馈。

医疗场景不能把未经校准的模型 judge 直接当绝对真值。

## P6. DPO 的直觉

不要求推公式，但要能讲：

> 直接利用 chosen/rejected 对，让策略相对 reference 更偏好 chosen，而不显式训练独立 reward model + 在线 PPO rollout。

比较 SFT：
- SFT 学“示范是什么”；
- preference optimization 学“两个回答哪个更好”。

## P7. Reward Model / Verifier

作用：对模型输出给标量或结构化反馈。

医疗 reward 可能拆成：
- clinical correctness；
- evidence consistency；
- safety；
- uncertainty calibration；
- format/tool use；
- task completion。

警惕：
- reward hacking；
- judge bias；
- specification gaming；
- high-risk error 被平均掉。

---

# Part C — RL / GRPO / PPO

## P8. 为什么还需要 RL？

直觉：

有些目标很难用单一 gold response 覆盖，但可以对完整 rollout / reasoning / tool behavior 给结果反馈。

适用：
- reasoning；
- tool use；
- search/agent；
- long-horizon behavior；
- 可验证任务。

## P9. PPO 需要知道什么？

面试最低线：

- policy 生成 rollout；
- reward signal；
- advantage；
- 更新 policy；
- clipping 限制过大策略更新；
- KL/reference 约束防止策略漂移过快。

不要求一周内背完整推导。

## P10. GRPO 的直觉

最低要求：

> 对同一 prompt 采样一组输出，用组内相对 reward 构造学习信号，从而减少对独立 value model 的依赖。

需要讨论：
- group sampling 成本；
- reward quality；
- diversity；
- reward hacking；
- verifier 是否可靠。

## P11. KL 为什么常见？

作用直觉：

> 不希望为了追 reward，模型快速偏离原本合理语言/知识分布。

但 KL 太强：学不动；太弱：可能 reward hacking / collapse / 风格漂移。

## P12. On-policy rollout 为什么贵？

因为训练期间需要不断用当前策略生成新样本，并计算 reward / verifier；长序列和多模态输入会进一步放大成本。

---

# Part D — 医疗训练设计题

## PX1. 医疗问答 SFT 数据设计

设计 10k 样本 schema，并回答：
- 来源；
- evidence；
- guideline/version；
- uncertainty；
- hard negative；
- de-identification；
- split / leakage。

## PX2. LoRA 最小实验

假设有一个小型开源模型和 5k 医疗 instruction samples。

设计：
- baseline；
- train/val/test；
- LoRA rank；
- learning rate / epoch 只需要说明调参策略；
- early stopping；
- eval slices；
- regression；
- overfit 判断。

## PX3. 医疗 preference rubric

chosen vs rejected 不能只看“写得像不像医生”。至少包括：
- factuality；
- evidence sufficiency；
- clinical appropriateness；
- uncertainty；
- safety；
- usefulness。

## PX4. 医疗 RL reward

设计一个复合 reward：

```text
R = task correctness + evidence + safety + calibrated uncertainty - hallucination penalties
```

然后主动指出：简单线性加权可能掩盖 safety red line。

更成熟的答案要考虑：
- hard constraint / gate；
- slice-specific reward；
- expert calibration；
- reward model audit。

## PX5. Reward hacking 案例

如果 reward 偏好“回答引用指南”，模型开始生成大量看似专业但不存在的指南引用。

回答：
- 为什么发生；
- 如何检测；
- 如何改 reward；
- 哪个 held-out regression 能防止复发。

---

# 面试回答骨架

遇到训练问题按：

1. **数据/任务定义**；
2. **训练阶段和哪些参数更新**；
3. **loss / reward 信号来自哪里**；
4. **如何 eval**；
5. **failure mode**；
6. **成本/工程 trade-off**；
7. **医疗 safety / evidence 特殊约束**。

不要把所有问题都回答成模型名列表。