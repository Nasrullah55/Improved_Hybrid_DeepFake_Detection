# Training Strategy

## Overview

The proposed Improved Hybrid DeepFake Detection (DFD) model was trained using a transfer learning strategy based on the VGG19 architecture. The training pipeline was designed to improve convergence, reduce overfitting, and enhance model generalization through a combination of fine-tuning, regularization, and adaptive optimization techniques.

---

## Training Configuration

| Parameter | Value |
|-----------|-------|
| Random Seed | 42 |
| Image Size | 256 × 256 × 3 |
| Batch Size | 64 |
| Maximum Epochs | 35 |
| Optimizer | AdamW |
| Initial Learning Rate | 1 × 10⁻⁵ |
| Weight Decay | 1 × 10⁻⁴ |
| Gradient Clipping | ClipNorm = 1.0 |
| Exponential Moving Average (EMA) | Enabled |
| EMA Momentum | 0.99 |
| Loss Function | Binary Cross-Entropy |
| Label Smoothing | 0.1 |
| Evaluation Metric | Accuracy |

---

## Optimizer

The model was optimized using the AdamW optimizer with decoupled weight decay. Compared with the standard Adam optimizer, AdamW provides improved regularization by separating weight decay from the gradient update, leading to better generalization performance.

To further stabilize training, gradient clipping (ClipNorm = 1.0) was applied, and Exponential Moving Average (EMA) of model weights was enabled. At the end of training, the EMA weights were finalized before model evaluation and saving.

---

## Loss Function

Binary Cross-Entropy with label smoothing (0.1) was used as the optimization objective. Label smoothing reduces overconfident predictions by softening target labels, which helps improve generalization and model calibration.

---

## Learning Rate Strategy

The initial learning rate was set to **1 × 10⁻⁵**. A `ReduceLROnPlateau` callback monitored the validation loss and reduced the learning rate by a factor of **0.5** when performance plateaued.

Configuration:

- Monitor: Validation Loss
- Factor: 0.5
- Patience: 2 epochs
- Minimum Learning Rate: 1 × 10⁻⁷

---

## Callback Configuration

The following callbacks were used during training:

### EarlyStopping

- Monitor: Validation Loss
- Patience: 8 epochs
- Restore Best Weights: Enabled

This callback prevents unnecessary training once the validation performance stops improving.

---

### ModelCheckpoint

The best-performing model was automatically saved based on the lowest validation loss.

Saved Model:

```text
models/best_model.keras
```

---

### CSV Logger

Training history, including loss and accuracy values for each epoch, was recorded automatically for later analysis and visualization.

---

## Training Process

The model was trained for a maximum of **35 epochs**. However, EarlyStopping allowed training to terminate automatically once validation performance no longer improved, reducing unnecessary computation and limiting overfitting.

After training, the optimizer finalized the Exponential Moving Average weights before the best model was saved.

---

## Training Outputs

The training stage generates the following outputs:

- Best trained model (`best_model.keras`)
- Training history
- CSV training log
- Accuracy curve
- Loss curve

These outputs are used in the subsequent evaluation and explainability notebooks.

---

## Related Documentation

For additional information, refer to:

- `docs/Project_Documentation.md`
- `docs/Model_Architecture.md`
- `docs/Dataset_Description.md`
- `docs/Evaluation_Methodology.md`
- `docs/GradCAM.md`
