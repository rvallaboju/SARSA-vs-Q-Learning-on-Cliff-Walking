# README: SARSA vs Q-Learning on Cliff Walking

# Overview

This project implements and compares two Temporal-Difference (TD) control algorithms—SARSA (on-policy) and Q-learning (off-policy)—using Gymnasium’s CliffWalking-v0 environment. The goal is to evaluate how each algorithm learns optimal policies under the same conditions, focusing on learning behavior, risk sensitivity, and convergence performance.

# Objectives
Implement SARSA and Q-learning with online updates
Apply ε-greedy exploration with decay
Compare learning performance using multiple random seeds
Analyze differences between on-policy and off-policy learning
Environment Setup

The Cliff Walking environment is a grid-based task where the agent must navigate from a start state to a goal while avoiding a “cliff” that gives large negative rewards. The environment is episodic and supports step-by-step interaction using Gymnasium’s API.

# Training Configuration

The experiment uses 250 episodes and 20 seeds to ensure reproducibility. The learning rate (α) is set to 0.1 and the discount factor (γ) to 0.99. Exploration begins at ε = 0.1 and decays to 0.01. Both algorithms use NumPy-based Q-tables, updating values after each step using TD targets.


Both algorithms maintain Q-tables using NumPy arrays indexed by (state, action). Updates occur after every step using TD targets:

# SARSA uses the next action selected by the policy
Q-learning uses the maximum Q-value of the next state

# Key Features
Key features include online learning with step-by-step updates, ε-greedy action selection implemented using NumPy, and evaluation across multiple seeds to ensure reliable averaged learning curves. The project also provides clear visualizations of rewards, learned policies, and value functions, enabling effective comparison between SARSA and Q-learning performance.


# Results Summary

SARSA learns a safer path by accounting for exploration during updates, resulting in more stable performance. Q-learning converges faster to the optimal path but exhibits riskier behavior early in training. ε-decay helps both algorithms stabilize over time.

# Usage

Run the script in Python or Google Colab. Ensure required libraries (NumPy, Gymnasium, Matplotlib) are installed. Execute the training functions and visualize outputs to compare performance.
