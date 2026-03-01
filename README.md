# Flappy Bird - Jack Language
### Nand2Tetris Project 9

---

## About
A Flappy Bird clone implemented in the Jack programming language for the Nand2Tetris course. Guide your bird through the gaps in the pipes for as long as possible without crashing!

---

## How to Play

### Setup
1. Compile the project using the **JackCompiler**:
   ```
   JackCompiler.bat path\to\flappy_bird_jack
   ```
2. Open the **VMEmulator** from the Nand2Tetris tools folder
3. Load the `flappy_bird_jack` folder
4. Set the animation to **No animation** and speed to **Fast**
5. Click **Run**

### Controls
| Key | Action |
|-----|--------|
| `Space` | Flap — makes the bird jump upward |

### Rules
- Press **Space** to flap and keep the bird airborne
- Navigate through the gaps in the pipes
- The game ends if the bird hits a pipe, the top, or the bottom of the screen
- Each pipe you pass increases your score by 1
- After game over, press **Space** to restart

---

## Project Structure
```
flappy_bird_jack/
├── Main.jack       — Entry point
├── Game.jack       — Main game loop, score, and game state
├── Bird.jack       — Bird physics, sprite rendering
├── Pipe.jack       — Pipe movement, drawing, collision detection
└── Random.jack     — Pseudo-random number generation for pipe gaps
```

---

## Design Notes
- **Bird** is rendered using a custom 16x16 bitmap sprite drawn via `Memory.poke`
- **Pipes** are drawn as filled rectangles with a randomized gap
- **Gravity** is simulated using an integer velocity field that increases each frame
- **Collision detection** uses bounding box checks between the bird and pipe rectangles
- **Randomization** uses a Linear Congruential Generator (LCG) with a fixed seed, producing consistent pipe patterns each run
