---
name: research
description: Structured research workflow for daily inquiries. Use when the user wants to research a topic, compare options, verify information, or get a structured overview of any subject.
---

# Research Workflow

Research a topic and deliver a structured, actionable report.

## Workflow

Make a todo list for all tasks in this workflow and work through them one by one.

### 1. Clarify Scope
Ask: what is the purpose of this research?
- **Overview** — general background knowledge
- **Decision support** — comparing options to choose between them
- **Fact verification** — checking whether a specific claim is accurate
- **Deep dive** — detailed exploration of one specific aspect

If the user's question already makes the purpose clear, skip this step.

### 2. Research
Use WebSearch and WebFetch to gather information.
Prioritize: primary sources, official documentation, recent information (within 2 years).
Cross-reference at least 2 sources for any factual claim.

### 3. Deliver Report
Format based on the declared purpose:

**Overview:**
```
## [Topic]
### Summary (2–3 sentences)
### Key points
- ...
### Sources
```

**Decision support:**
```
## [Option A] vs [Option B]
| Dimension | A | B |
|---|---|---|
### Recommendation + reasoning
```

**Fact verification:**
```
## Claim: [claim]
### Verdict: Confirmed / False / Nuanced
### Evidence
### Sources
```

**Deep dive:**
Use sections appropriate to the topic. Cite all sources inline.

### 4. Flag Uncertainty
Explicitly mark any information that could not be cross-verified, may be outdated, or relies on a single source.

## Wrap Up
State: what was found, confidence level, and whether further research is recommended.
