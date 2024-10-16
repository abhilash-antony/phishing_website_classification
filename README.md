# Phishing Website Detection using Machine Learning

## Introduction

Phishing attacks are a significant threat to online security, where attackers impersonate legitimate websites to steal sensitive information. To tackle this issue, we have utilized a dataset containing various features related to websites to build and evaluate machine learning models for phishing detection.

## Dataset Description

The dataset used in this analysis is `Phishing Data - Phishing Data.csv`, which includes multiple features related to website URLs and their characteristics. These features help determine whether a website is phishing or legitimate. The dataset includes attributes such as URL length, use of IP address, presence of SSL certificate, and more.

## Data Exploration

### Missing Values

Upon inspection of the dataset, it was found that there are no missing values, ensuring that the data is complete and ready for analysis.

### Class Imbalance

The dataset shows a class distribution where approximately 55.5% of the samples are labeled as 'legitimate' and 44.5% as 'phishing'. This indicates a slight imbalance, but it is not severe and should not significantly impact the model performance.

### Feature Analysis

- **having_IP_Address**: Most websites (~88.7%) do not have an IP address in their URL, indicating they are more likely to be legitimate.
- **URL_Length**: The majority of websites have a normal URL length (~81.9%).
- **Shortening_Service**: About 12.3% of websites use URL shortening services.
- **having_At_Symbol**: Around 5.5% of websites have an '@' symbol, which can be indicative of phishing.
- **SSLfinal_State**: 57.7% of websites have a valid SSL certificate.
- **Domain_registration_length**: Mixed distribution, indicating a variety of registration lengths.
- **Favicon**: Most websites (~81%) use a legitimate favicon.
- **Request_URL, URL_of_Anchor, Links_in_tags**: Balanced categories in these features.
- **HTTPS_token, RightClick, popUpWidnow, Iframe**: High percentages of websites have proper security measures.
- **Abnormal_URL**: Most websites (~85.9%) do not have abnormal URLs.
- **Page_Rank, Google_Index, web_traffic**: Higher values are associated with legitimate sites.
- **Statistical_report**: Shows a particular statistical classification, likely reflecting more legitimate sites.

## Model Training and Evaluation

We built and evaluated several classifiers to identify the most effective model for phishing detection. The following models were considered:

### Logistic Regression

**Evaluation Metrics:**

- Accuracy: 0.95
- Precision: 0.96
- Recall: 0.92
- F1 Score: 0.94

The Logistic Regression model demonstrated strong performance but was outperformed by more complex models.

### Support Vector Machine (SVM)

**Evaluation Metrics:**

- Accuracy: 0.97
- Precision: 0.97
- Recall: 0.96
- F1 Score: 0.96

The SVM model showed improved performance over Logistic Regression, with higher accuracy and balanced metrics.

### Random Forest

**Evaluation Metrics:**

- Accuracy: 0.97
- Precision: 0.97
- Recall: 0.97
- F1 Score: 0.97

The Random Forest model provided the best performance, achieving high accuracy and balanced metrics across precision, recall, and F1 score. It outperformed both Logistic Regression and SVM, making it the most reliable model for phishing detection.

## Hyperparameter Tuning for Random Forest

To further enhance the Random Forest model, we performed hyperparameter tuning using GridSearchCV. The best hyperparameters identified were:

- **`max_depth`**: None
- **`max_features`**: 'log2'
- **`min_samples_leaf`**: 1
- **`min_samples_split`**: 2
- **`n_estimators`**: 100

These parameters were selected to optimize the model's performance.

## Conclusion

The Random Forest model, with tuned hyperparameters, has demonstrated the best performance for phishing detection in our analysis. Its high accuracy, precision, recall, and F1 score indicate that it is a robust choice for identifying phishing websites effectively.

---
**Author**: Abhilash Antony  
**GitHub**: [abhilash-antony](https://github.com/abhilash-antony)  
**Date**: August 2024
