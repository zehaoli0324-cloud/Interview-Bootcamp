# LEETCODE CORE 15 — V5 Anchor Set

> 这 15 道不是完整题库，而是 `PYTHON_LEVEL0.md` 通过后的**最小 Anchor 集**。
>
> 真正的算法课程由 `LEETCODE101_PYTHON_PATTERN_MAP.md` 组织：**Pattern → Anchor → Transfer → Delayed Retest**。

## 进入条件

只有满足以下条件后才开始正式 Core 15：

- `FOUNDATION_PASSED`；或
- 至少能看懂输入输出、写 for/if/function，并能完成 Two Sum 暴力版。

如果还看不懂 `nums[i]`，回到 `PYTHON_LEVEL0.md`，不要硬刷本文件。

---

# V5 Mastery

任何一道 Anchor 做对都不能直接记 MASTERED。

一个算法模式 MASTERED 必须：

1. Anchor 正式作答 ≥8；
2. 完成一个同模式不同题面的 Transfer；
3. 隔至少 3 个其他训练单元或下一 session；
4. 再做一个不透露 pattern 的 Delayed Retest；
5. Retest ≥8 且无 Hint 2/3。

刚看完答案立即重写不算 mastery。

---

# Level 1 — Easy 生存线 Anchor

## A1 — LC1 Two Sum

**Pattern：** HashMap / complement

最低要求：
- 先能写 O(n²)；
- 再理解 `need = target - x`；
- dict 保存 `value -> index`；
- 解释为什么先查再存。

V5 Transfer：
- 换成“以前见过某个 complement 吗？”的不同题面；
- 或 frequency / last-seen 类哈希变式。

目标：15–20 min。

## A2 — LC20 Valid Parentheses

**Pattern：** Stack

必须会：
- 栈里保存什么；
- 何时提前 False；
- 结束时为什么检查栈为空。

V5 Transfer：
- Min Stack / undo-like 简化题；
- 或同模式括号/嵌套结构题。

目标：15–20 min。

## A3 — LC165 Compare Version Numbers

**Pattern：** String parsing / two pointers or split

必须覆盖：
- 前导零；
- 段数不同；
- 缺失段视为 0。

V5 Transfer：
- 版本号/路径/分段字符串比较的不同表面。

目标：20 min。

## A4 — LC206 Reverse Linked List

**Pattern：** Linked List state transition

必须解释：
- `prev / cur / next`；
- 为什么先保存 `next`；
- 空链表 / 单节点。

V5 Transfer：
- 回文链表的“翻转一半”思想；
- 删除倒数节点的快慢指针只作为后续迁移，不强求第一轮。

目标：20 min。

---

# Level 2 — 高频 Medium Anchor

## B1 — LC3 Longest Substring Without Repeating Characters

**Pattern：** Sliding Window + HashMap

必须会：
- window 表示什么；
- left 为什么只右移；
- last-seen index；
- O(n) 为什么成立。

V5 Transfer：
- 固定/可变窗口；
- 至多 K 种元素的简化版；
- 《LeetCode 101》第 3 章滑动窗口相关题作为迁移池。

## B2 — LC56 Merge Intervals

**Pattern：** Sorting + interval invariant

必须会：
- 为什么先排序；
- 当前 merged interval 的含义；
- overlap / non-overlap。

V5 Transfer：
- Non-overlapping Intervals / scheduling 类题。

## B3 — LC102 Binary Tree Level Order Traversal

**Pattern：** BFS + Queue

必须会：
- 当前层大小；
- 空树；
- BFS 与 DFS 的差异。

V5 Transfer：
- 网格逐层扩散或最短步数简化题。

## B4 — LC200 Number of Islands

**Pattern：** Grid DFS/BFS

必须会：
- 四方向遍历；
- visited 何时标；
- DFS/BFS 至少一种能独立写，另一种能解释；
- 递归深度风险。

V5 Transfer：
- Max Area of Island；
- connected components 类题；
- 书中第 6 章 DFS/BFS 变式。

## B5 — LC215 Kth Largest Element

**Pattern：** Heap / Top-K

最低要求：
- min-heap size k；
- O(n log k)；
- 为什么不是必须全排序。

V5 Transfer：
- Top K Frequent；
- Track A 可改写成 top-k error categories；
- Quickselect 只作为加分。

## B6 — LC33 Search in Rotated Sorted Array

**Pattern：** Binary Search invariant

必须会：
- 每轮至少一半有序；
- target 属于哪半；
- `<= / <` 边界。

V5 Transfer：
- sqrt(x)；
- first/last position；
- rotated array variant。

## B7 — LC146 LRU Cache

**Pattern：** HashMap + Doubly Linked List

最低要求：
- 能画数据结构；
- `get / put / update / evict` 流程；
- 为什么平均 O(1)。

若现场手写链表仍困难，先用 `OrderedDict` 写可运行版，再解释手写结构。

V5 Transfer：
- cache / recent-items 的简化业务题。

---

# Level 3 — 强化 / Stretch Anchor

## C1 — LC221 Maximal Square

**Pattern：** Basic DP

只学：

> `dp[i][j]` = 以当前位置为右下角的最大正方形边长。

V5 Transfer：
- Climbing Stairs / House Robber / Minimum Path Sum 中任选一个基础 DP，用来验证是否会定义状态。

不扩成 DP 大全。

## C2 — LC32 Longest Valid Parentheses

**Pattern：** Stack / index sentinel

重点理解 base index，不背代码。

## C3 — sqrt(x)

**Pattern：** Binary Search on Answer + Newton

至少会二分；牛顿作为强化。

必须先澄清：整数平方根还是浮点近似。

## C4 — LC25 Reverse Nodes in K Group

**Pattern：** Linked List segment manipulation

唯一保留的 Hard stretch。

如果一周时间紧，可以做到“能解释分组 + reverse segment + 连接关系”，不强求闭卷满分。

---

# 非核心变式池

这些题主要用于 Transfer / Retest，不形成第二份必刷清单：

- LC160 相交链表；
- LC121 买卖股票；
- LC153 旋转数组最小值；
- LC155 Min Stack；
- LC112 Path Sum；
- LC53 Maximum Subarray；
- LC167 Two Sum II；
- LC88 Merge Sorted Array；
- LC435 Non-overlapping Intervals；
- LC695 Max Area of Island；
- LC347 Top K Frequent；
- 简化版 Top-K / BFS / interval / log-window 业务题。

更多变式从 `LEETCODE101_PYTHON_PATTERN_MAP.md` 对应章节抽取。

---

# 一周 V5 通过线

不要求 15/15 MASTERED。

建议：

- Foundation：通过；
- Level 1：至少 3/4 Anchor PASS，LC1 必须会；
- 至少 3 个 P0 pattern 完成 Transfer；
- Level 2：LC3 / LC200 / LC215 至少 PASS；
- LC33 / LC102 至少不空白；
- LC146 至少能解释完整结构；
- Level 3：至少理解 2 个，LC25 可放弃满熟练；
- 至少 2 个核心 pattern 完成 Delayed Retest ≥8；
- 陌生常见题：能先给 brute force，再识别模式并逐步优化，而不是完全沉默。

**目标不是“背 15 道”，而是建立 8–10 个能迁移的高频模式。**
