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

Episodes: 250
Seeds: 20 (for reproducibility)
Learning rate (α): 0.1
Discount factor (γ): 0.99
Exploration rate (ε): starts at 0.1 and decays to 0.01

Both algorithms maintain Q-tables using NumPy arrays indexed by (state, action). Updates occur after every step using TD targets:

# SARSA uses the next action selected by the policy
Q-learning uses the maximum Q-value of the next state

# Key Features
Online learning (step-by-step updates)

ε-greedy action selection using NumPy

Multiple-seed evaluation with averaged learning curves

Visualization of rewards, policies, and value functions

# Results Summary

SARSA learns a safer path by accounting for exploration during updates, resulting in more stable performance. Q-learning converges faster to the optimal path but exhibits riskier behavior early in training. ε-decay helps both algorithms stabilize over time.

# Usage

Run the script in Python or Google Colab. Ensure required libraries (NumPy, Gymnasium, Matplotlib) are installed. Execute the training functions and visualize outputs to compare performance.
