# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

EileenXY

---

## Posted upstream

**Claim comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72#issuecomment-5904035945

Hi, I’m going to look into issue #72 and test the malformed stored-hash case in `verify_password` on my own setup. I’ll document the environment, the exact commands I run, and what I observe, then post the results here before making any code changes.

**Reproduction comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72#issuecomment-5904838571

I was able to reproduce this issue on my setup.

Environment:

Windows
Python 3.12.10, running inside the project's .venv
pytest 9.1.1
passlib 1.7.4
bcrypt 4.3.0
Repository commit: f89c06f
Steps:

From the repository root with the project virtual environment activated, I ran:
python -m pytest tests/unit/test_security.py::TestSecurity::test_verify_with_wrong_hash_format -vv -rxX

The test was reported as XFAIL with:

issue #72 (manifest H-05): password verify raises UnknownHashError instead of returning False

I then ran the same test with xfail behavior disabled:
python -m pytest tests/unit/test_security.py::TestSecurity::test_verify_with_wrong_hash_format -vv --runxfail

This produced:

passlib.exc.UnknownHashError: hash could not be identified

and pytest reported:

FAILED tests/unit/test_security.py::TestSecurity::test_verify_with_wrong_hash_format
1 failed, 1 warning

Expected behavior:
verify_password should return False when the stored hash is malformed or unrecognized.

Actual behavior:
The malformed stored hash causes passlib.exc.UnknownHashError to escape instead.

I did not modify the code while reproducing the issue; the working tree remained clean.



## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

3/3 scored items

18/20 scored items

18/20 scored items (bar: 18/20: PASS)

**Package analysis**

pkg-01 — My rubric decided `reject`, while the gold label was `accept`. The eval result specifically marked the `environment` check as failed. The package records HTTPie 3.2.4, Python 3.12.4, multidict 6.6.0, and macOS 14.5 (arm64), and it provides an offline reproduction plus a control run. My environment check was stricter about confirming that the reproduction environment matched the issue's target environment or explicitly calling out relevant differences, so it rejected this package even though the gold label accepted the evidence as sufficient.

**Check rationale**

| behavior | The artifacts in the repro report, such as output excerpts, logs, or screenshots, read against the behavior described in the issue and the Behavior shown section of `references/evidence-guide.md`. | Pass if the artifacts show the behavior described by the issue, or clearly show that the behavior did not occur. Evidence of only a different or adjacent behavior does not pass. | required |

I kept this check required because a reproduction should not pass merely because some failure or unusual output occurred. The evidence has to be compared with the behavior described in the issue. I also allowed clear evidence that the reported behavior did not occur, because an honestly evidenced cannot-reproduce result can still be a valid reproduction report. I rejected a looser rule that would accept related or adjacent failures, because that could allow a report to claim the wrong behavior.

**Trade-offs**

My required checks favor avoiding unsupported reproduction claims, but that strictness can reject packages that the gold labels consider acceptable. In the final run, `pkg-01` was gold `accept` but my rubric returned `reject` because of the `environment` check, and `pkg-09` was gold `accept` but my rubric returned `reject` because of the `behavior` check. I accepted this trade-off rather than loosening the checks, because the final run still reached 18/20 and passed every category floor, while keeping environment and behavior evidence required.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
