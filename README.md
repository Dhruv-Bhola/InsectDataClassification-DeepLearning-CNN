# 🐞 Dangerous Insects Classification using PyTorch CNN

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red.svg)
![CNN](https://img.shields.io/badge/Model-CNN-green.svg)

A deep learning-based image classification system for identifying harmful agricultural insects and crop diseases using a custom Convolutional Neural Network (CNN).

</div>

---

## 📖 Project Overview
Developed a Convolutional Neural Network (CNN) using PyTorch for agricultural insect classification.

The model was trained on the **Dangerous Insects Dataset** and classified images into four categories: Aphids, Citrus Canker, Spider Mites, and Thrips.

The objective is to automate insect and disease identification for agricultural monitoring and early crop protection.

- Built a custom PyTorch Dataset and DataLoader pipeline for image preprocessing and batch generation.
- Applied image resizing, normalization, and data handling techniques for efficient model training.
- Designed a CNN architecture with Batch Normalization, Dropout Regularization, and Fully Connected layers.
- Trained the model using the Adam optimizer and CrossEntropy Loss.
- Evaluated performance using precision, recall, F1-score, and classification reports.
- Visualized training and validation loss trends to monitor model learning and generalization.

---

## 🎯 Classification Categories

| Class ID | Category |
|-----------|------------|
| 0 | Aphids |
| 1 | Citrus Canker |
| 2 | Spider Mites |
| 3 | Thrips |

---

## 📂 Dataset Structure

```text
farm_insects/
│
├── Aphids/
│   ├── Image_1.jpeg
│   ├── Image_2.jpeg
│   └── ...
│
├── Citrus Canker/
│   └── ...
│
├── Spider Mites/
│   └── ...
│
└── Thrips/
    └── ...
```

---

## 🛠 Tech Stack

| Component | Technology |
|------------|------------|
| Language | Python |
| Deep Learning Framework | PyTorch |
| Image Processing | Torchvision, PIL |
| Visualization | Matplotlib, Seaborn |
| Evaluation | Scikit-Learn |
| Numerical Computing | NumPy |

---

## 🔄 Data Preprocessing

All images undergo the following preprocessing pipeline:

```python
transforms.Compose([
    transforms.Resize((224,224)),
    transforms.ToTensor(),
    transforms.Normalize(
        (0.4642, 0.5204, 0.3377),
        (0.2419, 0.2262, 0.2446)
    )
])
```

### Applied Operations

- Resize images to **224 × 224**
- Convert images to tensors
- Normalize pixel values
- Prepare data for CNN training

---

## 📊 Dataset Split

| Dataset | Ratio |
|----------|--------|
| Training Set | 80% |
| Validation Set | 20% |

---

# 🧠 Model Architecture

The project uses a custom CNN architecture named **NetNormDrop**.

## Architecture Diagram

```text
Input Image (224×224×3)
            │
            ▼
Conv2D (3 → 32)
BatchNorm
ReLU
Dropout
            │
            ▼
Conv2D (32 → 64)
BatchNorm
ReLU
Dropout
            │
            ▼
Conv2D (64 → 128)
BatchNorm
ReLU
Dropout
            │
            ▼
Conv2D (128 → 256)
BatchNorm
ReLU
Dropout
            │
            ▼
Adaptive Average Pooling
            │
            ▼
Flatten
            │
            ▼
FC Layer (4096 → 1000)
            │
            ▼
FC Layer (1000 → 100)
            │
            ▼
FC Layer (100 → 4)
            │
            ▼
Output Classes
```

---

## ⚙️ Training Configuration

| Parameter | Value |
|------------|--------|
| Optimizer | Adam |
| Learning Rate | 1e-4 |
| Loss Function | CrossEntropyLoss |
| Batch Size | 32 |
| Epochs | 20 |
| Input Size | 224 × 224 |

---

## 🔁 Training Workflow

```text
Image Dataset
      │
      ▼
DataLoader
      │
      ▼
CNN Forward Pass
      │
      ▼
Prediction
      │
      ▼
Cross Entropy Loss
      │
      ▼
Backpropagation
      │
      ▼
Adam Optimizer
      │
      ▼
Weight Update
      │
      ▼
Next Batch
```

---

## 📈 Evaluation Metrics

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report

Generated via:

```python
classification_report(
    y_true,
    y_pred
)
```

---

## 📉 Loss Visualization

Training and Validation Loss curves are plotted to monitor:

- Learning Progress
- Overfitting
- Underfitting
- Convergence Behavior

---

## 🚀 Installation

### Clone Repository

```bash
git clone https://github.com/Dhruv-Bhola/InsectDataClassification-DeepLearning-CNN

cd InsectDataClassification-DeepLearning-CNN
```

### Install Dependencies

```bash
pip install torch torchvision matplotlib seaborn scikit-learn pillow numpy
```

---

## 🔮 Future Enhancements

- Transfer Learning with ResNet50
- EfficientNet Integration
- Vision Transformer (ViT)
- Data Augmentation
- Model Checkpointing
- Confusion Matrix Visualization
- TensorBoard Integration
- Web Deployment using Flask/Streamlit

---

## 👨‍💻 Author

**Dhruv Bhola**

Deep Learning | Computer Vision | Remote Sensing | Earth Observation

---

<div align="center">

⭐ If you found this project useful, consider giving it a star.

</div>
