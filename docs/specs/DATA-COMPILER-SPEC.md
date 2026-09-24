# data compiler specification

## purpose

convert changing public sources into replayable, queryable, and auditable data releases.

## storage layers

### bronze

exact source evidence:

- response body;
- endpoint and query;
- request parameters;
- response headers;
- HTTP status;
- ETag and Last-Modified;
- fetched_at;
- adapter version;
- authentication tier;
- cursor;
- content hash.

bronze is append-only.

### silver

canonical entities:

- repository immutable ID;
- issue number and global node ID;
- source event ID;
- created_at, updated_at, closed_at;
- author state;
- labels;
- comments;
- links;
- linked pull requests;
- body revisions;
- transfers;
- tombstones.

### gold

analysis-ready records:

- canonical issue type;
- repository class;
- language;
- policy classification;
- duplicate cluster;
- security classification;
- quality flags;
- feature values;
- source confidence;
- selection policy version.

### quarantine

records that are:

- sensitive;
- malformed;
- contradictory;
- unsafe;
- unresolved;
- license-uncertain;
- identity-uncertain;
- suspected prompt injection;
- excluded by a documented rule.

## release manifest

every release contains:

```yaml
release_id:
parent_release:
source_snapshot_ids:
adapter_versions:
schema_hash:
config_hashes:
random_seed:
sampling_frame:
sampling_weights:
contamination_manifest:
record_counts_by_stage:
quarantine_counts_by_reason:
artifact_locations:
known_gaps:
reproduction_command:
```

## source adapter contract

an adapter must record:

- source identity;
- query and parameters;
- pagination or cursor;
- retries and backoff;
- rate-limit status;
- response validation;
- entity identity mapping;
- deleted, private, transferred, and inaccessible states;
- partial failures;
- schema changes.

late events are stored by event time, not ingestion time.

## identity rules

primary issue identity:

```text
repository immutable ID + issue number
```

never use title or body as identity.

body edits create revisions, not new issues.

fork-local issues remain separate unless a documented migration proves identity.

REST issue responses that contain pull requests are routed or rejected explicitly.

## deduplication

use three layers:

1. exact source-event and payload deduplication;
2. normalized near-copy candidate generation;
3. human-reviewed cluster assignment.

embeddings can retrieve candidates but cannot delete a record without evidence.

repeated reports are preserved as a cluster because repetition may be meaningful.

## sampling and coverage

maintain:

- a recent bounded census;
- a longitudinal probability sample;
- targeted rare-stratum samples;
- an exploration queue;
- a production selection queue.

store inclusion probability, stratum, seed, and selection rank.

report:

- weighted results;
- unweighted results;
- effective sample size;
- missingness;
- response failures;
- coverage by language, repository class, time bucket, and issue type.

## quality gates

hard gates:

- valid JSON and schema;
- valid entity identity;
- plausible timestamps;
- issue versus pull-request classification;
- monotonic cursor continuation;
- referential integrity;
- no unexplained count drop;
- current snapshot agrees with canary reads.

statistical gates:

- ingestion lag p50 and p95;
- unresolved cursor age;
- adapter failures;
- duplicate rate;
- missing-field rate;
- drift by source and stratum;
- gold-panel precision and recall;
- human agreement on double-coded samples.

quality flags are versioned and never overwrite human judgment.
