# AGENTS.md

## Purpose

This file provides guidance for AI coding agents working in this repository.

Agents should follow these instructions to ensure the codebase remains:

- predictable
- maintainable
- consistent with the existing site structure
- safe for collaborative development

This repository is a **static website** for `n8v.dev`.
It currently consists of HTML pages, shared CSS, and image assets.

---

# Instruction Priority

If instructions conflict, follow this priority order:

1. **Direct instructions from the human developer**
2. **Repository documentation (`README.md`, `AGENTS.md`)**
3. **Existing page structure and code patterns**
4. **Agent judgment**

---

# Repository Shape

Current repo structure is simple:

- top-level static pages such as `index.html`, `about/index.html`, `support/index.html`
- product and concept pages such as `the-monster-math/`, `the-monster-match/`, and `commerce/schools/`
- shared styles in `storage/assets/styles/`
- shared images in `storage/assets/images/`

Agents should not assume there is an app backend, API layer, contracts folder, or `src/` directory unless those are actually added later.

---

# Repo Reconnaissance Before Coding

Before making large changes, agents should:

1. Inspect the relevant page and shared stylesheet
2. Check nearby pages for consistency in tone and structure
3. Confirm that referenced assets and links actually exist
4. Summarize understanding if the change is complex

Agents must not invent non-existent architecture or refer to files and folders that are not in this repository.

---

# Safe Change Policy

Agents should prefer **minimal, focused changes**.

Preserve the current static-site approach unless the human developer explicitly asks for a structural change.

Do NOT:

- refactor unrelated files
- rename large sections without approval
- move large directory structures
- rewrite working systems without justification

If a change is risky or large:

- explain the risk
- ask the developer before proceeding

---

# Content And UX Expectations

- Keep copy clear, concrete, and aligned with the existing brand voice.
- Reuse the current visual language and shared CSS where possible.
- Improve semantics and scanability when helpful, but avoid unnecessary redesign.
- Make sure internal links, asset paths, and page routes remain valid.

---

# Verification Expectations

When making changes:

- review the edited HTML for broken links or missing assets
- confirm any referenced files or routes exist in the repo
- state clearly if no automated tests exist for the change

Agents must not claim something works **without validating it**.

If tests cannot be run, state this clearly.

---

# Documentation Expectations

Agents should keep the repository clear.

If changes affect behavior or workflows:

- update relevant documentation
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

# Definition of Done

A change is considered complete when:

- the implementation matches the requested change
- links and referenced assets have been checked
- tests are updated if applicable, or the absence of tests is stated clearly
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
- consistent page structure
- well-defined content and behavior
- minimal complexity

Prefer the simplest implementation that fits the existing site.

Avoid unnecessary abstraction.

---

# Final Rule

If unsure about architecture, behavior, or safety:

**Ask the human developer before proceeding.**
