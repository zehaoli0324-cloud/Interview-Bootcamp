# MLLM / ViT CORE — 医疗大模型算法岗专项

> 目标：不是一周变成 CV researcher，而是能够和 MLLM 面试官进行一轮真实技术交流，并能把生命科学场景映射到多模态模型问题。

## 通过线

面试前至少做到：

- M1–M8 能不用稿子解释；
- M9–M12 至少完成 2 个；
- 能画出一个典型 MLLM 数据流；
- 能解释 ViT 为什么能处理图像；
- 能解释视觉特征如何进入 LLM；
- 能讨论医疗 MLLM hallucination / grounding / resolution / evaluation。

---

# Part A — ViT 基础

## M1. 图像为什么能送进 Transformer？

必须会讲：

1. 输入图像 `H × W × C`；
2. 切成固定大小 patch；
3. 每个 patch flatten / projection 成 token embedding；
4. 加 position embedding；
5. 送进 Transformer blocks。

追问：
- patch 越小会怎样？
- token 数量如何随分辨率变化？
- 为什么高分辨率成本很高？

## M2. Patch Embedding 是什么？

能解释：

> 本质上把二维局部图像块映射到 Transformer 的 embedding dimension。

知道常见实现可以用 stride=patch_size 的 Conv2d 等价完成。

## M3. Position Embedding 为什么需要？

Transformer 本身不天然知道 token 的二维/顺序位置。

追问：
- 分辨率变化时 learned positional embedding 怎么处理？
- interpolation 是什么思路？

## M4. Self-Attention 在图像里做什么？

不要只背公式。

必须能用一句话解释：

> 每个视觉 token 根据内容动态决定应该聚合其他哪些 token 的信息，因此可以建模远距离区域关系。

至少认识：Q/K/V、attention score、softmax、weighted sum。

## M5. ViT vs CNN

要求比较：

- inductive bias；
- locality；
- translation equivariance；
- 数据规模需求；
- global interaction；
- 计算成本。

不要求得出“谁更好”的绝对结论。

---

# Part B — MLLM 结构

## M6. 一个典型 MLLM 怎么连接图像和语言？

最小结构：

```text
image
  ↓
vision encoder (ViT/CLIP-like)
  ↓
visual tokens/features
  ↓
projector / adapter / resampler
  ↓
LLM token space
  ↓
LLM
  ↓
text response
```

必须解释 projector 为什么存在：视觉 encoder 的 hidden space / dimension 通常不等于 LLM 输入 embedding space。

## M7. LLaVA 类模型的基本训练逻辑

不背具体版本数字，只理解两阶段思想：

1. visual-language feature alignment；
2. multimodal instruction tuning。

追问：
- 第一阶段为什么不能只训练 LLM？
- projector 冻结/不冻结有什么取舍？
- instruction data 的质量会影响什么？

## M8. Q-Former / Resampler 是什么角色？

理解即可：

> 用少量可学习 query 从大量视觉特征中抽取/压缩与语言任务相关的信息，控制视觉 token 数量并完成跨模态桥接。

比较：
- simple linear projector；
- MLP projector；
- query-based resampler。

讨论 trade-off，而不是背论文。

---

# Part C — Detail Caption / 高分辨率

## M9. 什么是 Detail Caption？为什么岗位会点名？

要能解释：

普通 caption：
> “这是一张胸部 X 光。”

detail caption 更强调：
- 多实体；
- 属性；
- 空间关系；
- 局部细节；
- 覆盖率；
- 减少视觉信息被粗糙语言压缩。

医疗场景进一步强调：
- 解剖位置；
- lesion morphology；
- laterality；
- size / distribution；
- uncertainty；
- negative findings。

## M10. 高分辨率图像为什么困难？

核心：patch 数量随面积增加，attention 成本快速增长。

能讨论：
- resize；
- crop / tile；
- multi-scale；
- dynamic resolution；
- token compression；
- region selection。

医疗场景要主动提：小病灶可能在 resize 后丢失。

## M11. 图像 hallucination 从哪里来？

至少分四类：

1. visual encoder 没编码到；
2. bridge/projector 丢失信息；
3. language prior 压过 visual evidence；
4. training/evaluation data 偏差。

医疗场景要特别关注：
- 无证据病灶；
- 部位/左右侧错误；
- 把可能性说成确定；
- 没有图像 grounding 的诊断推断。

## M12. 如何评测医疗 MLLM？

至少分：

- factual / clinical correctness；
- image grounding；
- finding coverage；
- hallucination；
- localization / spatial relation；
- uncertainty；
- safety；
- report usefulness。

必须说明：单一 BLEU/ROUGE 或单一 LLM judge 不足以证明临床可靠。

---

# Part D — 小型实践题

## MX1. Patch 数量计算

图像 `224×224`，patch size `16×16`。

回答：
- 一行多少 patch？
- 总共多少 patch token？
- 若加一个 CLS token，总 token 数？

然后把分辨率改成 `448×448`，比较 token 数增加多少倍。

## MX2. 写最小 Patchify

用 Python / PyTorch 风格伪代码说明如何把 `[B,C,H,W]` 图像切成 patch tokens。

不要求一次写工业实现，重点是 shape 推导。

## MX3. MLLM Forward Shape Walkthrough

给：

```text
vision features: [B, 576, 1024]
LLM hidden size: 4096
```

回答：projector 输出应该是什么 shape，以及为什么。

## MX4. 医疗 Detail Caption 数据设计

给 1000 张胸片，设计 caption schema：

- anatomy；
- finding；
- location；
- severity；
- uncertainty；
- negative finding；
- evidence/provenance。

追问：如何避免模型从模板里 shortcut？

## MX5. 小病灶高分辨率方案

假设全图 resize 后小结节看不清。提出一个最小可实现方案，并讨论：

- recall；
- token cost；
- latency；
- false positive；
- training/inference consistency。

---

# 面试回答模板

遇到陌生 MLLM 问题时，不要空白。按：

1. **先定义模块/问题**；
2. **画数据流或 tensor shape**；
3. **说训练目标**；
4. **说 failure mode**；
5. **说医疗场景特殊风险**；
6. **最后说 trade-off / 如何验证**。

这套顺序比背大量模型名更重要。