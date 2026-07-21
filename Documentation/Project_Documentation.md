# Project Documentation

## Improved Hybrid DeepFake Detection using Deep Learning

---

## 1. Introduction

This document provides a comprehensive overview of the Improved Hybrid DeepFake Detection (DFD) framework developed for binary classification of authentic and AI-generated facial images. It serves as the primary technical reference for understanding the project's design, implementation, workflow, and reproducibility.

The project has been developed using TensorFlow and Keras and follows a modular design in which model development, evaluation, explainability, and documentation are organized into separate components. This organization simplifies maintenance, encourages reproducibility, and allows individual components to be executed independently.

Rather than presenting only the source code, this repository provides detailed documentation describing each stage of the experimental pipeline, from dataset preparation to model evaluation and visualization. Researchers interested in reproducing or extending this work are encouraged to consult the accompanying documentation available in the `docs/` directory.

---

## 2. Project Objectives

The primary objective of this project is to develop an effective and reproducible deep learning framework for detecting AI-generated facial images.

The proposed framework has been designed with the following objectives:

- Develop an improved hybrid architecture based on transfer learning.
- Detect manipulated facial images with high classification performance.
- Evaluate model performance using both in-domain and cross-domain testing.
- Improve model interpretability using Grad-CAM.
- Provide a reproducible implementation supported by comprehensive documentation.
- Facilitate future research through a modular repository structure.

---

## 3. Repository Organization

The repository is organized into several independent components, each serving a specific purpose within the overall workflow.

```text
notebooks/
```

Contains all executable notebooks used throughout the project, including model training, evaluation, cross-domain testing, and Grad-CAM visualization.

```text
models/
```

Stores the trained model checkpoints generated during the training process.

```text
images/
```

Contains all figures used throughout the project, including architecture diagrams, workflow illustrations, learning curves, confusion matrices, ROC curves, and Grad-CAM visualizations.

```text
results/
```

Stores numerical evaluation results, prediction outputs, and performance metrics.

```text
docs/
```

Provides detailed technical documentation explaining each stage of the implementation.

---

## 4. Overall Workflow

The proposed framework follows a structured deep learning pipeline consisting of several sequential stages.

```text
Dataset Preparation
        │
        ▼
Image Preprocessing
        │
        ▼
TensorFlow Data Pipeline
        │
        ▼
Transfer Learning
        │
        ▼
Hybrid Model Development
        │
        ▼
Model Training
        │
        ▼
Performance Evaluation
        │
        ▼
Cross-Domain Testing
        │
        ▼
Grad-CAM Visualization
        │
        ▼
Result Analysis
```

Each stage is implemented independently while remaining fully integrated into the overall experimental workflow.

A graphical representation of the workflow is available in:

```text
images/workflow.png
```

> **Placeholder:** The workflow figure will be updated as the repository evolves.

---

## 5. Development Environment

The implementation has been developed using Python and the TensorFlow deep learning framework.

The project relies on widely adopted open-source libraries for image processing, model development, visualization, and performance evaluation. Dependency management is handled through the `requirements.txt` file to ensure a consistent software environment across different systems.

The experiments were designed to execute efficiently on GPU-enabled platforms.

> **Placeholder:** Hardware specifications used for the reported experiments (GPU, CPU, RAM, CUDA version, TensorFlow version) will be included after final verification.

---

## 6. Project Components

The implementation is divided into four primary stages.

### Model Training

Responsible for constructing the proposed network architecture, preparing the datasets, training the model, and saving the best-performing checkpoint.

Notebook:

```text
01_Model_Training.ipynb
```

### In-Domain Evaluation

Evaluates the trained model using unseen samples originating from the same distribution as the training dataset.

Notebook:

```text
02_In_Domain_Evaluation.ipynb
```

### Cross-Domain Evaluation

Assesses the generalization capability of the proposed framework using an independent dataset that was not involved during model training.

Notebook:

```text
03_Cross_Domain_Evaluation.ipynb
```

### Explainability

Generates Grad-CAM activation maps to visualize the image regions influencing the model's predictions.

Notebook:

```text
04_GradCAM_Visualization.ipynb
```

Each notebook has been designed to operate independently while sharing a consistent preprocessing pipeline and trained model.
