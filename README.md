# AI Checkers Game

A Python-based checkers game built with **Pygame**, featuring an AI opponent that uses the **Minimax algorithm** to evaluate possible moves and choose a response.

This project explores how game logic, search algorithms, and a graphical interface can work together to create an interactive AI-driven game.

<p align="center">
  <strong>Python · Pygame · Artificial Intelligence · Adversarial Search</strong>
</p>

## Overview

The project brings together a playable checkers board and a computer opponent. The game loop handles user input and screen updates, while the AI searches possible board states to select a move.

The AI currently calls Minimax with a search depth of **3**. This makes the project a practical starting point for exploring how search depth affects decision-making and computational cost.

## Key Features

- **AI opponent:** Uses Minimax to evaluate possible moves in a two-player, turn-based game.
- **Interactive graphical interface:** Built with Pygame, with mouse input used to select board squares and pieces.
- **Modular codebase:** Separates the main game loop, checkers logic, constants, and AI algorithm into different modules.
- **Game-state evaluation:** Searches possible future board states to help the AI choose a move.
- **Real-time game loop:** Uses Pygame's event handling and clock to keep the interface responsive.

## Tech Stack

| Technology | Purpose |
| --- | --- |
| Python | Core programming language |
| Pygame | Game window, rendering, input, and event loop |
| Minimax | AI decision-making through adversarial search |

## Getting Started

### Prerequisites

- Python 3
- `pip`

### 1. Clone the repository

```bash
git clone https://github.com/DarshKParikh/AI-checkers-game.git
cd AI-checkers-game
```

### 2. (Recommended) Create a virtual environment

**macOS / Linux**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows**
```powershell
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install the dependency

```bash
python -m pip install pygame
```

### 4. Run the game

```bash
python main.py
```

## How the AI Works

The AI uses **Minimax**, a search algorithm commonly used in two-player, zero-sum games.

At a high level, Minimax works by considering how a move could be answered by an opponent:

1. Generate and examine possible moves from the current board state.
2. Simulate candidate moves and explore the resulting positions up to a fixed depth.
3. Compare the resulting positions using the game's board-evaluation logic.
4. Choose the move that gives the AI the best outcome, assuming the opponent also makes strong decisions.

### Why search depth matters

The current entry point calls Minimax at depth `3`. A greater depth can allow the AI to consider longer sequences of moves, but it can also increase the number of positions explored and make the AI slower.

This creates a useful engineering trade-off between **decision quality and runtime performance**.

> Note: Minimax is a search-based decision-making algorithm, not a trained machine-learning model. This project is an AI/game-search project rather than a model trained on a dataset.

## Project Structure

```text
AI-checkers-game/
├── assets/             # Game assets
├── checkers/           # Checkers game logic, board, and constants
├── minimax/            # AI search algorithm
├── main.py             # Application entry point and game loop
└── README.md
```

## Engineering Challenges and Learning

This project provided experience with several core software engineering and AI concepts:

- **Separating responsibilities:** Keeping the entry point, game logic, and AI search code in separate modules makes the project easier to understand and extend.
- **Representing game states:** The AI needs to inspect possible board states and compare outcomes before choosing a move.
- **Connecting the AI to the interface:** The selected board state must be passed back into the game so the computer's move appears on screen.
- **Balancing search and responsiveness:** Search depth affects how far ahead the AI can reason and how much computation is required.
- **Handling interactive input:** The main loop processes mouse events and updates the game display.

## Future Improvements

Potential next steps include:

- Add **alpha-beta pruning** to skip search branches that cannot affect the final Minimax decision.
- Make search depth configurable and compare response time at different depths.
- Improve the board-evaluation function to consider factors such as piece advantage, king pieces, mobility, and positional strength.
- Add automated tests for legal moves, captures, king promotion, and end-game conditions.
- Add a benchmark mode to compare AI decisions across fixed board positions.
- Improve onboarding with screenshots, clearer controls, and a short gameplay demonstration.

## Interview Talking Points

When discussing this project, be prepared to explain:

1. **Why Minimax?** It models the opponent's response rather than evaluating a move in isolation.
2. **How does depth affect performance?** Searching further ahead can improve decisions but expands the search space.
3. **How is the code organised?** The main loop coordinates the interface and game, while separate modules handle checkers logic and AI.
4. **What would you improve next?** Alpha-beta pruning, stronger evaluation heuristics, tests, and performance measurements are natural next steps.
5. **How would you validate the AI?** Test known board positions, verify legal moves, and compare decisions and runtime at different search depths.

## Acknowledgements

This project was developed as a learning project exploring Python game development and the Minimax algorithm. If you build on a tutorial or external reference, credit the original resource here and clearly describe the changes you made yourself.

---

**Author:** Darsh Parikh  
**Repository:** [DarshKParikh/AI-checkers-game](https://github.com/DarshKParikh/AI-checkers-game)
