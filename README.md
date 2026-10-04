# The Wild Between

A cozy open-world 3D nature game — a Studio Ghibli-inspired vertical slice built with **Three.js**. Wander a sun-dappled forest, follow the winding stone path, gather runes, and open the ancient gate.

![Three.js](https://img.shields.io/badge/three.js-r160-blue) ![License: MIT](https://img.shields.io/badge/license-MIT-green)

## Play

- **Live / local:** serve this folder over HTTP and open `index.html` — e.g. `npx serve .` or `python3 -m http.server`, then visit `http://localhost:8000`.
  - (Opening `index.html` directly via `file://` won't load the 3D models — browsers block that. Any static server works, including GitHub Pages.)
- **Desktop:** WASD / arrows to move, mouse drag to orbit, Shift to sprint, 1/2/3 for camera modes, N for day/night.
- **Mobile:** left joystick to move, drag to look, SPRINT button, camera + day/night toggles top-right.

## What's inside

- `index.html` — the whole game: terrain, third-person controller, quest/HUD, wildlife, day/night, particles.
- `assets/three.min.js`, `assets/GLTFLoader.js` — Three.js r160 (vendored, works offline).
- `assets/quaternius-nature/` — 30 curated models + 15 textures from the **Quaternius Stylized Nature MegaKit** (CC0, see `LICENSE.txt` in that folder): twisted hero trees, commons, pines, bushes, ferns, flowers, grasses, mushrooms, rocks, petals, and path stones.

## Rendering

- One `InstancedMesh` per model (30 draw calls for all nature), gradient toon shading with warm rim light, thresholded bloom, god-ray light shafts, drifting petals/motes, stylized water shader.
- **Adaptive quality:** capable GPUs render up to 2× device pixel ratio with full-res bloom; weak devices (software GL, ≤4 GB RAM, small screens) drop to 1×, half-res bloom, and closer LOD — same scene, held frame budget.

## License

- Game code: **MIT** — see `LICENSE`.
- Art assets in `assets/quaternius-nature/`: **CC0** (public domain) by [Quaternius](https://quaternius.itch.io/) — see `LICENSE.txt` in that folder.
