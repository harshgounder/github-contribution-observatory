# github contribution observatory

A private, documentation-first research project for designing a global GitHub issue observatory and a cautious contribution workflow.

## status

research and architecture phase: complete

implementation phase: not started

current version: v2 specification draft

This repository currently contains research records, architecture decisions, source indexes, operating rules, and evaluation contracts. It does not contain the production data system or an autonomous pull-request bot.

## mission

Build a system that can:

- observe a broad public GitHub universe;
- preserve source and transformation lineage;
- find issues that may be suitable for contribution;
- estimate difficulty, uncertainty, repository receptivity, and expected maintainer burden;
- assemble compact, evidence-backed context for analysis;
- run isolated code experiments;
- evaluate patches independently from the builder;
- require human approval before public actions;
- learn from merged, rejected, stale, and abandoned work.

The project is designed around public data and explicit gaps. It does not claim access to private repositories or deleted content.

## core architecture

```text
public sources
  -> source registry
  -> candidate universe
  -> versioned data compiler
  -> evidence and provenance graph
  -> context compiler
  -> uncertainty-aware experiment policy
  -> isolated contribution case
  -> OpenCode source patch
  -> deterministic tests and scans
  -> fresh evaluator
  -> human action gate
  -> approved GitHub action
  -> outcome dataset
  -> next research release
```

The design separates:

- observation from action;
- source data from derived summaries;
- context from memory;
- model capability from agent runtime behavior;
- patch correctness from maintainer usefulness;
- benchmark claims from live contribution outcomes.

## important research conclusions

- GitHub is too large for an API-first crawl. Bulk sources and event archives must come first, with REST and GraphQL used for live reconciliation.
- A million-token context limit is capacity, not usable reasoning. Context must be compiled, measured, and perturbed.
- Retrieval can improve or harm a decision. The system needs a no-retrieval baseline, relevance checks, reformulation, and abstention.
- A citation does not prove causal use. Evidence must be removed, replaced, contradicted, and restored in controlled tests.
- Public benchmark scores are not current ground truth. Static, fresh, private, training, and construction artifacts require separate claim rules.
- Test passing is not the same as a useful contribution. Human mergeability, reviewer burden, and later maintenance matter.
- A clean Git checkout can still leak future data through tags, reflogs, unreachable objects, package caches, or Conda environments.
- Browser-disabled is not network-isolated when shell or API access remains enabled.
- The agent must never control permissions, grading, or public-action authority. Deterministic policy and capability controls sit outside the model.

## repository map

- `ABOUT.md`: mission, boundaries, audience, and design principles.
- `docs/research/EXECUTIVE-REPORT.md`: current situation and recommendation.
- `docs/research/RESEARCH-LOG.md`: chronological research record and methods.
- `docs/research/DECISIONS.md`: accepted decisions and rejected shortcuts.
- `docs/research/FAILURES-AND-LESSONS.md`: what did not work and what changed as a result.
- `docs/research/SOURCE-INDEX.md`: primary sources grouped by topic, with caveats.
- `docs/research/RESEARCH-MANIFEST.md`: research cutoff, tracks, methods, and limitations.
- `docs/research/OPEN-QUESTIONS.md`: decisions required before implementation.
- `docs/research/TRANSFER-CHECKLIST.md`: publication and privacy review gate.
- `docs/specs/V2-SYSTEM-SPEC.md`: complete v2 architecture.
- `docs/specs/DATA-COMPILER-SPEC.md`: bronze, silver, gold, quarantine, and release rules.
- `docs/specs/CONTEXT-COMPILER-SPEC.md`: retrieval, context budgets, memory, and perturbation tests.
- `docs/specs/EVIDENCE-GRAPH-SPEC.md`: atomic claims, provenance, contradictions, and causal evidence tests.
- `docs/specs/MEMORY-SPEC.md`: memory types, authority, expiry, and write gates.
- `docs/specs/AGENT-MATRIX.md`: controlled agent, model, budget, and environment comparisons.
- `docs/security/SECURITY-MODEL.md`: prompt injection, memory poisoning, network, sandbox, and action controls.
- `docs/evaluation/EVALUATION-SPEC.md`: private tasks, legacy tracks, grader integrity, and live contribution outcomes.
- `docs/operations/OPERATING-PROCEDURE.md`: daily, weekly, release, incident, and rollback procedures.
- `docs/specs/ACCEPTANCE-TESTS.md`: executable acceptance conditions for future implementation.
- `templates/`: task, issue, research, and evaluation record templates.
- `.github/`: issue and pull-request forms and repository metadata.

## current non-goals

This project does not currently:

- open public issues automatically;
- create pull requests automatically;
- merge pull requests automatically;
- accept legal terms or sign a DCO or CLA automatically;
- expose private repository data;
- use personal access tokens in prompts or logs;
- publish hidden chain-of-thought;
- claim that a score guarantees maintainer acceptance.

## planned first implementation

The first code phase should not be a global crawler or PR bot. It should be a small vertical slice:

1. create a source registry and immutable snapshot manifest;
2. normalize a bounded set of GitHub issue and repository records;
3. create atomic evidence records;
4. compile a task context pack;
5. create a private task package with hidden tests;
6. run a paired no-retrieval versus corrected-context experiment;
7. run a fresh evaluator and human review;
8. publish a reproducible report.

Only after the evaluation gates pass should the system be allowed to prepare a draft pull request for an approved repository.

## privacy and transparency

The repository stores research summaries, public source links, and project decisions. It must never store:

- access tokens;
- private API responses;
- personal contact data;
- raw vulnerability details;
- unpublished maintainer communications;
- private repository contents;
- hidden chain-of-thought.

The project can document concise rationale, evidence, uncertainty, rejected approaches, and reproducible decisions.

## contributing

Read `CONTRIBUTING.md` and `SECURITY.md` before proposing changes. Source code for the future implementation must be written through the OpenCode CLI. This documentation repository may be edited directly.

## ownership and visibility

Repository owner: `harshgounder`

Visibility: private until the owner chooses to publish it.

No software license has been selected yet. Do not assume permission to reuse code or documentation outside this repository.

## current recommendation

Keep the research repository private while the specification and acceptance tests are reviewed. The first public-facing release, if chosen later, should be a cleaned documentation release rather than a raw export of internal research notes.
