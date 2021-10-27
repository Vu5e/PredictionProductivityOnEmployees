# Prediction of Productivity On Employees In a Company with Imbalanced Handling Techniques

![image](https://user-images.githubusercontent.com/28688869/139130483-22dc4f28-2ed7-434f-a7c9-8272c1e5cf9f.png)

## Introduction
- The dataset that we used to predict contains the records about staff in a company. There are three main aspects about a staff in this dataset which are his/her profiles, workloads and tasks achieved. Our label variable is PerformerCategory which determine whether the staff is a high performer or low performer. 
- The profiles include staff position type (e.g. manager, supervisor,operator), position status (e.g. permanent, contract), career track (e.g. marketing, finance), Nationality, Education (e.g. degree, master, phd), Branch (e.g. KL, Shah Alam), position level (e.g. senior executive, junior executive). Due to privacy, the actual values have been converted to certain values, such as StatusA, StatusB, etc.
- For workload variables are divided into four which are generally the amount of time spend to do their jobs, while task variables consists of 23 tasks which represent their achievement.

## Research Questions
- 1. Which machine learning model is the best to predict PerformerCategory?
- 2. Which combination of machine learning and SMOTE imbalanced classifier that yield better sensitivity?

## Research Objectives
- 1. To evaluate the performance of various machine learning techniques
- 2. To validate constructed machine learning algorithm with SMOTE imbalanced classifier and without it

## Phase 1: Data Understanding
- In this section, we will follow from our methodology above. Below is the details of our approach:
  - 1. import data in excel 
  - 2. statistic summary for all variables
  - 3. data exploration (will check distribution for each variables)

### Variable: PositionType
![image](https://user-images.githubusercontent.com/28688869/139130519-735218ee-50e0-4a33-a1a6-bbd75101af06.png)

### Variable: PositionStatus
![image](https://user-images.githubusercontent.com/28688869/139130538-2162ffd2-aee2-4646-9795-a4182842877b.png)

### Variable: CareerTrack
![image](https://user-images.githubusercontent.com/28688869/139130796-e1e701c8-dc67-4cc4-843d-191c4f75ec7f.png)

### Variable: Nationality
![image](https://user-images.githubusercontent.com/28688869/139130823-986c6bc2-0513-45f0-9517-89edd4692411.png)

### Variable: Branch
![image](https://user-images.githubusercontent.com/28688869/139130906-cda1e226-8fa9-4891-81de-60c5db5d3eaf.png)

### Variable: PositionLevel
![image](https://user-images.githubusercontent.com/28688869/139130945-a62e2b38-eea4-431c-9982-bd76a68d27e1.png)

## Phase 2: Data Preparation
- In this section, we will implement data processing as following:
  - 1. Treat outliers
  - 2. Impute missing values

### Treat Outliers
- In this section, we will display each numerical variables in order to see the presence of outliers. Then we will drop the column that having extreme outliers. After that, we treat the other outliers (mild outlier) with Log Transformion using Power Transformer.

![image](https://user-images.githubusercontent.com/28688869/139131218-65141c06-13d3-4f56-b4d6-dced58b5015b.png)

- Outliers can be treated using Log Power Transformer

### Impute Missing Values
- In this section, we will check missing values or null values. Then, we will impute missing values with Mode as Mode usually used for imputation in categorical variables.

### Check Missing Values
![image](https://user-images.githubusercontent.com/28688869/139131443-fc2d467d-e4f4-408a-bff9-0c41d2d6349f.png)

### Impute Branch Variable with Mode
![image](https://user-images.githubusercontent.com/28688869/139131549-4fedffd1-738f-4f71-b4e1-4dab74e6d3ac.png)

## Imbalance Classifier
- In this section, we will implement few steps to imbalance the data with SMOTE and without SMOTE as below details:
  - 1. check distribution of label variable which is PerformerCategory
  - 2. Replace PerformerCategory Variable to 0 and 1
  - 3. Encoding categorical variables to numerical values
  - 4. Merge with encode dataframe & drop the existing categorical variable
  - 5. Divide X and Y with independent variables and target variable respectively
  - 6. Standarize the data
  - 7. Split data into training & testing
  - 8. Fit model LR, SVM, DT without SMOTE
  - 9. Fit model LR, SVM, DT with SMOTE

### Fit Model Logistic Regression, SVM and Decision Tree Using SMOTE
![image](https://user-images.githubusercontent.com/28688869/139131779-6305b4b6-4bd0-4b44-8eb3-a128dd1fd22c.png)

## Phase 4: Data Modelling
- Logistic Regression Without SMOTE
![image](https://user-images.githubusercontent.com/28688869/139131897-2aed9199-6f9e-4c42-b81b-95ab509ae852.png)

- Logistic Regression With SMOTE
![image](https://user-images.githubusercontent.com/28688869/139131969-bf1c81ff-d231-4420-83a3-38ed7b447fa7.png)

- SVM Without SMOTE
![image](https://user-images.githubusercontent.com/28688869/139132063-9767b6b5-724f-4ea9-8dd9-36f8173a1c04.png)

- SVM With SMOTE
![image](https://user-images.githubusercontent.com/28688869/139132106-8d4d7abb-cce1-4e61-ab63-fa783fdf878a.png)

- Decision Tree Without SMOTE
![image](https://user-images.githubusercontent.com/28688869/139132161-5f5e1e7c-2476-4c85-b960-3528de31bfb4.png)

- Decision Tree With SMOTE
![image](https://user-images.githubusercontent.com/28688869/139132196-6543145b-8bfe-455f-9a06-5a1931b8544d.png)

## Phase 5: Model Evaluation
- Comparison of performance for Logistic Regression (without SMOTE vs SMOTE)
![image](https://user-images.githubusercontent.com/28688869/139132300-978dd36f-b12c-4271-b803-0f2c201bc151.png)

- Comparison of performance for Support Vector Machine (without SMOTE vs SMOTE)
![image](https://user-images.githubusercontent.com/28688869/139132376-ae4f90b3-6faf-459a-9d9f-331b656622bf.png)

- Comparison of performance for Decision Tree (without SMOTE vs SMOTE)
![image](https://user-images.githubusercontent.com/28688869/139132436-71179d5f-8945-4a06-b761-5f5771991e04.png)

## Conclusion
- In this section, we will focus on as per below details: 
  - 1. select the best machine learning model
  - 2. select the best method in treating imbalance class
  - 3. data visualization

- In a classification problem accuracy will be the criteria for model selection in contrast with regression which using error estmations to detemine the best model. Based on the testing results shown above we concluded that the best model is Decision Tree followed by Support Vector Machine and Logistic Regression. 
- Based on the SMOTE comparison the sensitivity for Decision Tree is the highest compared to Support Vector Machine and Logistic Regression. Eventhough the outcomes is similar for SMOTE and without SMOTE we have to ensure that the model do not bias towards the dominant class. Low Performer constitutes 80% from our target variable compared to High Perfomer 20% which is our main interest in the prediction.

![image](https://user-images.githubusercontent.com/28688869/139132641-d435cd73-7af1-421b-97ba-c083eae50d88.png)

