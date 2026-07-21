# Grad-CAM Visualization

## Overview

To improve the interpretability of the proposed Improved Hybrid DeepFake Detection (DFD) framework, Gradient-weighted Class Activation Mapping (Grad-CAM) was employed. Grad-CAM provides a visual explanation of the model's predictions by highlighting the image regions that contribute most to the final classification.

Unlike quantitative metrics such as accuracy and F1-score, Grad-CAM offers qualitative insight into the model's decision-making process, helping verify that predictions are based on meaningful facial features rather than irrelevant background information.

---

## Purpose

The Grad-CAM analysis was performed to:

- Visualize the regions influencing model predictions.
- Improve the interpretability of the proposed model.
- Verify that the model focuses on meaningful facial characteristics.
- Support the quantitative evaluation with qualitative evidence.

---

## Methodology

The Grad-CAM visualization follows the steps below:

1. Load the trained model (`best_model.keras`).
2. Select an input image.
3. Apply the same preprocessing pipeline used during training.
4. Compute the gradients of the predicted class with respect to the final convolutional layer.
5. Generate the activation heatmap.
6. Overlay the heatmap on the original image.
7. Save the visualization for analysis.

---

## Visualization Process

For each input image, the notebook produces:

- Original Image
- Grad-CAM Heatmap
- Overlay Visualization
- Predicted Class
- Prediction Confidence

These visualizations help explain how the model reaches its final decision.

---

## Interpretation

The generated heatmaps indicate the regions that contribute most strongly to the model's prediction.

Ideally, the model should concentrate on facial attributes such as the eyes, nose, mouth, skin texture, and other facial structures rather than background elements. Consistent attention to these regions suggests that the model has learned meaningful discriminative features for distinguishing authentic and AI-generated faces.

---

## Output

The Grad-CAM notebook generates:

- Heatmap images
- Overlay visualizations
- Prediction summaries
- Publication-quality figures

The generated images are stored in the `images/` directory and can be included directly in reports or research publications.

---

## Significance

Grad-CAM complements the quantitative evaluation by providing visual evidence of the model's behavior. It helps verify that the proposed framework bases its predictions on relevant facial regions, thereby increasing the transparency and interpretability of the deep learning model.

This analysis strengthens the overall evaluation by demonstrating not only how accurately the model performs, but also how it arrives at its predictions.

---

## Related Documentation

For additional details, refer to:

- `docs/Model_Architecture.md`
- `docs/Training_Strategy.md`
- `docs/Evaluation_Methodology.md`
- `docs/Cross_Domain_Evaluation.md`
