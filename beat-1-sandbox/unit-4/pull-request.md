# Unit 4 — Test and Submit

## Your pull request

**Pull request**

https://github.com/codepath/pathreview-ai301-fa26-s1/pull/168

**Branch**

fix/72-verify-password-unknown-hash

## Eval iterations

**Run history**

1. First complete official Sonnet run: `17/20` agreement. All five categories had at least one match, but pkg-08, pkg-16, and pkg-19 were false rejections.
2. After clarifying that named tests/commands with concrete reported outcomes count without raw terminal transcripts, a partial run of `pkg-08,pkg-16,pkg-19,pkg-01,pkg-04` reached `5/5`. pkg-01 and pkg-04 were canaries for standards-wall and not-tested. This partial run did not replace the full-run transcript or establish the category floor.
3. Final complete official Sonnet run: `20/20`. The saved, unedited eval-run.txt reports:

```text
categories: clear-accept 7/7  not-tested 4/4  silent-drift 4/4  standards-wall 2/2  unreviewable 3/3
agreement: 20/20 scored items  (bar: 18/20: PASS)
```

The final run used the official, unmodified harness and installed skill. A local command wrapper added `--max-budget-usd 0.15` to each Claude call to bound spending; it did not alter prompts, outputs, labels, or grading. All 20 calls yielded grades without reported errors. The course's `sonnet` alias was retained.

**Package analysis**

Package: `pkg-08`. Final skill verdict: `accept`; gold label: `accept`. The first run returned `reject` on Repository checks, which was too strict about the form of execution evidence.

The package records the before/after interaction: before, `s` opened a name prompt and did nothing; after, it shows the error toast, no name prompt, and leaves the untracked file present. It also says:

> Integration test `stash_untracked_only_errors` passes; `go test ./...` passes; `go generate ./...` produces no cheatsheet diff.

These are named executions with concrete outcomes, not a generic claim that everything works. The controller guard, translation, and integration test match the plan; the description handles the repo checklist and states no UserConfig changes. Requiring raw stdout for every named command was an invented standard. The revision accepts this evidence while still rejecting packages with no meaningful behavior proof or missing mandatory requirements.

**Check rationale**

The current Repository checks row is quoted exactly:

| Repository checks | Repo-facts required checks or live PR template/CONTRIBUTING.md, compared with test-evidence commands and results. | The repo's applicable checks have recorded executions and outcomes (a named command/test plus its concrete reported result is sufficient; raw terminal logs, exit codes, and formatter transcripts are not mandatory unless the repo explicitly requires them), including failures or no-tests outcomes; a documented environment blocker identifies the attempted command and its effect. A disclosed failure is not automatically a rejection. Merely saying tests pass, or never running the required checks without observable blocker evidence, fails. | required |

The first version led the grader to demand more logging than the repo asked for. The revision states what counts as evidence: a named command or test plus a concrete reported result. It preserves the boundary against a bare "tests pass" and against required checks never attempted, while allowing honest failures and concrete environment blockers. This evaluates evidence content rather than formatting.

**Trade-offs**

Accepting concise reported outcomes cannot prove that the author really ran them; a plausible fabricated result could pass. Requiring full stdout would not establish authenticity either and falsely rejected the concrete evidence in pkg-08, pkg-16, and pkg-19. The partial run included pkg-01 (standards-wall) and pkg-04 (not-tested), and both stayed reject. The final full run preserved every earlier correct verdict and matched all categories, so the loosened evidence rule did not cause a regression in this fixed set. It does not guarantee correctness on unseen PRs.

## Live check and assistance

The live-mode Sonnet precheck returned `accept` with all five checks passing, using the installed skill and captured issue thread, plan, committed branch diff, PR template, contribution rules, PR draft, and actual test output. Voice feedback was used to distinguish observed results from reasoning and to avoid implying that every xfail had been investigated.

Codex assisted with writing and revising the Unit 4 skill and this report, ran the tests and official evaluations, and prepared the PR from the existing Unit 3 branch. The reported evaluations are real harness runs; eval-run.txt was copied without hand edits. No claim is made that the student personally executed the agent's commands. The PR description includes the AI-use disclosure.
