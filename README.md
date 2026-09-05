# S. Bhuvanesh — Portfolio Web App

A fully self-contained, installable web app (PWA). The photo, fonts CSS, and all
JavaScript are embedded directly in `index.html` — nothing external is required
to view the page itself. `manifest.json`, the icons, and `sw.js` add real
"install as an app" and offline support on top of that.

## Run it locally
Just double-click `index.html` — it works straight from disk.

Note: service workers require a real server origin (not `file://`) to register,
so offline caching and "Add to Home Screen" only activate once it's hosted (see
below). The page itself works fine either way.

## Host it (any of these work, all free)
- **Vercel / Netlify / Cloudflare Pages**: drag-and-drop this whole folder in
  their dashboard, or connect a GitHub repo containing these files.
- **GitHub Pages**: push this folder to a repo, enable Pages on the `main`
  branch, root folder.

No build step, no `npm install` — it's static files.

## Installing it as an app
Once hosted over `https://`:
- **Desktop Chrome/Edge**: an install icon (⊕) appears in the address bar.
- **Android Chrome**: menu → "Add to Home screen" / "Install app".
- **iOS Safari**: Share → "Add to Home Screen" (uses `apple-touch-icon.png`).

## Files
- `index.html` — the entire portfolio (single file, photo embedded as base64)
- `manifest.json` — app name, colors, icons (PWA install metadata)
- `sw.js` — service worker; caches the app so it still opens with no network
- `icons/` — app icons generated from the Spidy AI spider mark
- `favicon.ico` — browser tab icon
