# transparent reasoning summary

This document records concise rationale, not private hidden chain-of-thought.

## rationale behind the architecture

### why separate observation and action

A global reader can safely inspect a large public universe. A public writer changes another person’s repository and may create review, security, and maintenance work. Those are different risk classes.

### why use a data compiler

A list of scraped issues is not enough. A useful data system needs source identity, event time, transformations, deduplication, quarantine, release manifests, and known gaps.

### why use an evidence graph

A summary can hide the exact source that supports a claim. Evidence records preserve source location, freshness, contradictions, and allowed actions.

### why compile context

A large model window can still fail when evidence is placed poorly, surrounded by distractors, contradicted, stale, or unrelated to the decision. The context compiler should select and test evidence.

### why allow no retrieval

Retrieval can fail or distract. The system must compare no evidence, retrieved evidence, oracle evidence, corrupted evidence, and restored evidence.

### why use a fresh evaluator

A builder can overstate progress. A clean evaluator with no write access should inspect the diff, evidence, tests, and acceptance criteria independently.

### why keep public action human-approved

Maintainer consent, repository policy, licensing, security handling, and review burden are contextual. The model cannot infer permission merely because an issue is public.

### why separate benchmarks

A legacy score, a fresh public score, a private task score, a training corpus, and a live contribution outcome answer different questions.

### why record failures

The strongest design changes came from finding where the first approach was wrong. Failure records prevent the same mistakes from returning.

## reasoning boundary

The repository records:

- questions;
- hypotheses;
- evidence;
- decisions;
- uncertainty;
- rejected paths;
- acceptance gates;
- source links.

It does not record private hidden reasoning, private credentials, or raw sensitive context.
