# Dynamic Routing Between Capsules

This repository contains the code and report for reproducing the results of the paper [Dynamic Routing Between Capsules](https://arxiv.org/abs/1710.09829) by Sara Sabour, Nicholas Frosst, and Geoffrey Hinton. The project explores Capsule Networks (CapsNet) and their ability to achieve competitive performance on image classification tasks using dynamic routing.

## Table of Contents

- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Datasets](#datasets)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Reproduction Analysis](#reproduction-analysis)
- [How to Run](#how-to-run)

## Introduction

The aim of this project is to reproduce the original findings of CapsNet and evaluate its performance on various datasets such as MNIST, Fashion MNIST, and CIFAR-10. This project provides a comprehensive analysis of CapsNet’s architecture and performance, highlighting its strengths and areas where improvements are needed.

## Project Structure

```
.
├── Capsnet_Routing_Reproduce.ipynb  # Jupyter Notebook with the implementation
├── Dynamic Routing Between Capsules_ Reproduce.pdf  # Reproduction report
├── Dynamic Routing Between Capsules.pdf  # Original research paper
├── README.md  # Documentation file
```

## Datasets

The following datasets were used to evaluate the CapsNet:

1. **MNIST**: Handwritten digits (28x28 grayscale images).
2. **Fashion MNIST**: Fashion items (28x28 grayscale images).
3. **CIFAR-10**: 10-class colored images (32x32 RGB images).

## Model Architecture

The CapsNet model consists of:

1. **Convolutional Layer**: Extracts low-level features from input images.
2. **Primary Capsule Layer**: Encodes low-level entities as multi-dimensional vectors.
3. **Digit Capsule Layer**: Encodes high-level entities (class representations) with dynamic routing.
4. **Reconstruction Network**: A decoder network to regularize and improve representation quality.

Key Features:
- **Dynamic Routing Algorithm**: Ensures capsules in lower layers assign their output to the most relevant higher-level capsules.
- **Squashing Function**: Normalizes capsule vectors to stabilize training.

## Results

### Accuracy Comparison

| Dataset       | Original Paper (%) | Reproduced Results (%) |
|---------------|---------------------|-------------------------|
| MNIST         | 99.75              | 99.07                  |
| Fashion MNIST | N/A                | 90.7                   |
| CIFAR-10      | 89.4               | 55.86                  |

### Observations:
- The model performed well on MNIST but struggled with more complex datasets like CIFAR-10, requiring architectural enhancements.

## Reproduction Analysis

- **Alignment with Original Results**: The reproduced model achieved results close to the original paper on MNIST.
- **Challenges**: Significant performance drop on CIFAR-10 due to architectural limitations and lack of advanced data augmentation.
- **Insights**: The effectiveness of the dynamic routing mechanism was validated, but improvements are necessary for better generalization.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Dynamic-Routing-Between-Capsules.git
   ```
2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook Capsnet_Routing_Reproduce.ipynb
   ```
4. Run the cells to train and evaluate the model on the datasets.

