# executive research report

## current situation

The project began as a request to scan GitHub and the wider internet for issues that could be fixed and submitted as pull requests. The first plan established a global observatory, ranking model, sandbox, evaluator, and human approval gate.

The research phase then found several places where the first plan was too simple.

## what changed

### 1. data collection became a data compiler

The system now separates:

```text
bronze source evidence
silver canonical records
gold curated records
quarantine records
private benchmark records
```

Every release records source lineage, transformations, counts, exclusions, sampling, seeds, schema versions, and reproducibility details.

### 2. summaries became evidence graphs

A model summary is now a derived artifact. Decision-critical claims need stable evidence IDs, source locations, timestamps, trust tiers, contradictions, and allowed actions.

### 3. large prompts became context compilers

A large context window is not treated as a reasoning method. The system assembles bounded evidence packs, records a context manifest, tests position and distractor sensitivity, and allows a no-retrieval path.

### 4. static ranking became sequential decision-making

The system can choose a cheap uncertainty-reducing experiment before spending money on implementation. It records expected information value, cost, risk, and the decision to continue, stop, or abstain.

### 5. public benchmarks were reclassified

Public benchmark artifacts are not all equivalent. The research separates:

- legacy static benchmarks;
- fresh public task sets;
- private post-cutoff capability tasks;
- training or stress corpora;
- construction tools and proof-of-concept datasets;
- descriptive event or metadata sources;
- observational real-world PR datasets.

### 6. tests were separated from contribution value

A test pass is necessary but not enough. The system adds independent re-grading, human mergeability, reviewer burden, maintenance outcomes, and regression checks.

### 7. execution security became a measured property

No-egress network policy, clean Git history, full image filesystem audits, grader fail-closed behavior, trajectory scanning, and capability controls are now required evidence.

## what worked

- the global-observatory framing;
- separating public action from public observation;
- using GH Archive and third-party metadata as bulk sources;
- using REST and GraphQL for live reconciliation;
- treating search limits and incomplete results as first-class states;
- separating issue difficulty from maintainer receptivity;
- requiring human review before public actions;
- using isolated execution for untrusted repositories;
- researching benchmark contamination and task validity;
- using source-specific citations and dated evidence;
- recording unresolved disagreements rather than choosing convenient numbers.

## what did not work or was insufficient

- an API-first crawl at GitHub scale;
- a single static ranking score;
- a single large context prompt;
- trusting `good first issue` labels as ground truth;
- treating a citation as proof of causal use;
- treating GitHub Search totals as a complete universe;
- treating `checked: true` as full independent verification;
- treating public benchmark scores as current frontier capability;
- treating a test-passing patch as maintainer-ready work;
- treating browser-disabled agents as network-isolated;
- treating a clean Git checkout as a clean image;
- allowing a per-agent evaluator to define patch scope;
- reporting estimated cost as billing truth.

## current recommendation

Do not build a public auto-PR system first.

Build a private, documentation-first implementation with these gates:

1. source registry and immutable data release;
2. issue and repository normalization;
3. atomic evidence records;
4. context compiler with perturbation tests;
5. private post-cutoff task suite;
6. image and network allowlists;
7. sandboxed OpenCode patch runner;
8. independent grader and human review;
9. shadow mode;
10. one opt-in repository pilot.

## open decisions

The owner still needs to choose:

- target languages and ecosystems;
- whether the first task set is triage-only or triage plus repair;
- time and compute budget;
- model endpoints to freeze for the first matrix;
- image build and storage provider;
- whether to use a GitHub App or a separate read-only token during research;
- whether a public release will ever be created;
- software and documentation license.

## current status

```text
research: complete
specification: ready to draft
implementation: not started
public actions: disabled
private pilot: not started
```
