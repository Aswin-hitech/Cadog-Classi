# CADOG CLASSI

A deep learning project for classifying cat and dog images using a convolutional neural network (CNN). This repository includes both a notebook version and a Python training script for reproducing the workflow from dataset download through evaluation and model export.

## Overview

This project builds a binary image classifier that learns to distinguish cats from dogs using a CNN trained on a Kaggle dataset. It demonstrates a complete deep learning pipeline:

- downloading a cat-and-dog image dataset
- preparing training and validation datasets
- applying image augmentation and normalization
- training a CNN model
- evaluating classification performance
- saving plots, metrics, and the trained model

## Repository Contents

- `CADOG_CLASSI_PROJ.ipynb` — notebook version of the full workflow
- `cadog_classi_proj.py` — standalone Python implementation
- `README.md` — project documentation
- `outputs/` — generated during training and evaluation (not committed by default)

## Model Architecture

The model is a TensorFlow/Keras CNN trained for binary classification:

- input size: 160 x 160 RGB images
- data augmentation: random flip, rotation, zoom, and contrast adjustments
- rescaling layer for pixel normalization
- 3 convolutional blocks with batch normalization and max pooling
- global average pooling
- dense classification head with dropout
- sigmoid output for binary prediction

## Training Setup

The training configuration is:

- optimizer: Adam
- loss function: binary crossentropy
- batch size: 32
- epochs: 30
- validation split: 20%
- random seed: 42
- learning rate: 0.001
- dropout: 0.4

## Evaluation Metrics

The project evaluates the model using both standard and extended metrics:

- accuracy
- precision
- recall
- F1-score
- AUC
- loss
- sensitivity
- specificity
- balanced accuracy
- false positive rate
- false negative rate
- MCC
- Pearson correlation
- Youden's J statistic

A confusion matrix is also generated to show true positives, true negatives, false positives, and false negatives.

## Generated Outputs

When the training script or notebook is executed, it creates an `outputs/` folder containing artifacts such as:

- `accuracy_graph.png` — training and validation accuracy curve
- `loss_graph.png` — training and validation loss curve
- `auc_graph.png` — training and validation AUC curve
- `confusion_matrix.png` — confusion matrix heatmap
- `classification_report.json` — classification report
- `evaluation_metrics.json` — detailed metrics and confusion matrix
- `model_summary.txt` — CNN architecture summary
- `dog_cat_cnn_final.keras` — saved trained model
- `best_dog_cat_cnn.keras` — best checkpoint during training

## Running the Project

### Option 1: Jupyter Notebook

Open `CADOG_CLASSI_PROJ.ipynb` in Jupyter or Google Colab and run the cells sequentially.

### Option 2: Python Script

Run the script from the repository root:

```bash
python cadog_classi_proj.py
```

## Requirements

Make sure these dependencies are installed:

- Python 3.x
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- kagglehub

## Summary

This project demonstrates an end-to-end deep learning workflow for binary image classification. It combines dataset preparation, CNN model training, validation, metric evaluation, and artifact saving into a single reproducible pipeline for identifying cats and dogs from images.
