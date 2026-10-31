# TicTac Orbit

A stunningly designed tic-tac-toe game in three.js — a glowing glass board floating in space, with a perfect-play minimax AI, an orbitable camera, synthesized sound, and a gold win beam.

**Play it now:** https://oferhalevi.github.io/tictac-orbit/

Or open `tictac-orbit.html` in any browser locally. No build step, no server, no dependencies beyond the three.js CDN scripts.

## Play

- **vs AI** — you play X against a minimax engine that searches every possible continuation before each move. It never loses; your best hope is a draw.
- **2 players** — share the board on one screen.
- **Drag** to orbit the camera, **scroll** to zoom, **click a tile** to place your mark.
- The **about** button (top-right) explains the technology — WebGL, raycasting, minimax, Web Audio — in plain language.

Scores persist in the browser between visits.

## How it works

| Piece | Technology |
|---|---|
| 3D scene | three.js r128, WebGL, ACES filmic tone mapping, UnrealBloomPass post-processing |
| Camera | damped orbit (current values chase targets), cinematic fly-in on load |
| Picking | raycasting from the cursor through the scene |
| AI | minimax with depth-preferenced scoring — perfect play, computed in well under a second |
| Sound | Web Audio API — every chime synthesized live, no audio files |
| Motion | spring-physics tweens, honors `prefers-reduced-motion` |
| State | vanilla JS, score persistence via `localStorage` |

The game reuses the same win-detection logic as the `qrt` CLI evaluator (the 8 hardcoded win lines), so it stays consistent with that project's TypeScript implementation.

## Educational purpose

This project exists to demonstrate how a small, classic game can become a showcase of browser 3D, procedural audio, and game AI — every layer is code you can read in a single file.

## Attribution

Code co-authored with Claude Code.
