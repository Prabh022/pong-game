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
