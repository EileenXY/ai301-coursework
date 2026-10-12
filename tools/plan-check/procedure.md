# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

# Procedure: Grade a Fix Plan

## Read order

1. Read rubric.md to identify all checks, evidence requirements,
   pass conditions, weights, and the final verdict rule.

2. Read references/evidence-guide.md to understand how to interpret
   reproduction evidence, repository facts, and issue discussions.

3. Read the provided issue description and thread highlights to
   understand the reported problem, expected behavior, and constraints.

4. Read the reproduction evidence, including reproduction steps,
   environment details, commands, outputs, and observed failures.

5. Read the proposed fix plan, including diagnosis, scope,
   implementation approach, tests, risks, and unknowns.

6. Read the draft plan comment and any repository conventions
   included in the package.

## Evidence gathering

1. Identify the exact behavior reported in the issue and the
   expected behavior.

2. Extract the observed behavior and supporting evidence from
   the reproduction report.

3. Compare the plan's diagnosis with the reproduced behavior.
   Record any contradictions or unsupported assumptions.

4. Identify the proposed code changes, affected components,
   and explicitly excluded work.

5. Compare the implementation approach with the failure
   mechanism supported by the evidence.

6. Extract the proposed verification steps and determine whether
   they can demonstrate that the original failure is resolved.

7. Identify material unknowns and check whether the plan
   provides a reasonable way to investigate them.

8. Compare the draft plan comment with relevant issue-thread
   constraints and repository conventions.

9. Use only evidence available in the provided package.
   Do not invent missing repository facts or test results.

## Check execution

1. Evaluate every check defined in rubric.md independently.

2. For each check, locate the specific evidence named in
   its Evidence column.

3. Compare that evidence against the check's Pass condition.

4. Assign one grade:
   - pass: the available evidence satisfies the condition.
   - fail: the evidence contradicts or does not satisfy the condition.
   - unclear: the available evidence is insufficient to decide.

5. Record a concise explanation grounded in specific evidence.

6. Do not treat the presence of a heading, section, or keyword
   as proof that a check passes.

7. Do not infer success from an unsupported claim.

8. Apply the same standards to every package.

## Verdict assembly

1. Collect the grades for all required and preferred checks.

2. Apply the verdict rule from rubric.md.

3. Return accept only if every required check passes.

4. Return reject if any required check fails or is unclear.

5. Preferred checks may affect feedback but must not
   change the final verdict.

6. For rejected packages, identify the checks preventing
   acceptance and explain what needs to change.

7. Produce the final result in the output format required
   by SKILL.md, including the per-check results and
   the final accept or reject verdict.

8. Do not claim that a fix has been implemented or verified.
   This procedure evaluates the readiness of a plan only.