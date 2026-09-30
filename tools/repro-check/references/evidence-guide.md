# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

**Where it lives:** In an eval package, look at the issue context and the repro report's environment record. In live mode, compare the environment stated in the draft repro comment with the issue thread and the repository documentation.

**What good looks like:** The environment identifies the platform, runtime, and relevant dependency or version information needed to understand the reproduction. The environment matches what the issue targets, or any relevant difference is explicitly called out.

## Steps

**Where it lives:** In an eval package, look at the reproduction steps in the repro report and use the issue context when needed to identify the expected starting state and trigger. In live mode, look at the reproduction steps in the student's draft comment and the setup instructions in the repository documentation.

**What good looks like:** The steps give a stranger enough information to move from the stated starting state to the behavior being tested without having to guess a required action or setup step.

## Behavior shown

**Where it lives:** In an eval package, look at the artifacts in the repro report, such as output excerpts, logs, screenshots, or other recorded results, and compare them with the behavior described in the issue context. In live mode, compare the artifacts in the student's draft with the behavior described in the GitHub issue.

**What good looks like:** The artifacts directly show the behavior described by the issue, or clearly show that the behavior did not occur. Evidence of a different or merely related behavior does not count as proof of the issue.

## Honesty

**Where it lives:** In an eval package, compare the outcome stated in the repro report with its steps and artifacts and with the issue context. In live mode, compare the student's stated conclusion in the draft comment with the evidence the student provides.

**What good looks like:** The stated outcome does not claim more than the evidence supports. A cannot-reproduce result is acceptable when the report accurately states what was attempted and what was observed; a reproduction claim is acceptable only when the evidence actually shows the issue's behavior.

## Comms

**Where it lives:** In an eval package, look at the claim comment and repro report together with the repo-facts block and any stated repository contribution or communication requirements. In live mode, check the draft comment against the issue thread, repository templates, contribution documentation, and any stated AI-use disclosure requirements.

**What good looks like:** The comments are specific to the issue and accurately describe the student's own planned or completed work. They follow applicable repository communication requirements, including required disclosures, and do not use generic boilerplate in place of issue-specific information.