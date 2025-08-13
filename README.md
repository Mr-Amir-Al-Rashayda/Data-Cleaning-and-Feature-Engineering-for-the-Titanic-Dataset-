# CASE STUDY: Data Cleaning and Feature Engineering for the Titanic Dataset

This repository contains the code and documentation for a case study conducted as part of the Intelligent Systems Laboratory at Birzeit University. The objective is to demonstrate a full data preprocessing and model optimization pipeline on the Titanic passenger dataset, culminating in a comparison of multiple classifiers.

---

## Table of Contents

1. [Abstract](#abstract)  
2. [Methodology Pipeline](#methodology-pipeline)  
3. [Repository Structure](#repository-structure)  
4. [Installation](#installation)  
5. [Usage](#usage)  
6. [Results](#results)  
7. [Conclusion](#conclusion)  
8. [Contact](#contact)  

---

## Abstract

The goal of this study is to implement and evaluate an end-to-end data preprocessing and model optimization pipeline on the Titanic dataset. Key stages include data cleaning, feature engineering, dimensionality reduction via Principal Component Analysis (PCA), and model validation. Four models were compared:

- Baseline Random Forest on minimally processed data  
- Random Forest on fully preprocessed data  
- Hyperparameter-tuned Random Forest  
- Hyperparameter-tuned Support Vector Machine (SVM)  

The tuned SVM, trained on the lower-dimensional feature set, achieved an accuracy of **81.56%**, closely matching the **82.12%** of the complex baseline model.

---

## Methodology Pipeline

The full workflow is implemented in `CaseStudy1.ipynb` and comprises:

1. **Data Loading & EDA**  
   - Inspect missing values and feature distributions  

2. **Data Cleaning**  
   - Drop the `deck` column due to high missingness  
   - Impute `Age` with median, `Embarked` with mode  
   - Cap `Fare` outliers using the IQR method  

3. **Feature Engineering & Selection**  
   - Remove redundant columns (`alive`, `class`, `embark_town`, `who`, `adult_male`, `alone`)  
   - One-hot encode categorical variables (`Sex`, `Embarked`)  
   - Scale numerical features with `StandardScaler`  

4. **Dimensionality Reduction**  
   - Apply PCA to reduce from 8 original features to 6 principal components (95% variance retained)  

5. **Model Training & Hyperparameter Tuning**  
   - Split data into training and test sets  
   - Train four models:  
     1. Baseline RF  
     2. Preprocessed RF  
     3. GridSearch-tuned RF  
     4. GridSearch-tuned SVM  

6. **Final Evaluation**  
   - Compare accuracy, precision, recall, and F1-scores on the held-out test set  

---

## Repository Structure

- `CaseStudy1.ipynb` — Jupyter Notebook with the full implementation  
- `CaseStudy1_1222596.pdf` — Written report and figures  
- `requirements.txt` — Project dependencies  
- `README.md` — This overview  

---

## Installation

Requires Python 3.8+. Install dependencies with:

```bash
pip install -r requirements.txt
