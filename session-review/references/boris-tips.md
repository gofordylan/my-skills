# Boris Cherny's Claude Code Tips

From the creator of Claude Code, sourced from the Claude Code team.

## 1. Do More in Parallel
- Spin up 3-5 git worktrees, each running its own Claude session
- Single biggest productivity unlock
- Name worktrees, set up shell aliases (za, zb, zc) for fast switching
- Dedicated "analysis" worktree for logs/BigQuery

## 2. Start Complex Tasks in Plan Mode
- Pour energy into the plan so Claude can 1-shot implementation
- One person has Claude write plan, second Claude reviews as staff engineer
- When things go sideways, switch back to plan mode and re-plan
- Tell Claude to enter plan mode for verification steps too

## 3. Invest in CLAUDE.md
- After every correction: "Update your CLAUDE.md so you don't make that mistake again"
- Claude is eerily good at writing rules for itself
- Ruthlessly edit over time until mistake rate drops
- Maintain notes directory for every task/project, point CLAUDE.md at it

## 4. Create Your Own Skills
- If you do something more than once a day, turn it into a skill or command
- /techdebt slash command to find/kill duplicated code at end of session
- Slash command that syncs 7 days of Slack, GDrive, Asana, GitHub into one context dump

## 5. Claude Fixes Most Bugs by Itself
- Enable Slack MCP, paste bug thread, say "fix"
- "Go fix the failing CI tests" - don't micromanage
- Point Claude at docker logs for distributed systems troubleshooting

## 6. Level Up Your Prompting
- Challenge Claude: "Grill me on these changes, don't make PR until I pass your test"
- "Prove to me this works" - have Claude diff main vs feature branch
- After mediocre fix: "Knowing everything you know now, scrap this and implement the elegant solution"
- Write detailed specs, reduce ambiguity before handing work off

## 7. Terminal & Environment Setup
- Ghostty: synchronized rendering, 24-bit color, unicode
- /statusline to show context usage and git branch
- Color-code and name terminal tabs
- Voice dictation (fn x2 on macOS) - 3x faster, more detailed prompts

## 8. Use Subagents
- Append "use subagents" for more compute on problem
- Offload individual tasks to keep main context clean
- Route permission requests to Opus 4.5 via hook for auto-approval

## 9. Use Claude for Data & Analytics
- Use "bq" CLI for BigQuery
- Haven't written SQL in 6+ months
- Works for any database with CLI, MCP, or API

## 10. Learning with Claude
- Enable "Explanatory" or "Learning" output style in /config
- Have Claude generate visual HTML presentations for unfamiliar code
- Ask for ASCII diagrams of protocols and codebases
- Spaced-repetition skill: you explain, Claude asks follow-ups, stores result

## Community Additions
- Use /chrome to validate changes on the web
- Auto-evaluate each session with scored criteria
- Treat Claude like a coworker, not a tool
- Context >> prompting - a well-written CLAUDE.md changes everything
