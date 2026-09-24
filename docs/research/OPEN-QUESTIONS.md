# open questions

## scope

- Which languages and ecosystems are in the first private task set?
- Should the first set focus on triage, repair, or both?
- Which contribution types are allowed first?
- Should documentation and accessibility work be separate queues?

## data

- Which bulk export formats and licenses are acceptable?
- Which private snapshot date becomes the first reproducibility cutoff?
- Which source disagreements require human adjudication?
- What coverage target is realistic per source and language?

## context

- Which model and tokenizer are frozen for the first context experiments?
- What is the initial context budget by role?
- Which retrieval depth should be selected for triage versus repair?
- Which perturbation tests are mandatory for the first release?

## execution

- Which sandbox implementation is approved?
- Which image registry and digest policy will be used?
- Which network policy engine is available?
- Which GitHub App permissions are needed for the private pilot?

## evaluation

- How many private tasks are enough for the first claim?
- Which maintainers will review mergeability?
- What is the primary utility function?
- Which cost metric is primary?
- What score difference is meaningful under repeated trials?
- How long should the live contribution pilot run?

## governance

- repository visibility: public by owner decision;
- Which license applies to documentation and future code?
- What public release date is acceptable?
- Which security contact should be listed?
- Which maintenance owner handles incidents?

## implementation

- Should the first runtime use a simple local database or a lakehouse?
- Should the first evidence graph use a relational store or a graph store?
- Which workflow engine will manage long-running cases?
- Which model gateway and secret store are approved?

## decision rule

do not begin public contribution automation while any of these remain unresolved:

- target task population;
- private benchmark protocol;
- image and network policy;
- human approval owner;
- credential model;
- rollback path;
- license and visibility decision.
