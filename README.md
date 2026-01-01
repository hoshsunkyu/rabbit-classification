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

## Authors
- **RAUDHATUL SAADAH BINTI ABDUL RAZAK** (52213122400)
- **PUTRI NURSYAZANA BINTI MUSTAFA KAMAL** (52213122010)
- **WAN NURUL EZZAH BINTI SAHARDI** (52213123227)

## Usage
1.  Install the required dependencies (see imports in `project.ipynb`).
2.  Run the cells in `project.ipynb` to execute the workflow.
