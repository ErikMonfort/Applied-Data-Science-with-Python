## Predicting Educational Video Engagement with Machine Learning
### Project Overview

This project uses supervised machine learning to predict whether an educational video is likely to generate high learner engagement. The work is based on a tabular dataset derived from the public VLE Dataset, which contains video-level features related to educational content.

The goal of the project is to build, evaluate, and compare machine learning models for a binary classification task, with particular attention to model evaluation and ROC AUC performance.

### Dataset

The data used in this project is derived from the public VLE Dataset repository:

'https://github.com/sahanbull/VLE-Dataset' by sahanbull

For this project:

* train.csv contains the labelled training data.
* test.csv contains the prediction set, with the target column removed to simulate unseen production-style data.

The target variable is engagement, representing whether a video achieved high engagement.

### Project Structure

project/  
   ├── data/     
   │   ├── train.csv  
   │   └── test.csv  
   ├── video_engagement_prediction.ipynb  
   ├── README.md  
   └── requirements.txt    

### Methods Used
The project includes:

* baseline modelling using DummyClassifier
* feature scaling with StandardScaler
* model pipelines using Pipeline
* hyperparameter tuning with GridSearchCV
* Logistic Regression and Support Vector Machine models
* evaluation using:
    * ROC AUC
    * confusion matrix
    * ROC curve / precision-recall curve visualized
    * Accuracy, precision, recall, F1 score compared at the model selection stage.

### Model Summary

The best-performing model was a balanced Support Vector Machine using an RBF kernel. The model was selected using cross-validation and evaluated against a dummy baseline to confirm that it provided meaningful predictive value beyond class-frequency guessing.

The final model achieved strong validation performance, with a satisfactory ROC AUC score.

### Visualizations

Below are the visualizations from the project:

1. Feature Importance Check with a Decision Tree (ID included here out of curiosity as to whether the model was able to derive useful information from it)



2. Confusion Matrix - Balanced SVM



3. ROC Curve - Balanced SVM



4. Precision-Recall Curve - Balanced SVM



### Outcome

####Technical / Project Takeaways
* The target distribution is imbalanced, so accuracy alone is not sufficient for evaluating model quality. Metrics such as ROC AUC, precision, recall, F1 score, and confusion matrices provide a more complete view of performance.
* A dummy classifier provides an important baseline, helping confirm whether the supervised models are learning useful patterns rather than simply reflecting the majority class.
* Pipelines ensure that preprocessing steps such as scaling are applied safely during cross-validation, reducing the risk of data leakage.
* The Balanced SVM performed best in validation based on ROC AUC, showing stronger ranking performance than both the dummy baseline and Logistic Regression model.
* ROC AUC was useful as the main selection metric because it evaluates how well the model ranks high-engagement videos above lower-engagement videos across different thresholds.

####Business / Product Takeaways
* The final model outputs probability scores for unseen videos, which could be used to rank or prioritise content by predicted engagement.
* For a learning platform, this type of model could help identify videos that are likely to perform well, support content recommendation, or highlight promising educational material for further promotion.
* The precision-recall trade-off has practical implications. A higher-recall model reduces the chance of missing genuinely high-engagement videos, which may benefit content creators, but it may also increase false positives and surface some lower-quality recommendations to learners.
* In a production setting, the decision threshold should be chosen based on business priorities. If the goal is content discovery, higher recall may be preferred; if the goal is learner experience and recommendation quality, higher precision may be more important.

