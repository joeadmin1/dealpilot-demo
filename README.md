# DealPilot — AI Assistant for Real Estate

A working demo of an AI copilot for a solo real-estate agent: it pulls CMAs, short-lists homes, books consultations, re-warms cold leads, and drafts listing agreements — with the agent (you) approving anything that actually goes out to a client.

Single file. No build step, no framework, no dependencies — open `index.html` and it runs.

## Run it

```bash
open index.html
```

Or host the folder anywhere static — GitHub Pages, Vercel, Netlify, Cloudflare Pages. Every flow is scripted and self-contained, so it feels real in under 30 seconds without touching anything sensitive.

## What it does

- **Assistant chat with live tool work** — streaming replies show what the AI is actually doing (CRM query, comps pull, valuation model, document checks) as inline tool chips you can expand
- **Five scripted demos** — CMA with a defendable price range · MLS short list ranked against a buyer brief · consultation scheduling with a shared calendar view · cold-lead re-warm wave · listing agreement draft — each ends in an approval card, never silent sending
- **Artifacts** — every flow opens a real side panel: interactive CMA, listing grid with short-listing hearts, week calendar with proposed windows + voice/email/SMS previews, DocuSign-style document
- **Tasks** — ranked, sourced-signal suggested tasks; one click runs one as a live conversation
- **Approvals** — every outbound action (call, email, SMS, envelope) waits at a gate; approve, reject, or edit the plan
- **Agents** — six back-office workers doing one job each, with what they're working on right now
- **⌘K command palette** — jump to any conversation, task, page, or flow

## Demo data

Everything is scripted sample data for a fictional agent ("Jordan Avery, Crestpoint Realty") and one fictional client ("Dana Whitfield, 48 Maple Grove Ln"). No real client data, no backend, no network calls. A "Reset demo" button restores the seeds by clearing `localStorage` (`dealpilot_demo_v1`).

## Rebrand it for a client (the template block)

This repo is a **template for spinning up client demos fast**. Copy the folder, then edit the `CONFIG` object at the very top of the `<script>` in `index.html` — it's marked `⚙️ CONFIG — THIS IS THE TEMPLATE BLOCK`:

- product name, agent persona name, brokerage, contact details
- color palette (one place), fonts, logo mark
- connected tools shown in the UI (CRM, MLS, Google Calendar, Twilio, DocuSign…)
- demo client + property + seed conversations and scripted flows

Everything else — palette, copy, icons — is generated from that object. Rename the persona and brokerage to avoid two demos looking like the same product.

## Cloning for the next client

1. Copy this folder to `clientname-demo`
2. Edit the `CONFIG` block (names, palette, connections, seed data)
3. Search-and-replace any remaining hardcoded copy tied to the persona (there's deliberately very little)
4. Host it and share the link

## Notes

- Dark-mode only, mobile-aware, ~60 KB of hand-written HTML/CSS/JS in one file
- All playback is time-scripted and idempotent: conversations replay from scratch per conversation, and artifacts are stored per conversation so parallel demos don't overwrite each other
