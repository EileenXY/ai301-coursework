# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| environment | The repro report's environment record, read against the issue context and the Environment section of `references/evidence-guide.md`. | Pass if the environment identifies the platform, runtime, and relevant dependency or version information needed for the reproduction, and it matches the issue's target environment or clearly calls out relevant differences. | required |
| steps | The reproduction steps in the repro report, read against the issue context and the Steps section of `references/evidence-guide.md`. | Pass if a stranger can follow the stated steps from the required starting state through the trigger without having to guess a necessary setup step or action. | required |
| behavior | The artifacts in the repro report, such as output excerpts, logs, or screenshots, read against the behavior described in the issue and the Behavior shown section of `references/evidence-guide.md`. | Pass if the artifacts show the behavior described by the issue, or clearly show that the behavior did not occur. Evidence of only a different or adjacent behavior does not pass. | required |
| honesty | The stated outcome in the repro report, read against its steps and artifacts, the issue context, and the Honesty section of `references/evidence-guide.md`. | Pass if the stated outcome does not claim more than the evidence supports. An evidenced cannot-reproduce may pass; a reproduction claim passes only when the evidence shows the issue's behavior. | required |
| comms | The claim comment and repro report, read against the repo-facts block, repository requirements, and the Comms section of `references/evidence-guide.md`. | Pass if the comments are specific and honest about the planned or completed work and follow applicable repository communication requirements, including required AI-use disclosure. | required |

## Verdict rule

Accept only if every required check passes. Any required check graded fail or unclear makes the verdict reject. Preferred checks, if any, do not change the final verdict. 
