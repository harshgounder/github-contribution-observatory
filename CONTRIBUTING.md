# contributing

## current phase

This repository is in research and specification phase. There is no production source implementation yet.

## documentation changes

Documentation changes are welcome. Keep claims tied to:

- a primary source;
- a dated local observation;
- an explicit experiment;
- a clearly marked assumption;
- an unresolved question.

Do not present search snippets, secondary summaries, or unconfirmed audit reports as settled facts.

## future source changes

When implementation begins:

- source code must be written through the OpenCode CLI;
- DSH acts as architect, reviewer, test orchestrator, and policy checker;
- do not commit secrets, tokens, private API responses, or personal data;
- do not include copied issue bodies, vulnerability details, or private maintainer communications;
- add tests before claiming a behavior change;
- pin external dependencies;
- record environment and runtime assumptions.

## commits

Use imperative commit subjects and short bodies that explain why.

Examples:

```text
document the evidence graph contract
add image audit acceptance cases
record benchmark status corrections
```

Do not use emoji in commit messages.

## pull requests

A pull request must include:

- scope;
- source or issue reference;
- tests or validation performed;
- known limitations;
- security and privacy impact;
- documentation changes;
- rollback plan.

No public contribution automation is enabled by this repository.

## research claims

Use these labels:

```text
observed
measured
reported
estimated
self-attested
independently-regraded
unconfirmed
unresolved
```

Do not collapse them into one claim.

## review

Reviewers should check:

- factual accuracy;
- source quality;
- reproducibility;
- security;
- privacy;
- denominator and score status;
- failure and exclusion disclosure;
- compatibility with the v2 contracts.
