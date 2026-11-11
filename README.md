# CogMod RL Bandit

Reinforcement learning models fitted to a two-armed bandit task, comparing learning and choice behaviour between healthy controls and participants with major depressive disorder.

This code supports Lab Report 2 for Cognitive Modelling, Leiden University.

## Contents

- `cogmod-rl-bandit.ipynb` - analysis notebook: model fitting, model comparison, model recovery, statistics, and figures
- `dataset_students.csv` - task data, 40 participants x 300 trials
- `fig1_learning_rates.png`, `fig2_beta.png`, `fig3_model_comparison.png` - figures from the report
- `results_M1.csv`, `results_M2.csv`, `results_M3.csv`, `results_M4.csv` - fitted parameters per participant (optional, regenerated if deleted)

## Requirements

- Python 3
- pandas, numpy, scipy, matplotlib

## How to run

1. Put `dataset_students.csv` in the same folder as the notebook.
2. Open `cogmod-rl-bandit.ipynb` and run all cells from top to bottom.
3. The notebook fits four models (M1-M4) to each participant by maximum likelihood, using differential evolution with three seeds, then compares them with BIC, runs a model recovery simulation, and computes the group statistics.

If the `results_M*.csv` files are present, the notebook loads them instead of refitting. Delete them to refit from scratch, which takes considerably longer.

## Models

- **M1**: symmetric learning rate, fixed starting value
- **M2**: separate learning rates for positive and negative prediction errors
- **M3**: symmetric learning rate, free starting value
- **M4**: separate learning rates and free starting value
