# Credit_Risk_Analysis

## OVERVIEW OF ANALYSIS
In this project, we use Python to build and evaluate several machine learning models to predict credit risk.
We adopted the following procedure:

oversample the data using the RandomOverSampler and SMOTE algorithms.
Undersample the data using the ClusterCentroids algorithm.
Use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm.
Compare two machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier.

We will evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.

## RESULTS(BALANCED ACCURACY SCORE, CONFUSION MATRIXES AND IMBALANCED CLASSIFICATION REPORT)

* RandomOverSampler Method
![randomoversampling](https://user-images.githubusercontent.com/86641997/136707933-abd6f7d7-0169-409e-96cd-b6273a3a7222.png)

The balanced accuracy score is 64%.
The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 65%.

* SMOTE Model
![smotemodel](https://user-images.githubusercontent.com/86641997/136708027-3631bc7a-0d67-4df1-a4b0-d7b50b7299be.png)

The results are pretty similar to the previous model.
The balanced accuracy score is 63%.
The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 64%.

* ClusterCentroids model
![clustercentroids](https://user-images.githubusercontent.com/86641997/136708221-32b73ec8-7417-495b-af41-fd8e8f56cde0.png)

Here the balanced accuracy score is down to about 53%.
The high_risk precision is still 1% only with 61% sensitivity which makes a F1 of 1%.
Due to the high number of false positives, the low_risk sensitivity is only 45%.

* SMOTEENN model
![smoteenn model](https://user-images.githubusercontent.com/86641997/136708305-8a739466-d595-4e01-b242-23c561d2e9c3.png)

The balanced accuracy score is about 62%.
The high_risk precision is still 1% only with 71% sensitivity which makes a F1 of only 2%.
Due to the high number of false positives, the low_risk sensitivity is 54%.

* BalancedRandomForestClassifier 
![brfc](https://user-images.githubusercontent.com/86641997/136708381-4654b488-b236-4209-b2bf-53bda26f59db.png)

The balanced accuracy score improved to about 79%.
The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.
Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.

* EasyEnsembleClassifier
![eec](https://user-images.githubusercontent.com/86641997/136708454-c1924c3a-0ebb-4f91-9c61-75ab0cc2e971.png)

Now, the balanced accuracy score is high to about 93%.
The high_risk precision is still low at 7% only with 91% sensitivity which makes a F1 of only 14%.
Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% presicion.

## SUMMARY
All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.
The Ensemble models brought a lot more improvment specially on the sensitivity of the high risk credits.
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On another hand, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities.
For those reasons I would not recommend the bank to use any of these models to predict credit risk.
