---
name: program-design
description: Software architecture and design workflow. Use when the user wants to design a system, plan architecture, define APIs, design data models, or create technical specifications before writing any code.
---

# Program Design Workflow

Produce a concrete, reviewable design document through structured analysis before any code is written.

## Workflow

Make a todo list for all tasks in this workflow and work through them one by one.

### 1. Interpret the Request (sub-agent)
Before doing anything else, spawn a sub-agent to rephrase the user's request from three angles:
- **Literal**: what was literally asked
- **Intent**: what problem they're actually trying to solve
- **Edge cases**: what was not said but probably matters

Present these three interpretations to the user and confirm which is correct before proceeding. If the interpretations reveal ambiguity, ask the clarifying question directly.

### 2. Gather Requirements
Ask focused questions until these are answered:
- What problem does this solve, and for whom?
- What are the performance, scale, or availability requirements?
- What constraints exist — language, framework, existing systems, team familiarity, timeline?
- What does "done" look like? How will success be measured?

Do NOT proceed until requirements are clear.

### 3. Define Scope
State explicitly before designing:
- What is IN scope
- What is OUT of scope
- What assumptions are being made (write these down — they become risks)

### 4. Explore Design Options
For non-trivial decisions (architecture pattern, data model, API style, tech stack), present 2–3 options:

| Option | Summary | Pros | Cons | Best when |
|--------|---------|------|------|-----------|
| A | ... | ... | ... | ... |
| B | ... | ... | ... | ... |

Do not pick for the user. Present the trade-off clearly and ask for a decision.

### 5. Produce Design Document
After direction is confirmed, write a structured design document.
Save to `docs/design/<feature-name>.md`. Create the directory if it doesn't exist.

Required sections:
```
## Overview
One paragraph: what this is and what problem it solves.

## Architecture
System structure, component responsibilities, data flow.
Include a diagram in ASCII or Mermaid if the structure is non-trivial.

## Data Model
Entities, fields, types, relationships. Use a table or schema notation.

## API / Interface
Endpoints or function signatures. Input/output types. Error cases.

## Error Handling Strategy
What errors are expected. How each is handled. What surfaces to the user.

## Open Questions
Unresolved decisions, risks, things that need validation.
```

### 6. Sub-Agent Design Review
Spawn a reviewer sub-agent with the role of a skeptical senior engineer.
The reviewer's job is NOT to validate the design — it is to find problems.

Review criteria:
- Does the design actually solve the stated problem?
- Are there obvious failure modes or race conditions not addressed?
- Is there unnecessary complexity that could be eliminated?
- Are the trade-offs documented and intentional, or just accepted without thought?
- Does the error handling cover realistic failure scenarios?
- Are the open questions truly open, or are answers already implied?

If the review finds significant issues: revise the design and run a second review pass.
If minor issues only: address inline and note what was changed.

### 7. Present Final Design
Summarize for the user:
- Key architectural decisions and the reasoning behind them
- Trade-offs explicitly accepted
- Risks and open questions remaining
- Recommended next steps for implementation

## Wrap Up
State: design document saved to (path), review passed/revised, open questions count, recommended implementation order.
