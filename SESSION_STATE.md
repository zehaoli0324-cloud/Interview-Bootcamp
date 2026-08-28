# SESSION STATE — V5 Pattern-First + 双岗位跨会话恢复

> Shared Python/Coding 共享；Track A / B 专项分别保存。

```yaml
session_state:
  version: V5
  date: "2026-08-28"
  active_track: SHARED   # SHARED / A / B
  units_completed: 1
  current_mode: FOUNDATION_TO_PATTERN

  shared:
    foundation:
      status: LEARNING
      independent_skills:
        - list_index
        - variable_assignment
        - for_range
        - if_comparison
        - function_return
        - dict
        - len_range
        - tiny_trace
      remaining_gaps:
        - set
        - formal_foundation_exit_gate
        - independent_code_rule_generation

    coding:
      current_pattern: HASHMAP
      current_stage: ANCHOR_LEARNING
      anchor_passed: []
      transfer_passed: []
      mastered: []
      retest_due: []
      learning:
        - HashMap_TwoSum
      strongest_patterns: []
      highest_risk_patterns:
        - code_rule_generation

      pattern_evidence:
        HashMap_TwoSum:
          understands:
            - value_to_index
            - complement_need
            - check_before_store
            - same_value_different_index
            - function_parameter_vs_loop_value
            - seen_contains_only_previous_values
          still_needed:
            - mini_independent_python_gate
            - clean_anchor_retry
            - complexity_explanation
            - transfer_variant
            - delayed_retest

  track_a:
    evaluator_data_coding:
      passed: []
      learning: []
    eval_benchmark:
      passed: []
      learning: []
    data_system:
      passed: []
      learning: []
    rag_agent_medical:
      passed: []
      learning: []
    biggest_risk: ""
    mock_verdict: NOT_RUN

  track_b:
    vit_mllm:
      passed: []
      learning: []
    post_training:
      passed: []
      learning: []
    medical_research:
      passed: []
      learning: []
    biggest_risk: ""
    mock_verdict: NOT_RUN

  primary_failure_counts:
    READING_COMPREHENSION: 0
    SYNTAX_API: 0
    INDEXING: 0
    CONTROL_FLOW: 0
    PATTERN_RECOGNITION: 0
    INVARIANT: 0
    IMPLEMENTATION: 0
    BOUNDARY: 0
    COMPLEXITY: 0
    DEBUGGING: 0
    EVAL_REASONING: 0
    DATA_ENGINEERING: 0
    MLLM_CONCEPT: 0
    TENSOR_SHAPE: 0
    TRAINING_CONCEPT: 0

  hints_used:
    hint_1: 0
    hint_2: 0
    hint_3: 0
    full_answer: 0

  last_units:
    - date: "2026-08-28"
      type: teaching
      skill: HashMap_TwoSum
      result: "从几乎看不懂题目，推进到能理解 list/index/for/if/function/dict，并在指导后写出完整 Two Sum HashMap 主体"
      strengths:
        - tiny_trace
        - complement_logic
        - value_to_index_mapping
        - check_before_store
      observed_gaps:
        - concrete_value_vs_code_rule
        - state_timing_before_vs_after_store
        - independent_function_call_and_clean_rewrite
      mastery_evidence: false

  tomorrow_start:
    step_1: "2-3 个超短独立 Python gate，确认不是只会跟着提示"
    step_2: "Two Sum clean retry：只给题意和函数头，尽量独立写"
    step_3: "若 Anchor ≥8，进入第一个 HashMap Transfer；否则只修一个根因再 retry"
    step_4: "补时间/空间复杂度的一句话理解"
    stop_condition: "完成 clean anchor 或明确定位一个剩余根因即可，不追求一次学多个 pattern"

  next_priority: "mini independent Python gate → clean HashMap anchor retry"
  next_action: "CLEAN_GATE_THEN_ANCHOR"
```

---

# V5 恢复规则

- `active_track = SHARED` 表示只练两个岗位共用的 Python/算法；
- Foundation/Coding 状态跨 A/B 共享；
- Track A 专项不能自动写入 Track B passed；
- Track B 专项不能自动写入 Track A passed；
- `foundation.status = PASSED` 后，不因单个语法 bug 退回完整 Level 0；
- 一个 Anchor 做对不能直接 MASTERED；
- Shared Coding Pattern 必须按：`Anchor → Transfer → spacing → Delayed Retest`；
- 切换 Track 时保留 shared 状态，只切换专项题库；
- 已在 Teaching Mode 大量提示下完成的题，不算独立 mastery evidence。

---

# 新对话恢复

```text
读取 Interview-Bootcamp 中的 TUTOR V5、LEETCODE101_PYTHON_PATTERN_MAP.md、PROGRESS.md 和 SESSION_STATE.md。
下面是上一轮 session_state，请从 tomorrow_start 开始，不要重新从 list/index 开始，也不要把 guided completion 当成 MASTERED。
如果 active_track=SHARED，就继续共享 Python/算法；如果是 A/B，再进入对应专项。

<粘贴 YAML>
```
