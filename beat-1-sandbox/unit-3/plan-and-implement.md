# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

## Posted upstream

**GitHub username**

EileenXY

**Plan comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72#issuecomment-6116976215

## Implementation Plan for Issue #72

I reproduced the original bug using:

`python -m pytest tests/unit/test_security.py -q -k test_verify_with_wrong_hash_format --runxfail`

The test fails with `passlib.exc.UnknownHashError`.

I also investigated the malformed bcrypt hashes mentioned
in the issue discussion:

- `$2b$notarealhash` raises `ValueError`
- `$2b$12$tooshort` raises `ValueError`

Both cases were reproduced locally.

### Root Cause

`verify_password()` calls `pwd_context.verify()` without
handling exceptions caused by unrecognized or malformed
password hashes.

### Proposed Fix

1. Catch `ValueError` around `pwd_context.verify()` and
   return `False`.
2. Preserve normal verification behavior for valid bcrypt hashes.
3. Remove the existing strict `xfail` marker.
4. Add regression tests for the two malformed bcrypt hashes.

### Existing Work and Coordination

I reviewed the existing PR #75, which already proposes
catching ValueError and removing the xfail marker.

My planned contribution includes additional regression tests
for two malformed bcrypt hashes:

- `$2b$notarealhash`
- `$2b$12$tooshort`

I will check the status of PR #75 before opening my own PR.

If PR #75 merges first, I will avoid duplicating its production
changes and focus on the missing regression test coverage.

If PR #75 remains open, I will coordinate with its author
before submitting overlapping changes.

### Validation

I will run the Issue #72 regression test and the full
security unit test file, checking that valid bcrypt hashes
still behave correctly.

The planned changes are limited to `core/security.py`
and `tests/unit/test_security.py`

## Your branch

**Branch**

fix/72-verify-password-unknown-hash

**Evidence**

### Before the fix

Command:

```bash
python -m pytest tests/unit/test_security.py -q -k test_verify_with_wrong_hash_format --runxfail
```

Output (relevant excerpt):

```text
FAILED tests/unit/test_security.py::test_verify_with_wrong_hash_format
passlib.exc.UnknownHashError: hash could not be identified

1 failed, 24 deselected, 2 warnings
```

The original implementation raised `UnknownHashError` instead of
returning `False` for an unrecognized password hash.

### After the fix

Command:

```bash
python -m pytest tests/unit/test_security.py -q -k test_verify_with_wrong_hash_format
```

Output:

```text
1 passed, 24 deselected, 2 warnings
```

The same regression test now passes because `verify_password()`
returns `False` for an invalid password hash.

### Additional validation

I added two regression tests for malformed bcrypt hashes:
- `$2b$notarealhash`
- `$2b$12$tooshort`

Security test results:

```text
27 passed, 2 warnings
```

Full unit test results (`make test-unit`):

```text
378 passed, 52 xfailed, 3 warnings
```

Code quality checks (`make check`):
- Ruff: All checks passed.
- Black: Formatting completed.
- mypy: Success: no issues found in 76 source files.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

Run 1: 20/20 agreement (PASS).

I ran one complete evaluation using the Sonnet model.
The rubric correctly classified all 20 scored packages,
achieving 20/20 agreement with the gold labels.

All five categories passed:
- clear-accept: 7/7
- scope-creep: 4/4
- thread-convention: 2/2
- unbuildable: 3/3
- wrong-cause: 4/4

The final result matches the agreement line in eval-run.txt:
agreement: 20/20 scored items (bar: 18/20: PASS).

**Package analysis**

Package: pkg-06
Gold label: reject
My rubric verdict: reject  

My rubric rejected pkg-06 because it violates the required Scope check. The reported bug concerns saving preloaded images with containerd, which produces an empty tar file while returning exit code 0.
However, the candidate plan proposes upgrading containerd across all runtimes, introducing a unified image-operations abstraction for Docker, containerd, and CRI-O, and expanding the CI matrix.
These changes significantly broaden the implementation beyond the reported failure. Although some improvements may be useful, the plan does not sufficiently justify why such a large refactoring is necessary to resolve this specific issue.
Therefore, the Scope check fails, resulting in a reject verdict consistent with the gold label.

**Check rationale**


I selected the Scope check from my rubric.md:

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Scope | The plan's scope statement, affected components, and proposed changes compared with the issue. | The changes are bounded to the reported problem, and unrelated work is excluded or justified. | required |

I made Scope a required check because a plan can correctly
identify a bug but still propose unnecessary changes.

This check focuses on whether the proposed implementation
stays within the reported issue rather than judging the
plan's formatting.

I chose to evaluate the actual scope of the proposed changes
instead of requiring a particular document structure.

This makes the check applicable to different projects and
rejects unrelated changes unless they are justified.

**Trade-offs**

The Scope check intentionally prioritizes a focused fix over broader architectural improvements. In pkg-06, it rejects a plan that includes potentially useful changes, such as unifying image operations across runtimes, because those changes are not sufficiently justified by the reproduced bug.
This creates a trade-off: the rubric may reject ambitious improvements that could benefit the project in the long term. However, I accept this limitation because the purpose of the skill is to determine whether a plan is ready to execute for a specific issue.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
