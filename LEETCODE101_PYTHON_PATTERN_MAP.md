# LeetCode 101 → Python Pattern Map

> 参考资料：高畅《LeetCode 101：和你一起轻松刷题（C++）》正式版 1.00。
>
> **本仓库只学习它的算法组织方式、模式解释和变式设计，不学习 C++ 语法。所有训练代码统一使用 Python 3。**

---

# 1. 这本书在本仓库里的角色

不是：

> 再增加一份“101 道必刷题单”。

而是：

> **Pattern textbook + transfer pool**。

用途只有三个：

1. 给一个算法模式提供第二种解释；
2. 给 Core Anchor 提供同模式变式，验证是否真的迁移；
3. 给 delayed retest 提供陌生题面，防止只记住标准答案。

原则：

- Python only；
- 不要求按书本顺序通读；
- 不要求刷完 101 道；
- 只在当前模式已经进入学习时读取对应章节；
- 书中 Hard 默认不作为初学 Anchor，主要用于理解模式边界或后期 stretch；
- 如果书中 C++ 实现与 Python 常用写法不同，保留算法思想，改写为 Pythonic 实现。

---

# 2. 新的算法学习闭环

每个模式必须按下面顺序：

```text
0. 一句话扫盲
→ 1. 画/手推一个极小例子
→ 2. 3–8 行 Python mini exercise
→ 3. Core Anchor：第一次完整题
→ 4. 用自己的话说出 pattern / state / invariant
→ 5. LeetCode 101 同模式 Transfer Variant
→ 6. 隔 ≥3 个训练单元或下一 session 再做陌生变式
→ 7. RETEST ≥8 才 MASTERED
```

**Anchor 做对 ≠ 掌握模式。**

必须至少证明一次：

> 题面换了，但仍能识别“底层是同一种模式”。

---

# 3. Pattern Priority Map

## P0 — 两个岗位共享，必须学

### Pattern 1 — HashMap / “以前见过吗？”

**人话：** 把以前见过的信息存进 `dict`，以后可以快速查询。

Core Anchor：
- LC1 Two Sum

Transfer 方向：
- frequency / last seen / value→index；
- 哈希表类数据结构问题。

Python：`dict`, `set`, `Counter`, `defaultdict`。

---

### Pattern 2 — Stack / “最近一个还没解决的东西”

**人话：** 最后放进去的先处理，适合括号、撤销、最近未匹配状态。

Core Anchor：
- LC20 Valid Parentheses

书中可用变式：
- Min Stack（155）；
- 书中第 11 章栈/队列相关练习。

Python：先用 `list.append()` / `list.pop()`；需要双端操作再用 `collections.deque`。

---

### Pattern 3 — Two Pointers / 双指针

**人话：** 用两个位置一起移动，避免把所有组合都重复试一遍。

书中第 3 章把双指针分为：
- 同向；
- 反向；
- 快慢指针；
- 滑动窗口。

书中代表题：
- 167 Two Sum II；
- 88 Merge Sorted Array；
- 142 Linked List Cycle II。

我们的使用：
- 先理解“为什么两个指针可以排除一批答案”；
- Python 手推后再写代码；
- 不要求记 C++ pointer 语法。

---

### Pattern 4 — Sliding Window / 滑动窗口

**人话：** 维护一个连续区间，右边扩张，条件坏了就从左边收缩。

Core Anchor：
- LC3 Longest Substring Without Repeating Characters

书中第 3.5 节代表：
- 76 Minimum Window Substring（Hard，默认只用于理解窗口机制，不作为初学必写）。

Transfer：
- 固定窗口；
- 可变窗口；
- “最多 K 个不同元素”；
- 医疗日志连续片段/时间窗口的业务改写。

---

### Pattern 5 — Sorting + Interval / 排序后局部扫描

**人话：** 先把杂乱关系排成有规律的顺序，再只比较相邻或当前区间。

Core Anchor：
- LC56 Merge Intervals

书中相关：
- 第 2 章贪心的区间问题；
- 435 Non-overlapping Intervals。

教学重点：
- 为什么要按 start 或 end 排序；
- 排序后哪个 invariant 变简单。

---

### Pattern 6 — Binary Search / 二分

**人话：** 每次根据一个判断排除一半可能答案。

Core Anchor：
- LC33 Search in Rotated Sorted Array
- sqrt(x)

书中第 4 章代表：
- 69 Sqrt(x)；
- 34 Find First and Last Position；
- 81 Search in Rotated Sorted Array II。

教学重点：
- 搜索区间到底表示什么；
- 为什么能安全丢掉一半；
- 最后只剩 1–2 个位置时是否仍正确。

Python 不先背模板；先手推 `left / mid / right`。

---

### Pattern 7 — BFS / 一层一层扩散

**人话：** 像水波一样一层层向外走，常用于层序遍历或最短步数。

Core Anchor：
- LC102 Binary Tree Level Order Traversal

书中第 6.4 节强调 BFS 使用 FIFO 队列并按层遍历。

Python：`collections.deque`。

Transfer：
- 树的层序遍历；
- 网格最短步数；
- 多源 BFS（后期）。

---

### Pattern 8 — DFS / 沿一条路走到底

**人话：** 先把一条路径走深，再回来处理其他分支。

Core Anchor：
- LC200 Number of Islands

书中第 6.2 节代表：
- 695 Max Area of Island；
- 547 Friend Circles；
- 417 Pacific Atlantic Water Flow。

教学重点：
- 当前节点是谁；
- 邻居是谁；
- visited 何时标；
- 递归版和显式 stack 版的关系。

---

### Pattern 9 — Heap / Top-K

**人话：** 不需要把所有东西完全排序，只维护当前最重要的 K 个。

Core Anchor：
- LC215 Kth Largest

书中第 5 章：
- 215 Kth Largest：Quickselect；
- 347 Top K Frequent：频次 + bucket 思想；

书中第 11.5 节：
- priority queue / heap。

我们的生存线：
- Python `heapq` min-heap；
- `O(n log k)`；
- Quickselect 作为后期加分，不先强求。

---

### Pattern 10 — Linked List State / 链表状态迁移

**人话：** 链表不能像数组一样直接按下标跳过去，所以关键是保存“当前、前一个、下一个节点”。

Core Anchor：
- LC206 Reverse Linked List

书中第 13 章：
- 206 Reverse Linked List；
- dummy node；
- 快慢指针；
- 234 Palindrome Linked List；
- 19 Remove Nth Node From End（练习）。

Python 教学：
- `ListNode`；
- `prev / cur / nxt`；
- 不讲 C++ 内存管理。

---

## P1 — 面试常见，但在 P0 后学

### Pattern 11 — Basic DP / 动态规划

**人话：** 把已经算过的小问题答案存起来，再用它们拼出更大的答案。

Core Anchor：
- LC221 Maximal Square

书中第 7 章代表：
- 70 Climbing Stairs；
- 198 House Robber；
- 64 Minimum Path Sum；
- 221 Maximal Square。

教学顺序：
1. `dp[i]` 到底表示什么；
2. 当前答案依赖哪些旧答案；
3. 初始值；
4. 最后返回哪个状态。

暂时不系统刷背包/编辑距离/复杂股票 DP。

---

### Pattern 12 — Tree Traversal / 树遍历

**人话：** 从根节点开始，用 DFS 或 BFS 系统访问每个节点。

书中第 14 章：
- 树递归；
- 层次遍历；
- 前中后序；
- BST。

我们的生存线：
- 知道节点结构；
- BFS 层序；
- DFS 递归；
- 不把高级 BST / Trie 当 P0。

---

### Pattern 13 — Greedy / 贪心

**人话：** 每一步都做一个能被证明“不会害到最终答案”的局部最优选择。

书中第 2 章代表：
- 455 Assign Cookies；
- 435 Non-overlapping Intervals。

不要求先背“贪心模板”；重点是能解释：

> 为什么这个局部选择不会把全局最优解弄丢？

---

## P2 — 有余力再学

- Backtracking：排列/组合/Word Search；
- Quickselect 深入；
- Monotonic Stack；
- Prefix Sum；
- Union-Find；
- Topological Sort；
- 基础 Graph。

这些来自书中第 6、11、15、16 章，但不是当前两个岗位的一周 P0。

---

## P3 — 当前明确跳过

除非真实面试反馈出现，否则不系统投入：

- 复杂背包；
- Edit Distance / regex DP；
- 分治专题；
- 数论；
- 位运算技巧大全；
- MST / Dijkstra / Bellman-Ford；
- 竞赛级 Hard。

---

# 4. Anchor / Transfer / Retest 三种题的区别

## Anchor

第一次学习模式时使用。

目标：
- 允许 Teaching Mode；
- 允许拆解；
- 允许从 brute force 出发；
- 最终能理解 pattern。

## Transfer Variant

Anchor 完成后，立即或稍后换题面。

目标：
- 不告诉算法标签；
- 题目表面与 Anchor 不同；
- 底层模式相同；
- 验证是不是只背了代码。

首次 Transfer 可以比真实面试稍简单。

## Delayed Retest

隔 ≥3 个其他训练单元或下一 session。

要求：
- 无 Hint 2/3；
- 不先透露 pattern；
- ≥8 才能把模式标为 MASTERED。

---

# 5. 如何使用书中的 Hard

Hard 不等于必须会写。

例如书中滑动窗口使用 76 Minimum Window Substring 讲机制；当前阶段可以：

1. 用小输入手推窗口；
2. 理解为什么左右指针总共只向右走；
3. 不要求第一次就闭卷完整实现。

只有当前 Pattern 已稳定，才把 Hard 用作 stretch。

---

# 6. Track A / Track B 的使用差异

## Track A — A04613A

算法模式的目标是：

> **Coding 不成为否决项，并能把 Python 用到 evaluator / data pipeline / RAG / Agent 工程问题中。**

优先：
- HashMap；
- Stack；
- Sliding Window；
- Sorting/Interval；
- BFS/DFS；
- Heap；
- Binary Search；
- 基础 Linked List。

每学一个模式，尽量再做一个 Track A 业务改写：
- dedup；
- aggregation；
- top-k error cases；
- queue/batch processing；
- windowed logs；
- graph-like Agent trajectory。

## Track B — A180084A

算法模式目标更高：

> **常见 Easy 稳定、Medium 不空白、能解释 complexity/invariant 并迁移。**

同样使用 Pattern Map，但：
- Transfer 题更多；
- timed 要求更严格；
- LC215/LC33/LC200 等需要更稳定；
- 可逐渐加入 Quickselect、DP、Tree 等 P1 内容。

---

# 7. 教练使用规则

任何教练模型在教算法时：

1. 先查 `ONE_LINE_GLOSSARY.md`；
2. 再查本文件确认 pattern；
3. Foundation 未过，不直接塞完整算法模板；
4. 第一次教学只引入当前最必要的 1–2 个概念；
5. Core Anchor 完成后，必须安排一个同模式不同题面的 Transfer；
6. Transfer 题可以来自《LeetCode 101》对应章节/练习，但必须改写为 Python；
7. 不给候选人看 C++ 标准答案后再让其“翻译”；应该先自己解决，再把书作为解释/对照；
8. 书中题与 `LEETCODE_CORE_15.md` 冲突时：Core 15 决定当前面试优先级，本文件决定模式迁移方式。

---

# 8. 最终目标

不是：

> “我做过 30 道题。”

而是：

> “我看到陌生题时，可以先判断输入结构和约束，再把它归到一个熟悉的模式，并从 brute force 逐步构造出可运行的 Python 解法。”
