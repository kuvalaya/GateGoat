# GateGoat — Family Travel Companion

A single-file deployable website. No backend, no API keys, no build step.

## Run it locally

Just **double-click `index.html`** — it opens in your browser and works.

Or serve it locally if double-clicking gives you geolocation/notification trouble:

```bash
# Python (any version)
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy it (free, takes ~1 minute)

### Option 1 — Netlify Drop (easiest)
1. Go to https://app.netlify.com/drop
2. Drag the `gategoat-website` folder onto the page
3. You get a live URL instantly

### Option 2 — Vercel
1. `npm i -g vercel`
2. Run `vercel` inside the `gategoat-website` folder
3. Follow the prompts

### Option 3 — GitHub Pages
1. Push this folder to a GitHub repo
2. Settings → Pages → Deploy from branch → `main` / root
3. Live at `https://<you>.github.io/<repo>/`

### Option 4 — Cloudflare Pages
1. Push to GitHub
2. Connect repo at https://pages.cloudflare.com
3. No build command, output dir is `/`

## What's inside

- `index.html` — the entire app: React via CDN, embedded ~150-airport database, inline SVG icons, all components, styles
- Manual boarding-pass entry (no OCR needed, since there's no Claude on this version)
- Open-Meteo for weather (free, no key)
- Browser geolocation for distance to terminal
- Browser Notification API + in-app toast for the 15-min pre-boarding alert

## Browser notes

- Notifications and geolocation only work over **HTTPS** or `localhost`. All four hosts above serve HTTPS by default.
- The pre-boarding alert fires while the tab is open. If you close the browser, it won't fire — that would need a service worker / native app.
