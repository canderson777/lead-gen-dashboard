# How to Use the Lead Generation Dashboard

*A plain-English, step-by-step guide to turning local businesses into signed clients using the audit-led workflow.*

---

## What this dashboard does (in one paragraph)

This dashboard helps you find local businesses (like plumbers, roofers, and HVAC companies), check their websites for problems that are costing them customers, and send outreach that gets replies. The core idea is simple: instead of asking a business *"Want to chat?"* (which gets ignored), you run a quick free audit, find a real problem, and say *"Your website scores 34/100 — here's what's costing you customers."* That gets attention.

It does this in **two stages**:
1. **The email** — leads with exactly ONE hard number (the worst problem).
2. **The audit report** — follows up with the FULL list of problems, which proves the value and turns the lead into a paying client.

---

## Before you start

You'll need two things set up in **Settings** (the 🔐 tab):

- **Google API keys** — for the audits (PageSpeed / SEO checks). Same key works for both.
- **Your sender identity** — who the outreach email is signed by, e.g. *"Your Name from Your Business — I help local trades get found on Google."*
- **Your booking link** — where someone can book your walkthrough call (e.g. a Calendly link).

These make your drafts read like a real person, not a robot.

---

## The step-by-step workflow

### Step 1 — Find a prospect

Go to the **🔍 Prospecting** tab. You can either:
- Type a search like *"plumbers in Austin, TX"* and run a live search, or
- Import a CSV of businesses you already found.

You'll get a list of businesses with their info. **Open each record** (the ✎ button) and add what you know: the website URL, contact email, the "gap" you spotted (their problem), and any angle for the opening line.

> ⚠️ **Reset the Prospecting page** — the red **Reset page** button in the search toolbar (next to Export) wipes all prospects, saved searches, and activity log to zero so you can start a fresh campaign. API keys, projects, and settings are kept. It asks for confirmation; Export first if you want a backup, since the wipe is permanent.

> ⚠️ The more detail you add here, the sharper your outreach will be. A specific gap beats "you have problems with your website" every time.

### Step 2 — Run the audits (this is your pitch)

Open the prospect's record and click the two test buttons:

- **⚡ Test** — runs a quick Google speed check. Gives a score out of 100. **Under 50 = bad**, a hard number.
- **🧩 Test** — runs an SEO/schema check. Gives a score out of 100, plus a list of issues (missing title, no meta description, no structured data, etc.). **This is often the sledgehammer** — businesses can't see their own SEO problems.

When you run an audit, the prospect automatically moves from **New → Audit Recorded** in your pipeline. That's deliberate: every audit you complete is progress.

> 💡 **Bonus:** the schema/SEO check is frequently the strongest finding. If a business scores 20/100 on SEO, that's the number that'll make them say "oh no" — not their decent speed score.

### Step 3 — Generate the outreach email

Click **💬 Outreach** on the prospect. Pick a channel (Email, LinkedIn, etc.) and hit **⚙ Template draft**.

The draft auto-picks the **single worst finding** and leads with it:
- Bad score → it becomes the subject line AND the opening line (*"Your site scores 20/100 on technical SEO — customers can't find you"*).
- Fine score → it becomes a supporting detail in the body, not the hook.
- No score → falls back to a clean generic draft.

Edit the draft to sound like you, then use **📋 Copy** or **Open Email ↗**. **Open Email** copies the subject and draft to your clipboard and opens a pre-filled message in your default mail app — To, subject, and body already filled in. Review it and click **Send**. Social and phone buttons open their channels directly.

> 📌 **Rule:** Email #1 leads with ONE number only. Do NOT dump all the problems in the first email — it reads as a homework list and gets ignored. One punch. Save the pile for the report.

### Step 4 — The follow-up: full audit report

When the business replies (or as your follow-up), open the prospect → **📋 Audit report**. This generates the **full picture** — *everything* wrong, from every audit, plus the core issue and a bottom line. Hit **📋 Copy report** and paste it into the follow-up email.

This is where you pile everything on. The report:
- Proves the audit's value ("here are 5 real problems")
- Shows the fix is doable
- Sets up your offer (the walkthrough / paid pilot)

This is what turns a reply into a paying client.

### Step 5 — Follow-up reminders (don't let leads go cold)

The single biggest leak in solo lead gen is prospects dying from **no follow-up**. When you hit **Open channel** on any outreach, the dashboard automatically pops a **"⏰ Follow up when?"** prompt:

- Pick **+2 days**, **+5 days**, or **+1 week**, or set any **custom date**
- Optionally name the next action (e.g. "Send audit report")

This saves a `nextAction` + `nextActionDate` on the prospect and logs it to your activity feed. Then:

- A **🔔 badge** on the **Prospecting** tab counts how many follow-ups are due — the moment you open the app, you see what's waiting on you.
- At the top of the Prospecting list, a **"⏰ Overdue / Due today" strip** shows every prospect you need to chase, **red if overdue**, with a one-click **💬 Follow up** button and a **✓** to mark it done (which logs `followup_done`).

**The habit:** every time you send outreach, set the follow-up *before you close the tab*. Then each morning, work the strip. You can also set or edit a follow-up directly in a prospect's record (Next action / Follow-up date fields).

### Step 5b — Multi-touch cadences (set the whole sequence once)

Manual follow-ups mean re-deciding every touch. A **cadence** codes the sequence once and pre-schedules every step so you just show up and act.

**Set the template (once, per project):** go to **🔐 Settings → 📅 Multi-touch cadence**. It's a list of steps, each with a **channel** (Email / LinkedIn / X / IG / Call / Video), a **day offset** (day 0 = the day you start), and an **action note**. The built-in example is the classic cold-outreach rhythm:

| Touch | Day | Channel | Action |
|---|---|---|---|
| 1 | 0 | Email | Send audit email |
| 2 | 2 | LinkedIn | Circle back by DM |
| 3 | 5 | Call | Leave voicemail |
| 4 | 9 | Email | Send full audit report |

Add/remove steps, set your own channels and days, then **Save project + cadence**.

**Start it on a prospect:** open the prospect record → **▶ Start cadence**. That schedules every step's date from today in one click, and sets the first touch as the immediate next action.

**Restart it:** want to begin a prospect's cadence over again (started wrong, timing changed, or you just want a fresh run)? Open the record and hit **↺ Restart cadence**. It wipes that prospect's current progress and reschedules the whole sequence from today (day 0) — works for any project. It only appears on a prospect that already has a cadence; the button is hidden if none exists.

**Work it:** when a step comes due, it lands on your **⏰ Overdue / Due today** strip with a tag showing *Touch 2/4 · LinkedIn*. The **💬 Follow up** button opens the outreach modal with the correct channel pre-selected. Hit **✓** when done and it advances to the next scheduled touch automatically.

**The key rule — stop on reply:** the moment a prospect moves to **Replied** (or Call Booked / Client / Dead), the cadence **auto-cancels all remaining touches**. No pinging someone who already answered.

> 📌 A cadence never auto-sends anything. It tells you *what* to do and *when*, and opens the right channel pre-set — you still review and hit Send. That keeps outreach honest and compliant.

---

## The value ladder (where the money is)

Your dashboard is built around this ladder:

1. **Free audit** — one number, opens the door (email #1)
2. **Prove the number** — the full report shows everything (follow-up)
3. **Paid pilot** — fix ONE thing first, prove it worked
4. **Monthly partnership** — fix everything, keep them as a client

You're not selling audits. You're selling **recovered customers and regained hours**. Start with one free number, prove it, then sell the recovery.

---

## Quick reference — dashboard tabs

| Tab | What it's for |
|---|---|
| 📊 Dashboard | Your overall numbers — leads, pipeline, ad spend, ROI |
| 🔍 Prospecting | Find businesses, add records, run audits, generate outreach |
| 🎯 Pipeline | See where every prospect sits (New → Audit → Client) |
| 🧠 Content | Draft content / posts |
| 🗒 Logs | Every action automatically recorded — searchable history |
| 🔐 Settings | API keys, sender identity, booking link |

---

## The 30-second habit

Every day: **find a prospect → run ⚡ and 🧩 → send one email.** One good outreach a day beats ten half-hearted ones. The audits do the heavy lifting — you just copy, personalize, and send.

---

*Questions? This doc is a living file — open an issue and we'll rewrite the unclear parts.*