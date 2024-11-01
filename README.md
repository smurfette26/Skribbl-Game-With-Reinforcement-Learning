# Drawing Game Project

This project is a multiplayer drawing and guessing game that utilizes Q-learning and Monte Carlo methods for word difficulty adjustment. Players take turns drawing a word while others guess it. The system adjusts the difficulty of words based on players' performance.

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Q-Learning and Monte Carlo](#q-learning-and-monte-carlo)
- [Model Evaluation](#model-evaluation)
- [Contributing](#contributing)
- [License](#license)

## Features
- Real-time multiplayer drawing and guessing game
- Difficulty adjustment using Q-learning and Monte Carlo methods
- Dynamic word suggestion and feedback system

## Installation

### Prerequisites
- Python 3.8+
- Django 3.2+
- Channels 3.0+
- Numpy
- Matplotlib
- Gym
- Pandas

### Steps
1. Clone the repository:
    ```bash
    git clone https://github.com/sachinmoze/RL-drawing-game.git
    cd RL-drawing-game
    ```

2. Set up a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Apply migrations:
    ```bash
    python manage.py migrate
    ```

5. Run the development server:
    ```bash
    python manage.py runserver
    ```

## Usage
1. Open a web browser and navigate to `http://localhost:8000/`.
2. Create a new game room or join an existing one.
3. Players take turns drawing and guessing the word.

## Project Structure
- `game/`: Contains the main application code.
  - `consumers.py`: WebSocket consumers for real-time game logic.
  - `models.py`: Database models.
  - `q_learning_agent.py`: Q-learning implementation.
  - `monte_carlo_agent.py`: Monte Carlo implementation.
  - `rl_model.py`: Reinforcement learning model integration.
- `static/`: Static files (JavaScript, CSS).
- `templates/`: HTML templates.

## How It Works
### Game Flow
1. **Joining a Room**: When a player joins a room, they are added to the game and notified about other players.
2. **Starting the Game**: The game starts when a player clicks the "Start Game" button. Players take turns to draw a word.
3. **Drawing and Guessing**: The drawer draws a word, and other players guess. The system provides suggestions and feedback based on the Q-learning and Monte Carlo models.
4. **Adjusting Difficulty**: Based on players' performance, the difficulty of words is adjusted dynamically.

### Q-Learning and Monte Carlo
- **Q-Learning**: Used for adjusting word difficulty based on past performance. The Q-learning agent updates its Q-table with each correct or incorrect guess.
- **Monte Carlo**: Also used for word difficulty adjustment, but based on entire episodes rather than step-by-step learning.

### Model Evaluation
The project includes a separate script (`evaluation.py`) for evaluating the performance of the Q-learning and Monte Carlo models. This script trains both models and compares their performance.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue to discuss improvements.

## License
This project is licensed under the MIT License.
