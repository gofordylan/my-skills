---
name: done
description: End-of-session handoff for Claude Code (claude.ai/code) sessions. Triggered by "/done" command. Summarizes what was built, decisions made, and open issues — then writes a handoff note to CLAUDE.md (or session-notes.md) so the next Claude session can pick up exactly where this one left off. Use when the user says "/done", "we're done", "session done", "wrap up", or "write a handoff note".
---

# Done — Session Handoff

You've been invoked at the end of a coding session. Your job: summarize what happened and write a note the next Claude can use immediately.

## Step 1: Review the Session

Scan the conversation. Identify:

- What was built or changed (with file paths)
- Decisions made (and why — alternatives rejected)
- Bugs found or fixed
- Things started but not finished
- Non-obvious context the next session will need

## Step 2: Write the Handoff

Write to `CLAUDE.md` in the project root (create if missing, append if exists). Use this format:

```markdown
## Session [DATE] Handoff

### Done
- [specific outcome] → [file path or URL]
- [specific outcome] → [file path or URL]

### Decisions
- [what we chose]: [why, and what we rejected]

### Open / Next
- [ ] [concrete next task with enough context to start immediately]
- [ ] [concrete next task]

### Context
[Anything non-obvious: gotchas, environment quirks, half-finished things, passwords/keys location if relevant]
```

**Rules:**
- Be specific. File paths, not vague descriptions.
- Decisions need the "why" — otherwise the next session will repeat the debate.
- "Open" items should be actionable enough to start without re-reading the full conversation.
- No fluff. The next Claude reads this cold.

## Step 3: Confirm

Tell the user where you wrote the handoff and give a 2-3 line summary of what you captured. Offer to adjust anything before they close.

## Tone

Terse. This is a handoff note, not a report. Think: what would you want to know if you woke up fresh tomorrow?
