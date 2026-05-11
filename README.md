# Q-Learning Grid World

This project implements a basic **Q-Learning** algorithm to navigate a grid-based environment. The agent learns to navigate from a random starting position to high-reward cells while avoiding obstacles and negative-reward cells.

## Components

- **`qtable.py`**: The core Python script containing:
  - `Action`: Represents movement (UP, RIGHT, DOWN, LEFT).
  - `State`: Manages agent position and environment interaction.
  - `Env`: Defines the grid layout based on a string input.
  - `QTable`: Implements the Q-Learning update rule:
    `Q(s, a) = (1 - α)Q(s, a) + α(r + γ * max Q(s', a'))`
- **`run.sh`**: A shell script wrapper to execute the learning process.

## Environment Legend

- ` `: Empty traversable cell (Reward: 0).
- `#`: Obstacle/Wall (Impassable).
- `+`: Goal cell (Reward: +10, Ends episode).
- `-`: Trap cell (Reward: -10, Ends episode).
- `A`: The Agent's current position (during visualization).

## How to Run

Ensure you have Python 3 installed. You can run the learner using the provided shell script:

```bash
# Make the script executable
chmod +x run.sh

# Run with default environment
./run.sh learn

# Run with a custom environment string
./run.sh learn "   +| # -|   "
