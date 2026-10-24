# Pong Game

A classic Pong game that runs in the browser, built with plain HTML, CSS, and JavaScript — no libraries, no build step. You play the left paddle against a computer-controlled right paddle on an HTML5 canvas.

## How to Play

- **Your paddle (left):** move the mouse up and down over the game canvas.
- **Pause:** press **P** to pause or resume the game. While paused, the ball and AI paddle stop moving and a "PAUSED — Press P to resume" message is shown on the canvas.
- **Opponent (right):** a simple computer AI that tracks the ball, with a small dead zone so it can be beaten.
- **Scoring:** you score a point when the ball passes the AI paddle; the AI scores when the ball passes yours. The score is shown at the top of the canvas. After each point the ball resets to the center and serves in a random direction.
- **There is no win condition or game-over screen** — play continues indefinitely, so set your own target score.
- The ball speeds up slightly with every paddle hit, and where the ball strikes the paddle changes its angle.

## How to Run

No installation or server is needed. Just open the file in any modern browser:

```
open index.html        # macOS
xdg-open index.html    # Linux
```

or double-click `index.html`. If you prefer serving it locally:

```
python3 -m http.server
# then visit http://localhost:8000
```

## Tech

- **HTML5** — page structure and the `<canvas>` play field (800×500)
- **CSS3** — page layout and canvas styling
- **Vanilla JavaScript** — game loop (`requestAnimationFrame`), canvas drawing, collision detection, score tracking, and the AI opponent

## Project Structure

```
pong-game/
├── index.html   Page markup and the game canvas
├── style.css    Page and canvas styling
├── game.js      All game logic: rendering, physics, AI, scoring
└── README.md    This file
```
