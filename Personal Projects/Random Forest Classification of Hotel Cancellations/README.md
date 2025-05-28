# Random Forest Classification of Hotel Cancellations

# Research Question and Hypothesis:
The cancellation of hotel reservations is a costly and inevitable expense placed upon the lodging industry. 
 Hotels unable to replace cancelled reservations or fill un-booked rooms lose revenue and profitability. 
 Having the ability to predict if a customer is likely to cancel their reservation gives time to plan ahead 
 allows for hotels to prevent further cancellations and book rooms more efficiently. This study aims to predict 
 the likelihood of a customer cancelling their reservation and reject the null hypothesis that a Random Forest 
 Classifier machine learning model cannot predict hotel cancellations with at least 80% accuracy. Rejecting the 
 null hypothesis would mean accepting the alternative hypothesis that a Random Forest Classifier model could 
 predict hotel cancellations with at least 80% accuracy.

# Data Analysis:
After all data collection and preparation was completed, the X dataset contained 50 independent variables which 
 were included in the final analysis. The data was split into 80% training data and 20% testing data. Three 
 iterations of Random Forest Classifiers were used in order to compare each model and find the best fit for 
 this data set. The first iteration was a standard Random Forest Classifier with all default hyperparameters and 
 a random seed of 50 in order for results to be replicated in the future. The results of this iteration can be 
 seen in Table A.

![image](https://github.com/user-attachments/assets/b7527529-600f-4ecc-8e9b-3028f3429d8e)

Table A.

After running this preliminary model, another Random Forest Classifier was used in combination with GridSearchCV 
in order to determine the best values for the highest possible accuracy. The grid search was fit with parameters 
for n_estimators, max_depth, and max_features. The grid search yielded the same accuracy, precision, recall, and 
f1-scores as the preliminary model, which indicates that despite the grid search could not find better values, it 
also did not provide a worse result. The preliminary model and grid search had a 99.02% accuracy, and had precision, 
recall, and f1-scores of 0.99, except for recall of is_canceled equaling one where it had a score of 0.98. The best
hyperparameters chosen by GridSearchCV were 300 for n_estimators, 10 for max_features, and 40 for max_depth, which
were used in the creation of the final Random Forest Classifier model. The results can be seen below in Table B.

![image](https://github.com/user-attachments/assets/7b72bc48-0a6a-44be-a09e-dd52ae6ea9db)

Table B.

# Study Findings:
The final model was evaluated using the same metrics as the preliminary model and GridSearchCV model with the addition 
of calculating the Receiver Operating Characteristic Area Under the Curve (ROC AUC). The result of the final model was 
an accuracy of 86.63% with all precision, recall, and f-1 scores above 0.80, except for recall of the 1 value for 
‘is_canceled’, which was 0.77 (as seen below in Table C).

![image](https://github.com/user-attachments/assets/c78c7c25-1ea4-4a93-bc1d-f17ab7f09cb4)

Table C.

In other words, the model predicted the correct result against the test set almost 87% of the time, the model mitigated 
false positive predictions for both cancelled and uncancelled reservations (precision: 0.86 and 0.87, respectively), 
avoided making false negative predictions (recall: 0.77 and 0.92, respectively), and had a high f-1 score indicating 
good overall performance (0.81 and 0.90, respectively). The ROC AUC (as seen on the next page in Chart A) indicated 
that the model captured 93% of the data under the curve, which shows that this is a high performing classification model. 

![image](https://github.com/user-attachments/assets/89e768b3-ef5d-43d4-ab14-b382dd7fa320)

Chart A.

# Study Limitations:
One limitation is that there appears to be some overfitting in the model because the accuracy, precision, recall, and 
f-1 scores are all much higher for the training model than the testing model (accuracy: 99% and 87%, respectively). 
Another limitation is that Random Forest Algorithms are computationally expensive with larger datasets, which was 
noticeable with how long the models would take to run. A third limitation is that the GridSearchCV was only given 
three values for n_estimators, three values for max_depth, and four values for max_features to test within the model. 
I identified that anything less than these values had worsened the performance of the model, but there could’ve been 
higher values for the parameters which might have yielded better results. A fourth limitation is that the dataset only 
contains data for 2016 and 2017 which leads to very limited application without the addition of more recent data. 
Another limitation is that missing or incorrect data could’ve been imputed with the mean or median instead of being 
removed from the dataset. 

# Proposed Actions:
My recommended course of action and recommendations for further study would be to expand the dataset to include more 
than only two years of data, examine other possibilities of hyperparameters, and identify if any other machine learning 
models could perform at a higher level with this dataset than the Random Forest Classifier.

Expected Benefits:
The main expected benefit of the application and implementation of this model would be increased profitability in the hotel 
and hospitality sector. Hotels using this model, especially with more recent data, could better identify if customers are at 
higher risk of cancelling their hotel reservations and either increase prices or fees to account for the risk incurred by 
keeping their reservation on file, or through other methods such as maintaining a wait list or requiring a deposit if certain 
criteria are met. Overall, this model allows for better planning for hotels and would set better expectations for hotel staff 
as well as improve hotel efficiency while improving profitability. 

