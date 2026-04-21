---
name: novel-write
description: Novel writing execution workflow. Use when the user wants to write a chapter, scene, or prologue. Loads relevant setting materials and applies the full style guide from the project CLAUDE.md.
---

# Novel Write Workflow

Write novel content following the project's style guide and setting materials.

## Workflow

Make a todo list for all tasks in this workflow and work through them one by one.

### 1. Confirm Scope
Ask: which work, which chapter/scene, any special instructions (viewpoint, tone, length target)?

### 2. Load Relevant Settings
Load only the setting files relevant to this scene — do NOT load all files at once:
- Character files → if named characters appear
- World/location files → if specific places appear
- Plot file → if chapter position in the overall structure matters

### 3. Write
Follow all rules in the project CLAUDE.md:
- Short paragraphs, blank line between each
- Dialogue on its own line, blank lines before and after
- Emotion conveyed through action/expression, never stated directly
- `「」` for human speech, `『』` for non-human/AI/telepathy, `《》` for skill/ability names
- Furigana on difficult kanji
- Third-person limited or objective viewpoint as specified

**Target density:** ~10,000 characters per chapter. Build density within each scene — do not pad with thin atmospheric description.

### 4. Save
Save written content to `novels/<work-name>/<chapter>.md`:
- New chapter → create new file
- Continuation → append to existing file

### 5. Update Settings
If new confirmed information emerged during writing (character detail, place name, event), update the relevant setting file. Report all changes to the user.

## Wrap Up
State: what was written, how many characters, what was saved, what setting files were updated.
