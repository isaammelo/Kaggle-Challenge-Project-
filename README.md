# Kaggle-Challenge-Project
Name: Isaam Melo 
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

  - Each feature has there distriution in relation to either being edible or poisonous using 
  histograms across individual feature values. These were selected based on their initital 
  visual insights and later used in machine learning.

  Problem Formulation 
  - Input: Features include: bruises, odor, gill-size, gill-color, stalk-surface-above-ring, 
  stalk-surface-below-ring,  stalk-color-above-ring, stalk-color-below-ring, and ring-type
  - Output: Binary labels representing
         - '0'- Edible
         - '1'- Poisonous
    Task type is binary classification problem using supervised machine learning
    
  Models 
  - Random Forest: Chosen for its strong perfomances with categorical features and handle 
  feature interactions that we see here

  - Naive Bayes: Used as a simple baseline due to its speed and effeciency on categorical data 

  - Trained each in full and reduced some features (that will be shown)
 
    
  Hyperparameters 
  - Random Forest:
       - random_state=42

  Training
  - Packages: pandas, scikit-learn, matplotlib.pyplot 
  - Training time was minimal due to dataset size and efficient models. Validation and test 
    evaluations were used to compare model generalization. Feature selection was done after 
    observing feature importances. Confusion matrices and classification reports were generated 
    for all data splits.

  Performance Comparison
  -  The performances will be assessed using the Precision, Recall, F1-Score, and especially the Accuracy.
  -  Results for Random Forest (training, validation, and testing) 
     ![Screenshot 2025-05-02 140253](https://github.com/user-attachments/assets/c584227e-1af1-4b4b-bb32-d4e9c25dcae4)
     ![Screenshot 2025-05-02 140323](https://github.com/user-attachments/assets/3b960cc3-7fda-44b0-852d-7819b33cbbe5)
     ![Screenshot 2025-05-02 140342](https://github.com/user-attachments/assets/fff4da7d-9b8a-47c3-bb3f-daf1d424335c)
     ![Screenshot 2025-05-02 140420](https://github.com/user-attachments/assets/0038482c-a591-497e-a0f0-01b6ca196cd1)
      - The graphs are very accurate


  -  Results for Naive Bayes
    
     ![Screenshot 2025-05-02 141054](https://github.com/user-attachments/assets/e209299a-f2dd-46f2-aad0-476acdfe275c)
     ![Screenshot 2025-05-02 141110](https://github.com/user-attachments/assets/0b54fa9a-1f06-46af-9e18-35eb17adf7f3)
     ![Screenshot 2025-05-02 141122](https://github.com/user-attachments/assets/15010a19-b813-483f-9604-b8501857d5be)
     ![Screenshot 2025-05-02 141212](https://github.com/user-attachments/assets/9ce094cc-68f1-4d5a-86ae-d48a140cc955)
     - The graphs were both very accurate, which raised concerns. The features used had to be evaluated again to make sure some were not causing heavy bias. These were the results
    
     ![Screenshot 2025-05-02 141514](https://github.com/user-attachments/assets/f1e2960d-9240-4bac-8070-3be264ed947c)
    - odor_n, gill-size, odor_f were really high in featuer importance compared to others, so 
     they were dropped and the models were revaluated after.
    - The results of the Random Forest were near the same:
     ![Screenshot 2025-05-02 141844](https://github.com/user-attachments/assets/53e571ad-3d1f-4b26-a697-98adbfc29e6f)
     ![Screenshot 2025-05-02 141940](https://github.com/user-attachments/assets/8e01a8b3-860f-437f-bfbc-532cd374c2d5)
      - Other than the mushrooms it predicted to be poisonous actually being edible increasing than the origina full features, it still remained high.


     - But Naive Bayes:
       ![Screenshot 2025-05-02 142033](https://github.com/user-attachments/assets/fdfa1cbe-78a3-4208-8da5-e641e7b6b456)
       - The scores are all down compared to when there was a full set of features.
       ![Screenshot 2025-05-02 142051](https://github.com/user-attachments/assets/1102b658-d40d-49f4-82e4-9ca3992f6823)
       - This shows the increase the amount of incorrectly chosen edible mushrooms in the 
         testing, a sign of how overly cautious the model was getting
 
  Conclusions
  - Random Forest proved to be a highly effective classifier for this particular dataset.
  - Even after features were removed, the accuracy score still remained high (perhaps 
    indicating 
    some reduancy in the data.
  - Naive Bayes performed well at first but was not as consistent or accurate as Random Forest.
  - Overall, these two models proved that the model was at least being cautious as to 
    predicting 
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
  - preproccessing: encode target variable - class and gill-size and one hot encode the rest of    the features. One could also drop the selected features like odor_n, gill_size, and odor_f 
   to see changes to the models. Split the dataset into training (60%), validation (20%), and
   test (20%). 
 
  Overview of File in Repository
  - Kaggle Tabular Data Challenge - The complete notebook including data preprocessing, feature 
    encoding, model training (Random Forest and Naive Bayes), feature importance analysis, 
    performance evaluation, and final prediction 
  Software Setup
  - pandas
  - numpy
  - matplotlib
  - skikit-learn:
     - model_selection
     - naive_bayes
     - preprocessing
     - metrics
     - metrics.ConfusionMatrixDisplay
 
  Citations
  - https://www.kaggle.com/datasets/uciml/mushroom-classification
  - https://scikit-learn.org/stable/
  - https://matplotlib.org/stable/contents.html
