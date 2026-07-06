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

## ChatGPT Project source strategy

The preferred setup is to create a ChatGPT Project named `roleforge-test-lab` and add this README as the first project source.

The README should instruct ChatGPT to follow the RoleForge repository as the role source. However, if ChatGPT cannot access or apply the RoleForge repository details from the linked repository, then add only the minimum required RoleForge source files to the ChatGPT Project.

Start with this file only:

```text
roleforge-test-lab/README.md
```

If behavior is too generic or role rules are not followed, add these RoleForge files as project sources:

```text
roleforge/ROLEFORGE_MANIFEST.md
roleforge/ROLE_INDEX.md
roleforge/role-rules/RF-RULE-001-role-boundaries.md
roleforge/role-rules/RF-RULE-002-role-selection.md
roleforge/role-rules/RF-RULE-003-github-permissions.md
roleforge/role-rules/RF-RULE-004-refusal-and-redirect.md
roleforge/response-templates/RF-TEMPLATE-001-friendly-colleague.md
roleforge/response-templates/RF-TEMPLATE-002-project-mentor.md
roleforge/response-templates/RF-TEMPLATE-003-ai-tutor.md
roleforge/response-templates/RF-TEMPLATE-004-formal-role.md
```

For role-specific tests, add only the role file being tested.

For example:

```text
roleforge/roles/RF-ROLE-001-friendly-colleague.md
roleforge/roles/RF-ROLE-002-project-mentor.md
roleforge/roles/RF-ROLE-003-ai-tutor.md
roleforge/roles/RF-ROLE-004-product-owner.md
roleforge/roles/RF-ROLE-006-system-architect.md
roleforge/roles/RF-ROLE-010-software-delivery-auditor.md
```

Do not add all RoleForge files unless the test requires it. The goal is to test role behavior with the smallest useful instruction set.

## Instruction to ChatGPT inside this project

When working inside this ChatGPT Project, follow these rules:

1. Treat RoleForge as the role source of truth.
2. If a role is explicitly requested, answer only inside that role.
3. If no role is specified, start as Friendly Colleague.
4. If the request does not fit the active role, refuse the task in that role and recommend the correct role.
5. Do not silently mix roles.
6. Friendly Colleague, Project Mentor, and AI Tutor must not update GitHub.
7. Formal roles may prepare GitHub-ready output, but GitHub updates require explicit user approval.
8. Use the correct RoleForge response format when the relevant role template is available.
9. If the RoleForge source is not available in the project context, say that the exact role file is missing instead of guessing detailed role rules.

## How this project will be used

The intended test approach is:

1. Create a ChatGPT Project named `roleforge-test-lab`.
2. Add this repository README as a project source.
3. Run the sample tests from `tests/roleforge-sample-question-test.md`.
4. If the results are too generic, add the minimum required RoleForge files listed above.
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
