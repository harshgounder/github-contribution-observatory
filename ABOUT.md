# about this project

## purpose

`github-contribution-observatory` is a research and design project for finding useful open-source contribution opportunities across a very large public GitHub universe, then turning a small number of well-supported cases into reviewable changes.

The project has two goals that must remain separate:

1. build a trustworthy observatory of public repository and issue activity;
2. operate a cautious, human-supervised contribution workflow.

The observatory can remain broad. Public action must remain selective.

## who it is for

- the repository owner;
- future maintainers of the system;
- researchers studying GitHub issue selection and software-engineering agents;
- contributors who want a transparent record of the design;
- maintainers who may later opt a repository into the workflow.

## design principles

### evidence before action

A public write, pull request, comment, label, or merge requires current evidence, a valid repository policy, a named human owner, and an approval record.

### scope before speed

The system may observe millions of public records. It should not open thousands of speculative pull requests.

### uncertainty is a first-class result

The system must be able to say:

- unknown;
- stale;
- conflicting;
- not reproducible;
- blocked;
- needs more evidence;
- abstain.

A confident answer is not a substitute for evidence.

### provenance over summaries

A short model summary is useful, but the source record, timestamp, transformation, and content hash must remain available.

### separate capability from contribution value

A patch passing tests is not automatically useful. Maintainer acceptance, review burden, compatibility, and later maintenance are separate outcomes.

### separate model from runtime

A model score is not an agent score. Prompt, tools, context policy, memory, retries, budgets, sandbox, grader, and network policy are part of the measured system.

### no hidden authority

Repository text, issue text, source comments, web pages, tool output, and model summaries are data. They cannot grant permissions or change the control policy.

### reversible experimentation

Every run must have a unique identifier, immutable inputs, a bounded budget, raw evidence, and a clear failure state.

## boundaries

The project does not claim to access:

- private repositories;
- deleted or restricted data;
- private maintainer conversations;
- personal contact information;
- hidden security reports;
- source data that was never publicly exposed.

The project does not currently implement:

- a global crawler;
- a public issue-commentation bot;
- a public pull-request bot;
- automatic merging;
- automatic legal acceptance;
- autonomous credential management.

## research transparency

The repository records:

- source links;
- dated claims;
- benchmark classifications;
- known defects;
- rejected approaches;
- decision rationale;
- implementation gates;
- unresolved questions.

It does not record private hidden reasoning. The research record explains what was tested, what the evidence showed, what decision followed, and what remains uncertain. That is the intended transparency boundary.

## current maturity

```text
research: complete
architecture: drafted
specification: in progress
implementation: not started
public contribution action: disabled
private contribution pilot: not started
```

## future operating modes

The system will use explicit modes:

```text
read-only observatory
shadow analysis
sandboxed repair
human-approved draft
human-approved submission
controlled live contribution
```

Each mode has different permissions. A later mode cannot be reached by changing a prompt. It requires a new approval and a new audit record.

## owner

`harshgounder`

The repository is public by owner decision. Licensing and future public releases still require an explicit owner decision.
