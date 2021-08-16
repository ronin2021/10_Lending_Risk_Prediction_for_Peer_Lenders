# 11_Lending_Risk_Modeling_for_Peer_Lenders
Using Machine Learning techniques on unbalanced data sets to predict and model risk of a cohort of Peer Lenders

Machine Learning models: Simple Logistic Regression, Naïve Random Sample (Oversampling), SMOTE (Oversampling), Cluster Centroid (Undersampling), and SMOTEENN (Combination) applied on imbalance datasets of financial data. Depending on the resultant Balanced Accuracy Score, Confusion Matrix, and Imbalanced Classification Report of each of the models, what model would be better suited at predicting the data set was assessed.     
#### Part 1. Credit Risk Resampling
1. Credit Risk imbalanced dataset (lending_data.csv) of Peer Lending Loans was uploaded from the provided CSV files. 
2. These were formatted to a Pandas dataframe. 
3. Dataframe Checked for NAs and NANs in the data.
4. Some discrete data columns were digitized to numeric format using dictionaries for eventual application in Logistic Regression Models.
5. Data were split to Train and Test streams.
6. Their shapes were tested.
7. The X_train and X_test were scaled for applying to Logistic Regression models via StandardScalar from Scikit-Learn library.
8. These scaled streams were applied to: Simple Logistic Regression, Naïve Random Sample (Oversampling), SMOTE (Oversampling), Cluster Centroid (Undersampling), and SMOTEENN (Combination) where the corresponding predicted_y for each case was obtained. 
9. For each of the above models Balanced Accuracy Score, Confusion Matrix, and Imbalanced Classification Report were obtained and the models were compared for their ability to predict high risk loans.
 
Following are a summary of condensed observations obtained:

1. Which model had the best balanced accuracy score? SMOTEENN, SMOTE, Random Over Sampling gives best balanced accuracy scores while the Simple Logistic Reg. gives the worst balanced accuracy score.
2. Which model had the best recall score? Average recall score is equivalent to the second decimal place for all of the models, and it is 0.99. If it is only for the High Risk (bad loans) loans then the best scores are from SMOTEENN (1.00), SMOTE (1.00), and Random Over Sampling (1.00). 
3. Which model had the best geometric mean score? Average Geo Mean score for all the models are equivalent to the second decimal point and is at 0.99. In this regard all these models behaved the same.

#### Part 2. Ensemble Learning 
1. Credit Risk imbalanced dataset (LoanStats_2019Q1.csv) of Peer Lending Loans was uploaded from the provided CSV files. 
2. These were formatted to a Pandas dataframe. 
3. Dataframe Checked for NAs and NANs in the data.
4. A number of discrete data columns were dropped as their variables didn’t change (stayed a fixed value) for the duration of the test. 
5. A number of discrete data columns were digitized to numeric format using dictionaries for eventual application in Logistic Regression Models.
6. Data were split to Train and Test streams.
7. Their shapes were tested.
8. The X_train and X_test were scaled for applying to Logistic Regression models via StandardScalar from Scikit-Learn library.
9. These scaled streams were applied to: Balanced Random Forest Classifier and Easy Ensemble Classifer to train. Predicted_y for each case was obtained. 
10.	For each of the above models Balanced Accuracy Score, Confusion Matrix, and Imbalanced Classification Report were obtained, and the models were compared for their ability to predict high risk loans. 

Following are a summary of condensed observations obtained:

1. Which model had the best balanced accuracy score? Easy Ensemble Classifier provides the best balanced accuracy score: 0.926654
2. Which model had the best recall score? Considering each of the Recall Scores with a model, the Easy Ensemble Classifier is better with High Risk [0] recall score of 0.91 and Low Risk [1] recall score of 0.95. If one to consider only the average (weighted) recall score (with a 1.00) Balanced Random Forrest Classifier performs better. Since our focus is on High Risk lending Easy Ensemble Classifier having a High Risk Recall score of 0.91 as opposed to the 0.70 for the same in Balanced Random Forrest Classifier makes Easy Ensemble Classifier a better model.
3. Which model had the best geometric mean score? Geometric mean score is higher (with a 0.93 for both High Risk and Low Risk) for the Easy Ensemble Classifier is much better than Balanced Random Forrest Classifier (with 0.80 for both High and Low Risk cases).
4. What are the top three features? The top 3 features according their importance in descending order are "total_rec_int", "total_rec_prncp", and "total_pymnt_inv". These are among the 5 topfeatures disproporationately facotrs in for a lending loan being high risk or low risk.   

### Inputs
Data were read from lending_data.csv and LoanStats_2019Q1.csv for the analysis. 

### Outputs
Outputs are given out as mentioned above on the terminal as calculated values, visual plots (horizontal barh graphs), and explanations about the results. 

### Remarks
Models in both parts behave very closely. Small tweaks done iteratively likely improve them so that a standout model can be decerned which is better suited for analysis of similar sets of financial data.


