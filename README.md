# LifeFile Ticket Dashboard — Preston's Pharmacy

A lightweight web dashboard that pulls LifeFile support tickets from Outlook and makes them visible to the whole pharmacy team — no individual login required.

## Live Site

🔗 [jlopezrx2112.github.io/LF-TICKETS](https://jlopezrx2112.github.io/LF-TICKETS/)

> Team password required to access.

## How It Works

1. Joel signs in with his Microsoft account (PKCE OAuth2 — no library needed)
2. The app reads emails from the **LF TICKETS** Outlook folder via Microsoft Graph API
3. Tickets are parsed, cleaned, and saved to JSONBin (shared cloud storage)
4. The rest of the team opens the dashboard and sees the latest tickets instantly — read-only, no login needed

## Features

- 🔍 Search by ticket #, subject, keyword, reporter, or category
- 🏷️ Filter by status (Open, In Progress, Resolved) and category
- 📋 Expand any ticket to see issue description, resolution notes, and internal notes
- ✏️ Joel can update ticket status and add resolution/internal notes directly in the dashboard
- ⇓ Export all tickets to CSV
- 🔄 One-click sync pulls the latest emails from Outlook
- 🟣 **DUP** badge flags tickets with duplicate subject lines
- 🟡 **NEW** badge highlights tickets seen for the first time

## Tech Stack

| Layer | Tool |
|---|---|
| Hosting | GitHub Pages |
| Auth | Microsoft PKCE OAuth2 (native, no MSAL) |
| Email source | Microsoft Graph API (`Mail.Read`) |
| Shared storage | JSONBin |
| Frontend | Vanilla HTML/CSS/JS — single file |

## Azure App Registration

- **App name:** Preston's Pharmacy LF Tickets
- **Permissions:** `Mail.Read`, `User.Read`
- **Auth flow:** Authorization Code + PKCE

## Updating the Dashboard

1. Get an updated `index.html` from Claude
2. Go to this repo on GitHub
3. Click `index.html` → Edit (pencil) → paste new content, or drag-upload the file
4. Commit → wait ~2 minutes → refresh the live URL

---

*Built with Claude · Preston's Pharmacy · 2026*
