# AGENTS.md

## Project shape

Pure HTML5 Canvas game. Four files at the repo root: `index.html`, `game.js`, `favicon.svg`, `README.md`. No `package.json`, no build step, no bundler, no tests, no linter, no CI.

## Run

Just open `index.html` in a browser, or serve the directory:

```
npx serve .
```

`index.html` loads `game.js` directly via a `<script>` tag — there is nothing to install or transpile.

## Where things live

- `game.js` — all game logic in one file: input handling, `Ship`, `Asteroid`, `Bullet`, `Particle` classes, game state (`state` is `'playing' | 'dead' | 'gameover'`), update/draw loop using `requestAnimationFrame`. Canvas constants are `W=800`, `H=600`.
- `index.html` — only sets up the `<canvas width="800" height="600">` and includes `game.js`. No build wiring.
- `favicon.svg` — browser tab icon.

## Conventions

- Vanilla JS, ES6 classes, `'use strict'`. No modules, no imports.
- Spanish in code comments and HUD strings (`NIVEL`, `PUNTAJE`, `GAME OVER`). Keep new strings consistent.
- Scoring is indexed by asteroid `size` (1 = small, 3 = large) in the `POINTS` array; small=100, medium=50, large=20. README table matches this.
- Single-frame key presses go through `pressed(code)`, which consumes a `justPressed` flag set on `keydown`. Don't read `keys[...]` directly for fire/restart — that won't give single-shot behavior.
- Held inputs (thrust, rotate) read `keys[...]` directly. The 5 s speed boost is a **power-up**, not a key: `PowerUp` instances spawn with 25 % chance inside the bullet-vs-asteroid branch and float for 10 s. Ship collision sets `ship.boostTimer = 5`; the timer ticks down in `Ship.update` and is zeroed by `Ship.reset()`. While active, thrust is 2× but the player must still hold `↑` — the boost is a multiplier, not auto-thrust.