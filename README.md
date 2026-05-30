# ChordLens

Real-time MIDI chord recognition, grand staff notation, and practice drills in a single static HTML file.

## Deploying to Vercel (git push)

1. **Create a GitHub repo** and push these files to it:
   ```
   git init
   git add .
   git commit -m "Initial ChordLens deploy"
   git branch -M main
   git remote add origin git@github.com:YOUR_USERNAME/chordlens.git
   git push -u origin main
   ```

2. **Import to Vercel**
   - Go to https://vercel.com/new
   - Pick your `chordlens` repo
   - Framework Preset: **Other** (Vercel auto-detects static)
   - Build Command: *(leave empty)*
   - Output Directory: *(leave empty — defaults to repo root)*
   - Click **Deploy**

3. Done. Subsequent `git push` to `main` auto-deploys.

## Local preview

Any static server works. Two easy options:

```
# Python
python3 -m http.server 8080

# Node (one-off, no install)
npx serve .
```

Then open http://localhost:8080.

## Browser requirements

- **Chrome or Edge** on desktop (Web MIDI API).
- Safari/Firefox open the app but MIDI input is disabled.
- iOS Safari does not support Web MIDI — use a USB-OTG keyboard on Android/desktop instead.

## What's in this folder

- `index.html` — the entire app (HTML, CSS, JS in one file)
- `vercel.json` — security headers + cache rules; no build step
- `.gitignore` — keeps `.vercel/` and editor junk out of git

## External dependencies (loaded at runtime via CDN)

- `cdn.jsdelivr.net` — soundfont-player library
- `fonts.googleapis.com` / `fonts.gstatic.com` — Sora + Manrope
- `gleitz.github.io` — MusyngKite SoundFont samples (loaded on first instrument switch)

No bundler, no npm install, no secrets.
