# X Algorithm Deep Dive

## How the Algorithm Works

X's algorithm is a recommendation system that predicts which posts you'll engage with. It scores every post and ranks them in your feed.

### The Ranking Formula (Simplified)

```
Score = Engagement_Prediction × Author_Trust × Recency × Topic_Relevance
```

### Engagement Weights (Approximate)

Based on leaked/reverse-engineered data:

| Action | Weight |
|--------|--------|
| Reply | 1.0 (highest) |
| Retweet | 0.5 |
| Like | 0.2 |
| Time spent reading | 0.1-0.3 |
| Profile click | 0.3 |
| Follow from post | 0.5 |
| Link click | 0.1 (but post gets suppressed) |
| Report/Block | -5.0 |
| "Not interested" | -1.0 |

### Suppression Factors

These actively hurt your reach:

1. **External links** - Up to 50% reach reduction. X wants users to stay on platform.
2. **Hashtag spam** - More than 2 hashtags = spam signal
3. **Engagement bait** - "RT if you agree" patterns detected
4. **Duplicate content** - Copy-pasting same text
5. **Rapid posting** - More than 3-5 posts/hour
6. **Low follower engagement** - Your followers don't engage = low trust score
7. **New account** - Reduced reach until trust established

### Boost Factors

These help your reach:

1. **Blue checkmark** - ~2-4x boost for subscribers
2. **Media attachments** - Images/video get 2-3x more engagement
3. **Early engagement** - First 30 min crucial. High engagement = more distribution.
4. **Reply chains** - Active conversation signals quality
5. **Quote tweets over retweets** - Adding commentary = more valuable
6. **Posting during active hours** - When your audience is online

## Optimal Post Structure

### The Hook Formula

First line must stop the scroll. Patterns that work:

- **Contrarian:** "Most advice about X is wrong"
- **Curiosity gap:** "I made $100k doing something everyone said wouldn't work"
- **Number:** "3 things I wish I knew..."
- **Story opener:** "Last week I almost quit"
- **Question:** "Why does everyone ignore this?"

### Body Best Practices

- One idea per post
- Short sentences
- Line breaks for readability
- Specifics beat generalities ("500 signups" vs "lots of signups")

### Call to Action

End with something that invites engagement:
- Question to audience
- "What do you think?"
- "Reply with your experience"
- "Link in reply 👇" (for link sharing)

## Timing

Best times to post (varies by audience):

**B2B/Professional:**
- Tue-Thu, 9am-12pm
- Avoid weekends

**Consumer/General:**
- Evenings 5pm-9pm
- Weekends can work

**Tech/Startup:**
- Early morning 6-8am (hustle crowd)
- Late night 10pm-12am (night owls)

## Thread Strategy

Threads get more reach than single posts IF:
- First tweet is a strong hook
- Each tweet adds value (not filler)
- 3-10 tweets optimal
- End with summary or CTA

Thread opener template:
```
[Big claim or question]

Here's what I learned: 🧵
```

## Link Sharing Strategy

Since links are suppressed:

1. Post main content (no link)
2. Wait 1-2 minutes
3. Reply to your own post with the link
4. Pin reply or edit to say "link in reply"

This way the main post gets full reach, and interested people find the link.

## Profile Optimization

Your profile affects how posts perform:

- **Bio:** Clear value prop, who you help
- **Pinned tweet:** Your best/most relevant content
- **Banner:** Professional, shows what you do
- **Profile pic:** Face performs best
- **Location/Link:** Fill them out (trust signals)
