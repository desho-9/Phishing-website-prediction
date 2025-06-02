# Phishing-website-prediction

Title - Phishing website prediction using predictive analytics. 
Introduction 
Phishing websites are fraudulent websites designed to steal sensitive information from 
users by mimicking legitimate websites. Detecting such websites is crucial for online 
security, as phishing is one of the most common forms of cybercrime.We have used 
classification and some data analytics techniques to detect them. 
Dataset Description 
● Dataset: The dataset used for this project is sourced from the Phishing Website Dataset, 
which contains 11,000 URLs with 30 features, each representing various attributes of a 
website that can be used to detect phishing activity. 
Source: Kaggle 
https://www.kaggle.com/datasets/eswarchandt/phishing-website-detector 
● Features: The dataset contains the following columns: 
○ Index: Index number for each record. 
○ UsingIP, LongURL, ShortURL: URL-related features (e.g., whether the site uses 
an IP address or a short URL). 
○ Symbol@, Redirecting//, PrefixSuffix-: These features are related to the 
structure of the URL, potentially indicating phishing. 
○ SubDomains, HTTPS, DomainRegLen: Domain-related features like the use of 
HTTPS and domain registration length. 
○ Favicon, NonStdPort, HTTPSDomainURL: Indicators of the legitimacy of the 
website’s SSL setup and domain configuration. 
○ class: The target column indicating whether the URL is a phishing site (1) or not 
(0). 
● Input and Output Attributes: 
○ Input Attributes: All the columns except for the "class" and “index” column are 
input features. 
○ Output Attribute: The "class" column, indicating binary classification whether 
the website is phishing(1) or legitimate(-1). 
Candidate Algorithms 
Four potential algorithms were considered for this classification task: 
● Decision Trees: A tree-based model, which splits the data into branches based on 
feature values. It's simple to interpret but can overfit easily. 
● Logistic Regression: A statistical model for binary classification, which works well when 
the data is linearly separable. However, it can struggle with non-linear data. 
● Random Forest: An ensemble method combining multiple decision trees to improve 
accuracy and robustness. It works well with both linear and non-linear data, and it 
reduces the overfitting problem seen in individual decision trees. 
● Support Vector Machine (SVM): A popular algorithm for binary classification, especially 
when the data is high-dimensional. 
Algorithm used: Random Forest was chosen because it handles a large number of features 
well, can model both linear and non-linear relationships, and helps reduce overfitting through 
bagging (bootstrap aggregating). Its accuracy and robustness make it ideal for our phishing 
detection task. 
Implementation 
● Libraries Used: 
○ pandas for data manipulation 
○ scikit-learn for machine learning algorithms, including Random Forest, train-test 
split, and PCA 
○ matplotlib and seaborn for plotting and visualization 
● Steps: 
○ Data Preprocessing: Missing values were handled, and the data was split into 
features (X) and the target variable (y).Removed Index column. 
○ Data Splitting: The dataset was split into 80% for training and 20% for testing 
using train_test_split. 
○ PCA for Feature Reduction: Principal Component Analysis (PCA) was applied 
to retain 95% of the variance in the features, reducing the dimensionality of the 
dataset. 
○ Model Training and Testing: Random Forest was trained on the training data 
and tested on the test data. 
○ Model Evaluation: Accuracy, confusion matrix, and classification report were 
generated to evaluate the model's performance. 
5. Results 
● Model Accuracy: The Random Forest model achieved an accuracy of 96.16%. 
