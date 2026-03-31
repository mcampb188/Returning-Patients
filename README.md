# Returning-Patients
Predicts the likelihood of a patient being readmitted within 30 days.

Summary
In the code below, I am building a machine learning model that predicts the likelihood of a patient being readmitted within 30 days. In order to create the prediction I used a random forest classifier, which handles both categorical and numerical values. I used train.csv to train the model, validated the models accuracy with dev.csv and finally tested the model using test.csv. In the development phase the model received a ROC AUC score of 0.85 and in the testing phase it scored 0.82.

EDA
All datasets have null values in both categorical and numerical columns. Some of the features needed to be encoded because they were non-numeric, object data types. Lastly columns used for targetting or had unique identifiers were dropped from the training dataset.

##Preprocessing
To prepare the data for the model I removed any columns that weren't in features. I dropped the target column as well so that the model could run properly. Next I encoded any categorical variables and filled any missing values. Preprocessed any numerical columns and filled missing values with the median from the train.csv dataset.

##Model choice
As mentioned in the summary, I used the random forest classifier as my ML model of choice. This model works well with both categorical and numerical values. Also handles multiple features well. After a few tries with the random forest classifier, I attempted using XGBoost to raise my ROC AUC score but it didn't work as well as my previous method. In my first few attempts I was stuck with a 0.76 score, but after modifying the code I was finally able to boost the score over 0.80. To check model performance I used the dev.csv dataset, then checked the ROC AUC local score to check how it performs.

##Model results
In the development phase I locally scored a 0.85, which was the same score in Codabench. In the testing phase I locally scored a 0.99, but after refinements in the code my Codabench score was 0.82.

##Interpret the model
To see what features impact a patient being readmitted within 30 days, I created a bar plot visual of the top 10 most important features. The variables that stood out to me the most were age, total procedure cost and total med cost. All of these are important factors if a patient will return to the hospital.
