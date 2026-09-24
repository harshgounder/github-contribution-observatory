# decision ledger

## d001: observe broadly, act narrowly

Decision: keep discovery broad across public GitHub and supporting public sources. Keep public GitHub actions limited to approved repositories and reviewed cases.

Reason: the public universe is too large for API-first enumeration, while unconstrained public action creates policy, security, quality, and reputation risk.

Status: accepted.

## d002: separate the observatory from the contribution engine

Decision: build independent data, evidence, context, execution, evaluation, and action components.

Reason: a single agent loop makes it impossible to audit whether a failure came from data, retrieval, reasoning, tools, environment, grading, or policy.

Status: accepted.

## d003: use bulk and event sources before live API reads

Decision: use GH Archive, bulk repository and issue metadata, and cached snapshots as the broad seed. Use REST and GraphQL for reconciliation and selected objects.

Reason: API limits make one-request-per-repository enumeration impractical at current scale.

Status: accepted.

## d004: preserve candidate pools and selected sets separately

Decision: retain the full observable candidate universe even when expensive analysis selects a smaller set.

Reason: a shortlist is an action policy, not a complete census.

Status: accepted.

## d005: treat every filter as a versioned intervention

Decision: record filter configuration, input count, output count, quarantined count, effects, and confidence.

Reason: a final count without transformation lineage cannot be reproduced or challenged.

Status: accepted.

## d006: use claim-level evidence

Decision: store one atomic claim or code fact per evidence record, with source location, timestamp, hash, trust, relation, and conflict state.

Reason: document-level summaries and plausible citations do not establish causal use or truth.

Status: accepted.

## d007: compile context instead of filling a window

Decision: retrieve exact evidence spans, use hybrid search, protect decisive facts, test position and distractors, and allow a no-retrieval branch.

Reason: long-context benchmarks show that advertised capacity does not guarantee useful reasoning, and more context can reduce solve rate.

Status: accepted.

## d008: make memory authority-bound

Decision: separate raw evidence, derived summaries, repository facts, working state, and user-approved memory. Require origin, scope, expiry, and write authority.

Reason: persistent memory is a delayed attack and stale-state surface.

Status: accepted.

## d009: use expected information value for next actions

Decision: choose the next experiment based on expected uncertainty reduction, avoided rework, cost, delay, and risk.

Reason: a static rank cannot tell the system whether to search, clone, build, test, ask, or stop.

Status: accepted.

## d010: separate public benchmark tracks

Decision: use legacy static benchmarks for continuity, fresh public tasks for external validity, private post-cutoff tasks for current capability, and live repositories for contribution value.

Reason: no single public artifact is current ground truth.

Status: accepted.

## d011: require fresh evaluators and human review

Decision: use deterministic checks, an evaluator with a clean context and no write tools, and human review for mergeability.

Reason: builders can overstate progress and passing tests does not guarantee a useful patch.

Status: accepted.

## d012: require no-egress and clean-environment controls

Decision: block external network by default, log attempted and successful calls, pin image digests, scrub Git history, scan image filesystems, and quarantine anomalies.

Reason: shell access, local Git objects, caches, and future test artifacts can leak solutions even when browser access is disabled.

Status: accepted.

## d013: use one patch-scope policy

Decision: normalize raw patches with one documented evaluator policy and report raw and normalized results.

Reason: different agents and evaluators otherwise receive incomparable treatment of setup and configuration files.

Status: accepted.

## d014: classify source artifacts

Decision: separate evaluation benchmarks, training or stress corpora, construction tools, descriptive source datasets, and observational outcome datasets.

Reason: an artifact can be useful without supporting a model-score claim.

Status: accepted.

## d015: fail closed on audit ambiguity

Decision: missing logs, missing image digest, unknown history status, unknown network policy, parser disagreement, or score conflict must produce `unknown`, `flagged`, or `quarantined` status.

Reason: a confident score is less useful than an explicit unresolved state.

Status: accepted.

## d016: do not publish hidden chain-of-thought

Decision: save concise rationale, evidence, uncertainty, rejected approaches, and reproducible decisions. Do not save private hidden reasoning.

Reason: transparent research records are useful and safer than exposing private internal reasoning or sensitive context.

Status: accepted.
