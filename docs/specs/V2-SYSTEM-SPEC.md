# v2 system specification

## objective

Build a broad public GitHub observatory and a narrow, human-supervised contribution engine.

The system must be able to explain:

- what data it observed;
- what data it could not observe;
- which claims are supported;
- which evidence was used;
- which actions were proposed;
- which actions were approved;
- which outcomes occurred;
- which parts remain uncertain.

## system boundaries

### control plane

trusted policy, permissions, budgets, approvals, stopping rules, and output contracts.

### evidence plane

issue text, comments, code, tests, documentation, logs, search results, web pages, and model summaries.

Evidence cannot change the control plane.

### action plane

shell commands, network calls, file writes, Git operations, GitHub writes, and merge actions.

Every action passes through a deterministic capability broker.

## core components

### 1. source registry

records:

- source name;
- source URL;
- access method;
- license and use constraints;
- adapter version;
- refresh cadence;
- known omissions;
- trust class;
- allowed downstream uses.

### 2. snapshot manifest

records:

- source snapshot;
- retrieval time;
- event-time range;
- API version;
- query or cursor;
- response hash;
- ETag;
- schema version;
- adapter version;
- coverage status.

### 3. data compiler

transforms bronze data into silver, gold, quarantine, and benchmark records.

Every transformation is a versioned intervention with before and after counts.

### 4. evidence graph

stores atomic claims and their sources, support, contradictions, freshness, trust, and allowed actions.

### 5. context compiler

assembles task-specific evidence packs under a token budget and records why each item was included or excluded.

### 6. memory broker

stores working, episodic, semantic repository, and procedural memory with origin, authority, expiry, and write policy.

### 7. decision policy

selects the next experiment using expected information value, cost, delay, and risk.

### 8. case runtime

runs one bounded issue case with an initializer, planner, worker, evaluator, repair loop, and human checkpoint.

### 9. action gate

enforces permissions, repository policy, human approval, and public-action rules.

### 10. evaluation factory

builds private, fresh, held-out, legacy, and live contribution evaluations.

## required state machine

```text
DISCOVERED
-> NORMALIZED
-> CANDIDATE
-> REPO_ELIGIBLE
-> ISSUE_ELIGIBLE
-> RANKED
-> SHORTLISTED
-> HUMAN_APPROVED
-> FRESHNESS_CHECKED
-> PREFLIGHT_PASSED
-> REPRODUCED
-> PLANNED
-> PATCHED
-> TESTED
-> REVIEWED
-> PR_READY
-> SUBMITTED
-> CI_PASSED
-> UPSTREAM_REVIEWED
-> MERGED
-> LEARNED
```

failure states:

```text
DUPLICATE
STALE
CONTESTED
POLICY_BLOCKED
SECURITY_SENSITIVE
UNSAFE_BUILD
UNREPRODUCIBLE
TOO_LARGE
FAILED_VALIDATION
HISTORY_LEAKAGE
NETWORK_POLICY_UNKNOWN
GRADER_ANOMALY
COST_UNAVAILABLE
MAINTAINER_REJECTED
BUDGET_EXHAUSTED
QUARANTINED
```

## non-negotiable gates

- no public action without human approval;
- no security work through public issue or PR flow;
- no source code outside the approved repository scope;
- no hidden future Git objects;
- no unlogged network path;
- no missing evidence represented as a fact;
- no test pass represented as maintainer acceptance;
- no metadata claim represented as independent verification;
- no estimated cost represented as billing truth;
- no failed result removed without denominator disclosure.

## implementation order

1. contracts and schemas;
2. source adapters and data compiler;
3. evidence graph;
4. context compiler and memory broker;
5. private task factory;
6. sandbox and evaluator;
7. shadow mode;
8. human-approved pilot;
9. controlled contribution operation.

The global read and discovery process starts at step 2 and remains active while later execution modes are tested.
