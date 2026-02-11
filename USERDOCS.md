# Reinforcement Learning for Profiled Side-Channel Analysis

## User Guide and User Manual

---

## Overview

This project implements a reinforcement learning–based framework for **Radio Frequency Modulation Classification** using **Convolutional Neural Networks (CNNs)**. The system uses a MetaQNN style approach to automatically explore, train, and evaluate CNN architectures for side-channel attacks.

The repository enables users to:
- Run reinforcement learning experiments to generate CNN architectures
- Train and evaluate candidate models
- Visualize experiment results using Confusion Matrices for 

This document serves as a complete **user-facing reference** for installing, running, and interacting with the project.

---

### Key Directories

- **metaqnn/**  
  Contains the reinforcement learning logic, CNN training pipeline, and visualization utilities.

- **metaqnn/models/**  
  Each subdirectory defines a complete experiment, including model search space, training parameters, and dataset configuration.

---

## Installation

### 1. Clone the Repository

```
git clone https://github.com/ash-whut/CS-5001
cd CS-5001
```

---

### 2. Create a Virtual Environment and Install Dependencies (Recommended)

For the experiments in this repository, we will use Anaconda environments. Using the manual and installation for your specific OS,
install Anaconda Distribution and tools using the link provided [here](https://www.anaconda.com/download).

---

### 3. Install Dependencies

```
conda env create -f environment.yml
conda activate rfmod-metaqnn
```

This installs all dependencies with the exact versions used in the original experiments.

## TensorFlow Compatibility

This project is tested on **TensorFlow 2.1**

---

## Configuring Experiments 

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

Running the following command retrains candidate models created and outputs confusion matrices for the best-performing candidate
models

```
python topk-model-retraining-and-evaluation.py
```

---

## Frequently Asked Questions (FAQ)

### What does a "model" represent in this project?

A model refers to an **experiment definition**, not a single neural network. Each folder in `models/` defines the reinforcement learning configuration, training parameters, and evaluation settings.

---

### Is a GPU required?

A GPU is not strictly required but is **strongly recommended** for reasonable training times.

---

### Where are experiment results stored?

Results are automatically saved in experiment-specific output directories created during execution.

---

### Can I add my own experiment?

Yes. Copy an existing folder inside `models/`, modify the configuration, and run it using:

```
python -m metaqnn.main your_new_model
```

---