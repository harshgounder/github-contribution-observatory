# implementation backlog

This is a documentation-first backlog. No source implementation is authorized by this file.

## v2.0 contracts

- source registry;
- snapshot manifest;
- canonical entity schema;
- evidence claim schema;
- context manifest;
- memory item schema;
- case and session schema;
- task package schema;
- run manifest;
- score status;
- security policy schema;
- acceptance-test list.

## v2.1 data compiler

- bronze append-only storage;
- GH Archive adapter;
- ecosyste.ms adapter;
- GitHub REST adapter;
- GitHub GraphQL adapter;
- search partition ledger;
- exact event deduplication;
- calibrated near-copy clustering;
- temporal snapshots;
- dataset card generator;
- release manifest generator;
- canary repository checks.

## v2.2 evidence and context

- evidence graph;
- source authority;
- claim checklist;
- hybrid retrieval;
- reranking;
- context manifest;
- hierarchical summaries;
- context reset;
- perturbation tests;
- no-retrieval baseline;
- memory broker;
- origin and authority checks.

## v2.3 evaluation factory

- private post-cutoff task set;
- repository-held-out split;
- task auditors;
- hidden tests;
- contamination probes;
- image allowlist;
- no-egress runner;
- grader anomaly quarantine;
- independent regrade;
- human mergeability panel;
- cost metering;
- repeated-trial statistics.

## v2.4 case runtime

- initializer;
- planner;
- OpenCode worker;
- bounded execution;
- fresh evaluator;
- repair loop;
- handoff files;
- session event log;
- kill switch;
- artifact hashing.

## v2.5 shadow mode

- read-only ranking;
- internal draft branches;
- no public comments;
- no pull requests;
- no merges;
- comparison with human choices.

## v2.6 private pilot

- one approved repository;
- one issue class;
- one human owner;
- one PR at a time;
- explicit consent;
- full audit.

## v2.7 controlled operation

- portfolio constraints;
- external-cost limits;
- maintainer feedback;
- drift monitoring;
- incident response;
- periodic re-audits.

## implementation rules

- source code is written through OpenCode;
- DSH reviews architecture, diffs, tests, and policy;
- no direct public writes without approval;
- every phase has an exit gate;
- no phase can skip a failed gate;
- no old release is overwritten.
