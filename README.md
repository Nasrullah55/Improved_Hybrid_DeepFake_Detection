# Improved_Hybrid_DeepFake_Detection
# Improved Hybrid DeepFake Detection using Deep Learning

> **A transfer learning-based deepfake image detection framework utilizing an improved hybrid architecture for robust in-domain and cross-domain generalization.**

---

## Overview

The rapid advancement of Generative Artificial Intelligence (Generative AI) has significantly improved the quality of synthetic face generation, making manipulated images increasingly difficult to distinguish from authentic photographs. While these technologies provide numerous benefits across creative and industrial applications, they also introduce serious concerns regarding misinformation, identity theft, digital forgery, and privacy.

This repository presents an **Improved Hybrid DeepFake Detection (DFD)** framework developed to accurately classify real and AI-generated facial images using transfer learning and deep neural networks. The proposed framework combines the powerful feature extraction capability of a pre-trained **VGG19** backbone with a customized classification head specifically designed for binary deepfake image detection.

Unlike conventional approaches that focus solely on maximizing classification accuracy, this project emphasizes **generalization capability** through both **in-domain** and **cross-domain** evaluation. Furthermore, model interpretability is enhanced using **Gradient-weighted Class Activation Mapping (Grad-CAM)**, enabling visual analysis of the image regions contributing to model predictions.

The repository contains the complete implementation of the proposed framework, including model training, evaluation, explainability analysis, documentation, and reproducibility resources.

---

## Key Features

- Transfer Learning using **VGG19**
- Improved Hybrid CNN Architecture
- TensorFlow/Keras implementation
- Efficient `tf.data` input pipeline
- AdamW optimizer with weight decay
- Fine-tuning of selected VGG19 layers
- In-domain performance evaluation
- Cross-domain generalization analysis
- Grad-CAM visualization for model interpretability
- Publication-quality visualizations
- Fully documented implementation
- Reproducible experimental pipeline

---

## Repository Structure

```text
Improved-Hybrid-DeepFake-Detection/

│
├── notebooks/
│   ├── 01_Model_Training.ipynb
│   ├── 02_In_Domain_Evaluation.ipynb
│   ├── 03_Cross_Domain_Evaluation.ipynb
│   └── 04_GradCAM_Visualization.ipynb
│  
├── Figures/
│
├── results/
│
├── Documentation/
│   ├── Project_Documentation.md
│   ├── Model_Architecture.md
│   ├── Dataset_Description.md
│   ├── Training_Strategy.md
│   ├── Evaluation_Methodology.md
│   ├── GradCAM.md
│   └── Reproducibility_Guide.md
│
├── requirements.txt
├── README.md
├── LICENSE
├── CITATION.cff
```

---

## Project Workflow

The overall workflow of the proposed framework consists of the following stages:

1. Dataset preparation
2. Image preprocessing
3. TensorFlow data pipeline construction
4. Model development
5. Transfer learning using VGG19
6. Fine-tuning of selected convolutional layers
7. Model training
8. In-domain evaluation
9. Cross-domain evaluation
10. Grad-CAM visualization
11. Performance analysis

> ** Placeholder:** A detailed workflow diagram (`workflow.png`) will be included in the `images/` directory after repository completion.

---

## Research Contributions

The primary contributions of this work include:

- Development of an improved hybrid deepfake image detection architecture based on transfer learning.
- Investigation of model generalization through cross-domain evaluation.
- Integration of Grad-CAM for explainable deep learning.
- Construction of a reproducible experimental pipeline.
- Comprehensive documentation to facilitate reproducibility and future research.

---

## Documentation

Comprehensive technical documentation is available in the `docs/` directory.

| Document | Description |
|-----------|-------------|
| Project_Documentation.md | Complete project overview and workflow |
| Model_Architecture.md | Detailed explanation of the proposed network |
| Dataset_Description.md | Dataset preparation and organization |
| Training_Strategy.md | Model training methodology |
| Evaluation_Methodology.md | In-domain and cross-domain evaluation |
| GradCAM.md | Explainability using Grad-CAM |
| Reproducibility_Guide.md | Instructions for reproducing the experiments |

---

# Proposed Model Architecture

The proposed **Improved Hybrid DeepFake Detection (DFD)** framework is built upon a transfer learning strategy that combines the representational power of a pre-trained **VGG19** backbone with a customized convolutional classification head for binary image classification.

The VGG19 network, pre-trained on the ImageNet dataset, serves as the feature extraction backbone. Instead of training a deep convolutional network from scratch, the proposed approach leverages previously learned visual representations while fine-tuning higher-level convolutional blocks to adapt to deepfake image detection.

The customized classification head incorporates additional convolutional layers, batch normalization, max pooling, global average pooling, dense layers, dropout regularization, and a sigmoid output neuron to distinguish between authentic and manipulated facial images.

This hybrid design enables the framework to learn both generic visual representations and task-specific discriminative features, thereby improving detection accuracy while maintaining strong generalization across unseen datasets.

> **📌 Placeholder:** The complete architectural diagram is available in `images/architecture.png`.

For a layer-by-layer explanation of the proposed network, please refer to:

```text
docs/Model_Architecture.md
```

---

# Dataset

The proposed framework was developed and evaluated using publicly available deepfake image datasets.

The repository is organized so that datasets remain external to GitHub because of storage limitations and licensing restrictions.

> **📌 Placeholder:** Dataset download links will be added after repository publication.

Example:

Dataset 1:
```
RVF-10K
Link:
```

Dataset 2:
```
Cross-Domain Dataset
Link:
```

The repository documentation explains:

- Dataset organization
- Directory structure
- Class distribution
- Training/Validation/Test split
- Preprocessing methodology

A detailed description is available in:

```text
docs/Dataset_Description.md
```

---

# Experimental Pipeline

The complete experimental pipeline consists of four independent notebooks.

| Notebook | Description |
|-----------|-------------|
| 01_Model_Training.ipynb | Model construction and training |
| 02_In_Domain_Evaluation.ipynb | Evaluation using the test split of the training dataset |
| 03_Cross_Domain_Evaluation.ipynb | Generalization assessment on an unseen dataset |
| 04_GradCAM_Visualization.ipynb | Explainability analysis using Grad-CAM |

Each notebook is self-contained and can be executed independently after installing the required dependencies.

---

# Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/Improved-Hybrid-DeepFake-Detection.git
```

Move into the project directory:

```bash
cd Improved-Hybrid-DeepFake-Detection
```

Install the required packages:

```bash
pip install -r requirements.txt
```

---

# Requirements

The implementation has been developed using Python and TensorFlow.

Major dependencies include:

- Python 3.x
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- OpenCV
- Pillow

The complete list of dependencies is available in:

```text
requirements.txt
```

---

# Running the Project

The notebooks should be executed sequentially.

### Step 1

Train the proposed model.

```
01_Model_Training.ipynb
```

### Step 2

Evaluate the trained model on the in-domain test dataset.

```
02_In_Domain_Evaluation.ipynb
```

### Step 3

Perform cross-domain testing.

```
03_Cross_Domain_Evaluation.ipynb
```

### Step 4

Generate Grad-CAM visualizations.

```
04_GradCAM_Visualization.ipynb
```

---

# Trained Model

The best-performing trained model is stored in:

```text
models/best_model.keras
```

This model can be directly loaded for inference without retraining.

> **📌 Placeholder:** Future releases may include additional pretrained model checkpoints.

---

# Executable Notebook

The complete executable implementation is also available on Kaggle.

> **📌 Placeholder**

Kaggle Notebook:

```
https://www.kaggle.com/....
```

The Kaggle version contains:

- GPU-compatible implementation
- Complete training pipeline
- Saved checkpoints
- Figures
- Experimental outputs

---

# Reproducibility

The repository has been organized to facilitate reproducible research.

To reproduce the reported results:

1. Download the datasets.
2. Install all dependencies.
3. Execute the notebooks in sequence.
4. Use the provided random seeds.
5. Evaluate using the supplied evaluation notebooks.

A detailed reproducibility guide is available in:

```text
docs/Reproducibility_Guide.md
```
