# RoleForge Test Lab

## Purpose

RoleForge Test Lab is a sandbox project used to test whether ChatGPT follows RoleForge role instructions correctly before RoleForge is adopted in real projects such as Magna Enso.

This repository does not contain production code. It exists only to test role behavior, role boundaries, response formats, GitHub permission behavior, and role handoff behavior.

## RoleForge source

Role definitions are maintained in the RoleForge repository:

```text
https://github.com/MightyM-ouse/roleforge
```

This test project does not redefine RoleForge roles. It uses RoleForge as the source of role behavior.

## How this project will be used

The intended test approach is:

1. Create a ChatGPT Project named `roleforge-test-lab`.
2. Add this repository README as a project source.
3. Add the required RoleForge files as project sources when needed.
4. Run the sample tests from `tests/roleforge-sample-question-test.md`.
5. Record results in `results/test-results-log.md`.
6. Decide whether RoleForge is ready for controlled adoption in Magna Enso.

## What this project tests

This test lab checks whether ChatGPT can:

1. Select the correct RoleForge role.
2. Stay inside the selected role boundary.
3. Refuse or redirect when the request does not fit the active role.
4. Follow the expected response format.
5. Respect GitHub permission rules.
6. Avoid silently mixing roles.
7. Explain formal role output in simple language when asked through the correct role.

## First test cycle roles

The first test cycle should focus on these roles:

1. Friendly Colleague
2. Project Mentor
3. AI Tutor
4. Product Owner
5. System Architect
6. Software Delivery Auditor

The remaining roles can be tested in later cycles.

## Success criteria

RoleForge is ready for controlled project adoption when:

1. ChatGPT selects the correct role for common requests.
2. ChatGPT refuses work that does not belong to the active role.
3. Friendly Colleague, Project Mentor, and AI Tutor do not update GitHub.
4. Formal roles prepare GitHub-ready output only inside their role boundary.
5. Formal roles do not update GitHub without explicit approval.
6. Responses follow the defined RoleForge templates.
7. Role handoffs are clear and practical.

## Out of scope

This repository does not test:

1. Magna Enso implementation.
2. Production code.
3. Runtime automation.
4. RoleForge skills.
5. Multi-agent orchestration.
6. Direct adoption into Magna Enso.

## Recommended readiness decision

At the end of a test cycle, classify RoleForge as one of the following:

```text
Ready
Ready with conditions
Not ready
```

The decision must include the reason and any required fixes before Magna Enso adoption.
