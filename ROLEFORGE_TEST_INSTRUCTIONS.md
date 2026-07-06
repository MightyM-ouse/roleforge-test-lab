# RoleForge Test Instructions

## Purpose

This document explains how to test RoleForge behavior inside the `roleforge-test-lab` ChatGPT Project.

## Source of role behavior

RoleForge is the source of truth for role behavior:

```text
https://github.com/MightyM-ouse/roleforge
```

The test lab should not invent new role rules. It should test whether ChatGPT follows the existing RoleForge role definitions.

## Test setup in ChatGPT Projects

Recommended setup:

1. Create a ChatGPT Project named `roleforge-test-lab`.
2. Add this repository README as a project source.
3. Add `ROLEFORGE_TEST_INSTRUCTIONS.md` as a project source.
4. Add RoleForge source files as project sources, especially:
   - `ROLEFORGE_MANIFEST.md`
   - `ROLE_INDEX.md`
   - the role files being tested
   - relevant files from `role-rules/`
   - relevant files from `response-templates/`
5. Run the sample questions from `tests/roleforge-sample-question-test.md`.
6. Record actual behavior in `results/test-results-log.md`.

## Important test rule

This test project does not require `AGENTS.md`.

Reason:

This test is focused on ChatGPT Project behavior, not on repository-based coding-agent behavior.

`AGENTS.md` may be useful later for Codex or other repo-based agents, but it is not required for this test cycle.

## What to test

Each test should check:

1. Did ChatGPT use the correct RoleForge role?
2. Did ChatGPT stay inside that role?
3. Did ChatGPT refuse or redirect wrong-role requests?
4. Did ChatGPT follow the role response format?
5. Did ChatGPT respect GitHub permission rules?
6. Did ChatGPT avoid silently mixing roles?

## Result values

Use one of these results for each test:

```text
Pass
Pass with notes
Fail
Blocked
```

## Readiness decision

After all tests are completed, decide whether RoleForge is:

```text
Ready
Ready with conditions
Not ready
```

## Minimum passing expectation

RoleForge should not be used in Magna Enso until the first test cycle passes or all required fixes are documented.
