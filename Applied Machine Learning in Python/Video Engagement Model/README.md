Predicting Educational Video Engagement with Machine Learning
Project Overview

This project uses supervised machine learning to predict whether an educational video is likely to generate high learner engagement. The work is based on a tabular dataset derived from the public VLE Dataset, which contains video-level features related to educational content.

The goal of the project is to build, evaluate, and compare machine learning models for a binary classification task, with particular attention to model evaluation and ROC AUC performance.


Dataset

The data used in this project is derived from the public VLE Dataset repository:

https://github.com/sahanbull/VLE-Dataset

For this project:

train.csv contains the labelled training data.
test.csv contains the prediction set, with the target column removed to simulate unseen production-style data.

The target variable is engagement, representing whether a video achieved high engagement.

Project Structure

project/
├── data/
│   ├── train.csv
│   └── test.csv
├── notebook/
│   └── video_engagement_prediction.ipynb
├── README.md
└── requirements.txt

Methods Used
The project includes:
baseline modelling using DummyClassifier
feature scaling with StandardScaler
model pipelines using Pipeline
hyperparameter tuning with GridSearchCV
Logistic Regression and Support Vector Machine models
evaluation using:
accuracy
precision
recall
F1 score
ROC AUC
confusion matrix
ROC curve
precision-recall curve
