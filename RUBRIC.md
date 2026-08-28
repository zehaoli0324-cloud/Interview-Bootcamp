# RUBRIC — V3 分层评分

> 不同阶段用不同评分法。初学 Foundation 不用 10 分制；正式 Coding / MLLM / Post-training 才用严格 10 分制。

---

# 1. Foundation Mode

每个微型练习只判：

- `NOT_YET`：概念仍不清楚；
- `WITH_HELP`：提示后完成；
- `INDEPENDENT`：独立完成。

## Foundation Gate

通过必须同时满足：

1. list/index、for、if、function/return、dict 可解释；
2. Z15–Z18 至少 3/4 为 `INDEPENDENT`；
3. 能自己 trace 一个两层循环；
4. 能说清输入和输出分别是什么。

一旦通过，标 `FOUNDATION_PASSED`。

单个语法错误不应把状态降回 Foundation。

---

# 2. Algorithm Coding — 10 分

| 维度 | 分值 |
|---|---:|
| Correctness | 5.0 |
| Complexity | 1.5 |
| Edge cases / robustness | 1.5 |
| Explanation / invariant | 1.0 |
| Code clarity / self-test | 1.0 |

### 硬上限

- 主逻辑错 / 无法运行：最高 5.5；
- 复杂度明显不达标且无意识：最高 6.5；
- 核心算法由面试官明确指出后才完成：最高 6.5；
- 代码对但解释不了为什么：最高 7；
- 看完整答案后立即重写：不提供 mastery evidence。

### Hint 上限

| Hint | 最高分 | Mastery evidence |
|---|---:|---|
| 0 | 10 | 可作为首次 PASS 证据 |
| 1 苏格拉底问题 | 9 | 否 |
| 2 模式方向 | 8 | 否 |
| 3 局部伪代码/invariant | 7 | 否 |
| full answer | 不计 | 否 |

### Coding 状态

- 9–10：PASS / RETEST-DUE
- 8–8.9：PASS / RETEST-DUE
- 7–7.9：BORDERLINE
- 6–6.9：LEARNING
- <6：FAIL / FOUNDATION 或 micro-teach 视根因决定

MASTERED 仍需要延迟、不同题面、无提示复测 ≥8。

---

# 3. MLLM / ViT — 10 分

| 维度 | 分值 |
|---|---:|
| Concept correctness | 3 |
| Data flow / tensor shape | 2 |
| Training objective / model role | 2 |
| Failure mode / trade-off | 2 |
| Medical transfer | 1 |

### 硬扣分

- 只背模型名，无法解释模块数据流：最高 5.5；
- tensor shape 完全没有概念且题目明确要求：最高 6；
- 把 vision encoder / projector / LLM 角色混淆：最高 6；
- 高分辨率问题完全不考虑 token/compute：扣 1–2；
- 医疗 hallucination 问题只回答“用更多数据”：最高 6.5。

状态：
- ≥8：PASS；
- 7–7.9：BORDERLINE；
- <7：LEARNING。

MASTERED 需要在另一个 shape / 模型 / 医疗案例中迁移再次 ≥8。

---

# 4. Post-training — 10 分

| 维度 | 分值 |
|---|---:|
| Core mechanism | 3 |
| Data / training signal / objective | 2 |
| Experiment design | 2 |
| Failure modes / trade-offs | 2 |
| Medical safety | 1 |

### 硬扣分

- SFT / DPO / RL 完全混为一谈：最高 5；
- 只能背 PPO/GRPO 名字，说不清 rollout/reward：最高 6；
- LoRA 只会说“省显存”，不知道低秩增量：最高 6.5；
- 医疗 reward 不考虑 reward hacking / safety：扣 1–2；
- 把未经校准的 LLM judge 直接当 gold reward：最高 6。

---

# 5. Medical Eval / Benchmark

沿用严格标准：

| 维度 | 分值 |
|---|---:|
| Task / slice | 1.5 |
| Independent truth / evidence | 2 |
| Metric / rubric | 1.5 |
| Judge calibration | 1.5 |
| Shortcut / leakage / failure | 1.5 |
| Statistics / regression | 1 |
| Executability | 1 |

truth 循环依赖最高 5；单一未校准 LLM judge 当 gold 最高 6。

---

# 6. Mock Interview V3

建议权重：

- Coding：45%
- MLLM / ViT：25%
- SFT / RL：15%
- Medical domain / Eval / communication：15%

## 稳定通过参考

- Coding ≥7；
- MLLM ≥8；
- Post-training ≥7.5；
- 总体 ≥7.5；
- 无“题意完全读不懂 / 基本循环无法写”的 Foundation failure；
- 无 MLLM 核心结构完全空白；
- 无 SFT/RL 机制严重混淆。

注意：这个分数用于训练定位，不代表真实公司录取概率。