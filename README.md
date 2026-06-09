# IDGrid — Print-ready ID photo sheets in your browser

A zero-dependency, client-side web tool that tiles any photo into a print-ready grid (e.g. 6×3.5×4.5 cm photos on a 10×15 cm canvas) and lets you download a high-resolution PNG instantly.

**No uploads. No servers. No accounts. Everything runs in your browser.**

---

## Live demo

👉 `https://yourusername.github.io/id-photo-grid`

---

## Features

- Drag-and-drop or click-to-upload any JPG, PNG, or WEBP photo
- Country presets (India, Schengen, US passport, UK, Germany)
- Fully configurable photo size and print canvas size
- Auto centre-crops to the correct aspect ratio
- Even spacing across the full canvas with light grey cut guides
- Outputs a 300 DPI-equivalent PNG ready for any photo printer
- Runs entirely in the browser — your photo never leaves your device

---

## How to deploy (5 minutes)

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and sign in (create a free account if needed)
2. Click the **+** icon (top right) → **New repository**
3. Name it `id-photo-grid` (or anything you like)
4. Set it to **Public**
5. Click **Create repository**

### Step 2 — Upload the file

1. On your new repo page, click **Add file** → **Upload files**
2. Drag and drop `index.html` into the upload area
3. Scroll down, click **Commit changes**

### Step 3 — Enable GitHub Pages

1. Go to your repo's **Settings** tab
2. In the left sidebar, click **Pages**
3. Under **Branch**, select `main` and folder `/` (root)
4. Click **Save**

### Step 4 — Get your URL

GitHub will show a banner:
> *Your site is live at `https://yourusername.github.io/id-photo-grid`*

It takes 1–2 minutes to go live. That's it — share the link with anyone.

---

## Customising presets

Open `index.html` and find the `preset-list` section (around line 130). Each preset is a button like:

```html
<button class="preset-btn" data-w="3.5" data-h="4.5">
  🇮🇳 India / Italy permit (3.5×4.5 cm)
</button>
```

Change `data-w` (width in cm) and `data-h` (height in cm) to match your country's requirements. Standard sizes for reference:

| Country / Document | Width (cm) | Height (cm) |
|---|---|---|
| India passport / Italy residence permit | 3.5 | 4.5 |
| Schengen visa | 3.5 | 4.5 |
| US passport | 5.0 | 5.0 |
| UK passport | 3.5 | 4.5 |
| German ID card | 4.0 | 6.0 |
| Canada passport | 5.0 | 7.0 |
| Australia passport | 3.5 | 4.5 |

---

## Print instructions

1. Download the PNG
2. Send it to any photo printer (pharmacy kiosk, online service) as a **10×15 cm / 4×6 inch** print
3. **Important:** set print scale to **100% / actual size** — do not use "fit to page"
4. Cut along the grey lines

---

## How it works (technical)

The tool uses the browser's `<canvas>` API to:

1. Load the uploaded image into an `Image` element
2. Centre-crop it to the target photo aspect ratio
3. Draw it tiled onto an offscreen canvas sized at 300 DPI equivalent (10 cm / 2.54 × 300 = 1181 px wide)
4. Add 1 px cut guide rectangles around each photo
5. Export the canvas as a PNG blob and trigger a download

No libraries. No build step. One HTML file.

---

## Local development

No setup needed. Just open `index.html` directly in any browser:

```bash
# macOS / Linux
open index.html

# Windows
start index.html

# Or serve locally to avoid any file:// quirks
python3 -m http.server 8080
# then open http://localhost:8080
```

---

## Updating the site

Whenever you want to make changes:

1. Edit `index.html` locally
2. Go to your GitHub repo → click `index.html` → click the pencil (edit) icon
3. Paste your updated code → **Commit changes**

The live site updates within ~30 seconds.

---

## License

MIT — free to use, modify, and share.
