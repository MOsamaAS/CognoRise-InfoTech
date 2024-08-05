# Lung Disease Classification Model

## Overview
This project aims to develop a deep learning model for classifying lung diseases from X-ray images. The model distinguishes between Normal, Viral Pneumonia, and COVID-19 cases using the ResNet50 architecture.

## Features

### Model Architecture
- **Base Model**: ResNet50 pre-trained on ImageNet.
- **Custom Layers**: Added GlobalAveragePooling2D, Dense layers, and Dropout for better generalization.
- **Output Layer**: Dense layer with softmax activation for multi-class classification.

### Data Preprocessing
- **Image Data Generator**: Utilized Keras' ImageDataGenerator for real-time data augmentation.
  - Rotation: `10 degrees`
  - Width and Height Shifts: `0.1`
  - Shear: `0.1`
  - Zoom: `0.1`
  - Horizontal Flip: `True`
  - Fill Mode: `nearest`

### Callbacks
- **Custom Model Checkpoint**: Saves the model based on both validation accuracy and loss, ensuring minimal overfitting. The model is saved only if validation accuracy is less than 95%.
- **Early Stopping**: Stops training when validation loss does not improve for a specified number of epochs.

### Evaluation Metrics
- **Accuracy**: Overall accuracy of the model on the test set.
- **Precision, Recall, F1-Score**: Calculated for each class.
- **Confusion Matrix**: Visual representation of the model's performance.
- **Macro and Weighted Averages**: Provided for precision, recall, and F1-score to offer a comprehensive evaluation.

### Visualization
- **Training History**: Plots of training and validation accuracy and loss.
- **Randomized Image Prediction**: Visualization of randomly selected images from the test set with their true and predicted labels.

### Data Export
- **Excel Export**: Training history, classification report (including macro and weighted averages), and evaluation metrics are exported to an Excel file for further analysis.

## Installation
To run this project, you need to have the following libraries installed:
- `tensorflow`
- `numpy`
- `pandas`
- `matplotlib`
- `sklearn`
- `openpyxl`

You can install these dependencies using pip:
```bash
pip install tensorflow numpy pandas matplotlib scikit-learn openpyxl
```
## Usage

### Prepare the Data
Ensure your dataset is organized with directories for training and validation, each containing subdirectories for each class.

### Train the Model
Run the training script to train the model on your dataset.

### Evaluate the Model
Use the evaluation script to generate accuracy, precision, recall, F1-score, and confusion matrix.

### Visualize Predictions
Use the visualization script to see true vs. predicted labels for random images from the test set.

### Export Data
Export training history and classification report to an Excel file.

## License

This project is licensed under the [Creative Commons Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)](https://creativecommons.org/licenses/by-nd/4.0/) license. You are free to use the code, but you must give appropriate credit, and you may not make any modifications to it.

