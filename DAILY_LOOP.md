# DAILY LOOP — V3 自适应学习循环

> 不同 track 使用不同循环。核心原则：**先独立尝试，再诊断；不会时最小教学；会了就立即升级。**

---

# A. Foundation Loop（20–40 min / unit）

仅当 Foundation 未通过时使用。

1. **Explain one concept** — 3–5 min
2. **30-second recall** — 候选人自己回答
3. **Mini exercise** — 3–8 行
4. **Result** — NOT_YET / WITH_HELP / INDEPENDENT
5. **Advance or repair**

禁止：一次讲多个语法点、连续刷几十道基础题。

Foundation Gate 通过后，Foundation Loop 退出日常主线。

---

# B. Coding Loop（45–70 min / problem）

## 1. Problem

- 隐藏题号/标签；
- 候选人先复述输入输出；
- 鼓励先给 brute force。

## 2. Independent attempt

- 不查答案；
- 可以分多条消息；
- `提交` 后才判题。

## 3. Validate

先检查：
- syntax/runtime sanity；
- correctness；
- boundary；
- complexity。

错误时优先最小 counterexample。

## 4. Self-debug

候选人 trace 状态，不直接给修法。

## 5. Score

按 `RUBRIC.md` Coding 10 分制。

## 6. Micro-teach

只修一个主要根因。

## 7. Delayed retest

首次 PASS 不立即 mastered；隔其他训练单元再测。

---

# C. MLLM / ViT Loop（35–60 min / topic）

## Learn / Recall

只围绕：
- module role；
- data flow；
- tensor shape；
- training objective；
- failure mode；
- medical transfer。

## Mini transfer

每次至少一个：
- patch/token 计算；
- projector shape；
- high-res trade-off；
- detail-caption schema；
- hallucination diagnosis。

## Score

按 MLLM rubric。

不要用模型名堆砌代替理解。

---

# D. Post-training Loop（35–60 min / topic）

固定六问：

1. 数据是什么？
2. 哪些参数更新？
3. loss/reward 来自哪里？
4. 为什么比前一阶段有用？
5. 怎么 eval？
6. failure / safety 是什么？

再做一个最小实验设计或 reward-hacking case。

---

# E. Medical Eval Loop（20–40 min）

只用于保持差异化优势或连接训练闭环。

例如：
- 如何证明 MLLM hallucination 降了；
- 如何校准 medical judge；
- SFT/RL 后如何做 frozen regression；
- 如何防 reward hacking / benchmark shortcut。

已经稳定的内容不重复刷。

---

# 每天推荐交错顺序

Foundation 未通过：

```text
Foundation → Foundation → Coding mini → MLLM → Foundation/Coding
```

Foundation 通过后：

```text
Coding → MLLM → Coding → Post-training → Coding → Medical/Eval
```

不要连续 5 个同类单元。

---

# Error Log

每个训练单元只记录一个最主要根因。

## Coding/Foundation

- READING_INPUT
- SYNTAX_API
- INDEXING
- CONTROL_FLOW
- PATTERN_RECOGNITION
- INVARIANT
- IMPLEMENTATION
- BOUNDARY
- COMPLEXITY
- DEBUGGING
- EXPLANATION

## MLLM/Post-training

- CONCEPT
- DATA_FLOW
- TENSOR_SHAPE
- TRAINING_OBJECTIVE
- FAILURE_MODE
- TRADEOFF
- MEDICAL_TRANSFER

禁止写“粗心”。

---

# 每日收尾（10 min）

```text
Foundation: ...
Coding mastered/pass/retest: ...
MLLM learned/pass: ...
Post-training learned/pass: ...
Biggest risk (only 1): ...
Tomorrow first unit: ...
One thing I can now do independently: ...
```

然后更新 `SESSION_STATE.md`。

**每日目标不是完成题量，而是降低下一轮真实面试的最大淘汰风险。**