# memory specification

## purpose

preserve useful state across long tasks without allowing stale, injected, or model-generated content to become authority.

## memory classes

### working memory

current hypotheses, plan, open questions, and next action.

### episodic memory

actions, tool calls, test results, failures, approvals, and handoffs.

### semantic repository memory

validated facts about architecture, symbols, build commands, ownership, releases, and policy.

### procedural memory

tested methods for reproduction, testing, documentation, releases, and common repairs.

### user-approved memory

facts explicitly approved for persistence by the owner.

## memory record

```yaml
memory_id:
memory_class:
content:
origin:
authority:
source_ids:
scope:
base_commit:
created_at:
valid_until:
supersedes:
write_policy:
trust:
content_hash:
expiry_policy:
```

## write rules

raw external text cannot be written directly into approved memory.

promotion path:

```text
raw evidence
-> typed observation
-> reviewed fact
-> approved memory
```

model summaries cannot promote themselves.

trusted tool output cannot silently change authority.

high-impact facts require human approval.

commit-dependent facts expire when the base commit changes.

contradictory memories remain visible until adjudicated.

## retrieval

memory retrieval must return:

- memory ID;
- origin;
- authority;
- freshness;
- source evidence;
- conflicts;
- expiry;
- allowed scope.

a memory item is not a reason to change permissions or public-action policy.

## session handoff

each long-running session writes:

- completed work;
- failed hypotheses;
- current diff;
- test results;
- unresolved conflicts;
- next action;
- remaining budget.

the next session reads the handoff before doing new work.

## memory security tests

include:

- memory injection through a query;
- delayed trigger after context reset;
- false corroboration;
- source laundering through a summary;
- stale memory after a new commit;
- model attempt to promote a guess;
- conflict between trusted and untrusted records;
- memory item requesting a new tool permission.
