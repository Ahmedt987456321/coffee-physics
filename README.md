# Coffee Physics (web app)

Plan your coffee so you drink it at the temperature you want. Real cooling
physics (convection + radiation + evaporation) for different cups, milks, and
rooms, with a live drinking window, saved drinks, sharing, and live weather.

This is a single static file (`index.html`). No build step, no backend needed.

## Run locally
```
cd app
python -m http.server 8765
```
Open http://localhost:8765

## What works with no backend
- **Live weather**: the browser's location + Open-Meteo (free, no API key). The
  outdoor temperature and humidity feed the cooling physics. Best for drinking
  outside; indoors, keep the room presets.
- **Saved drinks**: stored in the browser (localStorage).
- **Sharing**: the drink is encoded into the URL; "Share" copies the link.

## Deploy (pick one, all free, all HTTPS)
Live weather needs HTTPS, which all of these provide automatically.

**Netlify (drag and drop, easiest)**
1. Go to https://app.netlify.com/drop
2. Drag the `app` folder onto the page. Done, you get a URL.

**Vercel**
```
npm i -g vercel
cd app && vercel
```

**GitHub Pages**
1. Push this repo to GitHub.
2. Settings -> Pages -> deploy from branch, folder `/app` (or move index.html to root).

## Later (needs a small backend)
- Accounts and cross-device saved drinks.
- Short share links.
- Usage analytics.
