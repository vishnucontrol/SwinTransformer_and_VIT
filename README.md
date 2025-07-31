# SwinTransformer_and_VIT
Comparative Analysis: Swin Transformer vs Vision Transformer (ViT)

This project presents a comparative study between two transformer-based deep learning architectures — **Swin Transformer** and **Vision Transformer (ViT)** — applied to grayscale medical image classification involving three classes: **AD (Alzheimer's Disease)**, **CN (Cognitively Normal)**, and **MCI (Mild Cognitive Impairment)**.

---

## 📁 Dataset

- **Format:** Grayscale PNG images
- **Resolution:** Resized to `224x224`
- **Classes:** 
  - `AD` (Alzheimer's Disease)
  - `CN` (Cognitively Normal)
  - `MCI` (Mild Cognitive Impairment)


## 🧠 Model Architectures

### ✅ Swin Transformer (Simplified)

A lightweight convolutional model simulating Swin Transformer behavior via convolution + pooling layers, followed by a global pooling and dense classifier.

- Convolution-based patch extraction
- Global average pooling
- Output: 3-class softmax classifier

### ✅ Vision Transformer (ViT)

A patch-based transformer architecture with multi-head self-attention and positional encoding.

- Patch embedding via `Conv2D` with stride = patch size
- 8 Transformer blocks with attention + MLP layers
- Flattened transformer output passed to dense classifier


🚀 How to Run
Prepare the dataset as described above.

Update data_dir paths in both scripts (swin.py and vit.py) to point to your dataset directory.

Run each script to train and evaluate Swin and ViT models.

Evaluation metrics and confusion matrix will be printed and plotted.

📊 Results

| **Metric**            | **Swin Transformer** | **Vision Transformer (ViT)** |
|-----------------------|----------------------|-------------------------------|
| Validation Accuracy   | 77.01%               | **95.54%**                    |
| Test Accuracy         | 80.12%               | **92.08%**                    |
| Cohen's Kappa         | 0.63                 | **0.86**                      |
| Log Loss              | 0.7557               | **~0.45**                     |
| Macro F1-Score        | 0.669                | **0.955**                     |

✅ ViT outperforms Swin Transformer across all evaluation metrics, particularly in precision, recall, and F1-score.

🧪 Evaluation Metrics (ViT Example)
Precision: [0.95, 0.96, 0.95]

Recall: [0.95, 0.95, 0.96]

F1-Score: [0.95, 0.95, 0.95]

Specificity: [0.99, 0.98, 0.94]

Plots:

✅ Confusion Matrix

✅ ROC Curve

✅ Precision-Recall Curve

✅ Accuracy vs Epoch Graph

🧠 Insights
Swin Transformer is faster and lightweight but underperforms in complex classification tasks compared to ViT.

ViT leverages transformer attention mechanisms more effectively and generalizes better to unseen data.

Training on grayscale images is viable with both architectures, although ViT benefits more from positional encoding and deeper attention layers.
