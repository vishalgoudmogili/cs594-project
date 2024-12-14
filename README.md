# Certifiable Robustness for k-NN Classifiers

## Overview

This project implements a framework to certify the robustness of k-Nearest Neighbors (k-NN) classifiers under inconsistent and uncertain datasets. It leverages **repair generation** to handle incomplete or conflicting data, ensuring the model's predictions are stable across all possible worlds (repairs).

The code evaluates robustness by testing predictions on synthetic and real-world datasets, employing techniques to manage functional dependencies and uncertainties.

## Features

- **Robustness Certification**: Certifies whether a predicted label is consistent across all dataset repairs.
- **Repair Generation**: Identifies and generates possible consistent worlds for inconsistent datasets.
- **Support for Uncertainty Models**:
  - `?-sets`: Handles missing data by considering all possible completions.
  - `or-sets`: Resolves uncertain categorical values.
  - `Codd-tables`: Manages missing attribute values with finite domain replacements.

## Experiments

### **Datasets**
1. **Synthetic Dataset**:
   - A small, controlled dataset with numeric features and clear labels.
   - Tests the basic functionality and correctness of the implemented algorithms.

2. **Iris Dataset**:
   - A standard machine learning dataset with three classes of flowers.
   - Contains consistent numeric features, with added inconsistencies (e.g., missing values) to simulate real-world challenges.

3. **Adult Dataset** (UCI):
   - A large, real-world dataset with both categorical and continuous features.
   - Challenges include preprocessing (e.g., one-hot encoding) and handling missing values.
   - Subset of 1,000 records used for scalability testing.

### **Experimental Setup**
- **k-Value**: Set to `k=3` for all experiments.
- **Robustness Metric**: Fraction of dataset repairs predicting the same label as the original data.
- **Scalability Test**: Subsets of the Adult dataset analyzed for runtime performance.

### **Findings**
- The synthetic dataset verified the correctness of robustness certification.
- The Iris dataset demonstrated stable robustness metrics despite added inconsistencies.
- The Adult dataset highlighted scalability challenges due to the computational cost of repair generation.

## Getting Started

### Dependencies
- Python 3.x
- Libraries:
  - `numpy`
  - `scipy`
  - `pandas`
  - `sklearn`

### Running the Code
1. Clone this repository and navigate to the project directory.
2. Install the dependencies using `pip install -r requirements.txt`.
3. Run the script:
   ```bash
   python certifiable_robustness.py
   ```

### Results
The script will print:
- Predicted labels for test points.
- Whether the predictions are robust.
- The number of dataset repairs supporting the predictions.

## Code Structure
- **`CertifiableRobustness` Class**:
  - Implements the k-NN classification, robustness certification, and repair generation algorithms.
- **Synthetic and Real-World Experiments**:
  - Synthetic dataset testing.
  - Real-world experiments with Iris and Adult datasets.

## Citation
If using this framework or the methodology, please cite the original paper:
**Fan, A. Z., & Koutris, P. (2022). Certifiable Robustness for Nearest Neighbor Classifiers.**

---

For detailed information on experiments, please refer to the code comments and experiment outputs.
