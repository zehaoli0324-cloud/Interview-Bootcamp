# SESSION STATE — V3 跨对话恢复

> 每 5 个正式训练单元或每天结束时更新一次。

```yaml
session_state:
  version: V3
  date: ""
  units_completed: 0
  current_day: 1
  current_mode: FOUNDATION

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

  mllm:
    passed: []
    learning: []
    strongest_topics: []
    highest_risk_topics: []

  posttraining:
    passed: []
    learning: []
    strongest_topics: []
    highest_risk_topics: []

  medical_eval:
    passed: []
    refresh_needed: []

  primary_failure_counts:
    READING_INPUT: 0
    SYNTAX_API: 0
    INDEXING: 0
    CONTROL_FLOW: 0
    PATTERN_RECOGNITION: 0
    INVARIANT: 0
    IMPLEMENTATION: 0
    BOUNDARY: 0
    COMPLEXITY: 0
    DEBUGGING: 0
    CONCEPT: 0
    DATA_FLOW: 0
    TENSOR_SHAPE: 0
    TRAINING_OBJECTIVE: 0
    FAILURE_MODE: 0
    MEDICAL_TRANSFER: 0

  hints_used:
    hint_1: 0
    hint_2: 0
    hint_3: 0
    full_answer: 0

  last_units: []
  biggest_interview_risk: ""
  next_priority: ""
  next_action: ""
```

## 恢复规则

- `foundation.status = PASSED` 后，不因为单个语法 bug 重新退回完整 Level 0；
- Coding PASS 仍需 delayed retest；
- MLLM / Post-training 的“刚学会复述”不能直接标 mastered；
- 如果某一 track 已明显强，不要为了平均题量继续刷；
- `biggest_interview_risk` 优先决定下一步。

## 新对话恢复 Prompt

```text
这是我上一轮 Medical MLLM Algorithm Interview Bootcamp V3 的状态。
请先读取仓库中的 DEEPSEEK_TUTOR.md / START_TUTOR.md，再把下面 YAML 当作真实进度继续训练。
不要重头 placement，不要展示完整题单。优先修复 biggest_interview_risk。

<粘贴 YAML>
```
