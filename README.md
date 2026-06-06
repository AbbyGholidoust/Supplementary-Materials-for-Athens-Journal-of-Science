# Supplementary-Materials-for-Athens-Journal-of-Science
Whether AI Has a Negative Impact on Education in 2025
Project Overview
This project uses a machine learning workflow to predict whether AI has a negative impact on higher education in 2025. The analysis is implemented in a Jupyter Notebook and uses a prepared dataset containing yearly indicators related to AI, education, academic dishonesty, and other higher education variables.
The notebook applies data preprocessing, bootstrapping, Random Forest classification, cross-validation, correlation analysis, and a final prediction for the 2025 record.

Citation

If you use this code, dataset preparation workflow, methodology, or results in your research, please cite the associated paper:

Gholidoust, A., & Wang, P. (2026). Analysis of the Relationship between AI Advancement and Employment Dynamics in Canadian Higher Education. Athens Journal of Sciences.

Files
`11Whether\_AI\_Has\_a\_Negative\_Impact\_on\_Education\_in\_2025.ipynb`  
Main Jupyter Notebook containing the full analysis and model workflow.
`DataPreparationforPrediction.csv`  
Input dataset required by the notebook. This file must be uploaded or placed in the correct working directory before running the notebook.

Dataset Requirement
The notebook expects a CSV file named:
```text
DataPreparationforPrediction.csv
```
In Google Colab, the current file path used in the notebook is:
```python
/content/DataPreparationforPrediction.csv
```
If you run the notebook locally, update the file path as needed, for example:
```python
file\_path = "DataPreparationforPrediction.csv"
```
The dataset must include the target column:
```text
Whether AI has a Negative Impact on Education
```
The dataset also uses other numerical or categorical indicators as model features. Missing values are handled using mean imputation in the main model workflow.

Main Methodology
The notebook follows these steps:
Import libraries  
The analysis uses `pandas`, `numpy`, and several modules from `scikit-learn`.
Load the dataset  
The dataset is loaded from a CSV file.
Prepare the target variable  
Rows with missing target values are removed. The target variable, `Whether AI has a Negative Impact on Education`, is encoded into numerical labels.
Prepare feature variables  
Feature columns are selected from the dataset, excluding the year and target-related columns. Non-numeric columns are label-encoded.
Handle missing values  
Missing feature values are replaced using mean imputation.
Standardize features  
Features are standardized using `StandardScaler`.
Train Random Forest models with bootstrapping  
The notebook creates 100 bootstrap samples and trains a `RandomForestClassifier` on each sample.
Evaluate model performance  
Model performance is evaluated using:
Bootstrap mean accuracy
5-fold stratified cross-validation accuracy
Classification report
Predict the 2025 outcome  
The final row of the dataset is treated as the 2025 observation. The model predicts whether AI has a negative impact on higher education for that year.
Correlation analysis  
The notebook also calculates correlations between the target variable and other variables in the dataset.
Bootstrap sample inspection  
The final section demonstrates how bootstrap sample indices may be generated for trees in a Random Forest model.


Required Libraries
Install the required Python packages before running the notebook:
```bash
pip install pandas numpy scikit-learn
```
If using Google Colab, these packages are usually already installed.


How to Run
Open the notebook in Jupyter Notebook, JupyterLab, or Google Colab.
Upload or place `DataPreparationforPrediction.csv` in the correct directory.
Check that the file path in the notebook matches the dataset location.
Run the notebook cells in order.
Review the printed outputs:
Bootstrap Mean Accuracy
Cross-Validation Mean Accuracy
Classification Report
Predicted 2025 result
Expected Output
The notebook prints model evaluation results similar to:
```text
Bootstrap Mean Accuracy: ...
Cross-Validation Mean Accuracy: ...
Classification Report:
...
Whether AI Has a Negative Impact on Higher Education: ...
```
The exact values depend on the dataset and model training results.

Notes and Limitations

The notebook assumes the final row of the dataset represents the 2025 observation.
The model uses Random Forest classification, which can perform well on small or structured datasets but may overfit if the dataset is limited.
The use of bootstrapping and cross-validation helps evaluate model stability, but results should still be interpreted carefully.
Label encoding is used for categorical variables. For some datasets, one-hot encoding may be more appropriate.
The correlation analysis converts selected categorical target variables into binary values and fills missing values with zero, which may influence correlation results.
The final bootstrap inspection section is illustrative and manually generates bootstrap indices rather than extracting the actual samples used inside each trained Random Forest tree.

Project Purpose
This notebook supports research into whether AI may have a negative impact on higher education in 2025. It combines predictive modelling and exploratory correlation analysis to examine the relationship between AI-related indicators and educational outcomes.

Author

Prepared for academic/research use.
