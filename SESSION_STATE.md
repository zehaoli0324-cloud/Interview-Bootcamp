# SESSION STATE — V4 双岗位跨会话恢复

> Shared Coding 共享；Track A / B 专项分别保存。

```yaml
session_state:
  version: V4
  date: ""
  active_track: A   # A or B
  units_completed: 0
  current_mode: FOUNDATION

  shared:
    foundation:
      status: NOT_PASSED
      independent_skills: []
      remaining_gaps: []
    coding:
      mastered: []
      pass_retest_due: []
      borderline: []
      learning: []
      strongest_patterns: []
      highest_risk_patterns: []

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

  last_units: []
  next_priority: ""
  next_action: ""
```

## 恢复规则

- Foundation/Coding 状态跨 A/B 共享；
- Track A 专项不能自动写入 Track B passed；
- Track B 专项不能自动写入 Track A passed；
- `foundation.status = PASSED` 后，不因单个语法 bug 退回完整 Level 0；
- Shared Coding PASS 仍需 delayed retest；
- 每次开始先读 `active_track`；
- 切换 Track 时保留 shared 状态，只切换专项题库。

## 新对话恢复

```text
读取 Interview-Bootcamp 中的 TUTOR V4 和 PROGRESS。
下面是上一轮 session_state，请按 active_track 继续；不要重新 placement，也不要混合两个岗位专项。

<粘贴 YAML>
```
