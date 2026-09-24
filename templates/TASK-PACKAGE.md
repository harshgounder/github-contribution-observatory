# task package

## identity

- task_id:
- issue_snapshot_id:
- repository:
- base_commit:
- base_timestamp:
- prediction_cutoff:

## visibility

- [ ] public task metadata is approved
- [ ] issue body is recorded
- [ ] hidden tests are stored separately
- [ ] gold patch is stored separately
- [ ] future history is absent
- [ ] image filesystem is scanned
- [ ] network policy is recorded

## environment

- image_digest:
- dependency_lock_hash:
- operating_system:
- architecture:
- test_command:
- test_timeout:
- local_service_image:

## audit

- reviewer_1:
- reviewer_2:
- adjudication:
- verdict: valid | broken | underspecified | unsolvable | leaked

## execution

- model:
- agent_runtime:
- prompt_hash:
- tool_schema_hash:
- network_policy_id:
- history_policy_id:
- turn_budget:
- dollar_budget:
- seed:

## results

- raw_log_uri:
- trajectory_uri:
- result_array_uri:
- grader_commit:
- independent_regrade:
- human_review:
- cost_status:
- leakage_disposition:
- final_status:
