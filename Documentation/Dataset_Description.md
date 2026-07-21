# Dataset Description

## Overview

The proposed Improved Hybrid DeepFake Detection (DFD) framework was developed using a combined dataset consisting of two publicly available deepfake image datasets. These datasets were selected to provide a diverse collection of authentic and AI-generated facial images for training and evaluation.

The combined training dataset contains **30,000 facial images**, equally distributed between real and fake classes.

---

## Training Datasets

### 1. RVF-10K

- Dataset Name: RVF-10K
- Source: Kaggle
- Total Images: 10,000
- Real Images: 5,000
- Fake Images: 5,000

**Dataset Link**

> Placeholder (RVF-10K Kaggle Link)

---

### 2. 10000 Real Vs Fake Faces (StyleGAN3)

- Dataset Name: 10000 Real Vs Fake Faces (StyleGAN3)
- Source: Kaggle
- Total Images: 20,000
- Real Images: 15,000
- Fake Images: 15,000

**Dataset Link**

> Placeholder (StyleGAN3 Kaggle Link)

---

## Combined Training Dataset

| Property | Value |
|----------|-------|
| Total Images | 30,000 |
| Real Images | 20,000 |
| Fake Images | 20,000 |
| Classes | 2 |
| Task | Binary Classification |

The two datasets were merged to increase the diversity of facial images and improve the model's ability to learn discriminative features from multiple data sources.

---

## Cross-Domain Evaluation Datasets

The generalization capability of the proposed model was evaluated using independent datasets that were not used during training.

### 140K Real and Fake Faces

Used for evaluating the model on a large-scale unseen dataset.

> Placeholder (Dataset Link)

---

### Fake-vs-Real Faces (Hard)

Used to assess the robustness of the proposed model on more challenging deepfake samples.

> Placeholder (Dataset Link)

---

## Dataset Split

The combined dataset was divided into:

| Subset | Ratio |
|---------|------:|
| Training | 70% |
| Validation | 20% |
| Testing | 10% |

The split was performed before model training to ensure unbiased performance evaluation.

---

## Image Preprocessing

Before training, all images underwent a consistent preprocessing pipeline.

- Images resized to **256 × 256 × 3**
- RGB color format
- Supported formats: JPG and PNG
- Pixel value normalization
- Batch size: 64

The same preprocessing pipeline was applied during both training and evaluation to maintain consistency across all experiments.

---

## Dataset Organization

The datasets were organized into separate directories for training, validation, and testing, with images grouped according to their respective class labels (Real and Fake). This directory structure is compatible with the TensorFlow data loading pipeline implemented in the training notebook.

---

## Notes

The datasets remain the property of their original authors and are distributed under their respective licenses. This repository does not redistribute the datasets. Users should download them directly from the original sources before running the notebooks.
