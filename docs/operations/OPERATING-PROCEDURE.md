# operating procedure

## repository stages

```text
research
-> specification
-> shadow
-> sandboxed pilot
-> human-approved pilot
-> controlled contribution operation
```

each stage has a separate permission profile.

## daily operations

- check source ingest lag;
- check failed adapters;
- check unresolved cursors;
- check source conflicts;
- check quarantine counts;
- check image and network policy status;
- review high-risk public-action proposals;
- review maintainer responses.

## weekly operations

- run stratified data-quality audit;
- review duplicate clusters;
- review bot and template classifications;
- review task validity sample;
- review rejected and abandoned cases;
- compare fresh and legacy task performance;
- review cost and latency distributions;
- check model and context drift.

## release operations

before promoting a data release:

1. run schema validation;
2. run canary checks;
3. run count reconciliation;
4. run contamination audit;
5. run temporal split audit;
6. update dataset card;
7. write release manifest;
8. run reproducibility replay;
9. record known gaps;
10. increment the release ID.

never rewrite a published release.

## incident response

for a security, leakage, grading, or data-integrity incident:

1. stop affected automation;
2. preserve raw logs and manifests;
3. identify affected instances;
4. classify the incident;
5. quarantine affected results;
6. repair the source or environment;
7. rebuild or rescan the image;
8. rerun the full affected campaign;
9. publish a postmortem;
10. increment the release.

a random subset rerun is not enough for a final claim.

## model or runtime change

a model, prompt, tool schema, context compiler, memory policy, image, grader, or network policy change creates a new experiment.

never compare the new result to an old result without recording the changed fields.

## pull-request procedure

1. verify repository opt-in;
2. read current contribution and security policy;
3. refresh issue state and linked work;
4. confirm no duplicate PR;
5. clone pinned base commit;
6. reproduce the issue;
7. create a focused branch;
8. write source through OpenCode;
9. run documented tests and scans;
10. normalize patch scope;
11. obtain independent evaluation;
12. prepare PR body;
13. obtain human approval;
14. submit once;
15. monitor CI;
16. respond only through reviewed drafts;
17. record the outcome.

## rollback

rollback means:

- close or supersede the internal case;
- do not force-push shared history;
- preserve the audit record;
- revoke credentials if needed;
- restore the last good dataset release;
- invalidate affected predictions;
- rerun the affected comparison;
- document the failure.
