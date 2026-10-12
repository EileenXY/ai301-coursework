# Evidence guide: where evidence lives in a plan package

## Diagnosis and grounding

Where it lives:
- Eval mode: the Issue section, Repro evidence section, and the
  Candidate plan's stated cause and proposed change.
- Live mode: the GitHub issue description, the student's posted
  reproduction report, and the diagnosis in plan.md.

What good looks like:
- The diagnosis explains the observed failure and is consistent
  with the reproduction evidence.
- The proposed change addresses a plausible failure mechanism
  supported by the evidence.
- A hypothesis may remain unconfirmed if it is clearly identified
  and the plan explains how it will be validated.
- Do not treat an observed symptom as proof of a specific
  implementation-level root cause.

## Scope

Where it lives:
- Eval mode: the Candidate plan's Change statement, including
  in-scope and out-of-scope work, affected files, and components.
- Live mode: plan.md, the issue description, and relevant
  repository documentation.

What good looks like:
- The proposed work is limited to changes necessary to address
  the reported problem.
- The plan identifies the affected behavior and implementation
  area sufficiently to establish a boundary.
- Unrelated refactoring, feature additions, or broad rewrites
  are excluded unless directly justified by the issue.

## Executability

Where it lives:
- Eval mode: the Candidate plan's proposed approach, named files,
  components, and any relevant Repo facts.
- Live mode: plan.md and the actual repository structure and code.

What good looks like:
- A contributor can identify where to begin and what behavior
  needs to change.
- The approach identifies an actionable modification rather
  than merely restating the desired outcome.
- Exact line numbers are not necessary when the component,
  mechanism, and intended behavior are sufficiently clear.
- The plan does not depend on an unexplained implementation
  decision that would prevent work from starting.

## Test plan

Where it lives:
- Eval mode: the Repro evidence steps and observed outputs,
  compared with the Candidate plan's Test statement.
- Live mode: the posted reproduction report, plan.md, and
  relevant existing tests or repository test instructions.

What good looks like:
- The tests exercise the behavior demonstrated by the original
  reproduction.
- The plan specifies an observable expected result that would
  distinguish the original failure from a successful fix.
- Related regression cases are included when the proposed
  change affects shared behavior.
- A vague instruction such as "run tests" is insufficient
  without a relevant verification target or observable result.

## Honesty

Where it lives:
- Eval mode: the Candidate plan's diagnosis, assumptions,
  risks, unknowns, and any claims in the Candidate plan comment.
- Live mode: plan.md, its risks and unknowns, the Deviations
  section, the posted reproduction evidence, and comment.md.

What good looks like:
- Confirmed observations are distinguished from hypotheses
  and planned actions.
- Material unknowns are acknowledged when the evidence
  does not establish a conclusion.
- The plan includes a reasonable way to investigate
  uncertainties that could affect the implementation.
- A draft comment does not claim that a fix has been
  implemented or verified when only a plan exists.
- During implementation, meaningful changes from the
  accepted plan are recorded as deviations.

## Comms

Where it lives:
- Eval mode: the Candidate plan comment, Thread highlights,
  and Repo facts, including contribution policies and templates.
- Live mode: comment.md, the GitHub issue discussion,
  CONTRIBUTING.md, issue templates, and other applicable
  repository policies.

What good looks like:
- The comment communicates the contributor's own diagnosis,
  bounded approach, and relevant verification plan.
- It addresses applicable maintainer requests and does not
  contradict important information in the issue thread.
- It respects repository contribution policies, including
  explicit AI-assistance disclosure requirements when present.
- If the repository has no stated AI-disclosure requirement,
  do not invent one.
- The comment does not merely copy another contributor's
  proposal or make unsupported claims about completed work.