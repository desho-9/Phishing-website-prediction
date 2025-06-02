# Phishing-website-prediction

# Phishing Website Prediction Using Predictive Analytics

## 📌 Introduction

Phishing websites are fraudulent websites designed to steal sensitive information from users by mimicking legitimate websites. Detecting such websites is crucial for online security, as phishing is one of the most common forms of cybercrime. We have used classification and some data analytics techniques to detect them.


## 📊 Dataset Description

* **Dataset**: The dataset used for this project is sourced from the Phishing Website Dataset, which contains 11,000 URLs with 30 features, each representing various attributes of a website that can be used to detect phishing activity.
  **Source**: [Kaggle - Phishing Website Detector](https://www.kaggle.com/datasets/eswarchandt/phishing-website-detector)

* **Features**: The dataset contains the following columns:

  * `Index`: Index number for each record.
  * `UsingIP`, `LongURL`, `ShortURL`: URL-related features (e.g., whether the site uses an IP address or a short URL).
  * `Symbol@`, `Redirecting//`, `PrefixSuffix-`: Features related to the structure of the URL, potentially indicating phishing.
  * `SubDomains`, `HTTPS`, `DomainRegLen`: Domain-related features like the use of HTTPS and domain registration length.
  * `Favicon`, `NonStdPort`, `HTTPSDomainURL`: Indicators of the legitimacy of the website’s SSL setup and domain configuration.
  * `class`: The target column indicating whether the URL is a phishing site (`1`) or not (`-1`).

* **Input and Output Attributes**:

  * **Input Attributes**: All columns except for `class` and `index`.
  * **Output Attribute**: The `class` column, indicating binary classification — whether the website is phishing (`1`) or legitimate (`-1`).


## 🧠 Candidate Algorithms

Four potential algorithms were considered for this classification task:

* **Decision Trees**: A tree-based model that splits the data into branches based on feature values. It's simple to interpret but can overfit easily.
* **Logistic Regression**: A statistical model for binary classification, effective with linearly separable data but less so with non-linear patterns.
* **Random Forest**: An ensemble method combining multiple decision trees to improve accuracy and robustness. It handles both linear and non-linear data well and reduces overfitting.
* **Support Vector Machine (SVM)**: A powerful algorithm for binary classification, particularly effective with high-dimensional data.

> **Algorithm Used**: **Random Forest** was chosen because it handles a large number of features well, can model both linear and non-linear relationships, and helps reduce overfitting through bagging (bootstrap aggregating). Its accuracy and robustness make it ideal for our phishing detection task.


## ⚙️ Implementation

### 🛠️ Libraries Used

* `pandas` – for data manipulation
* `scikit-learn` – for machine learning algorithms (Random Forest, train-test split, PCA)
* `matplotlib` and `seaborn` – for plotting and visualization

### 🧪 Steps

1. **Data Preprocessing**:

   * Handled missing values
   * Removed `Index` column
   * Split the data into features (`X`) and target (`y`)

2. **Data Splitting**:

   * Used `train_test_split` to divide the dataset into 80% training and 20% testing

3. **PCA for Feature Reduction**:

   * Applied Principal Component Analysis (PCA) to retain 95% variance in features and reduce dimensionality

4. **Model Training and Testing**:

   * Trained the Random Forest model on the training data
   * Evaluated it on the test data

5. **Model Evaluation**:

   * Generated accuracy, confusion matrix, and classification report



## 📈 Results

* **Model Accuracy**: The Random Forest model achieved an accuracy of **96.16%**

  

## 📊 Model Evaluation and Visualization

* **Confusion Matrix**:
  Demonstrates how well the classifier distinguished between phishing and legitimate instances.

* **PCA Feature Importance Chart**:
  Shows how much variance each principal component explains. This visualization is useful to demonstrate the effect of dimensionality reduction during the presentation.


## ✅ Advantages and ❌ Disadvantages

### ✅ Advantages of Random Forest

* Handles a large number of features effectively.
* Reduces the risk of overfitting compared to individual decision trees.
* Captures complex, non-linear relationships in the data.

### ❌ Disadvantages of Random Forest

* Can be computationally expensive, especially with many trees.
* Less interpretable than simpler models like decision trees.


## 🤔 Why Not Other Algorithms?

* **Decision Trees**:
  Although easy to interpret, they tend to overfit, especially on large datasets. Random Forest mitigates this issue using ensemble learning.

* **Logistic Regression**:
  Suitable for linear problems, but not ideal for complex, non-linear relationships like those found in phishing detection.

* **Support Vector Machine (SVM)**:
  Can perform well in high-dimensional spaces, but is sensitive to kernel choice and computationally expensive on large datasets.


## 🔮 Future Scope

1. Implement a function that takes a URL as input and predicts whether it's phishing or not, based on the trained model.
2. Collect more real-world data to improve model validation and robustness.


## 🏁 Conclusion

The model’s performance is strong.
Feature selection and dimensionality reduction through PCA helped mitigate overfitting and improved efficiency.
However, further validation with real-world data is recommended to ensure robustness in practical applications.




