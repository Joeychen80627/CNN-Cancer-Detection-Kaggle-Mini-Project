# CNN Cancer Detection Kaggle Mini-Project

## Project Overview
This project focuses on detecting cancer cells from histopathological tissue slice images using Convolutional Neural Networks (CNNs). The dataset comes from the Kaggle Histopathologic Cancer Detection challenge.

## Problem Description
A binary classification problem to predict whether a histopathological image contains cancer cells:
- **label = 1**: Presence of cancer cells
- **label = 0**: No cancer cells

## Dataset Structure
- **id**: Unique identifier for each image
- **label**: Binary value (0/1) indicating cancer presence

### Data Quality
No missing values found in the dataset:

```plaintext
Missing values summary:
id       0
label    0
dtype: int64

## Key Findings from EDA

### Label Distribution:
- 60% negative samples (no cancer)
- 40% positive samples (cancer)

### Image Characteristics:
- **Size**: 96×96 pixels
- **Color Channels**: 3 (RGB)
- **RGB Channel Contributions**:
  - **Red**: Highest contribution
  - **Green**: Moderate contribution
  - **Blue**: Lowest contribution

## Model Implementations

### Model 1: Basic CNN with BatchNorm
- **Architecture**: 3 convolutional layers + BatchNormalization
- **Learning rate**: 0.001
- **Params**: ~1.3M
- **Characteristics**:
  - Fast convergence but overfits
  - Validation accuracy plateaus at ~75%

### Model 2: Deep CNN with LayerNorm
- **Architecture**: 5 convolutional layers + LayerNormalization
- **Learning rate**: 0.0001
- **Params**: ~4.7M
- **Characteristics**:
  - Stable training
  - Better generalization (~80% validation accuracy)

### Model 3: Enhanced CNN with Augmentation
- **Architecture**: 5 convolutional layers + BatchNorm
- **Learning rate**: 0.0005
- **Params**: ~4.6M
- **Augmentations**: Rotation, shifting, shearing, zooming, flipping
- **Characteristics**:
  - Best private score (0.8888)
  - Small public-private score gap (+0.0178)

## Performance Comparison

| Model   | Private Score | Public Score | Difference |
|---------|---------------|--------------|------------|
| v3(3)   | 0.8888        | 0.8710       | +0.0178    |
| v3(2)   | 0.8329        | 0.8801       | -0.0472    |
| v3(1)   | 0.8316        | 0.8585       | -0.0269    |
| Model 3 | 0.8595        | 0.8908       | -0.0313    |
| Model 2 | 0.7880        | 0.8418       | -0.0538    |
| Model 1 | 0.8300        | 0.9009       | -0.0709    |

## Key Conclusions
- **Best Model**: v3(3) achieved the highest private score (0.8888)
- **Overfitting**: Model 1 showed the largest performance drop (-0.0709)
- **Stability**: v3(3) had the smallest difference (+0.0178), indicating the best generalization

## Requirements
- Python 3.x
- TensorFlow/Keras
- OpenCV
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Installation
Clone the repository and install dependencies:

```bash
git clone https://github.com/Joeychen80627/CNN-Cancer-Detection-Kaggle-Mini-Project.git
cd CNN-Cancer-Detection-Kaggle-Mini-Project
pip install -r requirements.txt
