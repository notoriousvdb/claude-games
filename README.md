# Claude Games

Browser-based games built with [Claude Code](https://claude.ai/code). All games run as single HTML files — no install, no server, just open in a browser.

## Games

### 🚀 NASA Space Defender (`spaceshooter.html`)
A Galaga-style space shooter. Play as a NASA spaceship defending Earth from alien invasions across escalating waves.

**Alien types:**
| Type | Color | HP | Speed | Firepower | Points |
|------|-------|----|-------|-----------|--------|
| Martian Scout | Green | 1 | Fast | Weak | 10 |
| Martian Warrior | Red | 3 | Medium | Medium | 25 |
| Alien Cruiser | Purple | 6 | Slow | Spread shot | 50 |
| Boss | Gold | 20 | Very slow | 3-way rapid | 200 |

**Controls:**
- `← →` or `A D` — Move ship
- `Space` — Shoot
- `P` — Pause

**Features:** Wave progression, diving aliens (Galaga-style), particle explosions, shield bar, hi-score saved locally.

---

### ⭕ Tic Tac Toe (`tictactoe.html`)
Classic 2-player tic tac toe. Tracks score across games.

**Controls:** Click a cell to place your mark. Press **New Game** to reset the board (scores persist).

---

## How to Play
Download or clone the repo, then open any `.html` file directly in your browser — no setup needed.

```bash
git clone https://github.com/notoriousvdb/claude-games.git
cd claude-games
open spaceshooter.html   # Mac
# or double-click the file in Finder
```

## Project Notes
- Built entirely in vanilla HTML/CSS/JS using the Canvas API
- No dependencies or build tools
- Each game is a self-contained single file
