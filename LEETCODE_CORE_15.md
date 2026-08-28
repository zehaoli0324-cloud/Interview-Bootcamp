# LEETCODE CORE 15 — V3 算法锚点

> 这 15 道不是起点，而是 `PYTHON_LEVEL0.md` 通过后的算法主线。
>
> 目标不是记题号，而是掌握可迁移的 invariant / data structure / debugging 能力。

## 进入条件

只有满足以下条件后才开始正式 Core 15：

- `FOUNDATION_PASSED`；或
- 至少已经能看懂输入输出、写 for/if/function，并能完成 Two Sum 暴力版。

如果还看不懂 `nums[i]`，回到 `PYTHON_LEVEL0.md`，不要硬刷本文件。

## V3 Mastery

- 第一次无 Hint 2/3 ≥8：`PASS_RETEST_DUE`；
- 隔至少 3 个其他训练单元或下一 session；
- 做不同题面、无提示变式再次 ≥8；
- 才是 `MASTERED`。

刚看完答案立即重写不算 mastery。

---

# Level 1 — Easy 生存线

## A1 — LC1 Two Sum

**模式：** HashMap / complement

最低要求：
- 先能写 O(n²)；
- 再理解 `need = target - x`；
- dict 保存 `value -> index`；
- 解释为什么先查再存。

目标：15–20 min。

## A2 — LC20 Valid Parentheses

**模式：** Stack

必须会：
- 栈里保存什么；
- 何时提前 False；
- 结束时为什么检查栈为空。

目标：15–20 min。

## A3 — LC165 Compare Version Numbers

**模式：** String parsing / two pointers or split

必须覆盖：
- 前导零；
- 段数不同；
- 缺失段视为 0。

目标：20 min。

## A4 — LC206 Reverse Linked List

**模式：** Linked List pointer invariant

必须解释：
- `prev / cur / next`；
- 为什么先保存 `next`；
- 空链表 / 单节点。

目标：20 min。

---

# Level 2 — 高频 Medium 主战场

## B1 — LC3 Longest Substring Without Repeating Characters

**模式：** Sliding Window + HashMap

必须会：
- window 表示什么；
- left 为什么只右移；
- last-seen index；
- O(n) 为什么成立。

## B2 — LC56 Merge Intervals

**模式：** Sorting + interval invariant

必须会：
- 为什么先排序；
- 当前 merged interval 的含义；
- overlap / non-overlap。

## B3 — LC102 Binary Tree Level Order Traversal

**模式：** BFS + Queue

必须会：
- 当前层大小；
- 空树；
- BFS 与 DFS 的差异。

## B4 — LC200 Number of Islands

**模式：** Grid DFS/BFS

V3 核心重点。

必须会：
- 四方向遍历；
- visited 何时标；
- DFS/BFS 至少一种能独立写，另一种能解释；
- 递归深度风险。

## B5 — LC215 Kth Largest Element

**模式：** Heap / Top-K

最低要求：
- min-heap size k；
- O(n log k)；
- 为什么不是必须全排序。

Quickselect 只作为加分，不作为生存线。

## B6 — LC33 Search in Rotated Sorted Array

**模式：** Binary Search invariant

必须会：
- 每轮至少一半有序；
- target 属于哪半；
- `<= / <` 边界。

## B7 — LC146 LRU Cache

**模式：** HashMap + Doubly Linked List

最低要求：
- 能画数据结构；
- `get / put / update / evict` 流程；
- 为什么平均 O(1)。

若现场手写链表仍困难，至少先用 `OrderedDict` 写可运行版，再解释手写结构。

---

# Level 3 — 强化 / Stretch

## C1 — LC221 Maximal Square

**模式：** Basic DP

只学这个 DP 状态：

> `dp[i][j]` = 以当前位置为右下角的最大正方形边长。

不扩成 DP 大全。

## C2 — LC32 Longest Valid Parentheses

**模式：** Stack / index sentinel

重点理解 base index，不背代码。

## C3 — sqrt(x)

**模式：** Binary Search on Answer + Newton

至少会二分；牛顿作为强化。

必须先澄清：整数平方根还是浮点近似。

## C4 — LC25 Reverse Nodes in K Group

**模式：** Linked List segment manipulation

唯一保留的 Hard stretch。

如果一周时间紧，可以做到“能解释分组 + reverse segment + 连接关系”而不是强求闭卷满分。

---

# 非核心变式池

只有为了验证迁移才抽，不形成第二份必刷题单：

- LC160 相交链表；
- LC121 买卖股票；
- LC153 旋转数组最小值；
- LC155 Min Stack；
- LC112 Path Sum；
- LC53 Maximum Subarray；
- 简化版 Top-K / BFS / interval 业务题。

---

# 一周 V3 通过线

不要求 15/15 MASTERED。

建议：

- Level 1：至少 3/4 PASS，LC1 必须会；
- Level 2：LC3 / LC200 / LC215 至少 PASS；
- LC33 / LC102 至少不空白；
- LC146 至少能解释完整结构；
- Level 3：至少理解 2 个，LC25 可放弃满熟练；
- 陌生常见题：能先给 brute force，再逐步优化，而不是完全沉默。

**Coding 的第一目标是消除一票否决风险，不是成为竞赛选手。**