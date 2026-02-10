# Reinforcement Learning for Profiled Side-Channel Analysis

## User Guide and User Manual

---

## Overview

This project implements a reinforcement learning–based framework for **Profiled Side-Channel Analysis (SCA)** using **Convolutional Neural Networks (CNNs)**. The system uses a MetaQNN-style approach to automatically explore, train, and evaluate CNN architectures for side-channel attacks.

The repository enables users to:
- Run reinforcement learning experiments to generate CNN architectures
- Train and evaluate candidate models
- Visualize experiment results using scatter plots
- Plot Guessing Entropy (GE) curves
- Evaluate simple ensemble methods using top-performing models

This document serves as a complete **user-facing reference** for installing, running, and interacting with the project.

---

## Intended Audience

This project is intended for:
- Students studying machine learning, cryptography, or hardware security
- Researchers experimenting with CNN-based side-channel analysis
- Users with basic Python and command-line experience

No prior reinforcement learning background is required.

---

## Repository Structure

```
.
├── metaqnn/
│   ├── main.py              # Entry point for reinforcement learning experiments
│   ├── display_results.py   # Result summaries and scatter plots
│   ├── plot_top_ges.py      # Guessing Entropy plots and ensembles
│   └── ...
├── models/
│   ├── experiment_1/
│   ├── experiment_2/
│   └── ...
├── requirements.txt
├── requirements.minimal.txt
└── README.md
```

### Key Directories

- **metaqnn/**  
  Contains the reinforcement learning logic, CNN training pipeline, and visualization utilities.

- **models/**  
  Each subdirectory defines a complete experiment, including model search space, training parameters, and dataset configuration.

---

## Installation

### 1. Clone the Repository

```
git clone <repository-url>
cd <repository-name>
```

---

### 2. Create a Virtual Environment (Recommended)

```
python3 -m venv venv
source venv/bin/activate
```

---

### 3. Install Dependencies

```
pip install -r requirements.txt
```

This installs all dependencies with the exact versions used in the original experiments.

## TensorFlow Compatibility

This project is tested on **TensorFlow 2.1**

---

## Running Experiments

### Step 1: Select an Experiment

Each experiment is defined by a folder inside the `models/` directory. Choose one of the available experiment configurations.

Example:

```
models/example_model/
```

---

### Step 2: Run the Reinforcement Learning Experiment

```
python -m metaqnn.main <model_name>
```

Example:

```
python -m metaqnn.main example_model
```

This command:
- Launches the reinforcement learning agent
- Generates CNN architectures
- Trains and evaluates candidate models
- Saves experiment results automatically

---

## Viewing and Analyzing Results