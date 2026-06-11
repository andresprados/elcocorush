# Reza's Voucher Hunt 🗺️🐠

A single-page treasure-hunt landing page with a Mexican / island theme: papel picado banner,
swimming fish, a palm-tree island, and **four treasures** that unlock one at a time. The first
treasure shows a live countdown; each treasure reveals a voucher code when its time arrives.

Everything is in one file: **`index.html`** — no build step, no dependencies.

## ✏️ Customize your treasures

Open `index.html`, scroll to the `TREASURES` array near the bottom (inside `<script>`), and edit:

```js
const TREASURES = [
  {
    chest: "🗺️",                          // emoji on the card
    title: "El Primer Tesoro",             // name
    hint:  "The hunt begins!",             // teaser shown before unlock
    unlockISO: "2026-06-18T18:00:00",      // when it unlocks (local time)
    code:  "REZA-UNO-2026",                // voucher code revealed
    desc:  "Your first voucher is yours."  // reward description
  },
  // ...three more
];
```

- `unlockISO` uses the format `YYYY-MM-DDTHH:MM:SS` (the visitor's local time).
- The **first** item in the array gets the big live countdown. The rest show "Unlocks <date>".
- When a treasure's time passes, the card opens with confetti and shows the code automatically.

> Note: this is a static page, so the dates and codes are visible in the page source. It's perfect
> for a fun reveal, but don't use it for secrets you truly need to keep hidden until reveal time.

## 🚀 Publish free on GitHub Pages

1. Create a new repository on GitHub (e.g. `voucher-hunt`).
2. Upload `index.html` (and this `README.md`) to the repo — either via the web "Add file → Upload
   files" button, or with git:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Reza's Voucher Hunt"
   git branch -M main
   git remote add origin https://github.com/<your-username>/voucher-hunt.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Select branch **`main`** and folder **`/ (root)`**, then **Save**.
6. Wait ~1 minute. Your site goes live at:
   `https://<your-username>.github.io/voucher-hunt/`

That's it — share the link. 🎉

## 🔧 Local preview

Just double-click `index.html`, or run a tiny local server:

```bash
python -m http.server 8000
# then open http://localhost:8000
```
