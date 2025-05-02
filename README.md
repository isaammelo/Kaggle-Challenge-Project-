# Kaggle-Challenge-Project
Mushroom Classification Using Machine Learning 

- The Mushroom Classification challenge asks us to build a model to safetely predict a mushroom's edibility to potentially save lives.

  Overview
  - The task is to classify mushrooms as either edible or poisonous based on categorical features describing their physical attributes (eg cap color, odor, gill size). Each instance in the dataset is a unique mushroom with no missing data.
  - Our approach formulated this as a binary classification task. We implemented and compared two models, including using Random Forest for and Naive Bayes using scikit-learn. We also performed basic feature selection by removing features with low importance to evaluate the impact on model performance.
Our best model was Random Forest with all features included, achieving a classification accuracy of nearly 100% on the training set and high accuracy on the validation/test sets, indicating strong performance without significant overfitting.

  Summary of Workdone
  - Name: mushroom.csv
  - Rows: 8124
  - Column: 23 
  - Split:
        - Training-60%
        - Validation-20%
        - Test-20%
  - Target Variable: Class Column containg edible (e) and poisonous (p)
    
  Preprocessing/Clean up
  - Label Encoding was used for binary features such as the class column and gill-size
  - One Hot Encoding was used for all of the other features
  - After doing One Hot Encoding, a few features were dropped in a "reduced features" experiment (odor_n, gill-size, odor_f) based on domain knowledge and their model feature importances being higher than all of the other 14 features used.
    
  Data Visualization
![Screenshot 2025-05-02 132922](https://github.com/user-attachments/assets/4b9ecd5e-26cf-489c-a749-bf88a9eb30d3)
![Screenshot 2025-05-02 132959](https://github.com/user-attachments/assets/9f2bb235-529e-4e3a-b962-f9401cdee839)
![Screenshot 2025-05-02 133034](https://github.com/user-attachments/assets/149771a2-47ca-463c-95e8-1ec03c97853c)
![Screenshot 2025-05-02 133110](https://github.com/user-attachments/assets/d7b8f34b-d6ea-4c9d-9357-d9c95354b534)
![Screenshot 2025-05-02 133144](https://github.com/user-attachments/assets/4978b4cc-f940-4053-87cb-8b1ae1e58a6e)
![Screenshot 2025-05-02 133204](https://github.com/user-attachments/assets/0b9b5dbd-8f5c-477b-ac87-b006e84c6a99)
![Screenshot 2025-05-02 133233](https://github.com/user-attachments/assets/5e88492d-22cf-488f-be29-1e6d68b572bd)
![Screenshot 2025-05-02 133302](https://github.com/user-attachments/assets/672ba74e-c439-43e3-9460-e0943fddd0bd)
![Screenshot 2025-05-02 133343](https://github.com/user-attachments/assets/d522524f-f03f-4af0-80ba-6a7e36592430)


  Problem Formulation 
  - Input:?

  Models 
  - ?

  Hyperparameters 
  - Random Forest:
       - random_state=42

  Training
  - Packages: pandas, scikit-learn, matplotlib ?
  - Training time was minimal due to dataset size and efficient models. Validation and test 
    evaluations were used to compare model generalization. Feature selection was done after 
    observing feature importances. Confusion matrices and classification reports were generated 
    for all data splits.

  Performance Comparison
  -  ?
 
  Conclusions
  - Random Forest proved to be a highly effective classifier for this particular dataset.
  - Even after features were removed, the accuracy score still remained high (perhaps indicating 
    some reduancy in the data.
  - Naive Bayes performed well at first but was not as consistent or accurate as Random Forest.
  - Overall, these two models proved that the model was at least being cautious as to predicting 
    whether or not a mushroom was edible or poisonous.
 

  Future Work 
  - Use hyperparameters such as GridSearchCV and RandomizedSearcCV
  - Using other algorithms such as Decision Tree or maybe even more advanced like Gradient 
  Boosting or XGBoost
  - Investigate certain features and there affects to the model(s).
  - Deploy model in the real world.

  How To Reproduce Results
  - Download file
  - Open using Google Colab or Jupyter Notebook
  - Ensure you are running the required packages (skikit-learn, pandas, matplotlib).
  - Load the dataset: mushrooms.csv
  - preproccessing ?
 
  Overview of File in Repository
  ?

  Software Setup
  - pandas
  - numpy
  - matplotlib
  - skikit-learn
 
  Citations
  - https://www.kaggle.com/datasets/uciml/mushroom-classification
