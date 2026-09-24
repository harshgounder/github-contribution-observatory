# research log

This log records the research path, methods, decisions, and limitations. It is a transparent work record, not private hidden reasoning.

## research phases

### phase 1: scope and scale

Questions:

- How large is the public GitHub universe?
- Which sources can be queried at scale?
- What can and cannot be observed?
- How should “all GitHub” be defined?

Findings:

- GitHub reports hundreds of millions of total and public repositories.
- API-only enumeration is too slow at that scale.
- GH Archive, bulk metadata services, and event archives must precede targeted API reads.
- Private, deleted, restricted, and unindexed data require explicit gap states.

### phase 2: source and dataset methodology

Sources reviewed included:

- GH Archive;
- ecosyste.ms;
- GitHub REST and GraphQL documentation;
- FineWeb;
- Dolma;
- DataComp;
- Meta Llama 3;
- Datasheets for Datasets;
- Data Provenance Initiative;
- HELM;
- SWE-bench artifacts;
- SWE-rebench;
- SWE-smith;
- GitBug-Actions.

Transferred methods:

- candidate pool before selected set;
- fixed candidate pool during ablations;
- source-specific filtering;
- exact and near-duplicate detection;
- data cards and lineage;
- temporal and repository-held-out splits;
- hidden tests and delayed releases;
- explicit contamination status.

### phase 3: context and memory

Sources reviewed included:

- Lost in the Middle;
- RULER;
- HELMET;
- NoLiMa;
- LongBench;
- LongBench v2;
- LongMINT;
- BABILong;
- NoCha;
- ReAct;
- Toolformer;
- API-Bank;
- Anthropic context-engineering and long-running-agent guidance.

Transferred methods:

- context is a compiled, versioned evidence state;
- external session state survives context resets;
- context budgets reserve output and tool space;
- retrieval can harm decisions;
- retrieval depth is conditional;
- memory needs authority, origin, expiry, and write policy;
- position and distractor tests are required;
- context citation does not prove causal use.

### phase 4: evaluation and benchmarks

Sources reviewed included:

- SWE-bench Verified and Pro;
- SWE-bench-Live;
- SWE-rebench;
- RE-Bench;
- OpenHands benchmarks;
- Agentless;
- mini-SWE-agent;
- SWE-agent;
- Aider;
- AIDev;
- OpenAI benchmark audits;
- METR;
- OSWorld.

Transferred methods:

- keep legacy, fresh public, private, and live tracks separate;
- report model, shell, task cohort, budget, denominator, and score type together;
- use repeated trials and confidence intervals;
- report algorithmic correctness separately from human mergeability;
- audit task validity, tests, environment, leakage, and cost;
- treat a metadata claim differently from an independently auditable artifact.

### phase 5: security and execution

Sources reviewed included:

- indirect prompt-injection research;
- BIPIA;
- PoisonedRAG;
- Phantom;
- AgentDojo;
- Spotlighting;
- CaMeL;
- GitHub Actions security guidance;
- SWE-bench history-leakage reports;
- image and grader audit reports.

Transferred controls:

- evidence plane and control plane separation;
- origin-bound memory;
- deterministic capability broker;
- no-egress network policy;
- full image filesystem scans;
- clean Git history checks;
- trajectory scanning;
- grader fail-closed behavior;
- shared patch-scope policy;
- raw and normalized patch reporting.

### phase 6: synthesis

The final architecture separates:

```text
observation
data compilation
evidence assembly
context assembly
decision policy
execution
evaluation
human action
outcome learning
```

The first implementation should test these boundaries on private and fresh tasks before any public contribution workflow is enabled.

## research method

The work used three passes:

1. broad source discovery;
2. independent technical challenge and benchmark audits;
3. synthesis into contracts, gates, and acceptance tests.

The research also used paired comparisons where possible:

- no retrieval versus retrieved context;
- actual evidence versus oracle evidence;
- original context versus perturbed context;
- raw patch versus normalized patch;
- self-reported cost versus independent metering;
- historical benchmark versus fresh task set.

## known limitations

- proprietary lab data recipes are not fully public;
- some benchmark studies are observational;
- public benchmark data can be exposed in training;
- some audit reports are unconfirmed user reports;
- no local implementation has yet validated the proposed metrics;
- no private task suite exists yet;
- no clean image allowlist exists yet;
- no human mergeability panel exists yet.

## current conclusion

The research phase is complete enough to begin a formal specification and a controlled bake-off. It is not complete enough to enable public automated submissions.
