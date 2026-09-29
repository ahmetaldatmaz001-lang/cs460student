# 🌌 XTK Cube Odyssey — 3D WebGL Cube Art Visualization

A high-performance interactive 3D WebGL generative sculpture built with **XTK (The X Toolkit)** and **dat.GUI**.

---

## 🚀 Quick Start

Open [`index.html`](file:///Users/ahmetaldatmaz/Desktop/cs460student/02/index.html) directly in any modern WebGL-compatible browser:

```bash
# macOS terminal:
open index.html

# Or serve via python HTTP server:
python3 -m http.server 8000
# Then open http://localhost:8000 in your browser
```

---

## ✨ Features & Visual Formations

### 🔮 5 Generative Formations
1. **🌐 Quantum Matrix**: A $6 \times 6 \times 6$ crystalline 3D lattice (216 cubes) undulating with radial and cross-harmonic sine wave ripples.
2. **🌀 Galaxy Vortex**: A 3-arm logarithmic spiral galaxy where cubes orbit at Keplerian angular velocities with undulating vertical wave crests.
3. **🦅 Hyper Swarm (Flying Cubes)**: True 3D boid-style flocking dynamics where all cubes break free, soaring with turbulent 3D flow fields, velocity vectors, and cosmic boundary elastic bouncing.
4. **🧬 DNA Double Helix**: Intertwined helical ribbons revolving in 3D space with horizontal connector rungs and traveling pulses.
5. **💠 Tesseract (Kinetic Hypercube)**: A 4D hypercube projection with concentric breathing shells (inner core + outer shell) expanding and collapsing.

### 🚀 36 Dynamic Orbital Scouts
- In addition to the 216 formation cubes, **36 fast-moving scout cubes** continuously swoop, dive, and orbit across the scene like shooting stars in all modes.
- You can fire new orbital cubes into the swarm at any time!

### 💥 Physics & Explosions
- **Nova Burst (`E` key or button)**: Blasts all 252 cubes violently outward into deep space with high rotational momentum. A restorative spring force dynamically draws them back into crystalline alignment.
- **Wave Shockwave**: Clicking anywhere in empty 3D space sends an expanding spherical ripple that knocks cubes back and restores them.

### 🎨 Vibrant Color Palettes & XTK Magic Mode
- **Cyberpunk Neon**: Electric cyan, hot magenta, electric violet, acid green, and solar yellow.
- **Cosmic Nebula**: Deep ultraviolet, astral blue, starlight pink, ethereal cyan, and supernova gold.
- **Solar Flare**: Molten gold, sunburst yellow, blazing orange, crimson red, and obsidian ruby.
- **Aurora Borealis**: Shimmering polar emerald, glacial blue, mystic violet, and deep indigo.
- **Prismatic Rainbow**: Continuous real-time $360^\circ$ spectral HSL color wheel cycling.
- **✨ XTK Magic Mode (`M` key or button)**: Enables XTK's native WebGL vertex normal shader (`cube.magicmode = true`), coloring each cube face with iridescent RGB normals in real time!

### 🎵 Procedural Sci-Fi Synthesizer (Web Audio API)
- Zero-latency synthesized sound effects for mode switches, nova explosions, cube clicks, and rocket launches. Can be toggled on/off with one click.

---

## 🎮 Controls & Shortcuts

| Key / Action | Function |
| :--- | :--- |
| **`Space`** | Play / Pause animation |
| **`1` – `5`** | Switch Formations (Matrix, Galaxy, Swarm, DNA, Tesseract) |
| **`E`** | Trigger **Nova Burst** Explosion |
| **`M`** | Toggle **XTK Magic Mode** (iridescent normal shader) |
| **`C`** | Cycle Color Palette |
| **`F`** | Instantly launch into **Hyper Swarm** |
| **`R`** | Reset 3D camera view |
| **`H`** | Toggle **Cinema Mode** (hide/show HUD overlay) |
| **Left Click Drag** | Orbit / rotate 3D camera |
| **Middle / Right Drag** | Pan 3D camera |
| **Mouse Wheel / Pinch** | Zoom in / Zoom out |
| **Click on Cube** | 3D Raycasting pick: triggers local shockwave, spin & flash |
| **Double Click** | Reset camera view to center |

---

## 🛠️ Architecture & Under the Hood

- **Framework**: [XTK (The X Toolkit)](https://github.com/xtk/X) WebGL framework.
- **Canvas Rendering**: `X.renderer3D` with custom background color `[0.03, 0.04, 0.08]` and 60 FPS `onRender` callback loop.
- **Geometry**: `X.cube` primitives initialized with centered local origins `[0, 0, 0]`.
- **Mathematical Matrix Math**: Column-major $4 \times 4$ transformation matrices (`cube.transform.matrix`) composed in real-time and uploaded to WebGL shaders on each frame.
- **3D Picking**: Real-time hardware GPU color-buffer picking (`r.pick(x, y)` and `r.get(id)`).
- **GUI Control Panel**: Integrated `dat.GUI` (`xtk_xdat.gui.js`) with responsive controls for amplitude, frequency, speeds, scale, turbulence, and palettes.
