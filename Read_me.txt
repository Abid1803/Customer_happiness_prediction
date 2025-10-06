1. Imported the dataset(used Google Colab)

2. looked for data imbalance{
    found no data imbalance
}
3. dropped irrelevant columns which don't contribute in prediction{
    came to that conclusion using feature impotance scode in random forest..
    remove columns like "Sex","User_Id","User_Age","City","Full_Name"
}
4. imported model (logistic ,random forest , xgboost)

5. spited the data into train and test test=20%{
    initially tried to scale and encode the data but that didnt help in any increase in accuracy ..so remove that part completely
    moved direclty to data spliting
    used 20% data to train and 80% to train as we are using ml model..
}

6. trained models on training data{
    model fitting... applied al three model on the dataset (trainin data)..adjusted hyper paraments of xgboost accordingly
}

7. displaced evaluation metrics(accuracy, recall, precsion, etc){
    as the accuracy was <70 it was arround 49 to 50...
    imported SVC and linearSVC too and applied to check if the reason for loweraccuracy is model selection or anything else(DATASET GIVEN)

    but there was no change in accuracy. so, to determine the reason.. folowed next steps.....
    {
        1.Checked for dataimbalance...wasnt the issues....
        2.Checked for feature with less importance are in play...(it wasnt the isseu we use only relevant and promissing features only)
        3.Checked for correlation between features and target variables...
        {
            found the issue...the most promissing feature's correlation were almost 0(zero)
            {
                Correlation with 'Is_Happy' Target Variable{
                    Is_Happy                1.000000(Traget Variable)
                    Plan_Duration_Months    0.002328
                    Monthly_Charge_USD     -0.000211
                    Data_Usage_GB          -0.002842
                }
            }
        }
        {
            The dataset provied doesnt help model in mapping the featues to the target vaibale..can't possible make a predictions...

            0.5 accuracy is randomly guessing...(fliping a coin)!
        }
    }
}


8.poltted the heatmap of there model(logistic, RandomForest, XGBoost)

9.
Note:
to run the code for yourself..change the path Variable accordingly...