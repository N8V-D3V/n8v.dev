# AGENTS.md

## Purpose

This file provides guidance for AI coding agents working in this repository.

Agents should follow these instructions to ensure the codebase remains:

- predictable
- maintainable
- consistent with system architecture
- safe for collaborative development

This repository follows **Contract-Oriented Programming (COP)**.  
Agents must understand and respect this architecture before making changes.

---

# Instruction Priority

If instructions conflict, follow this priority order:

1. **Direct instructions from the human developer**
2. **Contracts in `docs/contracts/`**
3. **Repository documentation (`README.md`, `AGENTS.md`, `docs/`)**
4. **Existing architecture and code patterns**
5. **Agent judgment**

Contracts always override implementation details.

If the code and contracts disagree, **the contract is the source of truth**.

---

# Contract-Oriented Programming (COP)

This project follows **Contract-Oriented Programming (COP)**.

COP separates **system behavior** from **system implementation**.

## Core Principle

> Contracts define what the system does.  
> Code implements how the system does it.

Contracts must be human-readable and act as the **source of truth** for system behavior.

---

## COP Structure

Typical project structure:

```
docs/contracts/
    sale.md
    ticket_sales.md
    inventory_tracking.md
    reporting.md

src/
    protocols/
    modules/
    orchestrators/
```

---

## Contracts

Contracts describe:

- system behavior
- inputs
- outputs
- success conditions
- failure conditions
- side effects
- events produced

Contracts **must not contain implementation details**.

Contracts should be understandable by humans without reading code.

Example contract sections:

```
# Purpose
# Inputs
# Outputs
# Success Behavior
# Failure Behavior
# Side Effects
# Events
```

---

## Protocols

Protocols define **capabilities required to fulfill contracts**.

Protocols represent *interfaces*, not implementations.

Example:

```
PaymentProcessor
InventoryProvider
TicketValidator
FactProvider
```

Protocols must **not** be named after contracts.

Avoid names like:

```
SaleContract
TicketContract
```

Instead use capability-based names.

---

## Modules

Modules fulfill contracts by implementing protocols.

Rules for modules:

- modules are **self-contained**
- modules hide internal implementation
- modules expose behavior through protocols
- modules should be replaceable

Modules **must not directly depend on other modules' internals**.

---

## Orchestrators

Orchestrators coordinate modules.

Responsibilities:

- manage workflows
- connect modules through protocols
- enforce system-level behavior

Rules:

- modules should **not call other modules directly**
- orchestration logic should **not live inside modules**

---

# Contract-First Change Policy

Agents must follow **contract-first development**.

If a change affects system behavior:

1. Update or create the contract first
2. Then update implementation

Agents must **not silently change behavior in code** without updating the contract.

If a relevant contract does not exist:

- propose a contract
- ask the developer for approval before proceeding

---

# Architecture Rules

Agents must respect these architectural boundaries.

### Modules must not:

- reach into other modules’ internals
- depend on implementation details
- create hidden coupling

### Modules should:

- depend on protocols/interfaces
- expose clear capabilities
- remain replaceable

### Avoid:

- god services
- global mutable state
- hidden dependency injection frameworks
- framework "magic" when explicit wiring is clearer

Prefer **explicit dependencies**.

---

# Repo Reconnaissance Before Coding

Before making large changes, agents should:

1. Read relevant contracts
2. Inspect nearby files and patterns
3. Identify existing architecture
4. Summarize understanding if the change is complex

Agents must **not invent architecture that conflicts with the existing system**.

---

# Safe Change Policy

Agents should prefer **minimal, focused changes**.

Do NOT:

- refactor unrelated files
- rename large sections without approval
- move large directory structures
- rewrite working systems without justification

If a change is risky or large:

- explain the risk
- ask the developer before proceeding

---

# Testing Expectations

When behavior changes:

- update or add tests where possible
- ensure tests reflect contract behavior

Agents must not claim something works **without validating it**.

If tests cannot be run, state this clearly.

---

# Documentation Expectations

Agents should keep the repository clear.

If changes affect behavior or workflows:

- update relevant documentation
- update contracts
- note assumptions
- highlight open questions

Avoid creating stale documentation.

---

# Git Safety Rules

Agents must **never perform destructive or permanent repository actions without approval**.

This includes:

- committing
- pushing
- merging
- rebasing
- force pushing
- deleting branches
- rewriting history

### Required Workflow

After making changes:

1. Show the developer what was changed
2. Provide a summary
3. Wait for approval before committing
4. Wait for approval before pushing

Agents should treat commit/push operations as **human-authorized actions only**.

---

# Secrets and Environment Variables

Agents must never:

- expose secrets
- log credentials
- fabricate environment variables

If environment variables are required:

- document them clearly
- ask before modifying configuration

---

# Database and Migration Safety

Agents must ask before performing:

- destructive schema changes
- irreversible migrations
- large backfills
- data deletions

Prefer **additive migrations** when possible.

Explain production impact before proposing schema changes.

---

# Definition of Done

A change is considered complete when:

- contracts are aligned
- implementation matches contracts
- tests are updated (if applicable)
- documentation is updated
- no commit or push has occurred
- the agent has summarized the work

---

# Agent Response Format

When completing a task, agents should respond with:

### Summary
What was implemented.

### Files Changed
List of files modified.

### Reasoning
Why the change was necessary.

### Risks / Assumptions
Anything uncertain or potentially risky.

### Next Steps
Anything that may need follow-up.

---

# Development Philosophy

This repository values:

- clarity over cleverness
- explicit dependencies
- replaceable modules
- well-defined system behavior
- minimal complexity

Prefer the **simplest implementation that satisfies the contract**.

Avoid unnecessary abstraction.

---

# Final Rule

If unsure about architecture, behavior, or safety:

**Ask the human developer before proceeding.**
