# Ad Click Prediction Project

## 📖 Project Overview
This project uses machine learning to predict whether a user will click on an online advertisement. The goal was to build and evaluate several classification models based on user features (like age, device, and browsing history) to find the most effective one for this task.

---

## 📊 Dataset
The dataset used is `ad_click_dataset.csv`. It contains information about a user's profile and their interaction with an online ad.

**Features:**
* `age`: User's age in years.
* `gender`: User's gender (Male, Female, Non-Binary).
* `device_type`: The type of device used (e.g., Mobile, Desktop).
* `ad_position`: The position of the ad on the webpage (e.g., Top, Bottom).
* `browsing_history`: The category of the user's browsing history (e.g., Shopping, Social Media).
* `time_of_day`: The time of day the ad was shown.
* `click`: The target variable (**1** if the user clicked, **0** if not).

---

## 🛠️ Methodology
The project followed a complete machine learning workflow:
1.  **Data Cleaning**: Handled missing values using mean/mode imputation and removed a large number of duplicate entries.
2.  **Exploratory Data Analysis (EDA)**: Created visualizations to understand the data and find patterns, such as the relationship between browsing history, device type, and click rate.
3.  **Data Preprocessing**: Encoded all categorical features using one-hot encoding and balanced the dataset with `RandomOverSampler` to address class imbalance.
4.  **Model Training & Comparison**: Trained and evaluated several classification models to find the best performer, including:
    * AdaBoost
    * Gradient Boosting
    * Stacking Classifier (with Random Forest, Decision Tree, and KNN)
    * XGBoost Classifier
5.  **Hyperparameter Tuning**: Used `GridSearchCV` to find the optimal parameters for the best-performing model.

---

## 📈 Results
After comparing all models, the **XGBoost Classifier** (with default parameters) provided the best performance. While hyperparameter tuning was attempted, the default model proved to be the most robust on the test set.

Here is a summary of the final model performances:

| Model | Accuracy | Recall (for 'Click') |
| :--- | :---: | :---: |
| **XGBoost (Default)** | **66%** | **74%** |
| XGBoost (Tuned) | 65% | N/A |
| Stacking Classifier | 62% | 71% |
| Gradient Boosting | 60% | N/A |
| AdaBoost | 55% | N/A |

The final model is not only the most accurate but also has the highest recall, meaning it is the best at identifying the users who will actually click the ad.

---

## ✔️ Conclusion
The project successfully developed a model that can predict ad clicks with **66% accuracy** and a strong **recall of 74%**. The `XGBClassifier` was identified as the most effective algorithm for this dataset.
