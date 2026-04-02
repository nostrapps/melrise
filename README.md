# Melrise

A tower stacking game built with Preact + HTM standalone, featuring C64-style chiptune music, combo streaks, and a global Nostr leaderboard.

## Play Now

[https://nostrapps.github.io/melrise/](https://nostrapps.github.io/melrise/)

Tap or click to drop blocks and stack them as precisely as you can. The game runs entirely in the browser with no install required.

## How to Play

1. **Tap / Click / Spacebar** to drop the swinging block onto the tower
2. Align it as closely as possible with the block below
3. Misaligned portions get sliced off, making the next drop harder
4. A complete miss costs you a life (you have 3)
5. Land **perfect** drops to trigger combos and regrow your block

## Scoring System

| Action | Points |
|---|---|
| Normal landing | 25 |
| Perfect landing | 50 + (streak - 1) x 10 bonus |
| 2x streak | "NICE!" |
| 3x streak | "AMAZING!" + block regrowth begins |
| 5x streak | "ON FIRE!" |
| 7x streak | "UNSTOPPABLE!" |
| 10x streak | "LEGENDARY!" |

- **Perfect threshold**: landing within 5px of the block below
- **Block regrowth**: at 3+ streak, your block grows back by 15px per streak level (up to the original 200px width)
- **High scores** are saved locally and can be published to the Nostr leaderboard

## Levels

The game progresses through themed levels, each with unique colors, music, and increasing difficulty:

| Level | Name | Goal | Speed | Start Width |
|---|---|---|---|---|
| 1 | Foundation | 10 blocks | 0.8x | 200px |
| 2 | Skyscraper | 15 blocks | 1.0x | 190px |
| 3 | Stratosphere | 20 blocks | 1.2x | 180px |
| 4 | Endless | Infinite | 1.0x | 200px |

Each level has its own C64-inspired chiptune track played via MOD/XM tracker files.

## Features

- **Tower stacking** with real-time block slicing and physics
- **C64-style chiptune music** via MOD/XM tracker playback (ScripTracker)
- **Combo system** with escalating streak bonuses, particle effects, and screen shake
- **Block regrowth** mechanic that rewards sustained precision
- **4 themed levels** with unique color palettes and background gradients
- **Nostr integration** for login (extension, private key, or guest) and global leaderboard
- **Share cards** — auto-generated score images for sharing
- **Haptic feedback** on supported devices
- **Music Lab** (`music.html`) for exploring procedural and tracker-based music
- **Mobile-friendly** — works on touch devices

## Tech Stack

- [Preact](https://preactjs.com/) + [HTM](https://github.com/developit/htm) (no build step)
- HTML5 Canvas for rendering
- Web Audio API for procedural sound effects
- [ScripTracker](https://github.com/nickreserved/scriptracker) for MOD/XM playback
- Nostr protocol for authentication and leaderboard
- GitHub Pages for hosting

## Project Structure

```
index.html             Main game (MOD/XM music)
index-procedural.html  Game variant with procedural music
index-mod.html         Game variant (MOD-only music)
levels.html            Level progression version
music.html             Music Lab — explore the soundtrack
nostr.js               Nostr authentication & leaderboard module
og-image.svg           Open Graph share image
mods/                  MOD/XM tracker music files
```

## Local Development

```bash
git clone https://github.com/nostrapps/melrise.git
cd melrise
# Serve with any static file server
npx serve .
# or
python3 -m http.server 8000
```

No build step required — everything runs directly in the browser.

## Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b my-feature`)
3. Commit your changes
4. Open a pull request

## License

AGPL-3.0 - Copyright (C) 2025 Melvin Carvalho. See [LICENSE](LICENSE) for details.
