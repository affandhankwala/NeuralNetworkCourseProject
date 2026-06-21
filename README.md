# Neural Network Course Project

A **feed-forward backpropagation (FFBP) neural network built entirely from scratch** in Python, developed
as a course project. The network is composed from first principles: individual perceptrons are assembled
into layers, and layers are assembled into a trainable network.

## Overview

Rather than relying on a deep-learning framework, every component is implemented by hand:

- **Perceptron** (`perceptron.py`) — the fundamental unit. Computes activity (weighted sum + bias) and an
  activation. Uses the sigmoid activation and its derivative by default; swap in a different
  activation/delta function to change behaviour.
- **Network Layer** (`networkLayer.py`) — the `NodeLayer` class holds a list of perceptrons and records
  the inputs feeding into them (top to bottom). Each perceptron defaults to 2 inputs plus 1 bias.
- **FFBP Network** (`FFBP.py`) — the full network, built from layers. By default it has one hidden layer
  and one output layer, and supports the forward pass and backpropagation-based weight updates.
- **Methods** (`method.py`) — training routines (e.g. single-cycle and repeated-cycle training) used to
  drive learning and measure error.

## Dataset

`nnfinaldataset.csv` provides a small classification dataset with two input features (`LAC`, `SOW`) and a
binary target (`TACA`). Records are split into train/test sets by index parity.

## Repository Structure

```
NeuralNetworkCourseProject/
├── README.md
├── ClassificationProgrammingAssignment-A.pdf   # Assignment specification
├── Final_Paper.pdf                             # Final write-up / results
└── NN_Project/
    ├── main.py            # Constructs perceptrons / layers / networks to experiment with
    ├── perceptron.py      # Perceptron unit (sigmoid activation + derivative)
    ├── networkLayer.py    # NodeLayer: a layer of perceptrons
    ├── FFBP.py            # Feed-forward backpropagation network
    ├── method.py          # Training cycle helpers
    ├── nnproject.py       # End-to-end experiment: load data, build, train, plot
    ├── nnfinaldataset.csv # Classification dataset (LAC, SOW → TACA)
    ├── nnfinalproj.ipynb  # Notebook version of the experiments
    └── readme.txt         # Notes on constructing and using the classes
```

## Running

```bash
cd NN_Project
python nnproject.py        # full data-loading + training + plotting experiment
# or
python main.py             # scratchpad for building networks directly
```

You can also open `nnfinalproj.ipynb` in Jupyter to step through the experiments interactively.

### Requirements

- Python 3
- `numpy`, `matplotlib`

## Results

The methodology and results are documented in [`Final_Paper.pdf`](Final_Paper.pdf); the original task
specification is in [`ClassificationProgrammingAssignment-A.pdf`](ClassificationProgrammingAssignment-A.pdf).
