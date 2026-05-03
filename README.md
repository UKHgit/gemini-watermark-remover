# ✦ Gemini Watermark Remover by UKH

> Automatically removes watermarks from Gemini AI-generated images — copy, download, and share clean full-resolution images with one click.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Netlify Status](https://api.netlify.com/api/v1/badges/placeholder/deploy-status)](https://app.netlify.com)

---

## 🚀 Features

| Feature | Details |
|---|---|
| **Auto Detection** | Spatial + gradient analysis finds the exact watermark region |
| **Real-Time Removal** | Processes images the moment Gemini loads them |
| **One-Click Copy** | Copy the clean image straight to your clipboard |
| **Full-Size Download** | Download original-resolution PNG — no quality loss |
| **100% Private** | Everything runs in your browser; nothing is uploaded |
| **Before/After Slider** | Interactive comparison in the Demo Tool |
| **Live Adjustments** | Brightness, contrast, saturation sliders in demo |

---

## 📦 Installation (Userscript)

1. Install [Tampermonkey](https://www.tampermonkey.net/) for your browser.
2. Click **[Install Userscript](userscript/gemini-watermark-remover.user.js)** from the site.
3. Confirm the installation in Tampermonkey.
4. Open [gemini.google.com](https://gemini.google.com/app) and generate any image.
5. Hit **Copy** or **Download** — your image is now watermark-free.

---

## 🖼 Demo Tool

The **Live Demo** at `/dev-preview.html` lets you test the watermark-removal algorithm on any local image:

- Drag & drop, click to browse, or paste (Ctrl+V)
- Interactive before/after comparison slider
- Live brightness / contrast / saturation adjustments
- Copy result to clipboard or download as PNG

---

## 🛠 Local Development

```bash
# Install dependencies
pnpm install

# Start local dev server (auto-serves dist/)
pnpm dev

# Production build
pnpm build
```

The dev server starts at `http://127.0.0.1:4173/` (auto-increments if busy).

---

## 🌐 Deployment (Netlify)

This project is configured for **one-click Netlify deployment**:

1. Push this repo to GitHub (`UKHgit/gemini-watermark-remover`)
2. Connect the repo in [app.netlify.com](https://app.netlify.com)
3. Netlify auto-detects `netlify.toml` — build command: `node build.js --prod`, publish dir: `dist`
4. Deploy!

---

## 🔬 How It Works

The algorithm uses **reverse alpha-blending** to reconstruct the original pixel values beneath the semi-transparent watermark layer:

1. Detects the watermark bounding box using spatial residual analysis
2. Estimates the watermark alpha channel via gradient scoring
3. Inverts the blending equation to recover the clean pixel
4. Outputs a full-fidelity PNG with no visible artefacts

> Read the original deep-dive: [Removing Gemini AI Watermarks — Reverse Alpha Blending](https://allenkuo.medium.com/removing-gemini-ai-watermarks-a-deep-dive-into-reverse-alpha-blending-bbbd83af2a3f)

---

## 📄 License

MIT © UKH
