# SidelineReel — PM Assessment Submission

**Video:** `<PASTE VIDEO LINK HERE — if on YouTube, include "Ajaia" in the title>`
**Prototype:** `<PASTE HOSTED LINK HERE>` (runnable file: `prototype/index.html`, open it in any browser — no install, no backend)
**Company:** [Ajaia](https://ajaia.ai)
**Portfolio (optional):** `<link or leave blank>`

---

## Task 1 — The roadmap call

### Decision in one line
**Build roster-tag confidence scoring plus a coach confirm step next**, so SidelineReel stops putting the wrong kid in a reel. **Do not build livestreaming for Ridgeline this cycle, and do not build more Reel Editor controls.**

### How I read each piece of signal

| # | Material | What it actually says | How much I trust it |
|---|---|---|---|
| 1 | Carla (Ridgeline) email | Reels are why **half of her parents renewed**. The board wants live streaming for grandparents and scouts. Signups open in 6 weeks. | Real stakeholder, but it's one buyer's *proposed solution*. The underlying need (remote relatives and scouts watching) is plausible and unproven. |
| 2 | Research summary | 58% of 210 surveyed parents ask for more editing controls. In 90 days of usage, only **6% opened the Reel Editor** and **under 1% of those finished an edit**. The Share button is used in 90% of auto-recaps. | **Behavior beats stated preference.** Parents say they want editing but don't use it. They share. The value is in the finished product arriving correct, and then going to other people. |
| 3 | Support tickets | Three of five are the same defect: **wrong kid in the reel** (14 vs 4, 1 vs 11, swapped digits). They come from three different clubs: Ridgeline, Brightwater, Cobblestone. The other two are an app icon preference and an occasionally missing watermark. | Three independent clubs describing one failure is a pattern, not noise. The icon and watermark tickets are low-severity, single reports. |
| 4 | Slack (Jamal, Sales Ops) | $180k season, biggest account. Carla has said twice she may shop around. Sales wants something concrete. | The revenue risk is real, and I'm not dismissing it. But urgency comes from who is asking, not from usage evidence. |
| 5 | Product Health dashboard | Reel Share Rate = 92%, but only over reels that were *opened*. About **30% of reels are never opened**. The analytics note says those are mostly late-night notifications or a **wrong-kid thumbnail**. | The headline number flatters us. See below. |

### The metric that looks better than it is
The 92% is calculated over opened reels only. About 70% of reels are opened. If the 92% holds for opened reels, then roughly **0.70 × 0.92 ≈ 64% of all generated reels are shared**, not 92%. The missing 30% is exactly where the wrong-thumbnail problem sits. I would report share rate over *generated* reels going forward, and show "opened" as a separate funnel step. (Caveat: the analytics note says "most" of the unopened reels are explained by timing and thumbnails. It doesn't give a split, so I don't know how much of the 30% is wrong-kid versus timing.)

### Why roster tagging wins
1. **It's the one problem three unrelated sources point at.** Tickets (3 clubs), the dashboard note (wrong thumbnails lower open rate), and Carla's own club (the *first* ticket is a Ridgeline parent).
2. **It protects the thing customers say they pay for.** Carla says reels are why half her parents renewed. A reel that shows another child is the failure that most directly attacks that value. This is a bigger threat to Ridgeline's renewal than the absence of live streaming, and it's one we can fix.
3. **It sits upstream of the other metrics.** Wrong thumbnails depress opens, opens gate shares, and shares are the growth loop (90% share use on recaps). Fixing tagging lifts the funnel without adding new surface area.
4. **It's the core job.** SidelineReel's job is "the right highlight in the right kid's reel."

### Ranked roadmap

| Rank | Item | Evidence | Verdict |
|---|---|---|---|
| **1** | **Roster-tag confidence + coach confirm queue** (spec in Task 2) | 3 tickets across 3 clubs; dashboard note on thumbnails; Ridgeline's own parent | **Build next** |
| **2** | **Quiet-hours delivery** (don't notify families late at night) and **thumbnails taken from confirmed clips only** | Analytics note links late-night notifications to unopened reels. Small change. | Fast follow, same cycle if capacity allows. Confidence is medium because the analytics note gives no split. |
| **3** | **Fix the share-rate metric** (denominator = generated reels) and instrument the open funnel | The 92% is misleading | Do now, near-zero cost. It's a dashboard fix, not a roadmap item. |
| **4** | **Discovery on remote viewing** (grandparents, scouts): who watches, how often, what they'd pay for. Test whether a lighter option (shareable season highlight page) meets the need. | One buyer asked. No usage data supports it yet. | Research only, no build commitment. |
| **5** | **Triage the missing-watermark bug** (camera-roll save) | One coach, "not urgent" | Bug backlog. Escalate only if brand/co-marketing is affected or reports repeat. |

### What I would NOT build next
- **Livestreaming for Ridgeline: not this cycle.** Reasons:
  - It's a different product (real-time video delivery, uptime, bandwidth, moderation of live video of minors, a very different cost structure). It is not on the path of "find each kid's highlights."
  - The evidence is one stakeholder's email plus a renewal-driven sales request. No usage or survey data supports it.
  - Six weeks is not credible for a safe live-video product involving children, and a rushed version would damage trust.
  - The risk is real: I'm choosing to accept some chance of losing a $180k account rather than promise something we can't deliver. I would flag that explicitly to leadership so it's an informed decision, not a surprise. If leadership wants to hedge, the right move is to explore a partner or integration option as a separate investigation, not to commit to a build.
- **More Reel Editor controls / music: not now.** 58% *said* it, but 6% open the editor and under 1% of openers finish an edit. Music also brings licensing risk. I would revisit only if the editor's open rate rises once reels are trustworthy.
- **App icon change:** one ticket. Log it, fold it into the next brand pass.

### What Sales can honestly tell Carla (draft)
> Carla, thanks for being direct. Live streaming isn't something we can commit to before your signups, and I'd rather say that now than promise something we'd ship badly with children on camera. What we can commit to: a fix for the wrong-player clips your parents have reported, which our data shows is the most-reported reel problem across clubs. We'll bring your club into the first rollout, and I'll share a date once engineering has sized it. Separately, I'd like 20 minutes with you to understand who on your board's list would be watching live (grandparents? scouts?), because there may be a lighter way to serve them.

This is concrete without over-promising. It names a real action, a pilot slot, and a next step. The date is deliberately conditional on an engineering estimate I don't have.

### How I'd hold this under pushback
- **"We could lose $180k."** Agreed, it's the biggest exposure, and I'm not hiding it. But the commitment that protects the renewal is the one customers are already complaining about: the wrong kid in the reel at Ridgeline itself. If I promise streaming and miss, we lose the account *and* credibility. I'd change my mind if Ridgeline gave a written, specific requirement and we found it could be met with a small, safe build. New evidence would move me, volume of asking wouldn't.
- **"The survey says editing controls."** Stated preference versus behavior: 6% opened, under 1% finished. If the editor were the real need, people who opened it would complete edits.
- **"Three tickets is anecdotal."** Fair. That's why the spec starts with a baseline audit of real tag accuracy, and why the 92% number needs fixing. If the audit shows wrong-kid clips are under, say, 1%, I would drop this from #1.

---

## Task 2 — Spec: Roster-tag confidence + coach confirm

### Problem
When jersey numbers look alike (1/11, 4/14, 16/61 or swapped digits), SidelineReel sometimes assigns a clip to the wrong kid. The wrong clip lands in the kid's reel or becomes the thumbnail. Parents are upset, may not open the reel, and the club's renewal is at risk.

### Outcome
- **Primary:** wrong-kid clips in delivered reels fall to **≤ 1%** of delivered clips within four weeks of general release (measured by weekly human audit).
- **Secondary:** reels with an unopened status fall toward ≤ 20% (from about 30%), jointly with the quiet-hours item.
- **Leading indicator:** "wrong player" support tickets and "Not my kid" reports.
- **Step 0:** the baseline is unknown. Before building, audit a labeled sample (about 300 clips from games at the three clubs that filed tickets) to measure current accuracy and which number pairs fail. The targets above are provisional until that baseline exists.

### Behavior
Each detected highlight gets a **confidence** that its jersey number was read correctly. A clip lands in one of three states:

| State | Rule (starting values, tuned after the audit) |
|---|---|
| **Auto-confirmed** | Confidence ≥ 0.90 and no look-alike number on the roster, **or** confidence ≥ 0.97 if a look-alike number exists |
| **Needs review** | Anything between the bars, or reported by a parent as "not my kid" |
| **Unassigned** | Confidence < 0.60 or no number readable |

**Look-alike numbers** are roster pairs where one is the other with digits swapped (16/61), contains the other (1/11, 4/14), or differs by one commonly confused digit (e.g. 3/8, 5/6, 1/7).

Clips in Needs review or Unassigned are **held**: excluded from every reel, every thumbnail, and the weekly recap until resolved.

### Coach review queue
- Shows each held clip (still frame plus the moment), why it was flagged, the model's guess, look-alike candidates from the roster, and an option to pick anyone else or discard.
- Common case is one tap. Coach can delegate to an assistant coach.
- On resolve: the clip joins the right reel, the reel and thumbnail regenerate.
- **Reminders:** one when processing finishes if anything is held, one 12 hours before the send cutoff.
- **Send cutoff fallback:** at cutoff, the recap sends with **confirmed clips only**. Held clips are never sent. If a kid has zero confirmed clips, the family gets a short "no highlights this week" note instead of a reel. The coach receives the list of leftover clips to tag for next time.

### Parent report
Every clip in a reel has a **"Not my kid"** action. It removes the clip from that reel immediately and returns it to the coach queue.

### In scope
Confidence scoring, look-alike rule, three states, hold logic, coach queue, cutoff fallback, thumbnail-from-confirmed-only, parent report, decision logging, weekly audit tooling, metrics, per-account thresholds editable by ops with an audit log.

### Out of scope
- A new or retrained detection model (corrections are logged as labeled data for a later effort).
- **Face recognition.** These are minors; this is deliberately jersey-number-only.
- Livestreaming, Reel Editor changes, music.
- Quiet-hours notifications (separate item #2).
- Retroactively re-tagging old games (parents can use "Not my kid" on past reels).

### Where a human stays in the loop
1. **Coach (or delegate)** decides every ambiguous clip. Nothing ambiguous reaches families without a human.
2. **Parent** can flag any clip.
3. **Internal reviewer** audits 100 random auto-confirmed clips per week (at least half from clubs/games with look-alike numbers) and signs off on any threshold change.

### Acceptance criteria
1. Given roster numbers 4 and 14, a clip read as 14 at 0.88 is **Needs review** and appears in no reel or thumbnail.
2. Given the same roster, a clip read as 14 at 0.98 is **Auto-confirmed**.
3. Given no look-alike number, a clip read at 0.93 is Auto-confirmed; at 0.75 it is Needs review; at 0.40 or with no number it is Unassigned.
4. Held clips appear in zero reels, zero thumbnails, and zero recap emails (test with a fixture game).
5. When a coach confirms a clip, the reel and thumbnail update within 1 minute.
6. At the send cutoff with unresolved clips, the recap sends with confirmed clips only, a kid with none gets the "no highlights" note, and the coach gets the leftover list.
7. "Not my kid" removes the clip from that reel immediately and creates a queue item.
8. Coach reminders fire at processing completion (if any held) and 12 hours before cutoff; none fire if nothing is held.
9. Every decision (clip, before, after, who, when) is stored and exportable as labeled data.
10. Threshold changes require an authorized ops user and are audit-logged.
11. Only coaches/admins of that team can see queue frames. No facial recognition is performed or stored.
12. A dashboard shows: held rate, queue completion before cutoff, "Not my kid" per 1,000 clips, weekly audit error rate.
13. Median time to resolve a clip in the queue is ≤ 10 seconds (measured after pilot).

### Rollout
Baseline audit → pilot with the clubs that reported the issue (Ridgeline, Brightwater, Cobblestone) → general release. Timing depends on an engineering estimate I don't have, so I would not give a date outside the company until that estimate exists.

### Top two ways this fails, and what catches each
1. **The queue becomes a chore, coaches don't clear it, and reels come out thin or empty.** That swaps one disappointment for another.
   - *Catch:* alert when held rate is > 25% of clips in a game, or fewer than 60% of queues are cleared before cutoff for two weeks in a row, or kids with zero clips rise. *Response:* loosen thresholds based on audit data, add assistant-coach delegation and batch confirm.
2. **Confident wrong matches slip through as Auto-confirmed** (the look-alike rule misses a case, e.g. partial occlusion or a number the model reads confidently but wrongly).
   - *Catch:* weekly human audit of random auto-confirmed clips (alert above 1% error), and "Not my kid" reports per 1,000 clips (alert above 3). *Response:* automatically raise thresholds for the affected pairs and review at the next audit.

---

## Task 3 — Prototype

**File:** `prototype/index.html` (self-contained, opens in any browser; simulated data, no real footage or backend).

Three steps:
1. **Game processed:** the 12 highlight moments sorted into auto-confirmed, needs check, and can't read, with a "Matching rules" panel. Move the thresholds and see how the queue size changes. This is the tradeoff between wrong-kid errors and coach workload.
2. **Review queue:** one clip at a time with the frame, the reason it was flagged, the model's guess and the look-alike candidates, plus "someone else" and "discard."
3. **Recap and send:** per-kid reels and thumbnails built only from confirmed clips, a "Simulate Sunday 6 PM send" that leaves out anything still held, and a hover-to-reveal "Not my kid" report that returns a clip to the queue.

Try it: Review queue → tag a few clips → open Recap → send before finishing to see held clips excluded.

> **Before submitting:** upload `index.html` somewhere public (GitHub Pages, Netlify Drop, etc.), paste the link above, and open it in an incognito window to confirm it loads.

---

## Task 4 — AI workflow note (draft; edit so it matches what you actually did)

I used Claude to cross-read the five materials, draft the spec structure and acceptance criteria, and build the prototype. I kept the decisions human: which problem is #1, the call not to commit to livestreaming for Ridgeline, and the wording I'd give to Sales. One thing I checked: the dashboard's 92% share rate, which I recomputed over all generated reels (about 64%) after noticing the denominator was opened reels only. One thing I rejected: a suggestion to offer Ridgeline a "livestream-lite" commitment before signups. I couldn't support it with evidence or a credible estimate, and it would have meant promising a date to a customer on hope. I also caught and fixed a prototype bug where dragging a threshold slider re-rendered it mid-drag.

---

## Video outline (5–10 min, screen + camera)
1. **Roadmap call (2 min):** the five signals, the 92% → ~64% point, why tagging beats livestreaming and the editor.
2. **Spec (2 min):** the three states, look-alike rule, coach queue, send-cutoff fallback, two failure modes.
3. **Demo (2 min):** the prototype, end to end, including moving a threshold and a parent report.
4. **Close (1 min):** who I am, why this role, why Ajaia, salary expectation: `<YOUR NUMBER>`. Do not mention current compensation.
