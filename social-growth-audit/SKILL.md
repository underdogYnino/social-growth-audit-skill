---
name: social-growth-audit
description: >
  Diagnose a social media account (X/Twitter or 小红书/Xiaohongshu/RED) and
  produce a growth strategy + executable SOP grounded in the account's real
  backend data. Use this whenever the user wants to analyze an account, figure
  out why a post or account isn't growing, audit follower growth, turn analytics
  into an action plan, build a posting cadence or content SOP, or asks "why
  aren't people following me / why isn't this growing / how do I get to N
  followers". Trigger even when the user just shares an account handle/profile
  and asks for "advice" or a "growth plan" — this skill turns that vague ask
  into a data-driven diagnosis. Covers X and 小红书 only.
  Diagnosis-and-SOP only; this skill never publishes, posts, or sends anything.
---

# Social Growth Audit

A method for diagnosing a single social account from its real data and producing a strategy + daily/weekly SOP. The output is a judgment, not a template. **The same six-step process applies to every account; the conclusions must be re-derived every time from that account's actual numbers.**

## The one mistake to avoid

The biggest failure mode is pattern-matching a previous account's diagnosis onto a new one. "Long-form posts drive follows," "convert the bookmarkers," "go series-based" — these were *findings for one specific account*, not laws. A different account's bottleneck might be the opposite (e.g. content that converts fine but never gets impressions, or huge reach with a mismatched audience). If you find yourself writing a conclusion before looking at this account's funnel, stop. Every recommendation in the final deliverable must trace to a number you actually pulled from *this* account.

## Scope guardrail

This skill **diagnoses and plans only**. It never posts, replies, sends DMs, edits the bio, or takes any publish action — even if asked, even in an automation context. All deliverables are drafts and recommendations the user executes themselves. If the user wants you to act on the account, say that's outside this skill and they should perform publish actions themselves.

---

## Step 0 — Gather inputs (do this before touching data)

You cannot diagnose without context. Ask for whatever is missing, ideally in one batched round (use the elicitation tool if available). Required:

1. **Account(s)**: handle / profile URL, and which platform(s) — X, 小红书, or both.
2. **Persona / positioning**: who they are, what they post about, and any constraints on what they can credibly produce. (Persona shapes which advice is safe — e.g. a "not-really-a-developer" persona must avoid authoritative deep-technical claims.)
3. **Goal**: target followers + timeframe. Get the *downstream* purpose too (influence? product cold-start? selling courses/consulting? brand deals?) — it decides whether to optimize for precise vs. high-volume followers.
4. **Constraints**: time/day available; whether paid promotion, follow-for-follow, giveaways are acceptable; subscription tier (X Premium affects long-form + reply weighting); content language.
5. **Backend access**: can you reach the analytics backend (X Analytics / 小红书 创作服务平台)? Front-end posts alone make the "impression → profile-visit" diagnosis unreliable. If you have browser tools and the user is logged in, plan to pull it.

If the user says "just analyze it, you have access," still confirm persona and goal — those are not observable from data.

---

## Step 1 — Collect data

Read the relevant platform reference file(s) for exactly where each metric lives and how to navigate:
- X → `references/platform-x.md`
- 小红书 → `references/platform-xiaohongshu.md`

Collect at two levels:

**Account level** (the funnel inputs): followers/following, impressions, profile visits, engagement rate, follows-over-time, and the period trend. Pull at least two time windows (recent + 4-week) so you can see trend, not just a snapshot.

**Post level** (the distribution shape): top posts by impressions, plus the long tail. You're looking for the *gap* between best and median — that gap is the most diagnostic single fact about most accounts.

Capture the actual numbers into a data snapshot you can cite later. If you have browser tools, navigate and read the backend directly; if not, ask the user to paste screenshots or numbers. **Never invent a number** — if a metric is unavailable, say so and diagnose around the gap.

One trap: posts boosted/promoted inflate the natural baseline. Flag any promoted post and discount it when setting expectations.

---

## Step 2 — Run the funnel

Every social account is the same pipe. Diagnose by finding which segment leaks:

```
reach (impressions)
  → consumption (read/watch/CTR)
    → profile visit
      → follow
        → retention (do they stay / engage with later posts)
```

Compute the conversion at each stage from real numbers. The leak location dictates the entire strategy — this is the heart of the method:

| Leak location | Symptom | Strategy center of gravity |
|---|---|---|
| reach itself low | impressions tiny even on good content | distribution: hooks, hashtags/topics, timing, posting into where the algorithm can find it; possible shadowban/limit check |
| reach high, consumption low | impressions fine, low CTR / read-through | the hook and the first screen — title, cover, opening line |
| consumption high, profile-visit low | people read/save but don't click through | the post gives no reason to want *the author*; + profile doesn't invite |
| profile-visit high, follow low | they visit but bounce | the profile (bio, pinned, timeline coherence) fails to promise future value |
| follow ok, retention low | follows then unfollows / dead engagement | content inconsistency; audience/persona mismatch; over-reliance on one-off viral/hot-topic reach |

Most accounts leak at one or two specific stages. Name them explicitly with the numbers. Resist diagnosing stages that are actually healthy.

Also check **audience match**: high reach from an off-target hot-topic (e.g. a meme that goes viral) often produces near-zero follows because the audience isn't the target. Reach quality > reach quantity.

---

## Step 3 — Reality-check the goal

Before writing the plan, sanity-check the target against the data, and say so plainly even if it's not what the user wants to hear. Compute the required daily net growth (target − current, ÷ days). Compare against the account's demonstrated ceiling (best real day, discounting promoted reach, net of unfollows).

If the math needs a once-in-account-history event every single day, the goal is unlikely. Don't refuse it — recalibrate: give a tiered projection (baseline / good / breakout) with the condition each requires, and recommend a realistic anchor target plus a longer runway for the stretch number. The reason to do this is concrete: an over-tight target pushes the user into account-damaging moves (mass follow-for-follow, buying followers) that poison the exact audience their downstream goal depends on.

---

## Step 4 — Build the strategy

Strategy follows directly from the leak(s) found in Step 2. Organize per platform. For each platform produce:

- **The single sentence diagnosis** (what's the one病灶 / bottleneck).
- **The highest-ROI one-time fix** (often profile/bio/pinned when the leak is profile-visit→follow — but only if that's where *this* account leaks).
- **Content structure**: what to make more of, what to stop. Anchor to what the data shows already works for *this* account — find their proven winner (the post type that actually drove follows, not impressions) and concentrate fire there.
- **The conversion mechanism** for the leaking stage (e.g. if consumption→visit leaks, what makes a reader want the author; if visit→follow leaks, what the profile must promise).
- **Topic ideas** that fit the persona's safe zone and ride current relevant trends (search for live trends/hot topics in the niche rather than guessing).
- **Engagement / interaction tactics** appropriate to the platform and corrected for what the user has already observed works or doesn't.

Use the platform reference for platform-specific levers (X reply strategy, 小红书 series/cover/comment mechanics, compliance red lines like off-platform link penalties on 小红书).

## Step 5 — Write the SOP

A strategy nobody can execute is useless. Produce:

- **Daily SOP** that fits the user's stated time budget — time-boxed blocks (morning/noon/evening), total within budget.
- **Weekly cadence** — what gets produced which day, concrete and assignable.
- **Metrics dashboard** — pick the *north-star* metric for this account (the leaking-stage metric, e.g. weekly profile visits if that's the leak), 4-6 metrics total with current baseline → target, each with a one-line "why this metric." Add review rules written as hard triggers, not vibes (e.g. "a content type 2 posts below baseline → cut it"; "a post 3× baseline → make a variant within 48h").
- **Discipline / red lines** — restate the user's constraints as rules (follow-for-follow cap, no buying followers, platform compliance, persona safe-zone).

## Step 6 — Deliver

Output the diagnosis + strategy + SOP as **both** a Markdown file and an HTML report. The HTML must be built from the design system in `templates/report-template.html` — read that file before writing a single line of HTML. Save a separate data snapshot file with the raw numbers and date. Present all three files; don't bury them in a postamble.

### HTML output rules (template-based)

The template at `templates/report-template.html` defines the design system: CSS variables, component classes (`.card`, `.funnel`, `.fbar`, `.honest`, `.formula`, `.checklist`, `.verdict`), typography, and colour palette. **Do not rewrite or inline a new stylesheet.** Copy the `<style>` block verbatim; only the content changes.

**Eight sections — all required, content replaced per account:**

| # | Section | Template element | What changes |
|---|---|---|---|
| HERO | Header band | `<header>` | H1 = this account's one-line diagnosis; subtitle = specific bottleneck; meta = account handle, follower count, data date |
| 01 | Core diagnosis | `.cards` + `.funnel` | Evidence cards with this account's numbers; funnel bars sized to real conversion rates |
| 02 | Data baseline | `<table>` blocks | Per-platform account metrics + per-post breakdown |
| 03 | Goal calibration | `.honest` boxes | Required daily pace vs. demonstrated ceiling; tiered projection |
| 04–05 | Strategy per platform | `h3` blocks + `.formula` + `.checklist` | All tactics derived from *this* account's leak; do not recycle generic advice |
| 06 | Daily SOP | Time-block table + weekly cadence table | Fit the user's stated time budget |
| 07 | Metrics dashboard | Metrics table + `.checklist` review rules | North-star = the leaking-stage metric; 4–6 total |
| 08 | Discipline | `ol.plain` | User's constraints restated as hard rules |

**HERO customisation:**
- H1 is the single-sentence diagnosis for *this* account — make it specific and honest, not a generic label.
- The `.eyes` cat-eye element is the brand signature; keep it.
- Adjust `--amber` / `--xhs` accent colours if the account has a strongly different aesthetic (e.g. a pure X-only audit can drop `--xhs`).
- The `.kicker` line = `"Growth Audit / [Account Name]"`.

**What must NOT be changed:**
- The `<style>` block and CSS variable names.
- The `secno` numbering convention (`01 / 核心诊断`, etc.).
- The `.funnel` component — always include it for the primary leaking platform, with bars proportional to real numbers (use log compression if the gap is extreme, as shown in the template).

---

## Output structure (both MD and HTML)

ALWAYS follow this skeleton, adapted to findings:

```
HERO — account name + one-line diagnosis + meta
01. Core diagnosis — one sentence, then the evidence (2-3 hard data points)
02. Data baseline — the numbers, per platform, with post distribution
03. Goal reality-check — required pace vs. ceiling; tiered projection
04–05. Strategy per platform — diagnosis → fixes → content → mechanism → topics → tactics
06. Daily SOP + weekly cadence
07. Metrics dashboard — north star + 4-6 metrics, baseline→target, review triggers
08. Risk & discipline — constraints as rules
```

## Tone

Honest over flattering. If the goal is unrealistic or a tactic the user believes in is failing, say so with the numbers. The user is trusting this to be a real diagnosis, not encouragement — a wrong-but-comforting plan wastes weeks of their effort.
