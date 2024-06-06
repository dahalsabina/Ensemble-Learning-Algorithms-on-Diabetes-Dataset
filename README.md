**Diabetes Dataset Conclusions**

Split Train, Dev, and Test Set -> used 80,000 for train, 10,000 for dev, and 10,000 for test
Training Models:

We fit our data to five Ensemble Learning algorithms and the recall values for class 1 (Diabetes) are as follows:



GradientBoostingClassifier: 0.68

StackingClassifier = 0.68

HistGradientBoostingClassifier: 0.67

RandomForestClassifier: 0.65

AdaBoostClassifier: 0.63

BaggingClassifier: 0.53



**Analysis:** For the problem of detecting Diabetes (Class 1), higher recall values indicate better performance in identifying all positive cases of diabetes. The values indicate that GradientBoostingClassifier and StackingClassifier show the highest recall for Diabetes at 0.68, suggesting they are slightly more effective at identifying diabetic cases compared to the other models.BaggingClassifier shows the lowest recall at 0.53, which might suggest that it is underperforming in identifying all true positive cases of Diabetes.



**Mean Recall for Ensemble Learning Algorithms**


GradientBoostingClassifier: 0.84

AdaBoostClassifier: 0.84

StackingClassifier = 0.84

HistGradientBoostingClassifier: 0.83

RandomForestClassifier: 0.83

BaggingClassifier: 0.76



 
 **Analysis:** The mean recall values suggest how well these classifiers perform across all classes ( 0 &1).GradientBoostingClassifier, AdaBoostClassifier, and StackingClassifier have the highest mean recall of 0.84.These models show robust performance across both classes.BaggingClassifier has the lowest mean recall at 0.76, aligning with its underperformance specifically for the diabetic class.
 
 
We continued with the two models with the highest recall scores -> GradientBoosting and AdaBoostingClassifier.

**Hypertuning Parameters:**

**GradientBoosting**

The best score:  0.7114600453310131

The best hyperparameters:

{'learning_rate': 0.6, 'max_depth': 5, 'min_samples_leaf': 1, 'min_samples_split': 2, 'n_estimators': 500}
Accuracy:  0.9658

Precision:  0.9120585554796081

Recall:  0.8635401506806358

F1 Score:  0.885910919245747


**Analysis**

The best score achieved during cross-validation is 0.711, suggesting that the model, on average, achieves this level of accuracy across different subsets of the training data.

Accuracy: 96.58% - Very high, indicating good overall performance on the dataset.

Precision: 91.21% - High precision indicates that the model has a low false positive rate.

Recall: 86.35% - The model's ability to detect all positive samples is quite high, though not perfect.

F1 Score: 88.59% - A balanced measure that takes both precision and recall into account, reflecting a strong model but 

suggesting room for improvement, especially in maximizing recall.



**AdaBoostClassifier**

The best score:  0.7042798062152901

The best hyperparameters:

{'base_estimator': DecisionTreeClassifier(max_depth=2), 'learning_rate': 0.8, 'n_estimators': 800}

Accuracy:  0.9688

Precision:  0.9385655562306492

Recall:  0.8558483223311275

F1 Score:  0.8919205183491941

**Analysis**

The best score during cross-validation is 0.704, slightly lower than that of GradientBoosting.
Accuracy: 96.88% - Slightly higher than GradientBoosting, indicating excellent overall performance.
Precision: 93.86% - Better precision, reflecting a very low rate of false positives.
Recall: 85.58% - Lower than GradientBoosting, suggesting it might miss more positive cases.
F1 Score: 89.19% - High, showing a good balance between recall and precision but confirming that recall could be a limiting factor.

Both models exhibit high performance metrics, but there are notable differences in their recall values, which is critical for our application, given the importance of not missing any diabetic cases. GradientBoosting offers a higher recall (86.35%) compared to AdaBoost (85.58%). Although the difference is modest, in medical applications such as diabetic detection, even small improvements in recall can be crucial as they reduce the risk of missing positive cases. 





**Comparing Results with Previsous Model :**

Random Forest (Previous)

Accuracy: 0.9551

Precision: 0.856671848722498

Recall: 0.8644210977011957

F1 Score: 0.8604930436829215




**Gradient Boosting (Current)**

Accuracy:  0.9658

Precision:  0.9120585554796081

Recall:  0.8635401506806358

F1 Score:  0.885910919245747





**Recall:** Random Forest achieves a slightly higher recall (86.44%) compared to GradientBoosting (86.35%). Although the difference is minimal, Random Forest edges out slightly in the context of minimizing missed cases.
Accuracy: GradientBoosting shows better accuracy (96.58%) compared to Random Forest (95.51%). This suggests that GradientBoosting generally performs better across all test instances, correctly classifying a higher percentage of total cases.
Precision: GradientBoosting has a notably higher precision (91.21%) than Random Forest (85.67%). Higher precision indicates that GradientBoosting has a lower rate of false positives, meaning it is less likely to label a non-diabetic patient as diabetic.
F1 Score: Again, GradientBoosting scores higher (88.59%) than Random Forest (86.05%), indicating a better balance between recall and precision in GradientBoosting.


Finally, based on model's complexity and better Recall, RandomForestClassifier appears to be the more suitable choice. This model's ability to detect all positive samples is better among all models.

Our Recall percentage is comparatively better than what I found in Kaggle. The link I have posted shows result on RandomForestClassifier and GradientBoostingClassifier. https://www.kaggle.com/code/abdalrahmanhassan/predicting-diabetes-onset-using-machine-learning 

