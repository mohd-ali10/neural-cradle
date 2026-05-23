# 🕸️ NEURAL CRADLE
### Holographic String Interface — Interactive Web Art Installation

![License](https://img.shields.io/badge/license-MIT-cyan) ![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow) ![MediaPipe](https://img.shields.io/badge/MediaPipe-Hands-magenta) ![p5.js](https://img.shields.io/badge/p5.js-1.9.3-blue)

> *An interactive cyberpunk art experience powered by real-time hand tracking.*
> *No controllers. No touch. Just your hands.*

---

## ✦ What is this?

**Neural Cradle** is a browser-based interactive art installation that tracks your hands through the webcam and renders holographic energy strings between your fingertips in real time.

Inspired by the classic *Cat's Cradle* string game — reimagined as a futuristic biometric interface. Move your hands to stretch glowing laser strings. Touch your fingertips together to trigger particle explosions. The visuals respond to your speed, distance, and gesture with cinematic light effects.

---

## ✦ Live Demo

🔗 **[Launch Neural Cradle](https://yourusername.github.io/neural-cradle)**

> Works best on desktop Chrome or Edge. Mobile supported via HTTPS.

---

## ✦ Features

- **Real-time hand tracking** — detects both hands simultaneously using MediaPipe Hands (21 landmarks per hand)
- **Holographic energy strings** — 5 elastic laser strings connect matching fingertips across both hands
- **Reactive physics** — string thickness, glow intensity, and oscillation all react to movement speed and distance
- **Particle explosions** — touch opposite fingertips together to trigger neon particle bursts
- **Cinematic visual style** — cyberpunk color palette, bloom glow, motion trails, CRT scanlines, and vignette
- **Webcam silhouette** — faint ambient background preserves your form without exposing raw video
- **Zero dependencies beyond CDN** — runs instantly in any modern browser, no install needed

---

## ✦ How to Use

1. Open the live link above in **Chrome or Edge**
2. Allow **camera access** when prompted
3. Hold both hands up in front of the webcam
4. **Move** your hands to stretch and animate the strings
5. **Touch** fingertips from opposite hands together to trigger explosions

---

## ✦ Tech Stack

| Layer | Technology |
|---|---|
| Hand Tracking | [MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) |
| Rendering | [p5.js](https://p5js.org/) + Canvas 2D API |
| Language | Vanilla JavaScript (ES6+) |
| Hosting | GitHub Pages |
| Build Tools | None — single HTML file |

---

## ✦ Architecture

```
cats-cradle/
└── index.html
    ├── Constants & Config
    ├── Utility Functions
    ├── Particle System (object-pooled, 300 cap)
    ├── SmoothedHand (LERP landmark filtering)
    ├── MediaPipe Initialization & Callback
    └── p5.js Rendering Pipeline
        ├── Webcam silhouette layer
        ├── Hand skeleton + landmark dots
        ├── Energy string renderer (4 glow layers)
        ├── Touch detection & particle bursts
        └── HUD overlay
```

---

## ✦ Run Locally

No build tools needed. Just serve the file over HTTP:

```bash
# Clone the repo
git clone https://github.com/yourusername/neural-cradle.git
cd neural-cradle

# Serve locally (Python)
python -m http.server 8080

# Then open in browser
http://localhost:8080
```

> ⚠️ Camera access requires a secure origin (`https://` or `localhost`). Opening the file directly via `file://` will block the webcam.

---

## ✦ Visual Design

- **Color palette:** Neon cyan `#00f0ff` · Magenta `#ff00cc` · Electric yellow `#ffdc00`
- **Background:** Deep midnight black with fade trails (`rgba(0,2,12,0.12)`)
- **Effects:** Canvas `shadowBlur` glow · Additive `screen` blending · CRT scanline CSS overlay · Radial vignette
- **Strings:** 4-layer glow rendering (bloom → core → filament) with sinusoidal standing-wave oscillation

---

## ✦ Performance

- Targets **~60 FPS** on modern hardware
- Object-pooled particle system — **zero runtime allocations**
- LERP-smoothed landmarks — eliminates tracking jitter
- Single HTML file — **no framework overhead**

---

## ✦ License

MIT — free to use, modify, and build upon.

---

## ✦ Credits

Built with [MediaPipe](https://mediapipe.dev/) by Google and [p5.js](https://p5js.org/) by the Processing Foundation.

*Concept, design, and engineering — [Your Name]*
