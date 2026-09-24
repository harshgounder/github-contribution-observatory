# evidence graph specification

## purpose

represent claims, sources, derivations, conflicts, decisions, and actions as inspectable graph records.

## node types

```text
source
snapshot
repository
issue
issue_revision
comment
pull_request
commit
test
policy_file
external_page
model_output
human_decision
claim
patch
evaluation
outcome
memory_item
action
```

## edge types

```text
derived_from
observed_at
supports
contradicts
supersedes
duplicates
depends_on
blocked_by
authorized_by
generated_by
verified_by
invalidated_by
caused_decision_change
caused_no_change
```

## claim record

```yaml
claim_id:
subject:
predicate:
object:
claim_type:
source_ids:
event_time:
observed_at:
confidence:
status:
counterevidence:
limitations:
allowed_actions:
```

claim types:

```text
repository_fact
issue_fact
policy_fact
code_fact
runtime_fact
test_fact
model_inference
human_judgment
outcome_fact
```

## source authority

authority depends on the question:

- executable tests and runtime observations for observed behavior;
- specifications and API contracts for intended behavior;
- issue text and reproduction for reported symptoms;
- maintainer comments and merged PRs for project decisions;
- model output for hypotheses only.

a model inference never becomes a fact without evidence and verification.

## contradiction handling

when sources conflict:

1. store both records;
2. create a conflict group;
3. mark the claim `conflicted`;
4. fetch a higher-authority or fresher source;
5. run a targeted experiment if allowed;
6. preserve the original conflict;
7. record the adjudication.

silently averaging or deleting a conflict is forbidden.

## causal-use test

for every decision-critical claim:

```text
original evidence
remove evidence
replace evidence
contradict evidence
swap irrelevant evidence
reorder evidence
restore correct evidence
```

record the decision under every condition.

a claim with a correct citation but no response to evidence perturbation has post-hoc attribution, not demonstrated causal use.

## provenance output

every final report should include:

- claim IDs;
- source IDs;
- source excerpts;
- base commits;
- retrieval queries;
- rank and rerank scores;
- conflicts;
- verifier;
- confidence;
- causal perturbation result;
- allowed action.
