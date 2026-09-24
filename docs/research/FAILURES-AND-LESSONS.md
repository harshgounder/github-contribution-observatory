# failures and lessons

This file records approaches that were insufficient, misleading, or rejected.

## f001: api-first universe crawl

Attempt: enumerate repositories and issues directly through GitHub API limits.

Problem: scale makes one-request-per-repository enumeration impractical. Search results also have caps and incomplete-result states.

Lesson: use bulk sources and event archives for the broad universe. Use the API for reconciliation and selected objects.

## f002: one ranking score

Attempt: rank every issue with one utility number.

Problem: difficulty, ambiguity, policy risk, maintainer receptivity, review cost, and portfolio fit are different dimensions. A single number hides uncertainty.

Lesson: use hard gates, separate feature families, confidence intervals, and portfolio constraints.

## f003: large context prompt

Attempt: place the issue, repository, history, and retrieved documents into one large prompt.

Problem: context position, distractors, stale facts, and token pressure can reduce decisions. More documents can improve recall and reduce solve rate.

Lesson: compile small evidence packs, use retrieval selectively, reserve output space, and test perturbations.

## f004: labels as truth

Attempt: use `good first issue`, `help wanted`, `bug`, and `priority` labels as direct labels for ranking.

Problem: labels are project-specific, can be stale, and can be wrong. Research found substantial rates of bug-labeled issues that were not fixed as expected.

Lesson: use labels as weak features. Verify the issue text, reproduction, policy, and linked work.

## f005: citation as proof

Attempt: treat a plausible citation as evidence that a claim is supported and used.

Problem: models can cite a source after the fact, cite unrelated evidence, or repeat a claim after adversarial evidence is inserted.

Lesson: measure citation correctness, citation support, and causal evidence sensitivity separately.

## f006: one benchmark score

Attempt: use public SWE-bench-family results as the single measure of agent quality.

Problem: static tasks can be exposed in training, tests can be defective, environments can leak future data, and agent budgets differ.

Lesson: separate legacy, fresh public, private, training, construction, and live contribution tracks.

## f007: tests as the final outcome

Attempt: treat pass/fail tests as the definition of a successful contribution.

Problem: tests can be too narrow, too broad, skipped, xfailed, forged, truncated, or infrastructure-dependent. Manual review found that many test-passing patches were not plausibly correct.

Lesson: use hidden tests, independent regrading, anomaly quarantine, human mergeability, and later maintenance outcomes.

## f008: browser-disabled as isolation

Attempt: treat disabled browser tools as no-network operation.

Problem: shell, GitHub API, package tools, and Docker networking can still reach external services.

Lesson: enforce network denial outside the agent, log attempts and successes, and classify unknown network policy as unmitigated.

## f009: clean checkout as clean image

Attempt: treat a repository reset to the base commit as sufficient contamination control.

Problem: future tags, reflogs, unreachable objects, package caches, Conda environments, and release artifacts can remain inside the image.

Lesson: audit Git history, the complete image filesystem, runtime paths, and the exact digest.

## f010: agent prompt as scope enforcement

Attempt: tell an agent not to edit setup files and assume the evaluator will enforce it.

Problem: agents can change build and test configuration to alter the evaluation environment.

Lesson: use one central patch-scope policy, restore protected files, log removals, and report raw and normalized results.

## f011: checked flag as full verification

Attempt: use a maintained metadata field such as `checked: true` as proof of complete independent reproduction.

Problem: the flag can refer to partial reruns or maintainer review without reconciling every artifact.

Lesson: define checked status through explicit artifact, environment, grader, denominator, and reconciliation requirements.

## f012: reported cost as billing truth

Attempt: report the agent or index cost field as actual spend.

Problem: missing price registries, cache-token handling, and estimator warnings can produce zero or inaccurate values.

Lesson: meter provider usage independently, fail closed on missing prices, and report uncertainty.

## f013: hidden internal reasoning as documentation

Attempt: preserve all internal model reasoning as a public research record.

Problem: private chain-of-thought may contain sensitive context and is not necessary for reproducibility.

Lesson: save evidence, concise rationale, uncertainty, rejected approaches, and reproducible decisions instead.

## f014: public PR volume as the objective

Attempt: use contribution count as the main success measure.

Problem: volume can produce duplicate, rejected, unwanted, or burdensome work and can violate platform policy.

Lesson: measure accepted useful work, reviewer burden, maintenance, safety, and maintainer response.
