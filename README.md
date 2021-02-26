# Final-Project-Purwadhika-JCDS-1104-LoanPrediction

About
-------

Final Project for Job Connector Data Science Program at Purwadhika Digital School.

Home Equity Loan
Home equity loan—also known as an equity loan, home equity installment loan, or second mortgage—is a type of consumer debt. Home equity loans allow homeowners to borrow against the equity in their home. The loan amount is based on the difference between the home’s current market value and the homeowner’s mortgage balance due.



In this project, my role is as a data scientist at a company engaged in HMEQ services. I am asked by stakeholder in my company To find the best model. The best model as a predictor and identification tool quickly, precisely, and accurately, so that companies can minimize borrowers who fail to pay.


I use dataset HMEQ, you can get the data from <a href="http://www.creditriskanalytics.net/datasets-private2.html">link-dataset.</a>The data set HMEQ reports characteristics and delinquency information for 5,960 home equity loans. A home equity loan is a loan where the obligor uses the equity of his or her home as the underlying collateral. The data set has the following characteristics:

- BAD: 1 = applicant defaulted on loan or seriously delinquent; 0 = applicant paid loan
- LOAN: Amount of the loan request
- MORTDUE: Amount due on existing mortgage
- VALUE: Value of current property
- REASON: DebtCon = debt consolidation; HomeImp = home improvement
- JOB: Occupational categories
- YOJ: Years at present job
- DEROG: Number of major derogatory reports
- DELINQ: Number of delinquent credit lines
- CLAGE: Age of oldest credit line in months
- NINQ: Number of recent credit inquiries
- CLNO: Number of credit lines
- DEBTINC: Debt-to-income ratio


The project consisted of several steps including data preprocessing and exploratory data analysis, data visualization, and modelling.


Data Preprocessing
-------
In this step, I tried to clean the dataset from missing values, duplicate data, and some outliers. Missing value missing value is not droped but will be imputed with a certain strategy. for the details you can see <a href="https://github.com/ramzymohammad/Final-Project-Purwadhika-JCDS-1104-LoanPrediction/blob/main/CLEANING_DATA.ipynb">'Data Cleaning'</a>.



Exploratory Data Analysis
-------
This step, i'am asked find the some information from the dataset. I am looking for correlations between features, univariate analysis, bivariate analysis, and multivariate analysis. Furthemore you can access <a href="https://github.com/ramzymohammad/Final-Project-Purwadhika-JCDS-1104-LoanPrediction/blob/main/EDA_2.ipynb">'EDA'</a>.



Modelling
-------
This case is classified as a problem. I use 4 models benchmark:
- Logistic Regression
- K-Nearest Neighbor
- Decision Tree Classifier
- Random Forest Classifier



In this case, I have an imbalanced target variable so i will apply resampling to the models:
-ROS
-RUS
-SMOTE



Here are the evaluation metrics for different models with resampling:

 <center>
  
| Models                                                     |  CrossVal Score | 
|------------------------------------------------------------| :--------------:|
| RandomForest_benchmark_rus                                 |         0.847561|   
| RandomForest_benchmark_smote                               |         0.764486|    
| RandomForest_benchmark_ros                                 |         0.714009|    

 </center>
 
  <center>
  
| Models                                                     |  CrossVal Score | 
|------------------------------------------------------------| :--------------:|
| K-NearestNeighbor_benchmark_smote                          |         0.769738|   
| K-NearestNeighbor_benchmark_ros                            |         0.740276|    
| K-NearestNeighbor_benchmark_rus                            |         0.719256|    

 </center>
 
  <center>
  
| Models                                                     |  CrossVal Score | 
|------------------------------------------------------------| :--------------:|
| DecisionTreeClassifier_benchmark_rus                       |         0.806503|   
| DecisionTreeClassifier_benchmark_smote                     |         0.668757|    
| DecisionTreeClassifier_benchmark_ros                       |         0.607842|    

 </center>
 
  <center>
  
| Models                                                     |  CrossVal Score | 
|------------------------------------------------------------| :--------------:|
| LogisticRegression_benchmark_rus                           |         0.647721|   
| LogisticRegression_benchmark_ros                           |         0.642458|    
| LogisticRegression_benchmar_smotek                         |         0.640369|    

 </center>
 
So 4 models have been selected:
- RandomForest_benchmark_rus
- K-NearestNeighbor_benchmark_smote
- DecisionTreeClassifier_benchmark_rus
- LogisticRegression_benchmark_rus



and then, i tuned for those 4 models. I get some new models:

<center>
  
| Models                                                     |  Recall Score   | 
|------------------------------------------------------------| :--------------:|
| RandomForest_tunned_rus                                    |        0.827731 |   
| VotingClassifier_tunned	                                   |        0.819328 |    
| DecisionTree_tunned_rus	                                   |        0.794118 | 
| Adaptive_tree_tunned                                       |        0.773109 |   
| GradientBoosting_tunned		                                 |        0.773109 |    
| KNN_tunned_smote	                                         |        0.764706 |
| Adaptive_logit_tunned                                      |        0.739496 |   
| VotingClassifier_benchmark	                               |        0.735294 |    
| AdaptiveBoosting_tunned                                    |        0.710084 |
| LogisticRegression_tunned_rus                              |        0.655462 |


 </center>
 


Based on the table above, it can be seen that the RandomForest_tunned_rus model has the highest Recall Score. So that the model will be used for the HOME EQUITY LOAN prediction model. For the details you can visit <a href="https://github.com/ramzymohammad/Final-Project-Purwadhika-JCDS-1104-LoanPrediction/blob/main/Modelling_2.ipynb">'Modelling'</a>.







