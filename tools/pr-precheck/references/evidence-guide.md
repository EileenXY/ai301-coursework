# Evidence guide: where evidence lives in a PR package

## Plan fidelity (harness category: silent-drift)

Eval: pair Plan context (scope, exclusions, implementation steps, test plan, deviation notes) with Candidate PR / Diff and Description. Live: pair plan.md including Deviations with git diff main...HEAD and pr_draft.md; use the issue thread to resolve stated constraints. Every material hunk and omitted step should map to the plan or an explained adjustment, and completion claims should match implementation. Honest partial delivery may pass; silently delivering less, adding unrelated scope, or contradicting the diff cannot.

## Test evidence (harness category: not-tested)

Eval: read the accepted reproduction inside Plan context, its test plan, Candidate PR / Test evidence, and repository check requirements in Repo facts. Live: compare the unit-2 repro record and plan.md test cases with test_evidence.md and the Testing section of pr_draft.md; read required commands in the PR template and docs/CONTRIBUTING.md. Good evidence identifies commands/steps and concrete before/after behavior plus results of repository checks, including nonzero exits. A named test or command with an explicit reported result (including a named control reported unchanged) counts; raw stdout and exact counts are helpful but not universally required. Added test code alone is not a recorded run. A documented failure is useful evidence; a bare 'tests pass' or a green unrelated test is insufficient. Distinguish an honest observed limitation from absent verification.

## Diff quality (harness category: unreviewable)

Eval: inspect every hunk in Candidate PR / Diff alongside Commits. Live: inspect git diff main...HEAD and git log main..HEAD, not merely the file statistics. Good evidence exposes a focused issue fix and necessary regression coverage. Debug prints, commented-out alternatives, unrelated formatting, copied logs, or generated artifacts obscure the change even when described honestly. Large or multi-commit changes are not automatically bad; evaluate necessity and reviewability of the actual hunks.

## Standards and comms (harness category: standards-wall)

Eval: collect only the asks actually present in Repo facts and Thread highlights, then find their fulfillment in Candidate PR / Title and Description. Live: read .github/PULL_REQUEST_TEMPLATE.md, docs/CONTRIBUTING.md, and the issue thread, comparing them with pr_draft.md. For this course, the description must disclose AI assistance in Notes for Reviewers and CI remains unchecked until it exists; do not claim pending checks passed. A substantive answer or justified N/A satisfies applicable sections; copied empty placeholders do not. If no template or AI policy is stated in an eval bundle, do not invent one. Voice-guide compliance is live-only feedback. Accuracy of description claims belongs under Plan fidelity, not merely writing style.
