# Lead Gen Dashboard — v3 Roadmap (Steps To Do)

Current state: `index.html` — tabs for Dashboard, Prospecting, Pipeline, Content, Logs, and Settings; localStorage data; live Google Places search + AI drafts (keys in Settings); deep-link sending with auto-logging; fictional sample prospects preloaded.

Recommended build order below — each item is independent, but 1 and 2 unlock 3 and 4.

---

## 1. Follow-up reminders with next-action dates
**Why first:** the #1 leak in solo lead gen is prospects dying from no follow-up, not bad first touches. Highest ROI, no external services needed.

Steps:
- Add `nextAction` (text) and `nextActionDate` (date) fields to the prospect record modal.
- Auto-suggest on every logged outreach: after `channel_opened`, prompt "Follow up when?" with quick picks (+2d, +5d, +1w).
- Add a "Due today / Overdue" strip at the top of the Prospecting tab, sorted by date — red for overdue.
- Add a 🔔 badge count on the Prospecting tab button.
- Log `followup_set` and `followup_done` actions.

## 2. Multi-touch cadences (email day 0 → DM day 2 → call day 5)
**Why:** manual sequencing = forgotten steps. Codify the cadence once, apply per prospect.

Steps:
- Define cadence templates in Settings (per project): ordered steps [channel + day offset + template].
- "Start cadence" button on a prospect → generates the whole chain of nextActionDates.
- Each due step deep-links straight into the Outreach modal with the right channel preselected.
- Stop rules: any reply (status → Replied) auto-cancels remaining steps.
- Depends on item 1's reminder engine.

## 3. Supabase backend — multi-device sync
**Why:** localStorage = one browser, one machine. Supabase gives real persistence, multi-device, and the foundation for true API sending. The URL/anon-key fields already exist in Settings → Per-project credentials.

Steps:
- Create a Supabase project.
- Tables mirroring the current data model: `projects`, `leads`, `campaigns`, `prospects`, `saved_searches`, `logs`, `settings`. Keep the same field names as the JS objects for a thin sync layer.
- Enable Row Level Security; single-user auth (email magic link) to start.
- Sync strategy v1: localStorage stays the working copy; add "Push to cloud / Pull from cloud" buttons + last-synced timestamp. (Full realtime sync later.)
- Migration: JSON backup → import script.

## 4. MailerLite → leads auto-flow
**Why:** new subscribers are leads; today they'd be entered manually.

Steps:
- Blocker to know: MailerLite's API does not allow browser (CORS) calls, so this cannot run from the HTML file directly. Two workable paths:
  - **Path A (no code):** run a scheduled server-side job that pulls new subscribers weekly and produces a CSV formatted for the dashboard's lead import.
  - **Path B (after item 3):** Supabase Edge Function on a cron calls the MailerLite API server-side (key stored as a Supabase secret, not in the browser) and inserts rows into `leads` with source "Email / Newsletter".
- Map: subscriber email + signup date + group → lead {name, email, project, source, date}.
- Dedupe on email before insert.

## 5. PageSpeed auto-evidence
**Why:** auto-attach a mobile speed score as audit evidence, so every prospect carries a hard number.

Steps:
- Google PageSpeed Insights API is free and CORS-friendly — works straight from the HTML file.
- Add "⚡ Test site speed" button on prospects that have a website.
- Call `https://www.googleapis.com/pagespeedonline/v5/runPagespeed?url=<site>&strategy=mobile` (key optional at low volume).
- Store mobile performance score + LCP in the prospect record; append to Visibility Gap notes (e.g., "mobile score 34/100 — evidence: PSI result").
- Feed the score into the Gap severity part of the rubric and into AI draft prompts.

---

## Parking lot (mentioned, not yet scoped)
- Open/reply tracking for email (needs MailerLite campaigns or a tracking pixel — server-side, post-item-3).
- True API sending for DMs — X/Meta/LinkedIn don't allow automated DMs without approved apps; deep links + clipboard stay the honest v1.
- Speed-to-lead metric on the Dashboard tab (time from lead created → first `channel_opened` log).
- Duplicate-check against your existing lead list before importing.
