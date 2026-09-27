# AirPulse

A two-page air quality + survey results site: `index.html` (homepage with AQI panel and survey CTA) and `results.html` (full survey dashboard).

## Run it locally in VS Code

**Easiest way — Live Server extension:**
1. Open this folder in VS Code (`File → Open Folder`).
2. Install the **"Live Server"** extension (by Ritwick Dey) from the Extensions panel if you don't have it.
3. Right-click `index.html` → **"Open with Live Server"**.
4. Your browser opens at something like `http://127.0.0.1:5500/index.html` — the site is now running locally, and edits auto-refresh.

**Alternative — no extension needed:**
Open a terminal in this folder and run:
```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000` in your browser.

## What to configure

**1. Survey link** — in `index.html` and `results.html`, find:
```javascript
const GOOGLE_FORM_URL = "https://docs.google.com/forms/d/1ZGXldcIQDR3OEaV3uUAYgscK2P4lvSC87jR1LEu3vRs/viewform";
```
Replace with your form's real public link if it changes.

**2. Live AQI data** — in `index.html`, find:
```javascript
const SAMPLE_AQI = 158;
```
Replace with a live fetch to the WAQI API (see comments in the file for the exact call).

**3. Live survey results** — in `results.html`, find:
```javascript
const CSV_URL = "";
```
Paste your Google Sheet's "Publish to web" CSV link (File → Share → Publish to web → CSV) here, and the results page will pull and tally fresh responses automatically on every load. Leave it blank to keep showing the bundled snapshot of your 73 responses.

## Deploying for real

Once you're happy with it locally, push this folder to a GitHub repo and connect it to Netlify or Vercel (both free) for a live public URL. Every `git push` will auto-redeploy.
