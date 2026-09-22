# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Maintainer activity | The "last 5 default-branch commits" and "maintainer first-response sample" under Repo facts | Pass if at least one non-bot default-branch commit occurred within 90 days before the capture date, OR the maintainer first-response sample shows at least one Owner, Member, or Collaborator response within 30 days. A bot commit alone does not satisfy this check. | required |
| Repository active | The "archived:", "latest release", and "last push to any branch" fields under Repo facts | Pass if the repository is not archived AND either the latest release or the last push occurred within 12 months before the capture date. | required |
| Bounded newcomer scope | The issue body, labels, and Comments section | Pass if the issue has one coherent, actionable goal that a newcomer could work toward without first resolving a major unanswered requirement or design decision. Multiple files, documentation pages, related sub-tasks, examples, possible causes, or suggested implementation approaches do not by themselves make an issue too broad when they all support the same coherent goal. A maintainer-applied `good first issue`, `beginner`, or equivalent label is positive evidence that the scope is newcomer-appropriate, but does not override a clear failure condition. Fail if the issue is explicitly an umbrella/tracking issue requiring multiple independent deliverables, is purely a usage/support question, a maintainer states that it requires changes to core internals, or a key requirement needed to implement the requested result is explicitly unresolved or TBD and has not been clarified by a maintainer. | required |
| Work is available | "this issue: assignees:" and "linked PRs:" under Repo facts, plus claim statements and PR references in the Comments section | Pass if there is no current assignee, no open linked or comment-mentioned PR implementing the issue, and no clear active claim to the work. Closed unmerged PRs count as abandoned attempts rather than active claims. | required |
| No repeated failed attempts | Linked PR history under Repo facts and PR references or prior-attempt discussion in the Comments section | Pass if the issue does not show multiple abandoned closed, unmerged implementation attempts suggesting that the work is substantially harder than its description indicates. One abandoned attempt alone does not fail this check. | preferred |
| First-issue signal | Issue labels and label events shown in the issue data | Pass if a maintainer-applied label such as `good first issue`, `beginner`, or an equivalent newcomer-friendly label is present. Absence of such a label does not make the issue unacceptable. | preferred |
| AI-compatible contribution policy | The "contribution policy" line under Repo facts, including CONTRIBUTING.md, linked contributor documentation, dedicated AI policy files, and relevant PR/issue template requirements summarized there | Pass unless the contribution policy explicitly bans AI-generated or AI-assisted contributions. Requirements to disclose AI use, personally understand the change, test the work, or human-review AI output pass. If the repository states no AI policy, pass. | required |

## Verdict rule

Accept an issue only if every required check passes. Reject an issue if any required check fails.

For a required check, `unclear` counts as fail unless the check's pass condition explicitly states that absence of a restriction is sufficient to pass. In particular, silence about AI use passes the AI-compatible contribution policy check.

Preferred checks never change an accept/reject verdict. They are used only to distinguish and rank issues that already pass every required check.

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
