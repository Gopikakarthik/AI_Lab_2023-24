# Ex.No: 10 Learning – Use Supervised Learning  
### DATE:  10.10.24                                                                         
### REGISTER NUMBER : 212222040046
### AIM: 
To write a program to train the classifier for Plant Growth Data

###  Algorithm:
```
1.Load Data: Load the dataset and split it into features (X) and target (y). 
2.Train-Test Split: Split the data into training and testing sets. 
3.Handle Imbalance: Apply SMOTE to balance the training set.
4.Preprocess: Use a column transformer to scale numerical features and one-hot encode categorical
features. 
5.Pipeline Setup: Build a pipeline with preprocessing and a RandomForestClassifier.
6.Hyperparameter Tuning: Use GridSearchCV to tune hyperparameters like n_estimators,
max_depth, etc.
7.Model Training: Train the model on the balanced training data. 8.Evaluate: Predict
on test data, and evaluate using accuracy, confusion matrix, and classification report.
```

### Program:
```
import pandas as pd
df = pd.read_csv("/content/plant_growth_data.csv")
df.head()
df.info()
df.isna().sum()
df.duplicated().sum()

from sklearn.model_selection import GridSearchCV, train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.svm import SVC
from sklearn.tree import DecisionTreeClassifier
from sklearn.neighbors import KNeighborsClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score


classifiers = {
    'RandomForest': (RandomForestClassifier(), {
        'n_estimators': [100, 200, 300, 400],
        'max_depth': [None, 10, 20, 30],
        'min_samples_split': [2, 5, 10],
        'min_samples_leaf': [1, 2, 4],
        'bootstrap': [True, False]
    })}

for name, (clf, params) in classifiers.items():
    grid_search = GridSearchCV(clf, params, cv=3, scoring='accuracy', n_jobs=-1)
    grid_search.fit(X, y)
    y_pred = grid_search.predict(X_test)
    accuracy = accuracy_score(y_test, y_pred)
    print(f"{name}: Best Params: {grid_search.best_params_}, Accuracy: {accuracy:.4f}")
```
### Output:

![375292616-12e60eb2-9283-416b-b6d0-010a1e7b96be](https://github.com/user-attachments/assets/f4fa4e94-a8e7-4a3b-bd0d-0a32c8ecc69d)

### Result:
Thus the system was trained successfully and the prediction was carried out.

