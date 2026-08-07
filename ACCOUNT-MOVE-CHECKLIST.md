# Moving to a new Claude account — checklist

Snapshot taken 2026-08-07 from the old account, so nothing gets lost in the move.
This file lives on GitHub, which belongs to your GitHub account (Mainhorsegirl22),
not your Claude account — so it survives the switch. From your **new** account,
open this repo and this file, and Claude there can set everything back up.

---

## 1. Things that DON'T need moving (already safe)

- **GitHub repositories** — `Mainhorsegirl22/The-Ginosko-Experience` and
  `Mainhorsegirl22/wkg-briefing` live on GitHub, not on the Claude account.
  On the new account, just connect GitHub again and grant it access to these repos.
  All the work branches Claude pushed over the past weeks are on GitHub and are safe.
- **Data in connected apps** — everything in Airtable (Windy Knoll Goldens Master
  base), Gmail, Google Drive, Google Calendar, Canva, and QuickBooks lives in those
  services. Nothing to copy — just reconnect the connectors (see section 3).

## 2. Scheduled tasks to recreate on the new account

Scheduled tasks are tied to the account and will NOT come along. There are two.

> ⚠️ **Important:** the daily briefing below is live and fires every morning.
> After you recreate it on the new account and see it work once, **delete or
> pause the one on the old account** (or just close the old account) so you
> don't get two briefing emails a day.

### 2a. "WKG Daily Briefing" (active — fires daily)

- Schedule: every day at 10:00 UTC (6:00 AM Eastern)
- Runs as: a fresh cloud session each day, checked out on repo
  `https://github.com/Mainhorsegirl22/wkg-briefing`
- Model: claude-sonnet-5 · Tools: Bash, Read, Write, Edit, Glob, Grep
- Prompt (paste verbatim when recreating):

```
You are running the Windy Knoll Goldens daily briefing as a scheduled cloud job. The git repository you are checked out in contains everything you need. Read BRIEFING.md in the repository root and follow it EXACTLY, top to bottom, for today's date in America/New_York. It tells you how to pull the day's data from Airtable over its REST API (the read-only token is in airtable_token.txt in the repo root), which sections to build and the wording rules, how to write the day's JSON data file to /tmp, and how to send the email by running render_briefing.py (the Brevo send-only API key is in brevo_key.txt in the repo root). This is the real daily send, so actually send the email; it is idempotent, so if a step fails partway just re-run the same render command. Never print, echo, cat, or commit either credential. When finished, report a one-line confirmation with the send result (HTTP status and messageId) and the item counts per section.
```

### 2b. "WKG Briefing DEBUG" (parked — scheduled Dec 31, effectively off)

A diagnostic version of the same job used for troubleshooting. You probably don't
need to recreate it. If the daily briefing ever breaks on the new account, ask
Claude to build a debug run against the `wkg-briefing` repo; the full original
debug prompt is preserved in that repo's history/context if needed.

## 3. Connectors to reconnect on the new account

Go to Settings → Connectors on the new account and reconnect:

- Gmail
- Google Drive
- Google Calendar
- Airtable
- Canva
- Intuit QuickBooks
- GitHub (for Claude Code) — grant access to `The-Ginosko-Experience` and `wkg-briefing`

## 4. Published artifact pages

These five pages are owned by the old account; their claude.ai links will stop
working once it's closed. Full backup copies of all five are in this repo under
[`artifact-backups/`](artifact-backups/). On the new account, ask Claude to
republish any of them from these files (or just open the HTML files directly
in a browser; they're self-contained).

| Page | Backup file |
|---|---|
| The Ginosko Experience (discipleship weekend info page) | `artifact-backups/the-ginosko-experience.html` |
| Maine Equine Calendar for Shooters, Jul 27–Aug 9 | `artifact-backups/maine-equine-calendar-jul27-aug9.html` |
| Airtable Automations — Windy Knoll Goldens playbook | `artifact-backups/airtable-automations-windy-knoll-goldens.html` |
| style_g_artifact (design draft) | `artifact-backups/style_g_artifact.html` |
| style_f_artifact (design draft) | `artifact-backups/style_f_artifact.html` |

**If you shared any of these links with other people** (e.g. the Ginosko page),
republish from the new account and send out the new link before closing the old one.

## 5. Chat history

Conversations can't be transferred between accounts. If you want a copy for your
records, do this **before** closing the old account:

claude.ai → Settings → Privacy → **Export data** — a download link is emailed to
mainehorsegirl22@gmail.com.

## 6. Unfinished conversations (for reference)

A few sessions on the old account were mid-task and waiting on your answer.
Any files they pushed are safe on GitHub branches; the conversations themselves
won't move. The notable ones:

- **Puppy photo collages in Canva** — boys' collage exported; girls' layout not chosen yet
- **WordPress Elementor centering** — waiting on which section to center
- **Airtable dashboard with planning interface** — waiting on whether to add the Completed Log to Greg's dashboard
- **Litter update email** — waiting on Facebook/blog links

If you still want any of these finished, just re-ask on the new account — the
underlying work (Canva designs, Airtable base, WordPress site) is all in the
external services and unaffected by the account switch.
