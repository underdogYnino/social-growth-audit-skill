# Platform Reference: X (Twitter)

Where the data lives, how to read it, and X-specific growth levers. Pair this with the funnel in SKILL.md — this file tells you *where to get each funnel number* and *which levers act on each leak*.

## Backend navigation

- **Analytics home**: `x.com/i/account_analytics` — tabs: 概览/Overview, 受众/Audience, 内容/Content, 视频/Video.
- **Overview tab**: account-level totals. Toggle windows 7D / 2W / 4W / 3M / 1Y. Pull **two windows** (e.g. 7D for current state, 4W for trend). Key cards: Impressions, Engagement rate, Engagements, **Profile visits** (this is usually the north-star — see below), Replies, Likes, Reposts, Bookmarks, Shares, Verified followers. Charts: Impressions over time, **Follows over time** (shows daily gross follows AND unfollows in red — read both), Posts vs Replies volume.
- **Content tab**: per-post table sortable by Impressions. Each post → click for Post Analytics: impressions, the full engagement breakdown, **profile visits from that post**, **new follows from that post**, bookmarks, "First 48 hours" activity curve, audience insights.
- Per-post analytics also reachable from the post's "View post analytics" link.

## Mapping metrics to the funnel

| Funnel stage | X metric | Where |
|---|---|---|
| reach | Impressions | Overview / per-post |
| consumption | Engagement rate; for video, video views | Overview / per-post |
| profile visit | **Profile visits** | Overview (account) + per-post |
| follow | New follows (per post); Follows over time (account) | Post Analytics / Overview chart |
| retention | Follows-over-time unfollow bars; engagement on recent vs old posts | Overview chart |

**Bookmarks are a key X tell.** A high bookmark-to-follow ratio means content is valued but "saving = owning" — readers don't feel they need to follow to keep it. That's a profile-visit→follow leak signature, common on utility/how-to content.

## Health reference points (rough, not laws)

- Profile-visit rate (profile visits ÷ impressions): low single-digit % is normal; if it's a fraction of a percent, the consumption→visit stage is the leak.
- Following > followers on a growth account is a negative trust signal on the profile — visitors read it as "follows everyone."
- Engagement rate context: a few % is healthy; sub-1% with high impressions often means reach is padded by low-quality surfaces (e.g. replies under big accounts that get seen but not engaged).
- "Promoted" tag on a top post → its impressions include paid reach; discount when setting the natural baseline.

## X-specific levers (apply only to the leak you found)

**reach low** → hooks in first line (X truncates), native media over links (links suppress reach), post into threads, posting time aligned to audience timezone, Premium boosts long-form + reply visibility.

**consumption→visit leak** → the post must make the reader curious about *the author*, not just the info. Add a reason-to-follow inside the post (mid-post soft CTA, not just at the end where savers have already left). For how-to content, a pinned reply offering a "companion resource: follow + DM keyword" converts savers.

**visit→follow leak** → profile overhaul is the highest-ROI one-time fix:
- Bio = identity hook + follow promise (what they'll keep getting) + credibility proof. Stop the label-stacking ("X engineer • AI • Workflow") — that's not a promise.
- Pinned post → a "content index" (a thread linking the best work + what's coming), updated as new flagship posts ship. Replace pinned product demos that don't convert.
- Timeline coherence: visitors should see consistent, same-lane output. Pause off-topic posting while growing.
- Stop following new accounts (except deliberate follow-back) so the ratio stops worsening.

**Reply/comment strategy** (the classic 0→500 lever, done right): commenting under mega-viral posts mostly buys impressions, not follows — you're noise and never rank to the top. Instead: target **mid-size accounts (≈5k–50k)** within 30 min of their new post, leave a *substantive additive* comment (a tool/数据/caveat they didn't mention) so the author replies or likes it, lifting you to where their followers see "this person knows things" → profile → conversion. Build a List of 10-15 such accounts and patrol daily.

**Follow-for-follow / 互关贴**: works to pad the base but those are numbers not assets; cap at ~30% of new follows and only same-niche, or the audience picture and timeline get polluted.

## Cadence note

Long-form (articles/threads) is frequently the strongest follow-driver on X because it demonstrates depth in one artifact — but verify against *this* account's Follows-over-time peaks before declaring it. Match flagship posts to the audience's active hours; give them a full day to compound (post mid-morning).
