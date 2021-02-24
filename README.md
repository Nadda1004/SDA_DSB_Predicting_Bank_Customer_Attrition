# Predicting Bank Customers Attrition 
### Table Of Content 
<li><a href="#Installation">Installation</a></li>
<li><a href="#Motivation">Motivation</a></li>
<li><a href="#data">Data</a></li>
<li><a href="#EDA">Exploratory Data Analysis (EDA)</a></li>
<li><a href="#Results">Results</a></li> 
<li><a href="#Conclusion">Conclusion</a></li>

<a id='Installation'></a>
## Installation
* Python 3.7.10
* Pandas
* Plotly
* Matplotlib
* Seaborn
* SKlearn

<a id='Motivation'></a>
## Motivation
Customer attrition which is also known as customer churn, customer turnover is defined as the loss of customers in a business, it is one of the biggest concerns especially in banking since customers are considered as the most valuable part of it.
We are using the bank customer’s data to predict possible attrited customers using Machine Learning to help prevent any possible attrition that may happen in the future.
* [Code](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Predicting_Bank_Customer_Attrition.ipynb) 
  * **Note: I highly encourage you to open the code in colab to view and interact with the plots**
* Medium Story: [Predicting Attrited Bank Customers Using Machine Learning](https://nadda1004.medium.com/predicting-attrited-bank-customers-using-machine-learning-33a1c3042c6a)

<a id='data'></a>
## Data:
* Source: Kaggle: [Credit Card Customers](https://www.kaggle.com/sakshigoyal7/credit-card-customers)
* File: [Credit Card Customers](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Data/BankChurners.csv)
* [Data Dictionary](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Data/BankChurners_%20Data%20Description.pdf)

<a id='EDA'></a>
## Exploratory Data Analysis (EDA)
* **Columns info**
  * The Data has 10271 smaples and 20 feature with no null values or duplicates.
  ![columns](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/columns.PNG)
* **Class Distribution**
  * The data is split into 2 classes that identified the customer attrition status: Existing Customer, Attrited Customer. Existing Customers represent 83.9% of our sample and the Attrited Customers represent 16.1%, we clearly see that the class ratio is imbalanced which might make it difficult for the model to identify attrited customers.
  ![Class Distribution](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/class.png)
* **Age Range**
  * The highest number of Attrited customers are in the age between 40–54 years, and the lowest numbers are customers in the age between 65–69 years.
  * The highest number of Existing customers are in the age between 40–54 years, and the lowest numbers are customers in the age between 75–79 years.
  ![age](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/age.png)
* **Credit Card Type**
  *  The highest number of attrited and existing customers are blue cardholders, and the lowest number of attrited and existing customers are platinum cardholders.
  ![credit card level](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/card.png)
* **Annual Income**
  * The highest number of attrited and existing customers have less than 40K dollars as an annual income, and the lowest number of attrited and existing customers have more than 120K dollars as an annual income.
  ![Annual Income](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/annaul_income.png)
* **Period Of Relationship With The Bank**
  * The longest period that existing and attrited customers spent with the bank is between 35–39 months, and the shortest period of they spent is between 10–14 months.
  ![relationship](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/relationship.png)

<a id='Results'></a>
## Results 
  * The Baseline Model Scored 0.8460, which was expected since the most accruing class was the existing customer. After the ensemble method, the Random Forest Classifier had the highest-scoring model with 0.968 accuracies, and after tuning it using GridSearchCV we achieved a 0.969 accuracy. The plot below shows the different metrics used to evaluate the baseline model, the Random Forest and the Random Forest after the GridSearchCV (After GridSearchCV).
  * The Random Forest model after the GridSearchCV had the highest accuracy and highest precision, but the original Random Forest model got the highest recall.
This means that the Random Forest model after GridSearchCV identified the attrited customers better than the original model, but the original model identified the existing customers better as you can see also in the confusion matrix below.
![comparing models](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/comp.png)

* **Confusion Matrix**
  * It seems like the model after the GridSearchCV was correctly identifying the attrited customer as shown in the TP (True Positive) part, but identified the existing customers less than the original model as shown in TN (True Negative).

Baseline Model             |Random Forest Model             |Random Forest After GridSearchCV             
:-------------------------:|:-------------------------:|:-------------------------:
![confusion matrix baseline](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/cf_baseline.png)  |  ![confusion matrix random forest](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/cf_rf.png)  |  ![confusion matrix random forest after grid](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/cf_rf_g.png)

* **Roc Curve**
* As seen in the ROC curve the Random Forest After GridSearch got a higher false-positive rate than the normal Random Forest Model between 0 and 0.1 on the false positive rate axes, which means that the positive class (the existing customer) was identified falsely in the model after GridSearchCV which also can be seen in the confusion matrix above in FP and TP.
![roc](https://github.com/Nadda1004/SDA_DSB_Predicting_Bank_Customer_Attrition/blob/main/Images/roc.png)

<a id='Conclusion'></a>
## Conclusion 
The Best attrition predicting model was the **Random Forest after the GridSearchCV** with 96.94% accuracy, 99.01% Recall, and 97.42% precision.

By:
Nada Alzahrani
