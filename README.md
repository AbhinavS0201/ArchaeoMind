# ArchaeoMind: Archaeological Artifact Classification using CNN

## Overview

ArchaeoMind is a deep learning–based framework for automated classification of archaeological artifact images. The system uses Convolutional Neural Networks (CNNs) and transfer learning to distinguish between archaeological artifacts and non-artifact images.

The project aims to support digital archaeology, cultural heritage documentation, and automated image-based artifact screening.

## Dataset

A custom archaeological image dataset was created and publicly released on Kaggle.

- Total images collected: **1,349**
- Valid images after preprocessing: **1,252**
- Training images: **849**
- Validation images: **202**
- Test images: **201**

### Class Distribution

| Split | Artifact | Non-artifact | Total |
|---|---:|---:|---:|
| Training | 383 | 466 | 849 |
| Validation | 101 | 101 | 202 |
| Test | 102 | 99 | 201 |

### Kaggle Dataset

https://www.kaggle.com/datasets/abhinavrama22/archaeomind-images

## Model

The primary ArchaeoMind model uses **MobileNetV2 with ImageNet-pretrained weights**.

### Configuration

- Architecture: **MobileNetV2**
- Learning approach: **Transfer Learning**
- Pretrained weights: **ImageNet**
- Input size: **224 × 224 × 3**
- Optimizer: **Adam**
- Learning rate: **0.0001**
- Loss function: **Binary Cross-Entropy**
- Epochs: **10**
- Training batch size: **32**
- Validation/Test batch size: **16**
- Dropout: **0.3**
- Classification: **Binary**
- Classes: **Artifact / Non-artifact**

The pretrained MobileNetV2 convolutional base was kept frozen while a custom classification head was trained.

## Data Augmentation

The training pipeline applies:

- Rotation: ±20°
- Width shift: 0.1
- Height shift: 0.1
- Zoom: 0.1
- Horizontal flipping

## Experimental Evaluation

To evaluate the stability of the model, experiments were repeated using three random seeds:

- **42**
- **123**
- **2026**

The reported values are calculated as mean ± standard deviation across the three runs.

### MobileNetV2 Results

| Metric | Mean ± Standard Deviation |
|---|---:|
| Test Accuracy | **86.90% ± 1.15%** |
| ROC-AUC | **93.62% ± 0.69%** |

### EfficientNet-B0 Comparison

An EfficientNet-B0 baseline was also evaluated using the same dataset split and experimental protocol.

| Model | Test Accuracy (%) | ROC-AUC (%) |
|---|---:|---:|
| MobileNetV2 | **86.90 ± 1.15** | **93.62 ± 0.69** |
| EfficientNet-B0 | **88.39 ± 0.29** | **95.76 ± 0.19** |

EfficientNet-B0 achieved slightly higher classification performance, while MobileNetV2 provides a more lightweight architecture suitable for resource-constrained deployment.

## Features

- End-to-end CNN classification pipeline
- Image preprocessing and normalization
- Data augmentation
- Transfer learning using ImageNet
- Binary artifact/non-artifact classification
- Accuracy and ROC-AUC evaluation
- Confusion matrix analysis
- Training and validation accuracy visualization
- Confidence-score-based image prediction
- Trained model saving and inference support
- Reproducible evaluation using multiple random seeds

## Project Structure

```text
ArchaeoMind/
│
├── ArchaeoMind_CNN.ipynb
├── accuracy_curve.png
├── confusion_matrix.png
├── archaeomind_cnn_model.h5
└── README.md
