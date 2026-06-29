## Predicting Educational Video Engagement with Machine Learning
### Project Overview

This project uses supervised machine learning to predict whether an educational video is likely to generate high learner engagement. The work is based on a tabular dataset derived from the public VLE Dataset, which contains video-level features related to educational content.

The goal of the project is to build, evaluate, and compare machine learning models for a binary classification task, with particular attention to model evaluation and ROC AUC performance.

### Dataset

The data used in this project is derived from the public VLE Dataset repository:

https://github.com/sahanbull/VLE-Dataset

For this project:

* train.csv contains the labelled training data.
* test.csv contains the prediction set, with the target column removed to simulate unseen production-style data.

The target variable is engagement, representing whether a video achieved high engagement.

### Project Structure

project/< br / >
   ├── data/< br / >
   │   ├── train.csv< br / >
   │   └── test.csv< br / >
   ├── notebook/< br / >
   │   └── video_engagement_prediction.ipynb< br / >
   ├── README.md< br / >
   └── requirements.txt< br / >

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

### How to Run

If you are interested in testing the model:
COMPLETE

### Outcome
