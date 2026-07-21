# Cross-Domain Evaluation

## Overview

To assess the generalization capability of the proposed Improved Hybrid DeepFake Detection (DFD) framework, the trained model was evaluated on publicly available datasets that were not used during the training process. This evaluation measures the model's ability to detect manipulated facial images from different data distributions and generation sources.

Unlike the in-domain evaluation, where the testing data originates from the same datasets used for training, cross-domain evaluation provides a more realistic assessment of model robustness in practical applications.

---

## Evaluation Datasets

Two independent datasets were selected for cross-domain evaluation.

### 140K Real and Fake Faces

The first evaluation was conducted using the **140K Real and Fake Faces** dataset. A balanced subset containing **2,000 real** and **2,000 fake** images was sampled to ensure an unbiased evaluation.

### Fake-vs-Real Faces (Hard)

The second evaluation used the **Fake-vs-Real Faces (Hard)** dataset, which contains more challenging manipulated facial images. Since the dataset is naturally imbalanced, a balanced subset consisting of **589 real** and **589 fake** images was created before evaluation.

---

## Evaluation Procedure

The cross-domain evaluation follows the workflow below:

1. Load the trained model (`best_model.keras`).
2. Prepare balanced test samples from each external dataset.
3. Apply the same preprocessing pipeline used during training.
4. Generate prediction probabilities.
5. Convert probabilities into binary class labels.
6. Compute performance metrics.
7. Generate confusion matrices and ROC curves.
8. Export the evaluation results.

---

## Performance Metrics

The following metrics are computed independently for each external dataset:

- Accuracy
- Precision
- Recall
- F1-Score
- AUC-ROC

These metrics provide a comprehensive assessment of the model's ability to generalize beyond the training distribution.

---

## Visualization

For each dataset, the notebook generates:

- Confusion Matrix
- ROC Curve
- Classification Report
- Performance Summary

These visualizations support the quantitative analysis presented in the research paper and facilitate comparison between datasets.

---

## Result Export

The evaluation notebook exports:

- Dataset-wise performance metrics
- Combined performance summary
- CSV files
- Excel files
- Prediction outputs
- Publication-quality figures

All generated outputs are stored in the `results/` and `images/` directories.

---

## Significance

Cross-domain evaluation is an important component of this work, as it demonstrates that the proposed framework is capable of maintaining strong performance on datasets that were completely unseen during training. This provides evidence that the learned representations are not limited to a single dataset and can generalize to different deepfake generation sources.

The inclusion of cross-domain testing addresses one of the major challenges in deepfake detection and strengthens the practical applicability of the proposed framework.

---

## Related Documentation

For additional details, refer to:

- `docs/Training_Strategy.md`
- `docs/In_Domain_Evaluation.md`
- `docs/GradCAM.md`
