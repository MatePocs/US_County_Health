# Analysis of Mental Health Indicators in USA (2019)

Collaborators: Mate Pocs & Song Ying

Executive Summary: Analyzing the most influential variables to predict the prevalence of mental health issues in USA.

Using the dataset collected by the University of Wisconsin, we achieved the following:
1. Performed Data Cleaning & Feature Engineering
2. Created Baseline Model for Comparison
3. Analyzed Model Performance with addition of Interaction Features
4. Analyzed Model Performance with addition of Polynomial Features
5. Analyzed Model Performance of an Overfitted Model
6. Analyzed Model Performance with different regularization techniques:
    * Lasso
    * Ridge
7. Verified Model with Test Data
8. Interpretation of Results
9. Actionable Insights with Visualizations

Methodology: This project uses Python 3, documented with Jupyter Notebook. We used a combination of Numpy, Pandas and StatsModels for data cleaning, filtering and feature engineering. ScikitLearn was used for preprocessing, model selection and model performance analysis. Matplotlib & Seaborn were both used for Visualizations. 1000 data samples were allocated for testing. K-fold (5-fold) cross-validation technique was used for our train and validation data during individual model analysis.

High Level Overview: The project started by identifying relevant metrics to our target variable, namely Poor Mental Health Days, which describes the average number of poor mental health days per month. The relevant metrics are then filtered by checking its multicollinearity with Variance Inflation Factor. After data cleaning, a baseline model was created for comparison with future adjusted models. Interactions and Polynomials Features were added to improve model performance. A high complexity model was created by including both interaction features and high degree of polynomial features, which resulted in an overfitted model. We then used regularization techniques like Lasso & Ridge method to reduce overfitting of the model while improving respective model performance during cross-validation. Residual Homoscedasticity & Normality Tests were conducted on the final model, which was then applied onto the test data. Finally, we interpretted the test results and formulated actionable insights from the analysis.

Limitations:
1. During our preliminary feature selection, we removed several variables with high levels of multicollinearity but remaining variables still possess relatively high VIF figures.
2. Our final model consists of too many variables after few rounds of screening and filtering, currently at 100 predictive variables, including interaction and polynomial features, which we aim to cut down for future work.
3. Scaling issues encountered with the addition of multiple polynomial features, as different model performance acquired before and after normalization of the train data.

Future Work (Technical):
1. Additional Feature Selection to be conducted by detailed analysis of variable coefficients.
2. Scaling Issues to be investigated.
3. Prediction Function (Reverse Scaling) to be improved
4. Columns with too many missing values to be removed (Currently at a threshold of 10% of total data points)
5. Non-Linear Data Transformations like Log Transformation could be conducted to a few variables during Feature Engineering
6. Quantifying test results for homoscedasticity and normality 

Future Work (External):
1. More relevant data like political and weather information to be added
2. Outsource missing data points from several states from external sources
