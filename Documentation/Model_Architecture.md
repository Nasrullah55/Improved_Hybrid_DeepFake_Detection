# Model Architecture

## Improved Hybrid DeepFake Detection (DFD)

---

## Overview

The proposed Improved Hybrid DeepFake Detection (DFD) model is a transfer learning-based framework designed to classify facial images as either **real** or **AI-generated**. The architecture combines the feature extraction capabilities of a pre-trained VGG19 network with a custom classification head to improve detection performance while maintaining good generalization across different datasets.

Instead of training a deep neural network from scratch, the model utilizes knowledge learned from the ImageNet dataset and fine-tunes the higher convolutional blocks to adapt to the deepfake image detection task.

---

## Architecture Overview

The proposed architecture consists of two major components:

1. Feature Extraction Backbone
2. Custom Classification Head

The feature extraction backbone learns high-level visual representations from input images, while the custom classification head performs binary classification based on the extracted features.

> **Placeholder:** A detailed architecture diagram is available in `images/architecture.png`.

---

## Input Layer

The network accepts RGB facial images with a fixed resolution of **256 × 256 × 3**.

| Property | Value |
|----------|-------|
| Image Size | 256 × 256 |
| Channels | 3 (RGB) |
| Input Shape | (256, 256, 3) |

All images are resized to the required input dimensions before being passed to the network.

---

## Feature Extraction Backbone

The backbone of the proposed model is based on the **VGG19** convolutional neural network pre-trained on the ImageNet dataset.

The pre-trained weights provide robust low-level and mid-level visual representations, allowing the model to converge more efficiently while reducing the amount of task-specific training required.

To adapt the model for deepfake image detection, transfer learning is employed by selectively fine-tuning the higher convolutional layers.

### Transfer Learning Strategy

The model follows a partial fine-tuning strategy:

- Pre-trained ImageNet weights are used.
- Lower convolutional layers remain frozen.
- VGG19 Block 4 is unfrozen.
- VGG19 Block 5 is unfrozen.
- Fine-tuning is performed using a low learning rate.

This approach preserves generic visual features while allowing the deeper layers to learn task-specific representations relevant to manipulated facial images.

---

## Custom Classification Head

Following feature extraction, a custom classification head is attached to the VGG19 backbone.

The classification head consists of:

- Convolution Layer
- Batch Normalization
- Max Pooling
- Dropout (0.4)
- Global Average Pooling
- Dense Layer (ReLU)
- Batch Normalization
- Dropout (0.4)
- Output Dense Layer (Sigmoid)

The additional convolutional layer enables the model to learn more discriminative features, while batch normalization improves training stability. Dropout layers help reduce overfitting by randomly deactivating neurons during training.

Global Average Pooling is used to reduce the spatial dimensions of the extracted feature maps before they are passed to the fully connected layers.

---

## Output Layer

The final classification layer consists of a single neuron with a **Sigmoid** activation function.

This configuration produces a probability score between **0 and 1**, representing the likelihood that the input image belongs to the manipulated class.

| Property | Value |
|----------|-------|
| Output Units | 1 |
| Activation | Sigmoid |
| Task | Binary Classification |

---

## Training Configuration

The proposed model is trained using the following configuration.

| Parameter | Value |
|-----------|-------|
| Optimizer | AdamW |
| Loss Function | Binary Cross-Entropy |
| Epochs | 35 |
| Dropout Rate | 0.4 |
| Backbone | VGG19 |
| Transfer Learning | Yes |

Additional training details, including learning rate scheduling, callbacks, and model checkpointing, are provided in `docs/Training_Strategy.md`.

---

## Design Rationale

The architecture was designed to balance classification performance and computational efficiency.

The use of VGG19 enables the framework to leverage rich visual features learned from a large-scale image dataset, while the custom classification head adapts these representations to the deepfake detection task.

Fine-tuning only the higher convolutional blocks reduces the number of trainable parameters compared to training the entire network from scratch, resulting in improved convergence and lower computational cost. The inclusion of dropout and batch normalization further enhances generalization by reducing overfitting and stabilizing the optimization process.

---

## Model Workflow

The processing pipeline of the proposed model can be summarized as follows:

```text
Input Image
      │
      ▼
VGG19 Feature Extraction
      │
      ▼
Custom Convolution Layer
      │
      ▼
Batch Normalization
      │
      ▼
Max Pooling
      │
      ▼
Dropout
      │
      ▼
Global Average Pooling
      │
      ▼
Dense Layer (ReLU)
      │
      ▼
Batch Normalization
      │
      ▼
Dropout
      │
      ▼
Dense Layer (Sigmoid)
      │
      ▼
Prediction
```

---

## Related Documentation

For additional implementation details, readers are encouraged to consult the following documents:

- Documentation/Project_Documentation.md`
- `Documentation/Dataset_Description.md`
- `Documentation/Training_Strategy.md`
- `Documentation/Evaluation_Methodology.md`
- `Documentation/GradCAM.md`
- `Documentation/Reproducibility_Guide.md`
