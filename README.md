# Multimodal Hybrid Deep Learning for Wheat Grain Yield Prediction

This repository contains the custom Python and R scripts, processed training datasets, and cross-validation folds used in the study: **"Improving genomic in wheat using a multimodal hybrid convolutional deep learning approach"**, submitted to *G3: Genes | Genomes | Genetics*.

## Overview
We propose a specialized modular multimodal hybrid deep learning architecture designed to predict wheat grain yield by integrating three complementary data modalities:
*   **AO (Pedigree):** Orthogonal additive relationship matrix processed via a Deep Learning Neural Network (DLNN).
*   **SNP (Genomic):** Additively encoded molecular markers processed via a One-Dimensional Convolutional Neural Network (1D-CNN) to capture local structural patterns.
*   **DM6 (Phenomic):** PCA-derived temporal multispectral features from six developmental stages processed via a DLNN.

The model utilizes independent branch pretraining with frozen weights prior to late fusion, ensuring robust feature extraction without data leakage.

## Repository Structure

*   `data_train/`: Contains the processed datasets required to reproduce the models.
    *   `AO.csv`: Orthogonal pedigree relationships.
    *   `SNP.csv`: Additively encoded molecular markers.
    *   `DM6.csv`: PCA-derived temporal multispectral features.
    *   `CV_folds.csv`: Explicit 5-fold cross-validation assignments to ensure exact reproducibility.
*   `src/`: Source code for the models and analyses.
    *   `HA_AO_SNP_DM6.py`: Architecture definition and training loops for the DLNN-AO + 1D-CNN-SNP + DLNN-DM6 model.
    *   `BLUP_RKHS`: R scripts for the conventional multimodal baselines (BLUP and RKHS).


## Data Availability
The raw datasets are available from the corresponding author upon reasonable request. All processed data required to train and evaluate the models described in the manuscript are fully provided in the `data_train/` directory.

## Requirements
*   Python 3.8+
*   TensorFlow / Keras
*   Optuna
*   Scikit-learn, Pandas, NumPy
*   R (for baseline linear/kernel models)
