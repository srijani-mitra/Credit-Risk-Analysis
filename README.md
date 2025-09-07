# Credit-Risk-Analysis

**Project Overview**
This project provides a comprehensive analysis of the bankloans.csv dataset to predict customer loan default. It explores two distinct methodologies for handling missing values in the target variable (default), develops and compares three machine learning models, and begins with a thorough Exploratory Data Analysis (EDA) to uncover underlying patterns in the data. The primary goal is to build a reliable predictive tool that can help financial institutions mitigate credit risk.

**1. Exploratory Data Analysis (EDA)**
Before modeling, an EDA was conducted to understand the relationships between different customer attributes and the likelihood of default. Key visualizations included:

Income and Debt-to-Income Ratio vs. Age: Line plots were used to visualize how income and debt-to-income ratios change across different age groups.

Income Distribution: A histogram revealed the distribution of customer incomes, showing the frequency of different income brackets.

Income vs. Default: A box plot was used to compare the income distributions of customers who defaulted versus those who did not. This helps to see if income level is a significant factor in defaulting.

Debt-to-Income Ratio vs. Default: A second box plot compared the debt-to-income ratios for both default outcomes, highlighting its potential as a strong predictor.

**2. Methodology & Modeling Approaches**
A key challenge in the dataset was the presence of 450 rows with a missing default status. This project investigates two distinct strategies to handle this:

Approach A: Modeling on Labeled Data Only (Dropping NA)
This approach follows a standard supervised learning workflow where any rows with missing target variables are removed. The remaining 700 complete records are used to train and evaluate the models, providing a baseline performance on high-quality data.

Approach B: Predictive Imputation for Unlabeled Data
This methodology preserves all 1150 records. The 700 labeled rows are used for training and testing, and the resulting trained models are then used to predict the default status for the 450 unlabeled rows. This approach creates a complete dataset with imputed target values for further analysis.

**3. Model Implementation & Evaluation**
For both approaches, the following steps were taken:

Feature Scaling: All predictor variables were standardized using StandardScaler to ensure that features with larger numeric ranges do not disproportionately influence model performance.

Model Training: Three different classification algorithms were trained and evaluated separately:

Logistic Regression: A baseline model valued for its interpretability. The model's coefficients were analyzed to understand the key drivers of default, and its performance was visualized with a confusion matrix heatmap.

Support Vector Machine (SVM): An advanced model whose performance was systematically optimized by tuning hyperparameters (C, gamma) using GridSearchCV with 10-fold cross-validation.

Random Forest Classifier: A powerful ensemble model whose stability and performance were robustly assessed using a 5-fold cross_val_score.

**4. Technologies Used**
Python 3

Pandas: For data manipulation and analysis.

Scikit-learn: For implementing all machine learning models, preprocessing, and evaluation metrics.

Matplotlib & Seaborn: For all data visualizations, including the EDA plots and the confusion matrix heatmap.

**6. Results & Findings**
The performance of the three models was compared based on their accuracy on the held-out test set from the labeled data in both Approach A and Approach B

Logistic Regression Accuracy: 85.71% in A ,81.43% in B

Tuned SVM Accuracy: 83.57% in A ,83.57% in B

Random Forest Accuracy: 78.21% in A, and 82.86% in B
