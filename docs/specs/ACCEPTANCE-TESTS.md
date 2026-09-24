# v2 acceptance tests

these tests are the release gate for a future implementation.

## data compiler

- identical source payloads reprocessed without duplicate canonical records;
- body edits create revisions;
- issue and pull-request records route correctly;
- transfers preserve repository identity;
- deleted and inaccessible states are explicit;
- late events use event time;
- capped search queries are marked incomplete;
- every aggregate can be reproduced from a release manifest;
- every removed or quarantined record has a reason;
- canary records pass through every layer.

## evidence graph

- every decision-critical claim has a source or is marked unknown;
- every source has a content hash and timestamp;
- contradictions remain visible;
- summary records cannot overwrite raw evidence;
- evidence perturbation records are stored;
- a citation cannot be marked causally used without a perturbation result;
- model output cannot create trusted authority by itself.

## context compiler

- total token count stays below the deployed limit;
- output reserve is never consumed by evidence;
- exact errors, symbols, paths, tests, and diffs survive compaction;
- stale commit-dependent memory expires;
- no-retrieval baseline runs;
- decisive evidence position is varied;
- distractor scaling is recorded;
- context reset and resume recover typed state;
- prompt injection cannot change policy or permissions.

## memory broker

- untrusted content cannot write approved memory directly;
- origin and authority remain immutable;
- model summaries cannot self-promote;
- expired memories are not returned as current;
- conflicting memories remain visible;
- delayed trigger tests are quarantined;
- every memory read is logged.

## image and history

- exact image digest is pinned;
- full filesystem scan runs;
- package caches are scanned;
- future refs, tags, reflogs, and unreachable objects are absent;
- no local history lookup command is allowed in strict mode;
- image allowlist contains only passing digests;
- source and test duplicates are detected.

## network

- DNS is denied in strict mode;
- HTTP and HTTPS are denied;
- Git fetch and push are denied;
- package registries are denied;
- metadata endpoints are denied;
- every attempted call is logged;
- unlogged network paths quarantine the run;
- browser-disabled status is not accepted as network isolation.

## grader

- baseline tests run before patch grading;
- protected test and build files are restored;
- empty runs fail;
- skipped or xfailed F2P tests fail closed;
- truncated IDs fail closed;
- forged pass markers do not pass;
- infrastructure errors are separate;
- result caching cannot reuse a verdict for a changed patch;
- two independent regrades are recorded;
- a human sample is reviewed.

## patch scope

- raw patch is retained;
- normalized patch is retained;
- one policy applies to every agent;
- removed files are logged;
- unauthorized setup changes are rejected or restored;
- configuration changes require task authorization;
- raw and normalized metrics are both reported.

## evaluation

- private tasks are post-cutoff or held out;
- task audits are independent;
- task denominator is explicit;
- repeated trials are recorded;
- cost is independently metered;
- leakage disposition is per instance;
- legacy and fresh scores are not merged;
- human mergeability is separate from test passage;
- result arrays and README disagreements are reported;
- repository and harness revisions are pinned.

## action

- no public action occurs without human approval;
- no issue comment is sent by default;
- no pull request is opened by default;
- no merge occurs automatically;
- no DCO or CLA is accepted automatically;
- security work uses the approved private channel;
- maintainer rejection closes the case without automated argument.
