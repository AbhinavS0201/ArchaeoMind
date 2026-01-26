# ArchaeoMind: Archaeological Artifact Classification using CNN

## Overview
ArchaeoMind is a deep learning–based project for automated classification of archaeological artifact images. The system uses a Convolutional Neural Network (CNN) with transfer learning to distinguish between artifact and non-artifact images, supporting digital archaeology and cultural heritage analysis.

## Dataset
- Custom archaeological image dataset published on Kaggle  
- Total images collected: **1,349**  
- Valid images used after preprocessing: **1,252**  
- Dataset split:
  - Training: 849 images
  - Validation: 202 images
  - Test: 201 images

Kaggle Dataset:  
https://www.kaggle.com/datasets/abhinavrama22/archaeomind-images

## Model Details
- Architecture: **MobileNetV2 (Transfer Learning)**
- Input image size: **224 × 224 × 3**
- Optimizer: Adam
- Loss function: Binary Cross-Entropy
- Epochs: 10

## Results
| Metric | Accuracy |
|------|----------|
| Training | 95% |
| Validation | 81.7% |
| Test | 87% |

The model demonstrates good generalization performance with mild overfitting due to limited dataset size.

## Features
- End-to-end CNN pipeline (preprocessing, training, evaluation)
- Binary classification (Artifact / Non-Artifact)
- Confidence score–based predictions
- Model saving and inference support

## How to Run
1. Clone this repository
2. Open the notebook in Google Colab
3. Download the dataset from Kaggle
4. Run all cells sequentially

## Future Work
- Expand the dataset with real archaeological site images
- Extend the system to multi-class artifact classification
- Fine-tune deeper layers of the network for improved performance
