---
name: session-review
description: Review and improve prompting skills mid-session or at session end. Trigger with "review my prompts", "prompt feedback", "session review", or "what could I have done better". Provides brutal honest feedback on prompt quality, suggests what context Claude needed, and generates session summaries for repo continuity.
---

# Session Review

Improve the human's prompting through brutal, specific feedback.

## Commands

- "review my prompts" - Analyze this session, grade prompts, give rewrites
- "session summary" - Generate CLAUDE.md context for next session
- "what do you need" - List missing context that would've saved time

## Prompt Review

When triggered, scan every human message. Find the 3-5 worst prompts.

For each bad prompt:

1. Quote what they said
2. Explain why it was bad (be specific)
3. Rewrite it the way it should have been written
4. Estimate time/messages wasted

### Example Output

```
PROMPT REVIEW

❌ Message 4: "Can you fix the bug?"

Problem: Zero context. I had to ask what bug, where, what behavior you expected.

Should have been: "Fix the auth bug in src/auth.ts line 42. Current: returns null on expired token. Expected: refresh the token and retry. Error log attached."

Time wasted: 3 messages, ~2 minutes

---

❌ Message 12: "Make it better"

Problem: "Better" how? Faster? Cleaner? More readable? I guessed wrong twice.

Should have been: "Refactor this function for readability. Split into smaller functions, add comments explaining the retry logic."

Time wasted: 2 messages, 1 revision

---

✅ Message 18: "Add rate limiting to the API endpoint. Max 100 requests per minute per user. Return 429 with retry-after header when exceeded."

This was good. Context, constraint, expected behavior. More like this.

---

HIGHEST IMPACT CHANGE

Stop saying "fix it" or "make it work". Every prompt needs:
- What file/function
- Current behavior
- Expected behavior

Do this one thing and you'll save 30% of your session time.
```

## Session Summary

Generate context for the next Claude session in this repo.

```markdown
# Session: [DATE]

## What Got Done
- [specific outcomes with file paths]

## Decisions Made
- [decision]: [why we chose this over alternatives]

## Known Issues
- [issue]: [workaround or plan]

## For Next Session
- [ ] [concrete next tasks]
- Context: [anything non-obvious the next Claude needs]
```

## What Claude Needs

List specific context that was missing. Be concrete:

```
MISSING CONTEXT

1. File structure - I didn't know services/ existed until message 8. Add to CLAUDE.md:
   "API handlers in src/routes/, business logic in src/services/"

2. Naming convention - I used camelCase, you wanted snake_case. Add:
   "Use snake_case for database fields, camelCase for JS variables"

3. Auth pattern - I didn't know you use middleware for auth. Add:
   "Auth via middleware in src/middleware/auth.ts, don't add auth checks in handlers"

4. Test approach - I wrote unit tests, you wanted integration. Add:
   "Prefer integration tests in __tests__/, mock only external APIs"

Copy these to your CLAUDE.md to save 10+ minutes next session.
```

## High-Impact Changes to Suggest

Based on how the Claude Code team uses Claude (see references/boris-tips.md):

1. "Start this in plan mode next time. Pour energy into the plan so Claude can 1-shot it."

2. "After I fixed that, you should've said: 'Update CLAUDE.md so you don't make that mistake again.'"

3. "You did this twice today. Make it a slash command or skill."

4. "You micromanaged the bug fix. Just say 'fix the failing CI tests' and let me figure it out."

5. "That was too vague. Write a detailed spec with expected behavior before handing it off."

6. "You accepted a mediocre fix. Say: 'Knowing everything you know now, scrap this and implement the elegant solution.'"

7. "Challenge me more. Say 'Prove this works' or 'Grill me on these changes.'"

## Tone

- Specific, not abstract
- Give exact rewrites, not vague suggestions  
- Quantify the waste
- One clear "highest impact change" at the end
- Brief praise for good prompts, focus time on fixing bad ones
