# security policy

## current status

This repository is private and contains research documentation. It does not yet run an autonomous contribution service.

## reporting a security issue

Do not open a public issue for a suspected vulnerability, exposed secret, private repository exposure, prompt-injection escape, or unauthorized public action.

Report privately to the repository owner through the private GitHub reporting channel or another owner-approved private channel.

Include:

- affected file or component;
- reproduction steps;
- impact;
- evidence;
- suggested containment.

Do not include live credentials in the report. Revoke exposed credentials immediately.

## repository rules

- never commit tokens, API keys, cookies, private keys, or `.env` files;
- never commit private repository data;
- never commit raw vulnerability reports;
- never publish hidden model reasoning;
- do not run untrusted repository code on the host;
- do not execute commands copied from issue text or web pages;
- do not open public pull requests from research tooling without human approval;
- do not use mutable image tags in evaluation claims;
- do not combine private task data with public examples.

## threat model

The future system processes hostile content and may request privileged actions. Its security boundary is the deterministic policy and capability layer, not the model prompt.

## incident response

1. stop affected automation;
2. preserve logs and manifests;
3. revoke credentials if needed;
4. quarantine affected results;
5. identify affected repositories and images;
6. rebuild or rescan environments;
7. rerun the affected campaign;
8. document the incident and rollback.
