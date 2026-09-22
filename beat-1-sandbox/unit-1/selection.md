# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72

**Verdict output**

I graded all three against your rubric and all three are accepted. Every required check passes for each one, so the ranking comes down to your fit profile: Python backend, debugging and AI engineering, and nothing frontend-heavy.

Accepted, in fit order:
1. #69 – Output parser crashes on a top-level JSON array. This is the best fit. It's a Python backend bug in the part that handles what the model sends back, so you get debugging and AI engineering in one. A classmate (jacho15) has already reproduced the traceback in the thread, which gives you a head start. Their claim doesn't block you under the house rule. Estimated at 2–4 hours.
2. #72 – verify_password raises UnknownHashError instead of returning False. Also a strong backend fit: API and security code in core/security.py, and the smallest of the three (1–2 hours). It has no comments or claims in this repo. A student's PR in their own coursework repo (foojanbabaeeian/ai301-coursework-Fozhan #1, merged) mentions picking this issue, but that isn't a PR against this repo and doesn't block you.
3. #68 – KeywordSearcher.index([]) raises ZeroDivisionError. Backend search code, but the fix is a small empty-input guard, so it's less AI-engineering than #69. A classmate (yulijasso) has claimed it with a detailed plan. That doesn't block you, but they've already mapped out the fix. Estimated at 2–4 hours.

Rejected: none.

Evidence that applies to all three:
- Maintainer: the last human commit was by Aburke225 on 2026-09-16, six days ago.
- Repo: not archived, and the last push was 2026-09-16. There's no release, but the push alone meets the 12-month condition.
- AI policy: neither docs/CONTRIBUTING.md nor .github/PULL_REQUEST_TEMPLATE.md says anything about AI use, and silence passes.
- Open PRs: the only one in the repo is #74, which fixes #60, not any of these.
- Labels: each issue has a good first issue label applied by the maintainer.

[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Non-bot commit by Aburke225 on 2026-09-16, 6 days before today (2026-09-22)"},
      {"name": "Repository active", "grade": "pass", "evidence": "isArchived=false; last push 2026-09-16 (no release, push within 12 months)"},
      {"name": "Bounded newcomer scope", "grade": "pass", "evidence": "Single goal: handle top-level JSON array in rag/generator/output_parser.py and remove xfail on H-02; labeled good first issue, est. 2-4h"},
      {"name": "Work is available", "grade": "pass", "evidence": "No assignees, no linked or mentioned PRs; jacho15 claim comment ignored per Path Review house rule"},
      {"name": "No repeated failed attempts", "grade": "pass", "evidence": "No closed/unmerged PRs in the issue's history"},
      {"name": "First-issue signal", "grade": "pass", "evidence": "'good first issue' label applied by maintainer Aburke225"},
      {"name": "AI-compatible contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no AI policy; silence passes"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Non-bot commit by Aburke225 on 2026-09-16, 6 days before today (2026-09-22)"},
      {"name": "Repository active", "grade": "pass", "evidence": "isArchived=false; last push 2026-09-16 (no release, push within 12 months)"},
      {"name": "Bounded newcomer scope", "grade": "pass", "evidence": "Single goal: verify_password returns False on malformed hash in core/security.py and remove xfail on H-05; labeled good first issue, est. 1-2h"},
      {"name": "Work is available", "grade": "pass", "evidence": "No assignees, no comments; only cross-ref is a merged PR in an external coursework repo, not an implementation PR here"},
      {"name": "No repeated failed attempts", "grade": "pass", "evidence": "No closed/unmerged PRs against this repo in the issue's history"},
      {"name": "First-issue signal", "grade": "pass", "evidence": "'good first issue' label applied by maintainer Aburke225"},
      {"name": "AI-compatible contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no AI policy; silence passes"}
    ],
    "verdict": "accept"
  },
   { 
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/68",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Non-bot commit by Aburke225 on 2026-09-16, 6 days before today (2026-09-22)"},
      {"name": "Repository active", "grade": "pass", "evidence": "isArchived=false; last push 2026-09-16 (no release, push within 12 months)"},
      {"name": "Bounded newcomer scope", "grade": "pass", "evidence": "Single goal: KeywordSearcher.index([]) must not raise in rag/retriever/keyword_search.py and remove xfail on H-01; labeled good first issue, est. 2-4h"},
      {"name": "Work is available", "grade": "pass", "evidence": "No assignees, no linked or mentioned PRs; yulijasso claim comment ignored per Path Review house rule"},
      {"name": "No repeated failed attempts", "grade": "pass", "evidence": "No closed/unmerged PRs in the issue's history"},
      {"name": "First-issue signal", "grade": "pass", "evidence": "'good first issue' label applied by maintainer Aburke225"},
      {"name": "AI-compatible contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no AI policy; silence passes"}
    ],
    "verdict": "accept"
  }
]

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

`agreement: 15/20 scored items  (bar: 18/20: below the bar)`

`agreement: 1/5 scored items`

`agreement: 4/4 scored items`

`agreement: 18/20 scored items  (bar: 18/20: PASS)`

`agreement: 18/20 scored items  (bar: 18/20: PASS)`

**Issue analysis**

`issue-19  accept  reject   NO     failed: Bounded newcomer scope, First-issue signal (preferred)`

For issue-19, the gold label was `accept`, but my rubric returned `reject`. The result was driven by the Bounded newcomer scope check, with First-issue signal also failing as a preferred check. The scope check treated the issue's multiple possible causes and suggested solutions as evidence that the task was not sufficiently bounded for a newcomer.

**Check rationale**

`Bounded newcomer scope`: "Pass if the issue has one coherent, actionable goal that a newcomer could work toward without first resolving a major unanswered requirement or design decision. Multiple files, documentation pages, related sub-tasks, examples, possible causes, or suggested implementation approaches do not by themselves make an issue too broad when they all support the same coherent goal. A maintainer-applied `good first issue`, `beginner`, or equivalent label is positive evidence that the scope is newcomer-appropriate, but does not override a clear failure condition. Fail if the issue is explicitly an umbrella/tracking issue requiring multiple independent deliverables, is purely a usage/support question, a maintainer states that it requires changes to core internals, or a key requirement needed to implement the requested result is explicitly unresolved or TBD and has not been clarified by a maintainer."

I wrote the check this way because my earlier version was too strict about issues that mentioned multiple files, possible causes, or suggested approaches. Those details can still belong to one coherent beginner-friendly task. At the same time, I wanted the check to reject issues that are genuinely blocked by unresolved requirements or that contain multiple independent deliverables.

**Trade-offs**

`issue-19  accept  accept   yes`

`issue-19  accept  reject   NO     failed: Bounded newcomer scope, First-issue signal (preferred)`

After I revised the Bounded newcomer scope check, issue-19 was correctly accepted in my targeted re-run, but it was rejected again in the final full run. This shows a trade-off in the current wording: it allows issues with multiple possible causes or suggested approaches when they support one coherent goal, but borderline issues can still be interpreted differently. I kept the stricter language about unresolved requirements because I still wanted issues like issue-20, whose key requirement was TBD, to be rejected.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. This issue fits my interests because it is a small Python/FastAPI backend debugging task involving authentication and security. I am focusing on backend development, and the estimated 1–2 hours also fits the time I have available.

2. The verdict correctly identified that the issue has a clear and bounded goal, the repository is active, and there is no active implementation claim. Besides the rubric result, I also considered that #72 is smaller and more directly related to backend development than the other accepted candidates.

3. I expect claiming it to be straightforward because there is currently no assignee, no claim comment, and no linked implementation PR. However, since this is a shared course repository, another student could still start working on it before I claim it in Unit 2.
---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
