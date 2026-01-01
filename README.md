# Rabbit Classification Project

## Overview
This project focuses on the classification of rabbit subspecies, specifically the **Californian Rabbit**, using Deep Learning models. The project utilizes web scraping for data collection and implements various Convolutional Neural Network (CNN) architectures for image classification.

## Models
The following models were implemented and experimented with:
- **DenseNet**
- **MobileNetV3 (Small & Large)**

## Project Structure
- `project.ipynb`: The main Jupyter Notebook containing the data collection (web scraping), data preprocessing, model training, and evaluation code.
- `data/`: Directory containing the dataset (downloaded images).
- `tuner_results/`: Directory for hyperparameter tuning results.
- `*.h5`, `*.keras`: Saved trained models (e.g., `best_model.h5`, `best_mobilenetv3_model.keras`).
- `training_log.csv`: Logs of the training process.



## Code Explanation

### 1. Data Collection
Images of various rabbit breeds were downloaded from the web. The dataset consists of the following classes (breeds):
- `Belgian_Hare`, `Blanc_de_Bouscat`, `Dwarf_Hotot`, `German_Lop`, `Harlequin`, `Lionhead`, `Miniature_Lop`, `californian_rabbit`, `continental_giant_rabbit`, `thrianta`, etc.

### 2. Data Preprocessing & Augmentation
The image data is preprocessed and augmented using `ImageDataGenerator` to improve model generalization:
- **Rescaling**: 1./255 (Pixel values normalized to [0,1])
- **Augmentation (Training only)**:
    - Rotation range: 40 degrees
    - Width/Height shift: 0.2
    - Shear range: 0.2
    - Zoom range: 0.2
    - Horizontal flip: True
    - Fill mode: Nearest

### 3. Model Architectures
Two primary deep learning models were implemented and compared:

#### A. DenseNet121
- **Base Model**: DenseNet121 (Pre-trained on ImageNet, top layers excluded).
- **Custom Head**:
    - Global Average Pooling 2D
    - Batch Normalization
    - Dropout (0.5)
    - Dense Layer (256 units, ReLU activation)
    - Batch Normalization
    - Dropout (0.5)
    - Output Layer (Softmax activation for classification)
- **Optimizer**: Adam (Learning rate=0.002, epsilon=0.1)

#### B. MobileNetV3 (Small & Large)
- **Base Model**: MobileNetV3 (Small & Large versions, pre-trained on ImageNet).
- **Purpose**: Efficient models suitable for mobile or edge devices.

### 4. Training Configuration
- **Loss Function**: `categorical_crossentropy`
- **Metrics**: `accuracy`
- **Epochs**: 50
- **Callbacks**:
    - `ModelCheckpoint`: Saves the best model based on validation loss.
    - `CSVLogger`: Logs training metrics to a CSV file.

## Usage
1.  Install the required dependencies (see imports in `project.ipynb`).
2.  Run the cells in `project.ipynb` to execute the training pipeline.

