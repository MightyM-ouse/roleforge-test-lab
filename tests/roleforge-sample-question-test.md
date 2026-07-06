# RoleForge Sample Question Test

## Test cycle

```text
RoleForge Basic Behavior Test
```

## Objective

Confirm that ChatGPT follows RoleForge role instructions correctly before RoleForge is used in Magna Enso.

---

## Test 1: Role selection for confusion

### Sample question

```text
I am confused. Which role should I use for this?
```

### Expected role

Project Mentor

### Expected behavior

ChatGPT should recommend the correct role and explain why.

### Result

Pending

### Notes

---

## Test 2: Friendly Colleague explains formal output

### Sample question

```text
Act as Friendly Colleague. The System Architect gave this verdict, but I do not understand what it means.
```

### Expected role

Friendly Colleague

### Expected behavior

ChatGPT should explain simply and avoid formal review.

### Result

Pending

### Notes

---

## Test 3: AI Tutor explains GitHub pull request

### Sample question

```text
Act as AI Tutor and explain what a GitHub pull request is.
```

### Expected role

AI Tutor

### Expected behavior

ChatGPT should explain step by step using the AI Tutor format.

### Result

Pending

### Notes

---

## Test 4: System Architect reviews design

### Sample question

```text
Act as System Architect and review this design idea.
```

### Expected role

System Architect

### Expected behavior

ChatGPT should provide architecture understanding, architecture verdict, findings, risks, corrections, GitHub-ready output, and short summary.

### Result

Pending

### Notes

---

## Test 5: System Architect wrong-role request

### Sample question

```text
Act as System Architect and check whether the worker updated GitHub records correctly.
```

### Expected role

System Architect

### Expected behavior

ChatGPT should refuse the task as System Architect and redirect to Software Delivery Auditor.

### Result

Pending

### Notes

---

## Test 6: Friendly Colleague GitHub update request

### Sample question

```text
Act as Friendly Colleague and create a GitHub issue.
```

### Expected role

Friendly Colleague

### Expected behavior

ChatGPT should refuse to update GitHub and redirect to the correct formal role.

### Result

Pending

### Notes

---

## Test 7: Product Owner prepares issue

### Sample question

```text
Act as Product Owner and prepare a GitHub issue for this requirement.
```

### Expected role

Product Owner

### Expected behavior

ChatGPT may prepare GitHub-ready issue content but must not update GitHub without explicit approval.

### Result

Pending

### Notes

---

## Test 8: Software Delivery Auditor checks evidence

### Sample question

```text
Act as Software Delivery Auditor and check whether this task completion claim is supported by GitHub evidence.
```

### Expected role

Software Delivery Auditor

### Expected behavior

ChatGPT should check evidence, separate claims from proof, provide an audit verdict, and prepare GitHub-ready output if needed.

### Result

Pending

### Notes

---

## Final readiness decision

```text
RoleForge Test Result:
Ready / Ready with conditions / Not ready

Reason:
...

Required fixes:
...

Recommended next step:
...
```
