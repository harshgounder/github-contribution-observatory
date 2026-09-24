# security model

## threat model

the system processes hostile public content:

- issue titles and bodies;
- comments;
- README files;
- source comments;
- dependency documentation;
- test output;
- web pages;
- package metadata;
- prior memory;
- model-generated summaries.

the system also handles sensitive actions:

- shell execution;
- network access;
- file writes;
- Git operations;
- GitHub writes;
- pull-request creation;
- issue comments;
- labels and merges.

## trust boundary

```text
trusted control plane
|
deterministic policy and capability engine
|
model proposals
|
untrusted evidence
|
sandboxed execution
```

retrieved content can influence reasoning.

it cannot change policy, permissions, token scope, public-action authority, or target scope.

## network policy

strict runs deny:

- DNS;
- HTTP;
- HTTPS;
- GitHub;
- package registries;
- Git remotes;
- cloud metadata;
- external databases;
- unapproved browser access.

log every attempted and successful network call.

browser-disabled does not mean network-isolated when shell or API access exists.

## filesystem policy

- no host credentials;
- no host network;
- no Docker socket;
- no cloud metadata route;
- no unrelated workspace access;
- isolated temporary filesystem;
- read-only source mount where possible;
- explicit output mount;
- resource and process limits;
- no unreviewed package install.

## image policy

scan the complete image for:

- duplicate source;
- duplicate tests;
- future branches and tags;
- reflogs;
- unreachable Git objects;
- package caches;
- Conda and Miniconda environments;
- release archives;
- hidden evaluator files.

only exact passing image digests enter the allowlist.

## capability policy

capabilities are separate:

```text
read_repository
search_repository
read_issue
read_external_docs
run_local_tests
write_workspace
install_dependency
network_fetch
git_fetch
git_push
create_issue_comment
create_pull_request
modify_labels
merge_pull_request
```

every capability records scope, expiry, token permission, human approval, and side-effect class.

## action gate

```text
model proposal
-> capability request
-> deterministic policy engine
-> human approval when required
-> sandboxed action
-> immutable action log
```

public actions default to human approval.

no unattended issue comments.

no unattended PR creation.

no unattended merges.

## security evaluation

measure:

- indirect-injection success;
- poisoned retrieval success;
- forbidden tool calls;
- privilege violations;
- secret exposure;
- exfiltration;
- unsafe patches;
- unsafe ticket writes;
- network escape;
- future-history access;
- memory promotion attempts;
- benign utility under attack.

report the tested threat model and residual risk.

do not claim that a system is injection-proof.
