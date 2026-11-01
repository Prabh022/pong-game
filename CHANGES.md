## 2026-10-24 — Pause with the P key

- `game.js`: pressing `P` (lower- or uppercase) toggles a pause state. While paused, the game loop skips the physics/AI update but keeps drawing, so the ball and paddles freeze and a "PAUSED — Press P to resume" overlay is drawn on the canvas. Pressing `P` again resumes from exactly where the game stopped.
- `README.md`: updated — the game no longer has "no keyboard controls"; the P pause key is now documented.
- Test (Node harness in /tmp with stubbed canvas/document, game loop driven one frame at a time): ball moves while unpaused, ball position is unchanged across a paused frame, the PAUSED overlay text is drawn while paused, and the ball moves again after resuming with capital `P`. All checks passed.

## 2026-11-01 — First-to-5 win condition

- `game.js`: a `WINNING_SCORE` of 5 and a `winner` flag. When either score reaches 5, the match ends: `update()` stops moving the ball and a win overlay ("You Win!" or "AI Wins!") is drawn on the canvas. Pressing `R` resets both scores and starts a new match. The pause key still works as before.
- `README.md`: updated — the game no longer has "no win condition"; the first-to-5 win and the R restart key are now documented.
- Test (Node harness in /tmp with stubbed canvas/document, game loop driven one frame at a time): at 4–4 with the ball past the AI paddle, the player reaches 5 and `winner` becomes "You"; the ball is frozen on later frames and the "You Win!" / "Press R to play again" overlay is drawn; `R` clears both scores and the winner and the ball moves again; the mirror case gives "AI Win!"; scoring below 5 leaves no winner; capital `P` still toggles pause. All 12 checks passed. `node --check` clean.

# Changes made when extracting pong-game into a standalone project

Prepared 2026-10-21 from the `pong-game` folder of the `web-projects-portfolio` repository.

## Code changes

**None.** `index.html`, `game.js`, and `style.css` are copied byte-for-byte from the original folder (verified with checksums against the source clone). The game ran as-is: `index.html` references `style.css` and `game.js`, both present in the same folder with matching names.

## Documentation changes

- `readme.md` was replaced with a corrected `README.md`. The original readme did not match the code:
  - It claimed two-player gameplay with keyboard controls (`W/S` and arrow keys). The code has no keyboard handling at all — the left paddle is controlled with the mouse, and the right paddle is a computer AI.
  - It claimed "first to reach the set score wins." The code has no win score or game-over state; scoring is open-ended.
  - Its file-structure listing included a `.gitignore` that does not exist in the folder.
  - The new README describes only what the code actually does: controls, scoring, tech, and how to run it.
- No `.gitignore` was added: the project is three static files with no build output, dependencies, or generated artifacts, so there is nothing sensible to ignore.
