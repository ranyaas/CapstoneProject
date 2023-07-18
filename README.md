# Credit Card Fraud Detection

![Chartered Professional Accountants of Canada. (2023, February 15). Unlikely targets: More young Canadians report being a victim of financial fraud than older Canadians: CPA Canada survey reveals. Cpacanada.ca.](https://www.cpacanada.ca/-/media/site/operational/mr-media-releases/images/2023-02-15-mr.jpg)
> Image Source: Chartered Professional Accountants of Canada. (2023, February 15). Unlikely targets: More young Canadians report being a victim of financial fraud than older Canadians: CPA Canada survey reveals. Cpacanada.ca. https://www.cpacanada.ca/en/the-cpa-profession/about-cpa-canada/media-centre/2023/february/cpa-canada-fraud-survey-2023 

## Project Overview

Credit card fraud, an event where an individual uses a stolen credit card or information to make unauthorized purchases (Rafter, 2017) is an ever increasing problem that can happen to anyone at any point in time as we progress towards a technologically advanced society. With roughly 76.2 million Visa and MasterCard credit cards in circulation (Canadian Bankers Association, 2023) and its number continuing to increase, this project investigates and addresses the occurrence of fraudulent transactions using a highly imbalanced dataset while comparing different classification models along with their performances in Python. Some of the research questions under consideration include what resampling technique is more suitable for creating the fraud detection model, what are the best features that better predict fraudulent transactions, and whether the classification models perform better with or without outliers present. As for the classification algorithms, the project will compare three supervised models, namely logistic regression, decision tree, and k nearest neighbor using Python’s Sklearn package.

### Motivation for Project

Though there have been a number of models proposed to better detect credit card fraud, fraudsters are developing and improving their ways to retrieve people’s credit card information. As a matter of fact, as more models become outdated, the increase in opportunities there are for fraudsters to crack the code and eventually make it easier for them to commit fraud. Therefore, models need to be updated routinely to adapt to the different forms of fraud. 

The research questions that will be addressed in this project are as follows and may be subjected to change: 

  1. Knowing that there does exist a bias towards non-fraudulent transactions, what sampling technique will perform better for creating a more accurate fraud detection model? 
  2. In relation to the first research question, will the models perform better when outliers are present and transformed, or when no outliers exist?
  3. What are the essential features that aid in classifying and differentiating what is a legitimate transaction or a fraudulent transaction?

### Challenges
In most credit card datasets that are publicly available, including the dataset used for this project, there exists critical problems when creating an appropriate fraud detection model. These include: 
  - **_Class imbalance_**: Most observations in the data are classified as legitimate transactions which consist of the majority class while the remaining few are fraudulent transactions, where that makes up the minority class. The problem that will arise from this are inaccurate classification models that are biased towards the majority class if no resampling techniques are implemented.
  - **_Skewness of data_**: A significant number of attributes in the dataset are very skewed, indicating the presence of outliers that can affect model performance and statistical analysis 
  
With this in mind, the proposed steps showcases my overall methodology in which it will aim to overcome these obstacles. 

## Methodology 
### Dataset 
The dataset used is a [Credit Card Transactions Fraud Detection Dataset](https://www.kaggle.com/datasets/kartik2112/fraud-detection) from Kaggle.


### Summary of Steps 
Before reading in the data into the machine learning algorithms for modelling, a number of steps such as data preparation/cleaning and data preprocessing are performed. Below lists and summarizes some of the important steps that will be taken:  
  - _Data cleaning / Feature engineering_: This includes the conversion to the appropriate data types of variables that are incorrectly assigned to the wrong data type, identifying missing values and dealing with outliers, creating additional features from existing variables, and dropping redundant variables that are not necessary for analysis.
  - _Exploratory Data Analysis (EDA)_: Performing univariate analysis by examining the distributions of variables in the form of plots (e.g. bar and pie charts, box plots), performing bivariate analysis with the target variable “is_fraud” to examine the occurrence of fraud through different predictor variables (e.g. fraud by gender, fraud by age, etc.). After obtaining a better understanding of the data, the data cleaning stage will be returned to as further changes and transformations may be needed to proceed to the next stages.
  - _Data preprocessing_: In this stage, categorical attributes will be converted into a numerical format through one-hot encoding to create ease for the machine learning algorithms to process the data. Furthermore, I will scale and transform the dataset using RobustScaler, which relies on the interquartile range rather than the median for scaling the numeric attributes, in order to handle outliers as it will negatively influence my results. Next, I will create a duplicate of the dataset where the outliers will be dropped based on whether the observations are outside of the 25th or 75th quantile range. Moreover, the numeric features will then be normalized using MinMax scalar in order to scale the values within the 0 to 1 range. This is done in order to identify whether the models perform better with the outliers transformed or without outliers present when applying resampling techniques along with the three machine learning algorithms. Then, the data will be split using 70% of the observations for training and the remaining 30% for testing. Resampling techniques that will be examined are undersampling, oversampling, and SMOTE. Whereas for the machine learning algorithms selected, the project will use logistic regression, decision tree, and random forest. In order to prevent data leakage, pipelines will be created containing the resampling technique and the machine algorithm used. For feature selection, this project will use a wrapper algorithm, known as recursive feature elimination with cross validation (RFECV), to create a subset of the optimum features in the dataset using the training data. This step will be done after examining the baseline models.
  - _Data modelling_: To evaluate the models, I will be cross validating the training data using stratified k-fold as I want to maintain the class distribution for each fold. A list of parameters of the machine learning algorithms will be selected in order to perform a grid search to identify the appropriate parameter to use for modelling. Essentially, I will use RandomizedSearchCV with the pipeline as my estimator to select the best model for detecting fraud, and this will be fitted with the training data.
  - _Performance_: This stage I will be evaluating the test set on the models by using performance metrics such as accuracy, recall, precision, and area under the curve (AUC) value. Note, more metrics will be considered as I progress through the project.

### Tools: Packages Used 
- [Pandas](https://pandas.pydata.org/about/index.html) : Package mainly used for data analysis
- [NumPy](https://numpy.org/doc/stable/user/whatisnumpy.html) : Package to compute mathematical operations for arrays
- [Scikit-Learn (Sklearn)](https://scikit-learn.org/stable/) : Package for machine learning
- [imblearn](https://imbalanced-learn.org/stable/) : Package offering tools for balancing datasets, also part of Scikit-Learn package
- [matplotlib](https://matplotlib.org/) : Data visualization package
- [Seaborn](https://seaborn.pydata.org/#:~:text=Seaborn%20is%20a%20Python%20data,attractive%20and%20informative%20statistical%20graphics.) : Based on matplotlib, another data visualization package

## What is in this Repository 
In this repository, my initial and final code is posted as a Jupyter Notebook and in PDF format demonstrating my efforts. 


## References

Canadian Bankers Association . (2023, March 31). Focus: Credit Cards: Statistics and Facts. Cba.ca. https://cba.ca/credit-cards

Rafter, D. (2017, September 14). What Is Credit Card Fraud? LifeLock by Norton. https://lifelock.norton.com/learn/fraud/what-is-credit-card-fraud 

