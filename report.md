# Loan Prediction Report

## Objective

The goal of this task was to use machine learning to predict if a loan application will be approved or rejected.

## Dataset

I used a dataset from Kaggle that contains two files:

- train.csv: 614 rows and 13 columns.
- test.csv: 367 rows and 12 columns.

The column I wanted to predict was Loan_Status. Y means approved and N means rejected.

## Data Preparation

First, I checked the dataset to understand the columns and find missing values.

I noticed that some columns had missing values, especially Credit_History.

To prepare the data, I did the following:

- Removed Loan_ID because it is just an application number.
- Filled missing numerical values using the median.
- Filled missing categorical values using the most common value.
- Converted text values into numbers using One-Hot Encoding.
- Used StandardScaler to scale the numerical values.
- Changed Y to 1 and N to 0.

I used a Pipeline to apply the same preparation steps to the different datasets and avoid data leakage.

## Model Training

I divided the training data into 80% for training and 20% for validation.

I tried three models to see which one would give better results:

- Logistic Regression
- Decision Tree
- Random Forest

I used a maximum depth of 5 for Decision Tree to reduce overfitting and 100 trees for Random Forest.

## Evaluation

I compared the models using accuracy, precision, recall, and F1 Score.

I also used a confusion matrix to see where the model made mistakes.

## Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 86.18% | 84.00% | 98.82% | 90.81% |
| Decision Tree | 82.11% | 82.47% | 94.12% | 87.91% |
| Random Forest | 82.11% | 84.62% | 90.59% | 87.50% |

Logistic Regression gave the highest accuracy and F1 Score, so I chose it as the final model.

## Prediction

After choosing Logistic Regression, I trained it again using all 614 training records.

Then I used it to predict the loan status for the 367 applications in the test file and saved the predictions in a CSV file.

## Limitations

The dataset has more approved loans than rejected loans. This may affect the model's ability to predict rejected applications.

I also could not check the accuracy of the final predictions because the test file does not have the actual loan status.

## Conclusion

Logistic Regression gave the best validation accuracy of 86.18%.

From this task, I learned how to prepare a dataset, handle missing values, train different machine learning models, compare their results, and make predictions on new data.

I also learned that a more complicated model does not always give better results.

## Dataset Source

https://www.kaggle.com/datasets/altruistdelhite04/loan-prediction-problem-dataset