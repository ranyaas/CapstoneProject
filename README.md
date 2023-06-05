# CapstoneProject: Credit Card Fraud Detection
With more consumers shifting to alternative forms of payment beyond cash, the adoption of the use of credit cards continues to increase at a rapid pace. In Canada alone, there are “76.2 million Visa and MasterCard cards in circulation” (Canadian Bankers Association, 2023). Though most credit cards come with their advantages ranging from cash back and rewards to easier and faster transactions, they too possess significant risk for consumers. Such risk is the increased exposure to credit card fraud. By definition, credit card fraud occurs when either a person steals or uses without permission a person's credit card or credit card information (Government of Canada, 2023). In fact, the Chartered Professional Accounts of Canada (CPA) found that 3 in 5 individuals between the ages 18-34 years have reported being a victim of at least one form of financial fraud (Chartered Professional Accountants Canada, 2023). Knowing this, especially at a time when data is easily and widely accessible and exchanged, how can financial institutions utilize such information to its optimum to create models that are able to detect and minimize the risk of credit card fraud for their customers? Using a credit card fraud dataset containing 1,296,675 observations and 23 features, published by Shenoy (2019) on Kaggle, this project strives to address and explore the occurrence of fraud while providing a sufficient model to classify whether a transaction is fraudulent or not in Python. Moreover, this project will follow similarly to Afriyie et al. (2023) as the authors utilize the same data set and similar approaches. Some of the key research questions under consideration include where and how credit card frauds happen more frequently, what sampling technique works best for creating a fraud detection model, and what are the best features that can better predict credit card fraud. With respect to the nature of the subject, classification will be the theme of this task, as the key objective is primarily to predict the correct label for fraud as accurately as possible given the training data. For context, classification is a supervised machine learning approach in which the model attempts to predict the appropriate label for a given set of data and is trained using the training set, where it is then evaluated on the testing set (Keita, 2022). Some of these approaches include logistic regression, decision tree, and k nearest neighbour (KNN) and these will be the three algorithms used and compared against using Python’s sklearn package to identify the appropriate model. Moreover, techniques for balancing the dataset and feature selection will be considered.




References

Afriyie, J. K., Tawiah, K., Pels, W. A., Addai-Henne, S., Dwamena, H. A., Owiredu, E. O., ... & Eshun, J. (2023). A supervised machine learning algorithm for detecting and predicting fraud in credit card transactions. Decision Analytics Journal, 6, 100163.

Canadian Bankers Association . (2023, March 31). Focus: Credit Cards: Statistics and Facts. Cba.ca. https://cba.ca/credit-cards

Chartered Professional Accountants of Canada. (2023, February 15). Unlikely targets: More young Canadians report being a victim of financial fraud than older Canadians: CPA Canada survey reveals. Cpacanada.ca. 

Government of Canada. (2023). Credit card fraud . Canada.ca. https://www.canada.ca/en/financial-consumer-agency/services/credit-fraud.html 

Keita, Z. (2022, September 21). Classification in Machine Learning: An Introduction. Datacamp.com; DataCamp. https://www.datacamp.com/blog/classification-machine-learning 

Shenoy, K. (2019). Credit Card Transactions Fraud Detection Dataset. Kaggle.com. https://www.kaggle.com/datasets/kartik2112/fraud-detection
