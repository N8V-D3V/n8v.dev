# Contract Template Usage Rules

Version: 0.3.0

---

## Purpose

This document defines how contracts must be written.

The goal is to ensure:

- clarity
- consistency
- AI compatibility
- enforceable behavior definitions

---

## Rule 1: No Implementation Details

Do not include:

- frameworks
- APIs
- databases
- code structures

Contracts define behavior only.

---

## Rule 2: Be Explicit

Avoid vague language.

Bad:

> Handle errors gracefully.

Good:

> If the ticket is expired, the system must return `EXPIRED_TICKET`.

---

## Rule 3: Define All Inputs And Outputs

Nothing should be implicit.

Every input and output required for correct behavior must be named and described.

---

## Rule 4: Define Failure Modes

Failure is not optional.

For every feature:

- list what can go wrong
- define the system response

---

## Rule 5: Cover Edge Cases

Think beyond the happy path.

Edge cases should be explicit enough that another agent can validate them.

---

## Rule 6: Keep Contracts Minimal But Complete

Do not:

- over-engineer
- add unnecessary detail

Do:

- include everything required for correct behavior
- keep behavior understandable

---

## Rule 7: Use Consistent Structure

Always follow `docs/cop/contract-template.md`.

---

## Rule 8: Use Testable Acceptance Criteria

Every acceptance criterion must be verifiable.

Avoid criteria that depend on taste, intent, or implied judgment unless those standards are explicitly defined.

---

## Rule 9: Do Not Invent Behavior

If something is unclear:

- add it to Open Questions
- do not assume

---

## Rule 10: Contracts Evolve

Contracts are not static.

They should be:

- refined
- updated
- improved based on real usage

Behavior changes should start by updating the contract.

---

## Summary

A good contract is:

- clear
- complete
- testable
- free of implementation detail

If an AI can reasonably misinterpret it, it is not good enough yet.
