# In Domain Evaluation Methodology

## Overview

The proposed Improved Hybrid DeepFake Detection (DFD) framework was evaluated using a comprehensive testing strategy designed to assess both dataset-specific performance and overall classification capability. The evaluation was conducted on the held-out test sets of the combined training dataset using the best-performing model obtained during training.

The evaluation notebook computes performance metrics separately for each dataset and also reports the overall performance on the combined test set.

---

## Evaluation Strategy

The in-domain evaluation consists of three independent experiments:

### 1. RVF-10K Evaluation

The trained model is evaluated on the test partition of the RVF-10K dataset to measure its performance on images originating from this dataset.

---

### 2. StyleGAN3 Evaluation

The trained model is evaluated on the test partition of the 10000 Real Vs Fake Faces (StyleGAN3) dataset to assess its ability to classify images from a second training source.

---

### 3. Combined Dataset Evaluation

Finally, the predictions from both datasets are combined to produce an overall evaluation of the proposed framework. This provides a comprehensive assessment of the model's performance across the entire in-domain test set.

---

## Evaluation Workflow

The evaluation notebook follows the workflow below:

1. Load the trained model.
2. Load the RVF-10K test dataset.
3. Load the StyleGAN3 test dataset.
4. Apply the same preprocessing pipeline used during training.
5. Generate prediction probabilities.
6. Convert probabilities into binary class labels.
7. Compute dataset-specific performance metrics.
8. Combine predictions from both datasets.
9. Compute overall performance metrics.
10. Generate visualizations and export the results.

---

## Performance Metrics

The following evaluation metrics are computed for each dataset individually as well as for the combined test set:

- Accuracy
- Precision
- Recall
- F1-Score
- AUC-ROC

This evaluation strategy provides both dataset-level insights and an overall measure of the model's classification performance.

---

## Visual Analysis

The evaluation notebook generates several visualizations to facilitate performance analysis, including:

- Confusion Matrix
- ROC Curve
- Accuracy Summary
- Classification Report
- Prediction Statistics

The generated figures are stored in the `images/` directory, while numerical results are saved in the `results/` directory for further analysis and reporting.

---

## Reproducibility

The evaluation process uses the same preprocessing pipeline, input image dimensions, normalization procedure, and trained model employed during training. This ensures consistency between training and testing and enables reproducibility of the reported results.
