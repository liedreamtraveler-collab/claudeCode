---
name: program-dev
description: Program development execution workflow. Use when the user wants to implement code based on a design, specification, or direct request. Interprets requirements, writes clean code, verifies correctness, and commits.
---

# Program Dev Workflow

Implement code correctly and cleanly, with verification before delivery.

## Workflow

Make a todo list for all tasks in this workflow and work through them one by one.

### 1. Interpret the Request (sub-agent)
Spawn a sub-agent to analyze the implementation request from three angles:
- **Literal**: what was literally asked to implement
- **Intent**: what behavior the user actually wants the code to produce
- **Constraints**: what must NOT break — existing behavior, interfaces, dependencies

If the three interpretations differ meaningfully, surface the ambiguity to the user before writing a single line of code.
If they align, proceed.

### 2. Load Context
Read the relevant files before writing anything:
- Design document if it exists (`docs/design/<feature>.md`)
- Existing code that will be modified or called
- Tests that cover related behavior
- README or project-level CLAUDE.md for coding conventions

Do NOT write code without understanding what already exists.

### 3. Plan the Implementation
Before writing, state the implementation plan:
- Which files will be created or modified
- What the core logic will do (in plain language)
- What edge cases will be handled
- What will NOT be handled (explicit scope boundary)

For non-trivial implementations, confirm the plan with the user before proceeding.

### 4. Implement
Write code following these principles:
- Match the style and conventions of the existing codebase
- No unnecessary abstractions — solve the problem at hand, don't design for hypothetical futures
- No dead code, commented-out blocks, or placeholder TODOs in committed code
- No comments explaining WHAT the code does — only add a comment if the WHY is non-obvious
- Handle only the error cases that can actually happen; don't add defensive code for impossible states
- Security: never concatenate user input into shell commands or SQL; validate at system boundaries

### 5. Verify
Before declaring done, verify:
- Run existing tests. If they fail, fix the code (not the tests, unless the tests were wrong).
- Manually trace through the happy path and at least one failure path
- Check that nothing obviously regresses in files you touched

If the project has a linter or type checker, run it.

### 6. Sub-Agent Code Review
Spawn a reviewer sub-agent with the role of a code reviewer doing a PR review.
The reviewer reads the diff and evaluates:
- Does the code do what was asked?
- Are there bugs, off-by-one errors, or missing null checks?
- Is there dead code or unnecessary complexity?
- Are there security issues (injection, unvalidated input, exposed secrets)?
- Does it match the project's existing style and conventions?
- Are there missing edge cases that should be handled?

If the review finds bugs or security issues: fix them and re-review.
If the review finds style/complexity issues: fix if straightforward, note if trade-off.

### 7. Commit
Stage only the files that belong to this change. Write a commit message that explains WHY, not WHAT:
- One-line summary (≤72 characters)
- Body if the change is non-obvious: what problem it solves, what approach was chosen, what trade-offs were made

Do NOT commit:
- `.env` files or anything containing secrets
- Generated files that shouldn't be versioned
- Unrelated changes

## Wrap Up
State: what was implemented, what files were changed, test results, review outcome, commit hash.
