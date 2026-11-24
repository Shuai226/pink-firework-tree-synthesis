# Pink Firework Christmas Tree · Zhang Aoyun

A single-file interactive pink firework Christmas tree, cloned from the reference video. It replays the full synthesis process: fireworks burst first, then light spots swirl down and gradually assemble into the tree. Particle spots, trails and fireworks are pink; the original multicolor bauble accents are kept unchanged.

## Synthesis timeline (matches the reference video, ~13s)

| Progress | Phase | What happens |
| --- | --- | --- |
| 0.00–0.12 | Waiting for fireworks | Dark sky and twinkling ambient dots as the first pink shells launch |
| 0.12–0.32 | Fireworks bursting | Pink shells burst in sequence; their light spots appear around the burst points |
| 0.32–0.55 | Light spots gathering | The burst remnants swirl downward and drift toward their tree positions |
| 0.55–0.80 | Tree forming | Cone particles fill bottom-up; spiral strands wrap on |
| 0.80–0.92 | Top star ignites | Radiant star with rotating light rays |
| 0.92–1.00 | Finale | Side fireworks, dedication caption fades in |

## Features

- **Auto-play on load**: the synthesis starts by itself; after the finished tree holds for 6 seconds, it resets and replays in a loop
- Progress-driven build-up: burst remnants reveal and gather into the tree; strands, baubles, star, and caption appear in their own phases
- Full-screen canvas runs behind a transparent code panel; **scrolling the code scrubs the animation**, and auto-play scrolls the code in sync
- Touch scrolling works in mobile browsers, including WeChat's in-app browser; open the root GitHub Pages link to watch and interact
- Click anywhere on the stage to launch an extra firework; the button pauses / resumes
- Pink palette for particles / trails / fireworks; baubles keep green / red / blue / amber
- Bottom dedication: **Zhang Aoyun** uses the same bold italic serif gradient style as **Merry Christmas**

## Run and share

The root `index.html` opens the standalone animation page. When GitHub Pages is enabled, share the site URL in WeChat; it opens as an interactive webpage rather than a downloaded document.

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
