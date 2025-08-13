======================================================================= CASE STUDY: DATA CLEANING AND FEATURE ENGINEERING FOR THE TITANIC DATASET
This repository contains the code and summary for a case study on the Titanic dataset, conducted as part of the Intelligent Systems Laboratory at Birzeit University. The project demonstrates a comprehensive data preprocessing and model optimization pipeline.

--- ABSTRACT ---

The goal of this study is to implement and evaluate a full data preprocessing and model optimization pipeline on the Titanic dataset. The process involves several key stages: data cleaning, feature engineering, dimensionality reduction using Principal Component Analysis (PCA), and model validation.

The effectiveness of the pipeline was measured by training and comparing multiple classifiers. The models included a baseline Random Forest, a Random Forest on the fully preprocessed data, and optimized versions of both Random Forest and Support Vector Machine (SVM) models using GridSearchCV.

The results show that a tuned Support Vector Machine (SVM), trained on the preprocessed and lower-dimensional data, achieved a test accuracy of 81.56%. This performance is nearly on par with the 82.12% accuracy from the baseline model, which used a more complex feature set. This demonstrates that a systematic preprocessing and tuning pipeline can produce a simpler, more efficient model with comparable predictive power.

--- METHODOLOGY PIPELINE ---

The experiment follows a systematic data preprocessing and modeling pipeline, which is fully implemented in the CaseStudy1.ipynb Jupyter Notebook.

Data Loading and EDA: The Titanic dataset is loaded, and an initial exploratory data analysis is performed to identify issues like missing values.

Data Cleaning:

The deck column is dropped due to a high number of missing values.

Missing age values are imputed with the median.

Missing embarked values are imputed with the mode.

Outliers in the fare feature are managed by capping extreme values using the Interquartile Range (IQR) method.

Feature Engineering and Selection:

Redundant features (alive, class, embark_town, who, adult_male, alone) are removed.

Categorical features (sex, embarked) are encoded into a numerical format.

Numerical features are scaled using StandardScaler.

Dimensionality Reduction:

Principal Component Analysis (PCA) is applied to reduce the feature space from 8 to 6 components while retaining 95% of the data's variance.

Model Training and Validation:

The dataset is split into training and testing sets.

Four models are trained and evaluated for comparison:

A baseline Random Forest on minimally processed data.

A standard Random Forest on the fully preprocessed data.

A tuned Random Forest using GridSearchCV.

A tuned Support Vector Machine (SVM) using GridSearchCV.

--- RESULTS ---

The analysis identified gender, passenger class, and fare as the most significant predictors of survival. The final performance comparison of all models is summarized below:

+--------------------------------+----------+---------------------+
| Model                          | Accuracy | Weighted F1-Score   |
+--------------------------------+----------+---------------------+
| Baseline RF                    | 0.8212   | 0.82                |
| Tuned SVM (with PCA)           | 0.8156   | 0.81                |
| Tuned RF (with PCA)            | 0.8045   | 0.80                |
| Preprocessed RF (with PCA)     | 0.7989   | 0.80                |
+--------------------------------+----------+---------------------+

--- CONCLUSION ---

The data preprocessing pipeline was highly effective. While the baseline Random Forest model achieved the highest accuracy, the tuned SVM model performed nearly as well on a simpler, lower-dimensional dataset. This outcome highlights the importance of a thorough preprocessing workflow and demonstrates a successful balance between model performance and complexity.

--- HOW TO USE ---

To run this analysis, you will need a Python environment with Jupyter Notebook and the following libraries installed:

pandas

seaborn

matplotlib

scikit-learn

Clone or download this repository.

Open the CaseStudy1.ipynb file in Jupyter Notebook or JupyterLab.

Run the cells sequentially to execute the entire data analysis and modeling pipeline.
