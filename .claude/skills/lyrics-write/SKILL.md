---
name: lyrics-write
description: Lyrics writing execution workflow. Use when the user wants to write the actual lyrics of a song. Checks for an existing design file and writes within that structure.
---

# Lyrics Write Workflow

Write lyrics based on an existing design, or a quick brief if no design exists.

## Workflow

Make a todo list for all tasks in this workflow and work through them one by one.

### 1. Load Design
Check if `lyrics/<song-name>/design.md` exists:
- If yes → load it and confirm we're following this structure
- If no → run a 2-question quick brief (emotional core + speaker) before writing

### 2. Write
- Match the tone, rhythm feel, and imagery style the user has indicated
- Preserve intentional line breaks and breathing points
- Avoid clichés; favor concrete, specific images over abstract statements
- Each section must carry a distinct emotional register that advances the arc
- The hook/chorus should be the most memorable and concentrated expression of the core theme

### 3. Offer Variants for Key Lines
For the title line, hook, or any line with low confidence — offer 2–3 alternatives.

### 4. Save
Save to `lyrics/<song-name>/lyrics.md`.
Create the directory if it doesn't exist.

## Wrap Up
State: what was written, what was saved, and which lines the user may want to revisit.
