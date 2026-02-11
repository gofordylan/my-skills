---
name: x-poster
description: Create and optimize posts for X (Twitter) using algorithm-aware scoring. Use when drafting tweets, evaluating post quality, or wanting to maximize engagement. Includes pre-flight rubric check before posting.
---

# X Poster

Create high-performing X posts by scoring them against known algorithm factors before publishing.

## Workflow

1. Draft post
2. Score against rubric (must score 7+/10 to post)
3. Iterate if needed
4. Post via browser or API

## Scoring Rubric (10 points)

Score each post before publishing:

| Factor | Points | Criteria |
|--------|--------|----------|
| **Hook** | 0-2 | First line grabs attention. Strong opener = 2, decent = 1, weak = 0 |
| **No External Links** | 0-1 | Main post has no links = 1. Links suppress reach. Put links in reply. |
| **Media** | 0-2 | Image/video = 2, none = 0. Media boosts engagement significantly. |
| **Conversation Starter** | 0-1 | Asks question or invites reply = 1 |
| **Length** | 0-1 | 70-200 chars optimal = 1. Too short or walls of text = 0 |
| **Clarity** | 0-1 | One clear idea, easy to understand = 1 |
| **Emotional Resonance** | 0-1 | Triggers emotion (curiosity, surprise, agreement, humor) = 1 |
| **Timing** | 0-1 | Posted during high-activity hours (9am-12pm, 5pm-9pm local) = 1 |

**Minimum to post: 7/10**

## Algorithm Factors

What X prioritizes (in order):
1. **Replies** - Highest signal. Posts that spark conversation win.
2. **Time on post** - People stopping to read = quality signal
3. **Retweets/Quotes** - Amplification
4. **Likes** - Basic engagement
5. **Profile clicks** - Curiosity signal
6. **Follows from post** - Strong quality signal

What X suppresses:
- External links in main post (put in reply instead)
- Too many hashtags (0-2 max)
- Engagement bait ("like if you agree")
- Rapid posting (looks spammy)

## Post Templates

**Insight/Take:**
```
[Contrarian or surprising statement]

[1-2 sentences explaining why]

[Optional: question to audience]
```

**Thread opener:**
```
[Big claim or question]

Here's what I learned: 🧵
```

**Story:**
```
[Situation that went wrong/right]

[What happened]

[Lesson or punchline]
```

**Build in public:**
```
[Milestone or update]

[What you did / numbers]

[What's next or ask for input]
```

## Pre-Post Checklist

Before posting, verify:
- [ ] Hook is strong (would YOU stop scrolling?)
- [ ] No links in main post (move to reply)
- [ ] Has image/video if possible
- [ ] Single clear idea
- [ ] Invites response somehow
- [ ] Not posted in last 2 hours
- [ ] Score is 7+/10

## Posting

Use browser automation to post, or if API access:
```bash
# Via bird CLI if available
bird post "Your tweet text"
bird post "Tweet" --media image.png
```

For links: Post main content first, then reply with link.

## Example Scoring

**Draft:** "Check out my new blog post: https://example.com/post"

| Factor | Score | Notes |
|--------|-------|-------|
| Hook | 0 | Generic, no intrigue |
| No Links | 0 | Has link in main post |
| Media | 0 | No media |
| Conversation | 0 | No question/invite |
| Length | 0 | Too short |
| Clarity | 1 | Clear what it is |
| Emotion | 0 | No emotional hook |
| Timing | 1 | Assume good timing |
| **Total** | **2/10** | ❌ Do not post |

**Improved:** "I spent 6 weeks building something I thought nobody wanted.

Turns out 500 people signed up in 48 hours.

Here's what I learned about validating ideas (link in reply) 👇"

| Factor | Score | Notes |
|--------|-------|-------|
| Hook | 2 | Curiosity gap, contrarian |
| No Links | 1 | Link moved to reply |
| Media | 0 | Could add screenshot |
| Conversation | 1 | "link in reply" invites click |
| Length | 1 | Good length |
| Clarity | 1 | Clear story |
| Emotion | 1 | Surprise, curiosity |
| Timing | 1 | Assume good |
| **Total** | **8/10** | ✅ Good to post |
