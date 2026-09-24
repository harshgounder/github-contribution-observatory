# research transfer checklist

Use this checklist before moving the project from research to public release or implementation.

## content review

- [ ] all claims have source or explicit uncertainty
- [ ] private URLs and credentials removed unless explicitly approved for a specific reason
- [ ] private repository names removed unless explicitly approved
- [ ] personal contact information removed
- [ ] raw issue bodies removed unless public and necessary
- [ ] vulnerability details removed
- [ ] hidden chain-of-thought removed
- [ ] raw logs removed
- [ ] unconfirmed reports labeled
- [ ] benchmark statuses preserved

## technical review

- [ ] all document paths resolve
- [ ] source URLs are reachable or marked unavailable
- [ ] code fences parse
- [ ] tables render
- [ ] no em dash characters
- [ ] no banned AI-tell phrases
- [ ] no unresolved merge markers
- [ ] no generated binaries
- [ ] no unnecessary large files

## research review

- [ ] version and date recorded
- [ ] artifact class recorded
- [ ] score denominator recorded
- [ ] contamination status recorded
- [ ] history status recorded
- [ ] network status recorded
- [ ] cost status recorded
- [ ] independent regrade status recorded

## implementation review

- [ ] OpenCode is the only source-code writer
- [ ] DSH review role is defined
- [ ] sandbox policy exists
- [ ] no public action lacks approval
- [ ] no DCO or CLA acceptance is automated
- [ ] kill switch exists
- [ ] rollback procedure exists

## publication decision

- [ ] owner selected visibility
- [ ] owner selected license
- [ ] owner selected public release date
- [ ] owner reviewed third-party source attribution
- [ ] owner reviewed security contact
