# CADOG CLASSI

A deep learning project for classifying cat and dog images using a convolutional neural network (CNN). The project is designed to learn visual patterns from image data, make binary predictions, and evaluate model performance using standard classification metrics.

## Project Overview

This repository contains a complete workflow for:
- downloading a cat-and-dog image dataset
- preparing image batches for training and validation
- building a CNN-based binary classifier
- applying data augmentation to improve generalization
- tracking training performance over epochs
- evaluating the model with multiple metrics
- saving artifacts such as graphs, reports, and the trained model

## Approach

The classification pipeline uses a TensorFlow/Keras CNN with the following structure:
- input image size: 160 x 160 RGB
- data augmentation layers: horizontal flip, rotation, zoom, contrast adjustment
- rescaling layer for normalization
- 3 convolutional blocks with batch normalization and max pooling
- global average pooling
- dense classification head with dropout
- sigmoid output for binary classification

This is a binary classification task where:
- class 0 = cats
- class 1 = dogs

## Techniques Used

- Image preprocessing and normalization
- Data augmentation to reduce overfitting
- Batch normalization for training stability
- Dropout regularization
- Early stopping to stop training when validation loss stops improving
- Learning rate reduction on plateau for adaptive optimization
- Model checkpointing to save the best-performing model

## Model Training

The model is trained using:
- optimizer: Adam
- loss function: binary crossentropy
- batch size: 32
- epochs: 30
- validation split: 20%
- random seed: 42

## Evaluation Metrics

The project reports both standard and extended binary classification metrics to assess performance:

### Core Metrics
- Accuracy
- Precision
- Recall
- F1-score
- AUC
- Loss

### Additional Metrics
- Sensitivity
- Specificity
- Balanced Accuracy
- False Positive Rate (FPR)
- False Negative Rate (FNR)
- Matthews Correlation Coefficient (MCC)
- Pearson Correlation Coefficient (r-score)
- Youden's J statistic

These metrics help evaluate not only overall prediction quality, but also class imbalance behavior and discrimination ability.

## Confusion Matrix

A confusion matrix is generated to summarize:
- true positives
- true negatives
- false positives
- false negatives

This provides a more detailed view of where the model is making mistakes.

## Outputs Generated

The project saves the following outputs in the `outputs/` directory:
- `accuracy_graph.png` — training and validation accuracy curve
- `loss_graph.png` — training and validation loss curve
- `auc_graph.png` — training and validation AUC curve
- `confusion_matrix.png` — confusion matrix heatmap
- `classification_report.json` — scikit-learn classification report
- `evaluation_metrics.json` — detailed metrics and confusion matrix
- `model_summary.txt` — CNN architecture summary
- `dog_cat_cnn_final.keras` — saved trained model
- `best_dog_cat_cnn.keras` — best model checkpoint
- `configuration.json` — experiment configuration metadata

## Repository Contents

- `cadog_classi_proj.py` — main training and evaluation script
- `README.md` — project documentation
- `outputs/` — generated results and saved model artifacts

## Example Interpretation

A strong model for this task should achieve:
- high accuracy
- high precision and recall
- high AUC
- low false positive and false negative rates
- strong MCC and balanced accuracy

## Usage

Run the model script from the repository root:

```bash
python cadog_classi_proj.py
```

Make sure the required Python dependencies are installed, including:
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- kagglehub

## Summary

This project demonstrates a practical end-to-end deep learning workflow for image classification using CNNs. It combines training, evaluation, visualization, and artifact saving into a reproducible experiment for cat-vs-dog detection.
