# 🗑️ Garbage Classification with Transfer Learning

A deep learning project for classifying household waste images into 12 distinct categories to promote effective recycling. Built using transfer learning with MobileNetV2 and fine-tuned on a custom dataset from Kaggle.

## 📌 Project Overview

Recycling is critical to environmental sustainability, but sorting waste manually is time-consuming and error-prone. This project explores an automated image-based garbage classification system using state-of-the-art deep learning techniques to improve sorting accuracy.

### ✅ Supported Classes
- Paper
- Cardboard
- Biological
- Metal
- Plastic
- Green-glass
- Brown-glass
- White-glass
- Clothes
- Shoes
- Batteries
- Trash

## 📊 Dataset

- **Source:** [Kaggle: Garbage Classification (12 Classes)](https://www.kaggle.com/datasets/mostafaabla/garbage-classification)
- **Total Images:** 15,150
- **Train/Val/Test Split:** 80% / 10% / 10%
- **Preprocessing:** Rotation, zoom, flipping, rescaling via `ImageDataGenerator`.

## 🧠 Model Architecture

- **Base Model:** MobileNetV2 (pretrained on ImageNet)
- **Added Layers:**
  - `GlobalMaxPooling2D`
  - Dense layer (50 units, ReLU)
  - Dropout (rate 0.5)
  - Output layer (12 units, softmax)

## ⚙️ Training Details

- **Optimizer:** Adam
- **Loss Function:** Categorical Crossentropy
- **Epochs:** 15
- **Callbacks:**
  - Early stopping
  - Learning rate scheduler (halves LR every 5 epochs)
  - TensorBoard & CSV logger
  - Model checkpointing
- **Hyperparameter Tuning:** Grid search for learning rate; best found: `2e-4`

## 📈 Results

| Metric     | Value  |
|------------|--------|
| Accuracy   | 94.65% |
| Precision  | 94.80% |
| Recall     | 94.65% |
| F1 Score   | 94.65% |
| AUC        | 99.72% |

