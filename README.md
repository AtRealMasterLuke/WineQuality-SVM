# 🍷 Red Wine Quality Classification using SVM
This project explores the physicochemical properties of red wine to predict its quality using a Support Vector Machine (SVM) classifier. The model classifies wines into two categories: **Good (1)** or **Poor (0)** quality.
## 📂 Dataset
The dataset used is the [Red Wine Quality dataset](https://www.kaggle.com/datasets/lovishbansal123/red-wine-quality)
## 🎯 Objective
  - ### Quality Label Binarization
    Wine quality scores were converted into binary categories using `pd.cut()`:
    - bins = (2, 6.5, 10)
    - labels = ["poor", "good"]
    - df["quality"] = pd.cut(df["quality"], bins=bins, labels=labels)
    - df["quality"] = df["quality"].map({"poor": 0, "good": 1})
  - Wines with quality scores between 2 and 6.5 were labeled as poor (0)
  - Wines with scores between 6.5 and 10 were labeled as good (1)
## Project Workflow
### 1. Exploratory Data Analysis (EDA)
- Checked for missing values, feature distributions, and correlations.
- Visualized a heatmap of the correlation matrix.
### 2. Preprocessing
- Binarized the `quality` column.
- Scaled features using `StandardScaler`.
### 3. Modeling
- Split the dataset (80% train, 20% test).
- Trained a **Support Vector Machine** classifier (`SVC`).
### 4. Hyperparameter Tuning
- Used `GridSearchCV` to find the optimal combination of `C`, `gamma`, and `kernel`.
### 5. 📊 Model Evaluation (After Hyperparameter Tuning)

- **Accuracy Score**: **90%**
- **Evaluation Metrics**:

```plaintext
              precision    recall  f1-score   support

           0       0.90      0.99      0.94       273
           1       0.82      0.38      0.52        47

    accuracy                           0.90       320
   macro avg       0.86      0.68      0.73       320
weighted avg       0.89      0.90      0.88       320
```
## Acknowledgments
- [Kaggle community](https://www.kaggle.com/datasets/lovishbansal123/red-wine-quality)
- Visual inspiration from seaborn documentation and Scikit-learn examples
