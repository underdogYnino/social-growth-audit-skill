# Platform Reference: 小红书 (Xiaohongshu / RED)

Where the data lives, how to read it, and 小红书-specific growth levers and compliance. Pair with the funnel in SKILL.md.

## Backend navigation

- **创作服务平台 (Creator platform)**: `creator.xiaohongshu.com` — login is the creator account.
- **数据分析 / 笔记数据**: `creator.xiaohongshu.com/statistics/data-analysis` — per-note table with columns: 曝光 (impressions), 观看 (views), **封面点击率 (cover CTR)**, 点赞 (likes), 评论 (comments), 收藏 (saves), **涨粉 (follows gained)**, 分享 (shares). Sortable; can filter by 笔记题材 (topic) and date; 导出数据 to export.
- **数据看板**: account-level trends (followers, total impressions, profile views).
- Front-end profile (`xiaohongshu.com/user/profile/<id>`) shows followers/following/总获赞与收藏 and the note grid with per-note like counts.

## Mapping metrics to the funnel

| Funnel stage | 小红书 metric | Where |
|---|---|---|
| reach | 曝光 (impressions) | 笔记数据 |
| consumption | **封面点击率 (cover CTR)**, then 观看 | 笔记数据 |
| profile visit | profile views | 数据看板 |
| follow | **涨粉 per note** | 笔记数据 |
| retention | follower trend; engagement on series notes | 数据看板 |

**The 小红书-specific tell: a note can have huge 曝光 and high 分享 but 涨粉 = 0.** This is the signature failure. It means the note was consumed/shared as a one-off (a meme, a hot-take) with no reason to follow. The fix is almost always *serialization* — see levers.

## Health reference points (rough, not laws)

- **Cover CTR (封面点击率)** is the make-or-break top-of-funnel metric. >15% is good, >25% excellent; <10% means the cover/title is the leak and reach will stay capped regardless of content quality.
- 涨粉-per-note near zero despite decent 曝光 → the conversion mechanism (series hook) is missing, not the content.
- Comments are heavily weighted by the algorithm; question-style notes that provoke comments get pushed harder.

## Compliance red lines (check these FIRST — they cap the whole account, not one note)

- **Off-platform links /导流** are the most sensitive. A bio containing another platform's handle (e.g. "X:@xxx") or external URLs can suppress account-wide weight. Flag and recommend removal.
- **Marketing/推广-style notes** get throttled. A note with launch-announcement tone ("XX 终于来了！") plus product-promo signals can get near-zero 曝光 (single/double digits) — a clear limit signal. Recommend first-person 分享体 ("I made myself a little tool that solves X") instead.
- **AIGC content** must be labeled per platform rules; screenshot-based how-to图文 from the user's own screen is safest.
- Brand deals (商单/蒲公英) require ≥1000 followers — note this if monetization is the downstream goal, but it's not an early-stage action.

## 小红书-specific levers (apply to the leak you found)

**Cover CTR leak (consumption top)** → big-character (大字报) cover with a pain-point title; the cover is 70% of the click decision on 小红书.

**涨粉 leak despite reach (the common one)** → **serialization is the core follow mechanism.** People follow because they fear missing the *next* one, not because one was good. Note template:
```
Cover: 大字报 style + series badge 「<series name> Day N」
Title: pain-point opener ("还在手打提示词？")
Body images: 3–6 step images, one action each, copy-able by a beginner
Last image: fixed "下一篇：《具体标题》｜关注不迷路"
Caption: ≤300 chars, spoken tone, ends with a question to drive comments
Pinned own-comment: extra value ("完整 prompt 在这") + follow nudge
```

**Comment-driven reach** → question-style notes that get the comment section going; reply to every comment within the first hour (golden发酵期 directly feeds the algorithm).

**Hot-topic harvesting** → pure hot-topic notes bring tourists, not followers (the 0-涨粉 trap). Always *hybridize*: ride the hot keyword but make it a teachable, series-able note so the reach converts.

## Cadence note

Cold-start needs volume: 5–7 notes/week minimum, not 2. 小红书's decentralized distribution means even a tiny account can hit 万级 (10k+) 曝光, so the lever is note *structure*, not account size. Post times 12:00–13:00 or 19:00–21:00. Tag 3–5 precise topics per note.
