# Pacman Reinforcement Learning Project

This project implements and compares various reinforcement learning algorithms in a Pacman environment. The goal is to train agents to effectively navigate the maze, collect dots, and avoid ghosts.

## Project Structure

```
pacman_rl_project/
├── data/
│   ├── gifs/        # Episode gameplay animations
│   ├── models/      # Saved model weights
│   ├── metrics/     # Training metrics
│   ├── plots/       # Performance visualizations
│   └── reports/     # Evaluation reports
├── src/
│   ├── agents/
│   │   ├── random_agent.py
│   │   ├── dqn_agent.py
│   │   ├── dueling_dqn_agent.py
│   │   └── a2c_agent.py
│   ├── environment/
│   │   └── pacman_env.py
│   └── evaluation/
│       ├── train.py
│       └── compare_agents.py
└── requirements.txt
```

## Installation

1. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/Scripts/activate  # Windows
source venv/bin/activate      # Unix/MacOS
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Training

The project includes four reinforcement learning algorithms:

1. Random Agent (Baseline)
   - Simple random action selection
   - Used to establish baseline performance

2. Deep Q-Network (DQN)
   - Value-based learning with experience replay
   - Target network for stable training
   - Epsilon-greedy exploration

3. Dueling DQN
   - Separate value and advantage streams
   - Improved value estimation
   - Better sample efficiency

4. Advantage Actor-Critic (A2C)
   - Policy gradient method with value baseline
   - Separate actor and critic networks
   - Entropy regularization for exploration

To train all agents sequentially:
```bash
python src/evaluation/train.py
```

Training configuration:
- 30 episodes per agent
- GIFs saved for episodes 0, 14, and 29
- Models saved after training
- Metrics tracked and saved

## Evaluation

To evaluate and compare trained agents:
```bash
python src/evaluation/compare_agents.py
```

The evaluation script:
1. Loads trained models
2. Runs evaluation episodes
3. Generates performance visualizations
4. Creates comprehensive comparison report

## Environment

The Pacman environment features:
- 20x20 grid world
- Randomly generated mazes
- Dots to collect (+10 reward)
- Ghosts to avoid (-100 reward)
- Movement penalty (-1 reward)
- Episode ends on ghost collision or all dots collected

## Results

Training metrics and evaluation results are saved in:
- `data/metrics/`: JSON files with training metrics
- `data/plots/`: Performance visualizations
- `data/reports/`: Comprehensive evaluation reports
- `data/gifs/`: Episode gameplay animations

## Implementation Details

### DQN Features
- Convolutional neural network for state processing
- Experience replay buffer (10000 transitions)
- Target network updated every 10 episodes
- Epsilon-greedy exploration with decay
- Gradient clipping for stability

### Dueling DQN Features
- Separate value and advantage streams
- Shared convolutional layers
- Improved state value estimation
- Same training procedure as DQN

### A2C Features
- Separate actor and critic networks
- Policy gradient with value baseline
- Entropy regularization for exploration
- RMSprop optimizer
- Gradient clipping

## Future Improvements

Potential areas for enhancement:
1. Prioritized experience replay
2. Multi-step returns
3. Noisy networks for exploration
4. Distributed training
5. Parameter tuning
6. Advanced architectures (Transformer, etc.)

## Requirements

- Python 3.8+
- PyTorch 1.9+
- Gymnasium 0.28+
- NumPy 1.21+
- Matplotlib 3.4+
- Pygame 2.1+
