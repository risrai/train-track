# Train Status Checker (Simple)

A single static page. No backend, no build step, no GitHub Actions.

## Setup

1. Create a new **public** GitHub repo.
2. Upload just this one file: `index.html` (drag it directly onto the repo's
   "Add file → Upload files" page - no folders involved, so the earlier
   upload issue won't come up).
3. Settings → Pages → Source: "Deploy from a branch" → branch `main` → folder `/ (root)` → Save.
4. Wait a minute, then visit `https://<your-username>.github.io/<repo-name>/`.
5. Get a free API key at https://railradar.in, paste it into the page along with
   a train number, and hit "Check Status."

Your API key, train number, and date are remembered in the browser (localStorage)
so you don't have to retype them next time you open the page.

## What it does

- Calls RailRadar's live status API directly from your browser
- Shows: train name, status, current delay, last-crossed station, next station,
  estimated ETA for the next station, last-updated time, and any diversion notices

## What it doesn't do (by design, for simplicity)

- No push notifications - you open the page and tap "Check Status" whenever you
  want an update.
- No automatic polling in the background.
- No server - your API key is visible in the page's JavaScript to anyone who
  opens dev tools on it, which is fine as long as you don't share the link.

If later you want automatic hourly/stop-reached push notifications without you
opening the page, that needs the backend + service worker version we built earlier -
just ask and I can bring that back in.
