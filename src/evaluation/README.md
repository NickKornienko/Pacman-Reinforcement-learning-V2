# Pacman RL Evaluation System

This directory contains scripts for training, evaluating, and analyzing the performance of reinforcement learning agents in the Pacman environment.

## Core Scripts

### run_comparison.py
Main script for training and comparing all agents:
- Trains all agents (Random, DQN, Dueling DQN, A2C, Multi-agent)
- Generates training GIFs
- Saves models and metrics

### train.py
Handles training for single agents:
- DQN
- Dueling DQN
- A2C
- Random Agent

### train_multi_agent.py
Specialized training for the multi-agent system:
- Handles agent coordination
- Tracks team performance
- Saves multi-agent metrics

## Analysis Scripts

### move_analysis.py
Analyzes agent movement patterns:
- Tracks move usage
- Creates animated visualizations
- Analyzes success rates of different moves

### tabulate_results.py
Generates detailed statistical analysis:
- Performance tables
- Episode-by-episode analysis
- CSV exports for further analysis
- Markdown reports

### visualize_results.py
Creates comprehensive visualizations:
- Learning curves
- Performance comparisons
- Multi-agent analysis
- Summary reports

## Usage

1. Run full training and comparison:
```bash
python run_comparison.py
```

2. Analyze results:
```bash
# Generate move analysis visualizations
python move_analysis.py

# Create statistical tables and reports
python tabulate_results.py

# Generate performance visualizations
python visualize_results.py
```

## Output Structure

Results are organized in the following directories:

```
data/
├── gifs/           # Training visualizations
│   ├── single/     # Single-agent training
│   └── multi/      # Multi-agent training
├── metrics/        # Performance metrics
├── models/         # Saved model weights
├── plots/          # Comparison plots
└── reports/        # Evaluation reports
```

## Key Features

1. Comprehensive Training
- 30 episodes per agent
- Consistent environment settings
- GIF generation at key points (start, middle, end)

2. Detailed Analysis
- Statistical comparisons
- Move pattern analysis
- Performance visualization
- Multi-agent evaluation

3. Standardized Metrics
- Episode scores
- Rewards
- Step counts
- Move distributions
- Team performance (for multi-agent)

## Notes

- All agents are trained under identical conditions
- GIFs are saved at episodes 0, 14, and 29
- Multi-agent metrics include both individual and team performance
- Reports include both markdown and CSV formats for flexibility
