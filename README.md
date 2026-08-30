# Portfolio — Deploy Guide

## Why you were getting 404 on Vercel
Vercel looks for a file literally named `index.html` in the **root** of your
repo. Your uploaded file was named `index__2_.html` (a browser download
rename), so Vercel had nothing to serve at `/`. That's the whole bug — the
site itself is fine.

This folder fixes it:
- `index.html` — your site, renamed correctly.
- `vercel.json` — tells Vercel to treat this as a static site and always
  fall back to `index.html` (belt-and-suspenders, prevents 404s on refresh
  too).

## Push to GitHub
```bash
git init
git add .
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

## Deploy on Vercel
1. Go to vercel.com → **Add New → Project**.
2. Import the GitHub repo you just pushed.
3. Framework Preset: choose **Other** (not Next.js/etc — this is plain HTML).
4. Root Directory: leave as `./` (don't point it into a subfolder).
5. Build Command: leave **empty**. Output Directory: leave **empty**.
6. Deploy.

If you already have a Vercel project connected to this repo and it's still
404ing, the likely cause is the Root Directory setting is pointed at a
subfolder in Project Settings → General — check that it's set to `./`.

## Before it's really "done"
A few sections have "coming soon" placeholders you'll want to fill in
before sharing this widely:
- GitHub repo links (Certifications section is fine, but the repo cards say
  "Repository coming soon")
- LinkedIn / GitHub profile URLs in Contact section
- Resume PDF link
- Contact form isn't wired to a backend yet (Formspree or EmailJS both work
  in a few minutes if you want it live)
