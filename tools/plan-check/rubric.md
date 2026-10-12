# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Diagnosis | The plan's diagnosis compared with the observed behavior and reproduction evidence. | The diagnosis is consistent with the reproduced bug and does not contradict the evidence. | required |
| Root Cause Alignment | The proposed implementation compared with the failure mechanism shown in the reproduction evidence. | The proposed fix addresses the supported cause rather than merely hiding the symptom. | required |
| Scope | The plan's scope statement, affected components, and proposed changes compared with the issue. | The changes are bounded to the reported problem, and unrelated work is excluded or justified. | required |
| Executability | The implementation approach and affected files compared with the repository facts. | A contributor can identify where to begin and what behavior to change without inventing the core approach. | required |
| Test Plan | The proposed tests compared with the original reproduction steps and observed failure. | The tests specify observable outcomes that distinguish the original bug from the corrected behavior. | required |
| Uncertainty | The plan's assumptions and unknowns compared with the available evidence. | Material uncertainties are acknowledged and include a reasonable way to validate them. | required |
| Thread and Conventions | The draft plan comment compared with the issue thread and repository conventions. | The comment reflects the contributor's own plan and respects applicable thread constraints and repository policies. | required |

## Verdict rule

Grade every check as pass, fail, or unclear.

Accept the package only if every required check passes.

Reject the package if any required check fails or is unclear.

Treat unclear as a failure for required checks because missing evidence cannot establish readiness.

Preferred checks, if present, provide feedback but do not affect the final verdict.

Do not reject a package solely because of formatting, length, or missing headings. Judge the actual evidence and whether the proposed work is ready to execute.

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->
