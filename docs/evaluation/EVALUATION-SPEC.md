# evaluation specification

## objective

measure whether a system can safely and usefully turn a public issue into a maintainable contribution under a known budget.

separate:

```text
model capability
agent runtime behavior
task validity
execution environment
contribution workflow
maintainer value
```

## evaluation tracks

### legacy track

SWE-bench Verified and older artifacts.

purpose: historical comparison only.

### fresh public track

SWE-bench-Live and later public task cohorts.

purpose: public external-validity evidence.

### private capability track

private post-cutoff tasks, private tests, held-out repositories, and repeated human audits.

purpose: primary current capability estimate.

### live contribution track

opt-in repositories with real issue, PR, review, merge, and maintenance outcomes.

purpose: downstream contribution value.

## task package

```yaml
task_id:
issue_snapshot_id:
repository_id:
base_commit:
base_timestamp:
issue_cutoff:
hidden_test_patch:
gold_patch:
environment_image_digest:
dependency_lock_hash:
task_repo_commit:
human_rubric:
network_policy_id:
history_policy_id:
grader_commit:
contamination_class:
```

## task audit

use at least two independent reviewers.

audit:

- issue clarity;
- expected behavior;
- observed behavior;
- reproduction;
- test fairness;
- hidden assumptions;
- environment setup;
- solution leakage;
- solvability.

reviewers record structured verdicts and reasons.

unresolved conflicts block the task from the primary set.

## contamination controls

use:

- post-cutoff tasks;
- repository-held-out splits;
- private issue and solution text;
- hidden tests;
- canary metadata;
- gold-recall probes;
- issue-ID probes;
- delayed public release;
- exact artifact hashes.

## repeated trials

use multiple seeds and at least three trials for stochastic systems.

report:

- mean;
- median;
- standard deviation;
- confidence intervals;
- pass@1;
- pass@k separately;
- per-task flip rate;
- infrastructure failures;
- no-patch rate.

## grader gate

restore protected test and build files.

fail closed on:

- forged pass markers;
- empty runs;
- skipped or xfailed required tests;
- truncated test IDs;
- missing executed-test counts;
- infrastructure errors;
- parser disagreement;
- result-cache collisions;
- evaluator modification.

run two independent regrades from immutable logs.

audit a human sample.

## metrics

### retrieval

- file recall;
- function recall;
- line recall;
- test recall;
- candidate-pool recall;
- Precision@K;
- MRR;
- nDCG;
- source diversity;
- version match.

### evidence pack

- claim recall;
- context precision;
- locator validity;
- stale-source rate;
- conflict detection;
- citation support;
- citation completeness;
- causal evidence-use rate;
- context size;
- latency;
- cost per useful claim.

### triage decision

- accuracy;
- macro-F1;
- cost-weighted confusion;
- duplicate precision and recall;
- routing accuracy;
- calibration;
- Brier score;
- selective accuracy;
- abstention coverage;
- false escalation;
- negative transfer.

### repair

- patch applies;
- reproduction;
- fail-to-pass;
- pass-to-pass;
- full regression;
- revert;
- human correctness;
- repository fit;
- minimality;
- alternate-patch acceptance;
- mergeability;
- reviewer minutes;
- 30-day and 90-day maintenance.

### safety

- injection success;
- poisoned retrieval;
- forbidden tool calls;
- privilege violations;
- exfiltration;
- network escape;
- future-history access;
- unsafe patch or ticket write;
- benign utility under attack.

## reporting

every report includes:

```yaml
model:
agent_runtime:
task_track:
task_cohort:
task_count:
denominator:
budget:
environment_digest:
history_status:
image_status:
network_status:
grader_revision:
raw_results:
normalized_results:
human_results:
cost_status:
leakage_status:
reconciliation_status:
strict_v2_status:
```

## statistical rules

- paired per-task comparisons;
- repository-clustered bootstrap intervals;
- Wilson intervals for proportions;
- McNemar tests for paired binary outcomes;
- predeclared primary metrics;
- subgroup results;
- no post-hoc metric selection;
- no best-run-only reporting.
