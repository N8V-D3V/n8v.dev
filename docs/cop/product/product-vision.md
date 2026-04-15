# Product Vision: Contract-Oriented Programming

Version: 0.1.0

---

## Overview

Contract-Oriented Programming (COP) is a behavior-first way to build software with AI.

COP gives the system shape before implementation begins: define the behavior, prove the flow in stub form, then let implementation catch up.

---

## Purpose

AI can write code quickly, but it cannot define the system by itself.

COP exists to keep behavior visible while development moves fast. Contracts define what matters, stubs prove the flow, and implementation fills in the details without quietly redefining the system along the way.

---

## Goals

- Define behavior before implementation.
- Give humans and AI a shared source of truth.
- Make the full system flow demoable before real internals are finished.
- Let implementation replace stubs without changing agreed behavior.
- Keep systems understandable as they grow across domains and agents.

---

## Non-Goals

- COP is not intended to replace engineering judgment.
- COP is not intended to require a full system redesign before it can be tried.
- COP is not tied to one language, framework, or application architecture.
- COP is not a license for excessive documentation.

---

## Core Capabilities

- Contracts define expected behavior, inputs, outputs, success, failure, and constraints.
- Protocols define capabilities without locking the system to one implementation too early.
- Modules implement capabilities and satisfy contracts.
- Orchestrators coordinate modules through a controlled, testable flow.
- Stubs simulate the full system flow before production logic exists.
- Validation compares the built system against contract-defined behavior.

---

## Development Cycle

1. Contract Alignment: agree on what the system must do before implementation starts.
2. Stub Demo: make the system run end-to-end in stub form.
3. Implementation: replace stubs with production logic while preserving behavior.
4. Iteration: refine contracts, improve modules, and keep validating the full flow.

---

## Constraints

- Behavior must be clear before implementation begins.
- Contracts must remain the source of truth for behavior.
- Stubs must not perform real production logic or external integration.
- Real implementations must not introduce behavior not defined by contracts.
- Ambiguity must be handled through clarification or Open Questions, not assumption.

---

## Real Project Context

COP is being shaped through real project use.

Examples reflected in the public site:

- PerchNotes uses COP to shape an image-to-notes-to-audio pipeline before each module is fully wired.
- Kanati and Selu use COP to support a connected POS and ticketing ecosystem across multiple domains.

---

## Open Questions

- Which n8v.dev website features should receive formal contracts first?
- Should public COP site content and internal COP docs remain separate, or should one generate from the other later?
- What contract examples should be added to help future agents apply COP in this repository?
