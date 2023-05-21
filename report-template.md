# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Ege Çalışkan

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Kaggle does not accept predictions that have negative values in them. All negative outputs needed to be set to zero.

### What was the top ranked model that performed?
My top ranked model was the "WeightedEnsemble_L3" model.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
In my EDA I found that the datetime column was not parsed properly, so I added separate columns for it. (Day, month, hour) I found no missing values or outliers.

### How much better did your model preform after adding additional features and why do you think that is?
The performance went up by a lot. The reason was that because the datetime column was not formatted properly, the algorithm couldn't understand what the values meant. Properly formatting the values gave it access to this information.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
To my testing, the training error actually went up after doing hyperparameter optimization. The improvement was in the test performance. I think this is due to the fact that the model was previously overfitting the data getting high training performance but low test performance. After the optimizations, the algorithm didn't fit the training data as well; but it was able to generalize to unseen examples much better.

### If you were given more time with this dataset, where do you think you would spend more time?
I would spend more time doing feature engineering. I think there could definitely be more interesting and useful relationships in this dataset that could help the models perform better.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
(added as Hyperparameter Table.png)
![[Hyperparameter Table.png]] 

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![[model_train_score (RMSE).png]] 
### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.
![[model_test_score.png]]
## Summary
Overall, this project was a big learning experience for me. I did Exploratory Data Analysis, found that there were no missing values or outliers meaning there is no need for clearnup and created a new feature consisting of the seperate fields in the datetime column. I trained different models on the raw dataset and the new feature dataset and selected the best models for hyperparameter optimization which I performed on the new feature dataset. I found that after hyperparameter optimization the training performance suffered by a small margin however the testing score increased greatly. I believe this to be due to overfitting, which was resolved with the optimizations. In the end, the models achieved a kaggle test score of 0.53251.
