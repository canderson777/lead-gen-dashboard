# Lead Generation Dashboard

A single-file, self-hosted lead-generation and prospecting dashboard. Everything runs
in your browser — no backend, no build step, no account. Open `index.html` and go.

**It opens with fictional sample data**, so you can see exactly how it works before you
add anything. Replace it with your own prospects whenever you're ready.

<!-- Screenshot: add docs/screenshots/dashboard.png, then replace the next line with:
![Lead Gen Dashboard](docs/screenshots/dashboard.png) -->

## What you can use it for

- **Find local businesses** with Google Places search, filter and score them, and build a
  prospect list you actually work through.
- **Run quick website audits** (speed + SEO/schema) and turn the single worst finding into
  a specific outreach email that gets replies.
- **Track prospects through a pipeline** — New → Contacted → Qualified → Won → Lost.
- **Draft outreach and marketing content** with your own AI key, or fall back to built-in templates.
- **Follow up on time** — reminders, due/overdue lists, and multi-touch cadences.
- **See your numbers** — leads, pipeline value, ad spend, and ROI with charts and date filters.
- **Keep a local log** of every search, draft, and change.

## Quick start

1. **Download or clone** this repo.
2. **Open `index.html`** in any modern browser (double-click it — no server needed).
3. It opens on the **demo data**. Click through every tab to see how it works.
4. When you're ready for real data, open **Settings** (the 🔐 tab), add your keys, then
   clear the demo (Dashboard → **Demo data → clear & start fresh**) and add your own.

## Getting data for your business

Set these up in **Settings**:

- **Google Places API key** — powers live business search. In Google Cloud Console, enable
  **Places API (New)** and create a key. This is what lets you search real businesses by
  trade + city.
- **AI provider key** *(optional)* — Claude, OpenAI, or OpenRouter. With a key, outreach
  drafts are written by the model; without one, they fall back to built-in templates.
- **Your sender identity and booking link** — so drafts read like a real person, not a robot.

Paste your keys, then use **Prospecting → live search** to pull real businesses, or import a
CSV of businesses you already have. From there, run the audits, generate outreach, and work
the pipeline. The full walkthrough is in
[`How-To-Use-Lead-Gen-Dashboard.md`](How-To-Use-Lead-Gen-Dashboard.md).

### Optional: hosting

It's one HTML file, so any static host works — **GitHub Pages**, Netlify, Vercel, or
Cloudflare Pages. When it's hosted, each visitor enters their **own** keys in their **own**
browser; nothing is shared.

## Bring your own keys (privacy)

- All credentials live **only in your browser's `localStorage` on your own machine**. They
  never leave your computer except to call the APIs you configure.
- **Nothing is committed to this repo**, and nothing is sent to any server owned by this project.
- Because it's a static client-side app: don't run it on a shared/public computer with real
  keys entered, and don't bake keys into a public deployment — each user enters their own.
- Back up with **Settings → Export**. Backups include your keys, so store them safely.

## Demo data

The app ships with **fictional** sample projects, campaigns, leads, and prospects (names like
"Sample Plumbing Co", emails at `example.com`, phone numbers like `(555) 010-0101`). It exists
only so the dashboard looks complete on first open. Clear it at any time to start fresh.

## Files

- `index.html` — the entire app (UI, logic, and data model in one file).
- `How-To-Use-Lead-Gen-Dashboard.md` — a plain-English walkthrough of the audit-led workflow.
- `lead-gen-dashboard-ROADMAP.md` — where the project is headed next.

## Contributing

Issues and PRs welcome. Keep it dependency-light and single-file where possible.

## License

MIT — see [LICENSE](LICENSE).
