# agent matrix specification

## purpose

compare agents without confusing model ability, runtime design, task difficulty, and environment quality.

## comparison modes

### model-centric

hold the agent runtime constant and vary the model.

### runtime-centric

hold the model constant and vary the agent runtime.

### native-best

allow each runtime to use its intended configuration and budget, but label it as a separate treatment.

never mix native-best and common-budget results.

## common matrix

for each common run, freeze:

```yaml
task_set_id:
task_image_digest:
task_repo_commit:
model_provider:
model_id:
model_endpoint_snapshot:
system_prompt_hash:
tool_schema_hash:
context_compiler_version:
memory_version:
network_policy_id:
history_policy_id:
sandbox_image_digest:
dependency_lock_hash:
turn_budget:
dollar_budget:
wall_clock_budget:
retry_policy:
grader_revision:
patch_scope_policy:
random_seeds:
```

if any material field differs, the run is not a matched comparison.

## budget tracks

keep separate:

```text
one-shot pass@1
five-rollout best-of-5
native multi-sample runtime
```

record:

- internal sampling;
- candidate generation;
- repair attempts;
- tool calls;
- input and output tokens;
- cache usage;
- wall time;
- provider cost;
- no-patch rate.

a system that creates many internal candidates is not equivalent to a one-shot system.

## agent roles

possible systems include:

- OpenHands;
- Agentless;
- mini-SWE-agent;
- SWE-agent where still relevant;
- a local OpenCode-based runtime;
- future independent implementations.

historical artifacts remain historical until pinned and rerun.

## per-instance disposition

```yaml
instance_id:
raw_patch:
normalized_patch:
history_status:
image_status:
network_status:
grader_status:
test_status:
human_status:
cost_status:
leakage_disposition:
final_status:
```

## report

include:

- raw score;
- normalized score;
- patch validity;
- cost;
- time;
- failures;
- human review;
- external validity gap;
- task audit status;
- confidence intervals.

do not publish a single combined rank.
