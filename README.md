# Credit Score Prediction Project

This project demonstrates the process of building a machine learning model to predict credit scores. It includes data loading, exploration, preprocessing, training multiple classification models, evaluating their performance, and selecting the best model for prediction.

## Table of Contents

- [Project Description](#project-description)
- [Dataset](#dataset)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [Models Used](#models-used)
- [Evaluation](#evaluation)
- [Saving and Loading Models](#saving-and-loading-models)
- [Making Predictions](#making-predictions)

## Project Description

The goal of this project is to predict an individual's credit score based on various features. The process involves:
1. Loading and exploring the credit data.
2. Preprocessing the data, including handling categorical and numerical features, imputation, and scaling.
3. Training and evaluating several classification models:
    - Logistic Regression
    - Random Forest Classifier
    - Support Vector Machine (SVC)
4. Comparing the performance of the models using metrics like accuracy, classification report, ROC AUC score, and confusion matrix.
5. Identifying the best-performing model based on ROC AUC score.
6. Optionally, performing hyperparameter tuning on the best model (specifically shown for Random Forest in the provided code).
7. Saving the best-performing model for future use.
8. Demonstrating how to load the saved model and make predictions on new data.

## Dataset

The project uses a credit data dataset. This dataset should be an Excel file named `credit_data.xlsx` and is expected to be in the `/content/sample_data/` directory when running in a Colab environment or in the appropriate path in a local setup. The dataset includes features related to credit history, personal information, and financial details, with the target variable being 'creditScore'.

## Dependencies

The project requires the following libraries:

- pandas
- scikit-learn (sklearn)
- joblib
- IPython (for display and get_ipython - typically included in Colab/Jupyter)

You can install the required libraries using pip:
Use code with caution
bash pip install pandas scikit-learn joblib

## Usage

1. **Clone the repository:**
Use code with caution
bash git clone

2. **Place the dataset:** Ensure `credit_data.xlsx` is in the correct directory as expected by the code (e.g., `/content/sample_data/` if running in Colab).
3. **Run the notebook:** Execute the cells in the provided Jupyter Notebook or Python script sequentially.

The code will perform the following steps:
- Load and display information about the data.
- Define preprocessing pipelines for numerical and categorical features.
- Split the data into training and testing sets.
- Train and evaluate Logistic Regression, Random Forest, and SVC models.
- Compare model performance and identify the best model.
- (If Random Forest is the best) Perform hyperparameter tuning on the Random Forest model.
- Save the best-performing model.
- Demonstrate how to make predictions on new data.

## Models Used

- **Logistic Regression:** A linear model for binary classification.
- **Random Forest Classifier:** An ensemble learning method that builds multiple decision trees.
- **Support Vector Machine (SVC):** A model that finds an optimal hyperplane to separate classes.

## Evaluation

The models are evaluated using the following metrics:

- **Accuracy:** The proportion of correctly classified instances.
- **Classification Report:** Provides precision, recall, f1-score, and support for each class.
- **ROC AUC Score:** Measures the area under the Receiver Operating Characteristic curve, indicating the model's ability to distinguish between classes.
- **Confusion Matrix:** A table summarizing the performance of a classification algorithm.

The best model is selected based on the highest ROC AUC score on the test set.

## Saving and Loading Models

The best-performing model is saved to a file using the `joblib` library. This allows you to reuse the trained model without retraining. The filename is generated based on the best model's name.

To load a saved model:
Use code with caution
python import joblib

loaded_model = joblib.load('path/to/your/saved_model.joblib')

## Making Predictions

The notebook includes an example of how to use the trained model to predict credit scores for new, unseen data. The new data must be in a pandas DataFrame with the same column names as the training data. The same preprocessing steps applied to the training data are applied to the new data before making predictions.
