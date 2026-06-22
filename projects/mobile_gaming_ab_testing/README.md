# Mobile Game A/B Testing: Cookie Cats

## Project Overview

This project analyzes an A/B testing dataset from the mobile game **Cookie Cats**. The experiment compares two versions of the game where the first progression gate appears at different levels:

- `gate_30`: the first gate appears at level 30
- `gate_40`: the first gate appears at level 40

The goal of this project is to understand whether changing the gate placement affects player retention and engagement.

## Dataset Overview

The dataset contains user-level records from the experiment. Each row represents one player and includes information about the player’s assigned test group, total game rounds played, and whether the player returned after 1 day and 7 days.

Key fields include:

| Column | Description |
|---|---|
| `userid` | Unique player identifier |
| `version` | A/B test group: `gate_30` or `gate_40` |
| `sum_gamerounds` | Total number of game rounds played |
| `retention_1` | Whether the player returned 1 day after install |
| `retention_7` | Whether the player returned 7 days after install |

## Project Goal

The main objective is to evaluate whether moving the first gate from level 30 to level 40 improves player retention and overall engagement.

## Dataset Source

Dataset: [Mobile Games A/B Testing - Cookie Cats on Kaggle](https://www.kaggle.com/datasets/mursideyarkin/mobile-games-ab-testing-cookie-cats)
