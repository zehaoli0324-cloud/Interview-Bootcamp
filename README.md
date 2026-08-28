# Medical MLLM Algorithm Interview Bootcamp V3

> 面向 **大模型算法实习生（医疗方向）** 的 7 天定向训练。
>
> 当前目标不是把候选人包装成已经成熟的算法工程师，而是：**从 Python/算法基础起步，把 Coding 拉过面试生存线；同时建立 ViT / MLLM / SFT / RL 的真实技术对话能力，并保留医疗科研与 Eval 的差异化优势。**

---

# V3 为什么重构

岗位核心已经从“医疗大模型评测 / 数据工程”转向：

1. 医疗领域大模型预训练、SFT、强化训练；
2. 模型业务效果与落地；
3. CV / MLLM / ViT / Detail Caption；
4. 优秀 Coding、数据结构与基础算法。

因此训练权重改为：

- **Python + Algorithm Coding：约 50%**
- **MLLM / CV / ViT：约 25%**
- **SFT / LoRA / Preference / RL：约 15%**
- **Medical Eval / Benchmark / System：约 10%**

这个比例不是每天机械固定。最初 1–2 天如果 Python 基础仍不稳定，Coding 会临时占更高比例；一旦通过 Foundation Gate，立即减少基础语法练习。

---

# 四层训练结构

## Level 0 — Python Foundation

文件：[`PYTHON_LEVEL0.md`](./PYTHON_LEVEL0.md)

解决：

- 题目和示例看不懂；
- `list / index / for / if / function / dict` 不熟；
- 还不能把简单思路翻译成 Python。

**Level 0 是跳板，不是长期题库。** Z15–Z18 至少 3/4 独立完成后就退出。

## Level 1/2 — LeetCode / 牛客算法主线

文件：[`LEETCODE_CORE_15.md`](./LEETCODE_CORE_15.md)

保留原来的 15 个锚点，但它们现在是 **Foundation 之后的目标**：

- HashMap / Stack / String；
- Linked List；
- Sliding Window；
- Interval；
- Tree / Grid BFS-DFS；
- Heap / Top-K；
- Binary Search；
- LRU；
- 少量 DP / 括号 / sqrt；
- LC25 只作为 stretch。

不刷 Hot100 全套。

## Level 3 — MLLM / ViT 专项

文件：[`MLLM_VIT_CORE.md`](./MLLM_VIT_CORE.md)

覆盖：

- patch embedding / position embedding；
- self-attention；
- ViT vs CNN；
- vision encoder → projector/resampler → LLM；
- LLaVA 类 alignment / instruction tuning；
- Q-Former / resampler；
- Detail Caption；
- high-resolution / tiling / token cost；
- medical hallucination / grounding / evaluation。

## Level 4 — Post-training

文件：[`POSTTRAINING_SFT_RL_CORE.md`](./POSTTRAINING_SFT_RL_CORE.md)

覆盖：

- pretraining vs SFT；
- LoRA；
- instruction / preference data；
- DPO；
- reward model / verifier；
- PPO / GRPO 的面试级直觉；
- KL；
- reward hacking；
- 医疗模型 reward / safety 设计。

医疗 Eval / Benchmark 强项继续保留在 [`CORE_12.md`](./CORE_12.md)，但不再占据训练主线。

---

# Tutor V3：三种模式

核心协议：[`DEEPSEEK_TUTOR.md`](./DEEPSEEK_TUTOR.md)

虽然文件名为了兼容旧仓库保留 `DEEPSEEK_TUTOR.md`，V3 实际适用于 ChatGPT / DeepSeek / Claude 等教练模型。

### FOUNDATION MODE

当候选人连题意、下标、循环、函数都不理解时：

**解释一个最小概念 → 30 秒 recall → 3–8 行 mini exercise → 自己完成 → 再升级。**

不会强行模拟面试，也不会一次倒一整章 Python。

### INTERVIEW MODE

基础可用后：

**一次一道题 → 无提前提示 → 候选人提交 → 判题 → 最小反例 → self-debug → 严格评分。**

### TEACHING MODE

提交后发现知识缺口，或候选人明确说“完全不会”时进入。

只修**一个最主要根因**，修完立即回到练习。

---

# 7 天路径

详见 [`ROADMAP_7D.md`](./ROADMAP_7D.md)。

简版：

| Day | 主线 | 目标 |
|---|---|---|
| 1 | Python Level 0 + Two Sum 暴力版 | 从看懂题到能写最小函数 |
| 2 | Easy 算法 + ViT 基础 | HashMap/Stack/链表 + patch/token/attention |
| 3 | 高频 Medium + MLLM 架构 | Sliding window / binary search + vision→LLM |
| 4 | BFS/DFS/Heap + Detail Caption | 进入常见算法主战场 + 高分辨率医疗视觉 |
| 5 | LRU/强化 Coding + SFT/LoRA | 数据结构实现 + 最小 post-training 能力 |
| 6 | Mixed Coding + DPO/RL + Medical Eval | 陌生题面迁移 + 训练方案表达 |
| 7 | 两轮技术面 Mock | Coding + MLLM + training + 医疗 domain 综合 |

---

# 文件导航

- [`START_TUTOR.md`](./START_TUTOR.md)：给 ChatGPT/其他模型的启动指令。
- [`DEEPSEEK_TUTOR.md`](./DEEPSEEK_TUTOR.md)：Tutor V3 自适应教学协议。
- [`PYTHON_LEVEL0.md`](./PYTHON_LEVEL0.md)：从零 Coding 基础。
- [`LEETCODE_CORE_15.md`](./LEETCODE_CORE_15.md)：算法锚点。
- [`MLLM_VIT_CORE.md`](./MLLM_VIT_CORE.md)：MLLM/ViT 专项。
- [`POSTTRAINING_SFT_RL_CORE.md`](./POSTTRAINING_SFT_RL_CORE.md)：SFT/LoRA/RL 专项。
- [`ROADMAP_7D.md`](./ROADMAP_7D.md)：7 天路径。
- [`RUBRIC.md`](./RUBRIC.md)：V3 分层评分。
- [`PROGRESS.md`](./PROGRESS.md)：V3 能力地图。
- [`SESSION_STATE.md`](./SESSION_STATE.md)：跨对话状态恢复。
- [`CORE_12.md`](./CORE_12.md)：Medical Eval / Benchmark / System 优势模块。
- [`MOCK_INTERVIEW.md`](./MOCK_INTERVIEW.md)：全真模拟。

---

# 最终通过线

目标不是“所有知识都学完”，而是达到：

### Coding
- Python Foundation 全部通过；
- Easy 能独立完成；
- 常见 Medium 能识别模式并形成主解；
- 陌生题不会直接空白，能从 brute force 推到优化；
- LC3 / LC200 / LC215 至少 PASS；LC146 至少能完整解释实现结构。

### MLLM
- 能从 image → vision encoder → bridge → LLM 画出数据流；
- ViT 核心组件能解释；
- 能讨论 high-resolution、Detail Caption、hallucination、grounding；
- 至少完成两个 tensor/数据设计小题。

### Post-training
- 能解释 SFT、LoRA、preference、DPO、PPO/GRPO 的关系；
- 能设计一个最小医疗 SFT/LoRA 实验；
- 能指出 reward hacking 与医疗 safety 风险。

### 综合
- 至少一次 60 分钟 Mock：Coding 不出现基础性崩溃，MLLM/Post-training 能形成结构化答案，医疗科研/Eval 能作为加分项展开。

**V3 的目标：把“稀缺生命科学背景 + 强科研判断”前面的 Coding / MLLM 门槛尽快跨过去。**