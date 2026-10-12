# Fix Plan: Issue #72 — Handle Unknown Password Hash Formats

## Issue

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72

## Diagnosis

The `verify_password()` function in `core/security.py` directly
calls `pwd_context.verify()` without handling `UnknownHashError`.

When the supplied hash is not recognized as a valid bcrypt hash,
Passlib raises `UnknownHashError` instead of returning a boolean.

As a result, `verify_password()` propagates the exception even
though its documented behavior is to return `True` or `False`.

## Reproduction Evidence

Environment:
- Python 3.11.9
- Project dependencies installed from `pyproject.toml`

Command:

`python -m pytest tests/unit/test_security.py -q -k test_verify_with_wrong_hash_format --runxfail`

Observed result:

`FAILED tests/unit/test_security.py::TestSecurity::test_verify_with_wrong_hash_format`

Exception:

`passlib.exc.UnknownHashError: hash could not be identified`

Summary:

`1 failed, 24 deselected, 2 warnings in 0.83s`

Expected behavior:
- `verify_password("password", "not_a_valid_bcrypt_hash")`
  returns `False` without raising an exception.

## Scope

In scope:
- `core/security.py`: Handle `UnknownHashError` in
  `verify_password()`.
- `tests/unit/test_security.py`: Remove the strict `xfail`
  marker from the existing regression test after the fix.

Out of scope:
- Changing password hashing algorithms.
- Changing JWT authentication.
- Refactoring unrelated security utilities.
- Changing the behavior of valid bcrypt password verification.

## Implementation Steps

1. Wrap the existing `pwd_context.verify()` call in a
   `try/except ValueError` block.
2. Return `False` when `ValueError` occurs, including
   `UnknownHashError`, which is a subclass of `ValueError`.
3. Preserve the existing return value for valid bcrypt hashes.
4. Remove the strict `xfail` marker from
   `test_verify_with_wrong_hash_format`.
5. Add regression tests for malformed bcrypt hashes:
   - `$2b$notarealhash`
   - `$2b$12$tooshort`

## Test Plan

1. Run the existing regression test for Issue #72.
   Expected: the test passes and returns `False` for an
   unrecognized hash format.

2. Run the security unit test file:
   `python -m pytest tests/unit/test_security.py -q`

   Expected: existing password hashing, password verification,
   and JWT-related tests continue to pass.

3. Verify that a correct password with a valid bcrypt hash
   still returns `True`.

4. Verify that an incorrect password with a valid bcrypt hash
   still returns `False`.

5. Record the before-fix and after-fix test results.

6. Add and run regression tests for:
   - `$2b$notarealhash`
   - `$2b$12$tooshort`

   Expected: both return `False` without raising ValueError.

## Risks and Unknowns

The original reproduction raises `UnknownHashError`, but
additional malformed bcrypt hashes raise `ValueError`.

I independently reproduced both cases:

- `$2b$notarealhash` raises `ValueError`:
  "not enough values to unpack (expected 2, got 1)"
- `$2b$12$tooshort` raises `ValueError`:
  "salt too small (bcrypt requires exactly 22 chars)"

Since `UnknownHashError` inherits from `ValueError`,
catching `ValueError` covers all three reproduced cases.

The exception handler will be limited to the password
verification call. Unexpected exceptions outside this
category will not be suppressed.

GitHub Issue #72 already has an open PR #75 proposing
a ValueError-based fix. Before implementation, I will
review that PR and coordinate through the issue thread
to avoid duplicating existing work.

## Deviations

None yet. Any changes from this plan during implementation
will be documented here.