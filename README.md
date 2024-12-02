# Human activity recognition 

## Background
A study of 30 participants were carried out, to collect data for a human activity recognition project. They were asked to wear waist-mounted smartphones with embedded intertial sensors, and data were collected while they were going about their daily activities.

## Project goal and objectives
Goal - To identify activities of daily living with a smartphone. 
Objective - To train a machine learning model to classify human activities of daily living - walking, sitting, standing, laying, walking upstairs and walking downstairs.


## Data
Source - [Human Activity Recognition with Smartphones Dataset](https://www.kaggle.com/datasets/uciml/human-activity-recognition-with-smartphones)

## Approach taken
- Since this was a classification problem, I tried both Random Forest (which is a well known bagging algorithm for classification) and XGBoost (as a leading boosting algorithm for classification). 
- Steps taken
  - Prepare data
    - Checking max, min of float columns - they were withing the range of (-1 to +1), although scaling is not required for the chosen models
    - Label encoding the target 'Activity' column
    - Checking the balance of the 'Activity' column - fairly balanced, but to reduce the probabilities of biased predictions decided to apply SMOTE
    - Applyting SMOTE - to generate more minority class samples and reduce the risk of overfitting
    - Splitting the dataset - to test and train
  - Model data / make predictions / evaluate model
    - Random Forest
      - number of trees/n_estimators was set to 200 for least error 
      - Tuning hyperparameters -  max_features, max_depth, min_samples_split, min_samples_leaf 
    - XGBoost
        - Check for default parameters
        - Check for a higher learning rate to make the model more robust
  - Select the best model

## Technologies
- Technologies -
  - Machine learning algorithms - XGBoost, Random Forests, SMOTE
  - Model evaluation - accuracy, precision, recall, f1-sore, confusion matrix
  - Hyperparameter tuning
- Programming languages and libraries
  - Python - Scikit-learn, XGBoost, imbalanced-learn, pandas, matplotlib
- Tools
  - VS Code
  - GitHub

## Code
Link to the code - xxx  

## Observations and Recommendations
- XGBoost model was more accurate than Random Forest.
- The accuracy of 99% in the XGBoost model was deemed sufficient for the application of human activity recognition.

## Next steps
- Deploy the model in a production environment using 
  - Web applications (e.g.Django or FastAPI) or 
  - Cloud services (e.g., AWS Sagemaker, Azure ML, Google AI Platform)
