# context compiler specification

## purpose

produce the smallest task-specific evidence state that supports a correct decision without filling the model context window.

## context profiles

### triage

issue, comments, labels, linked issues and PRs, maintainer responses, repository policy, duplicate evidence, security signals, and routing evidence.

### investigation

issue, reproduction, error output, repository map, symbols, focused code, related history, and unresolved conflicts.

### repair

verified reproduction, affected symbols, complete candidate functions, tests, configuration, root-cause evidence, patch constraints, and rollback.

### evaluation

task statement, required behavior, hidden evaluator boundary, and evidence needed for grading.

## retrieval pipeline

```text
filter by repository, commit, language, dependency, visibility, trust
-> measure file, function, line, and test recall
-> rerank by support, authority, version match, and independence
-> select quote, AST, stack-frame, and test-span units
-> deduplicate copied origins while preserving conflicts
-> build claim checklist
-> classify support as correct, incorrect, ambiguous, or unknown
-> re-query or abstain when support is weak
-> assemble compact decisive evidence
-> test order sensitivity
-> generate
-> perturb evidence
```

## context manifest

```yaml
case_id:
context_version:
model:
tokenizer:
input_limit:
output_reserve:
safety_margin:
used_tokens:
source_ids:
retrieval_queries:
required_evidence:
conflicts:
excluded_items:
staleness:
compaction_events:
```

## token budget

reserve space for:

- trusted control contract;
- tool schemas;
- current evidence;
- model output;
- safety margin.

a starting profile is:

```text
15% issue and decision facts
50% primary evidence
12% plan, hypotheses, and conflicts
10% tests, diffs, and fresh observations
 8% typed memory
 5% reserve
```

calibrate this profile through paired experiments.

## adaptive retrieval

choose retrieval depth from uncertainty and task type.

simple triage can use one targeted pass.

ambiguous repair can use multi-hop symbol, test, and history retrieval.

security-sensitive work stops and changes channel.

failed retrieval can trigger query reformulation, a different index, or abstention.

never increase `k` blindly.

## context tests

- decisive evidence at beginning, middle, and end;
- related non-answering distractors;
- contradictory sources;
- stale source after commit change;
- forced compaction;
- context reset and resume;
- no-retrieval baseline;
- corrupted decisive evidence;
- evidence removal and restoration;
- issue text prompt injection;
- source comment injection;
- tool-output injection.

## causal evidence metrics

```text
decision_delta = actual_context_score - no_context_score
retrieval_ceiling = oracle_context_score - actual_context_score
evidence_harm = misleading_context_score - no_context_score
restoration_gain = restored_context_score - misleading_context_score
negative_transfer_rate = cases where evidence lowered the score
evidence_use_rate = decisions that changed correctly when decisive evidence changed
position_sensitivity = score variation under identical reordering
```
