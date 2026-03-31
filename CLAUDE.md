# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Browser-based games built as self-contained single HTML files (vanilla HTML/CSS/JS, no dependencies, no build step). Each file embeds all styles and scripts inline.

## Running Games

Open any `.html` file directly in a browser — no server needed:
```bash
open spaceshooter.html
open tictactoe.html
```

## Repository

GitHub: https://github.com/notoriousvdb/claude-games
After any changes, commit and push:
```bash
git add <files>
git commit -m "description"
git push
```

## Architecture

Every game is a single `.html` file structured as:
1. **Styles** — inline `<style>` block, dark theme, canvas centered
2. **Canvas setup** — fixed pixel dimensions (e.g. 800×720)
3. **Config constants** — speeds, sizes, timing at the top of `<script>`
4. **Entity data** — plain objects or classes (no frameworks)
5. **Input** — `keydown`/`keyup` listeners writing to a `keys={}` map, polled each frame
6. **Game state machine** — a single `state` string (`'start'|'playing'|'paused'|'waveclear'|'gameover'`)
7. **Update + Draw functions** — separated; `requestAnimationFrame` loop calls both
8. **Persistence** — `localStorage` only (hi scores, etc.)

### spaceshooter.html specifics
- Alien types defined in a `T` config object keyed by type name (`scout`, `warrior`, `cruiser`, `boss`)
- `Alien` class handles its own movement (formation follow vs. bezier dive path), shooting, and drawing via `_draw<Type>()` methods
- Formation is a global `formX` offset; each alien's position = `formX + col*65`
- Dive paths are cubic bezier curves (parametric `diveT` 0→1) looping back to formation
- Wave layouts defined in `WAVES` array; cycles with `(waveNum-1) % WAVES.length`
- Boss moves independently (ignores `formX`), enters from top, fires 3-way spread

## New Games

Follow the same single-file pattern. Add an entry to `README.md` when adding a new game.
