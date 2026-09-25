# Ultra Instinct — 身勝手の極意

An immersive, scroll-driven Dragon Ball Super experience that recreates Goku's Ultra Instinct transformation. Scroll to awaken, move your mouse to make him follow you.

## Features

- **Scroll-scrubbed transformation** — 70 frames of Goku's transformation from base form to Ultra Instinct, perfectly synced to scroll position
- **Mouse-reactive head tracking** — Post-transformation, Goku's head follows your cursor (frames 70–98), mirrored for both directions
- **Procedural lightning bolts** — Recursive branching lightning strikes with glow + core passes, synced to transformation state
- **Full-screen flash effects** — Radial flashes on thunder strikes, intensified in Ultra Instinct form
- **Dynamic HUD** — Live form name (基本形態 → 気の高まり → 極意「兆」 → 身勝手の極意) and power meter
- **Bilingual UI** — Japanese and English text throughout (Noto Serif JP + Zen Dots + Share Tech Mono)
- **Loader with progress** — Preloads all 140 WebP frames with animated kanji and progress bar
- **Responsive** — Adapts layout for mobile, respects `prefers-reduced-motion`

## Tech Stack

- Vanilla HTML/CSS/JS (no frameworks)
- Canvas API for frame rendering & lightning generation
- CSS custom properties for theming
- IntersectionObserver-free scroll scrubbing
- GPU-accelerated transforms (`will-change`, `transform3d`)

## Project Structure

```
.
├── index.html      # Main HTML structure
├── style.css       # All styling, animations, responsive rules
├── app.js          # Core logic: preload, render loop, scroll/mouse handling, lightning
└── frames/         # 140 WebP frames (f001.webp – f140.webp)
```

## Getting Started

Just open `index.html` in a browser — no build step, no server required (though a local server is recommended for `fetch`/`preload` reliability).

```bash
# Example with Python
python -m http.server 8080
# Then open http://localhost:8080
```

## Controls

| Action | Effect |
|--------|--------|
| Scroll | Scrub transformation (0–100%) |
| Mouse move | Head tracking (post-transformation) |
| Touch drag | Head tracking on mobile |

## Frame Ranges

| Frames | Purpose |
|--------|---------|
| 1–70 | Transformation sequence (scroll-driven) |
| 70–98 | Head turn left/right (mouse-driven, mirrored) |
| 99–140 | Idle/breathing loops (held at frame 140) |

## Credits

- Dragon Ball Super / Toei Animation — source material
- Fonts: [Noto Serif JP](https://fonts.google.com/noto/specimen/Noto+Serif+JP), [Zen Dots](https://fonts.google.com/specimen/Zen+Dots), [Share Tech Mono](https://fonts.google.com/specimen/Share+Tech+Mono) via Google Fonts
- Built as a passion project / tech demo

## License

MIT — feel free to fork, modify, and share. Not affiliated with Toei Animation, or Bandai Namco.
