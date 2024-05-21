# Housing Price Prediction Assignment

## Introduction
A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them at a higher price. For this purpose, the company has collected a dataset from the sale of houses in Australia. The goal is to build a regression model using regularization to predict the actual value of prospective properties and decide whether to invest in them or not.

## Business Goal
The objective is to model the price of houses with the available independent variables. This model will help the management understand how the prices vary with the variables, allowing them to manipulate the strategy and focus on areas yielding high returns. Additionally, the model will provide insights into the pricing dynamics of a new market.

## Methodology
1. **Data Preprocessing**
   - Handling missing values by imputing median for numerical columns and 'None' for categorical columns.
   - Encoding categorical variables using one-hot encoding.
   - Scaling features using MinMaxScaler.
   - Splitting the data into training and testing sets.

2. **Model Building**
   - **Linear Regression**: Built a basic linear regression model with Recursive Feature Elimination (RFE).
   - **Ridge Regression**: Applied Ridge regression with cross-validation to determine the optimal value of alpha.
   - **Lasso Regression**: Applied Lasso regression with cross-validation to determine the optimal value of alpha.

3. **Evaluation Metrics**
   - Evaluated the models using R2 Score, RSS (Residual Sum of Squares), and MSE (Mean Squared Error) on both training and testing sets.

## Results

### Linear Regression
| Metric              | Value                |
|---------------------|----------------------|
| R2 Score (Train)    | 0.75                 |
| R2 Score (Test)     | 0.62                 |
| RSS (Train)         | 1,736,000,291,646.84 |
| RSS (Test)          | 856,453,961,018.30   |
| MSE (Train)         | 38,552.58            |
| MSE (Test)          | 54,157.75            |

### Ridge Regression
| Metric              | Value                |
|---------------------|----------------------|
| R2 Score (Train)    | 0.90                 |
| R2 Score (Test)     | 0.87                 |
| RSS (Train)         | 729,049,310,188.63   |
| RSS (Test)          | 292,067,677,438.38   |
| MSE (Train)         | 24,983.72            |
| MSE (Test)          | 31,626.44            |

### Lasso Regression
| Metric              | Value                |
|---------------------|----------------------|
| R2 Score (Train)    | 0.89                 |
| R2 Score (Test)     | 0.88                 |
| RSS (Train)         | 763,423,313,686.70   |
| RSS (Test)          | 272,954,682,056.98   |
| MSE (Train)         | 25,565.91            |
| MSE (Test)          | 30,574.11            |

## Key Findings
1. **Optimal Alpha Values**:
   - Ridge Regression: Optimal alpha is determined through cross-validation.
   - Lasso Regression: Optimal alpha is determined through cross-validation.

2. **Choosing Between Ridge and Lasso**:
   - Based on the evaluation metrics, Lasso Regression is chosen because it provides the best balance of high explanatory power (R2 Score) and low prediction error (MSE and RSS) on the test set, making it more robust and reliable for new, unseen data.

3. **Excluding Top 5 Lasso Features**:
   - After excluding the top 5 most important predictor variables identified by Lasso Regression, a new model is built to identify the next set of important features.

## Ensuring Model Robustness and Generalizability
1. **Cross-Validation**: Ensures the model performs well across different subsets of the data.
2. **Regularization**: Prevents overfitting by penalizing large coefficients.
3. **Feature Selection**: Improves model interpretability and performance on unseen data.
4. **Hyperparameter Tuning**: Balances bias and variance, leading to better generalization.
5. **Model Evaluation**: Provides an unbiased estimate of the model's performance on new data.

## Conclusion
The Lasso Regression model, with its optimal alpha value, has been selected as the best model for predicting housing prices in the Australian market. This model provides a robust and generalizable solution, balancing high accuracy and reliability for prospective property investments.

## Repository Structure
- `Assignment.ipynb`: Jupyter notebook containing the complete analysis and model building process.
- `train.csv`: Dataset used for training the models.
- `preprocessed_train.csv`: Preprocessed dataset.
- `README.md`: This file, providing an overview of the assignment and results.

## Usage
1. Clone the repository.
2. Open the `Assignment.ipynb` notebook.
3. Run the cells to reproduce the analysis and results.

```sh
git clone <repository_url>
cd <repository_directory>
jupyter notebook Assignment.ipynb

