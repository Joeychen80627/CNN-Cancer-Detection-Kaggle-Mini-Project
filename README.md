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
