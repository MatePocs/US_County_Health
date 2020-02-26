# Analysis of Mental Health Indicators in USA (2019)

Collaborators: Mate Pocs & Song Ying

__Executive Summary__: Analyzing the most influential variables to predict the prevalence of mental health issues in USA.

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

__Methodology__: This project uses Python 3, documented with Jupyter Notebook. We used a combination of Numpy, Pandas and StatsModels for data cleaning, filtering and feature engineering. ScikitLearn was used for preprocessing, model selection and model performance analysis. Matplotlib & Seaborn were both used for Visualizations. 1000 data samples were allocated for testing. K-fold (5-fold) cross-validation technique was used for our train and validation data during individual model analysis.

__High Level Overview__: The project started by identifying relevant metrics to our target variable, namely Poor Mental Health Days, which describes the average number of poor mental health days per month. The relevant metrics are then filtered by checking its multicollinearity with Variance Inflation Factor. After data cleaning, a baseline model was created for comparison with future adjusted models. Interactions and Polynomials Features were added to improve model performance. A high complexity model was created by including both interaction features and high degree of polynomial features, which resulted in an overfitted model. We then used regularization techniques like Lasso & Ridge method to reduce overfitting of the model while improving respective model performance during cross-validation. Residual Homoscedasticity & Normality Tests were conducted on the final model, which was then applied onto the test data. Finally, we interpretted the test results and formulated actionable insights from the analysis.

__Files__:
- <code>index.ipynb</code> : main Jupyter Notebook
- <code>analytic_data_2019.csv</code> : input data 
- <code>data_linreg.csv</code> : data cleaned and ready for linear regression
- <code>us_county.py</code> : contains dictionary for column renaming

__Limitations__:
1. During our preliminary feature selection, we removed several variables with high levels of multicollinearity but remaining variables still possess relatively high VIF figures.
2. Our final model consists of many variables after few rounds of screening and filtering, currently at around 100 predictive variables, including interaction and polynomial features, which we aim to cut down for future work.
3. Scaling issues encountered with the addition of multiple polynomial features, as different model performance acquired before and after normalization of the train data.

__Future Work (Technical)__:
1. Additional Feature Selection to be conducted by detailed analysis of variable coefficients.
2. Scaling Issues to be investigated.
3. Prediction Function (Reverse Scaling) to be improved
4. Columns with too many missing values to be removed (Currently at a threshold of 10% of total data points)
5. Non-Linear Data Transformations like Log Transformation could be conducted to a few variables during Feature Engineering
6. Quantifying test results for homoscedasticity and normality 

__Future Work (External)__:
1. More relevant data like political and weather information to be added
2. Outsource missing data points from several states from external sources

__Outcomes__: 
<br>

One has to be careful when interpreting the outcome of a model like this. We can say that certain variables are a good predictor for other variables, but this does not necessarily mean that artificially changing them would also change the target variable. The causation could be reverse, or it could be tied to a third, perhaps external, unknown variable. When we say "improve" or "decrease" below, it is with understanding that we talk about the predictive powers of the variables, not necessarily the real-life implications. 

- We identified couple of variables, like insufficient sleep, physical inactivity, smoking, uninsured children, which have a high deteriorating effect on mental health. 
- On the positive side there are variables like going to college and having a large amount of social associations, these improve mental health.
- A number of variables were interactions, like excessive drinking, which in itself didn't have a large coefficient, but combined with other variables, it does. 
- The single most relevant variable (in the dataset that we kept, because remember, we excluded health-related variables) seems to be insufficient sleep. This variable shows up in many interactions, and has a very interesting polynomial shape. Higher insufficient sleep decreases mental health, but not in a linear shape, the effect is decreasing. 
<br>

__Actionable insights__: 
<br>

With keeping the precautions outlined in the paragraph above when it comes to interpreting results of regression models, we believe can still draw some insights from the model.
- Insufficient sleep is a very good indicator of mental health. It can be used as a good predictor for future mental health issues. If we assume there is some causation from sleep quality to mentahl health, mental health can be improved via awareness of this factor. Sleep quality can be improved to some extent via external economic factors, improving work-life balance, etc. 
- Smoking also highly correlates with mental health issues, which is a fact that could improve the effects of anti-smoking advertisements. 
