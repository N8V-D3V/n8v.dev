# Contract-Oriented Programming (COP) - Agent Manifesto

Version: 0.3.0

---

## Core Directive

You are operating within a system that follows Contract-Oriented Programming (COP).

Follow these rules strictly when defining or changing system behavior.

---

## 1. Contracts Are The Source Of Truth

- Contracts define system behavior.
- Do not introduce behavior not defined in the contract.
- If the contract is unclear, ask for clarification or record an open question.

---

## 2. Do Not Skip Layers

Respect the COP structure:

1. Contracts
2. Protocols
3. Modules
4. Orchestrators
5. Validation

Do not:

- implement modules without a contract when the work is COP-governed
- bypass protocols
- create hidden dependencies
- replace defined behavior with implementation guesses

---

## 3. Keep Implementation Details Out Of Contracts

When working on contracts:

- do not include frameworks
- do not reference APIs
- do not define code-level structures

Contracts describe behavior only.

---

## 4. Respect Defined Inputs And Outputs

- Do not add undocumented inputs.
- Do not produce undocumented outputs.
- All data flow must be explicitly defined.

---

## 5. Failure Modes Are Required

Every system must define:

- what can go wrong
- how the system responds

Do not assume a happy path only.

---

## 6. Do Not Invent Missing Behavior

If something is not defined:

- do not guess
- do not assume
- ask for clarification or mark it as an open question

---

## 7. Follow Constraints Strictly

Constraints defined in contracts must not be violated.

---

## 8. Prefer Explicitness Over Cleverness

Be clear, predictable, and consistent.

Avoid:

- hidden logic
- implicit assumptions
- unnecessary abstraction

---

## 9. Validation Is Required

When reviewing or implementing:

- compare output against the contract
- identify mismatches
- report violations

---

## 10. Produce Structured Outputs

When working in COP:

- follow defined templates
- produce complete artifacts
- ensure outputs are usable by other agents

---

## 11. Prefer Feature-Based Structure

Implementation should be organized around features and capabilities, not generic technical categories.

Avoid defaulting to folders such as:

- `models/`
- `services/`
- `utils/`
- `controllers/`

Prefer feature boundaries that correspond to contracts or capabilities.

---

## 12. Align Structure To Contracts

Where possible:

- each contract should map to a feature or module boundary
- code organization should reflect contract boundaries
- related logic should live together within the same feature

---

## 13. Stub-First Development

COP-governed modules should first be implemented as stubs.

A stub implementation:

- must conform to the protocol interface
- must simulate contract-defined behavior
- must log inputs, outputs, and decisions where logging exists
- must not perform real computation or external integration

---

## 14. Follow The COP Execution Cycle

Use this sequence:

1. Contract Alignment
2. Stub Module Implementation
3. Stub System Demo
4. Real Implementation
5. Validation

---

## 15. Enforce Green Flag Progression

Do not proceed to the next stage unless the current stage is validated.

Contract Alignment green flag:

- contracts are complete, consistent, and unambiguous

Stub Demo green flag:

- system runs end-to-end using stub modules
- behavior matches contract expectations

Implementation green flag:

- real system produces correct outputs
- behavior matches the validated stubbed system

If any stage fails, return to the previous stage and correct the issue.

---

## 16. Preserve Behavioral Consistency

Real implementations must not introduce new behavior.

- Stub behavior defines expected system behavior.
- Implementation must match that behavior.
- Any intentional behavior change must start with the contract.

---

## Summary

Structure must reflect behavior, not technical categories.

You are not just building code.

You are validating system behavior step by step before making it real.
