# Pink Firework Christmas Tree · Zhang Aoyun

A single-file interactive pink firework Christmas tree, cloned from the reference video. It replays the full synthesis process: fireworks burst first, then light spots swirl down and gradually assemble into the tree. Particle spots, trails and fireworks are pink; the original multicolor bauble accents are kept unchanged.

## Synthesis timeline (matches the reference video, ~13s)

| Progress | Phase | What happens |
| --- | --- | --- |
| 0.00–0.12 | Waiting for fireworks | Dark night sky, ambient twinkling dots |
| 0.12–0.32 | Fireworks bursting | Pink shells rise and explode into scattered sparks |
| 0.32–0.55 | Light spots gathering | Spots swirl downward and drift toward tree positions |
| 0.55–0.80 | Tree forming | Cone particles fill bottom-up; spiral strands wrap on |
| 0.80–0.92 | Top star ignites | Radiant star with rotating light rays |
| 0.92–1.00 | Finale | Side fireworks, dedication caption fades in |

## Features

- Progress-driven build-up: every element appears only at its phase (strands, baubles, star, caption)
- Left code panel shows the source grouped by phase; **scrolling the code scrubs the animation**, and auto-play scrolls the code in sync
- Click anywhere on the stage to launch an extra firework
- Pink palette for particles / trails / fireworks; baubles keep green / red / blue / amber
- Bottom dedication: script font **Merry Christmas** above **Zhang Aoyun**

## Run

No build step, no dependencies, no CDN. Open `firework-christmas-tree.html` directly, or serve locally:

```bash
npx serve .
```

Preview a specific phase without playing through:

```
firework-christmas-tree.html?p=0.5
```

(`p` from `0` to `1`; e.g. `0.15` burst, `0.5` gathering, `1` finished tree)

## Customize

| What | Where |
| --- | --- |
| Dedication name | `.caption .name` in the HTML |
| Pink palette | `PINK` array in the script |
| Bauble accent colors | `BAUBLE_COLORS` array (kept from the original video) |
| Particle count | `for (let i = 0; i < 900; ...)` in `buildTree()` |
| Build-up duration | `DURATION` constant (seconds) |
| Phase thresholds | `smoothstep` / `clamp01` gates in each draw function |

## Tech

- Vanilla HTML / CSS / JavaScript, one self-contained file
- Canvas 2D, additive blending, motion trails via translucent fade
- No framework, no camera, no network permission required
