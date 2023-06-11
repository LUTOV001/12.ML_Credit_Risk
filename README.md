# **UCB FinTech Bootcamp Module 12 Challenge**
# *Machine Learing (ML) for Credit Risk Analysis*
## **Introduction**
### The Bootcamp Module 12 Challenge - Machine Learning for Credit Risk Analysis requires the preparation and analysis of a Machine Learning (ML) model used to predict the risk classification (status) of a loan based on the provided original data for Loans and their features. The quality of the model and its predictions has to be prepared using ML metrics and analysis such as accuracy, confusion matrix and classification reports.
---
## **Goals and Objectives**
### *Part I.*  : Create a Logistic Regression model with the orginal data in the provided file with loan data in the Resources folder (lending_data.csv)
### *Part II.*  : Train the model and Test it by predicting the Loan Status (e.g Healthy or High Risk Loan). Analyze the quality of the model using model metrics such as accuracy, confussion matrix taking into accont the quality of the original data (e.g balanced vs. unbalanced)
### *Part III.* : Resample the data and create a new model to predict the Loan status with the updated data set and analyze the quality of the model and its prediction results
### *Part IV.* : Provide a report with your findings and recommendations
### 
---
## **Technologies and Tools**
### The following list includes the main technologies and tools using during the preparation and deployment of the solution:
### 1. *Python* - Programming language used to code the solution. Version 3.7.13 was used. Required libraries and frames listed in the Installation section below
### 2. *GitHub* - Reposotory for code deployment, version management and documentation of the presented solution
### 3. *Jupyter Labs* - IDE tool for coding, code testing/debugging and solution documentation. Version V3.4.4 was used
### 4. *Git Bash console* - Local console used to test the coded solution and sync wiht GitHub Version 2.40.0.windows.1 was utilized
### 5. *Slack* - Collaboration tool to communicate and brainstorm with other FinTech Bootcamp participants
### 6. *Operative System* - This solution was prepared in a PC running Windows 11 v H22
### For additional details, please refer to the watermark output at the bottom of the ***ml_credit_risk_resampling.ipynb*** Jupyter Notebook
---
## **Installation Guide**

### 1. [sklearn](https://scikit-learn.org/) : scikit-learn, also known as sklearn, is a popular open-source machine learning library for Python. It provides a wide range of machine learning algorithms, tools, and utilities for tasks such as classification, regression, clustering, dimensionality reduction, model selection, and preprocessing of data. To install, follow these steps:
#### 1.1. Open the GitBash terminal
#### 1.2 Type the following command and press Enter:
```python 
pip install scitkit-learn
```
### 2. [Imbalanced-learn](https://imbalanced-learn.org/) :  Imbalanced-learn (imported as imblearn) is an open source, MIT-licensed library relying on scikit-learn and provides tools when dealing with classification with imbalanced classes.
#### 2.1. Open the GitBash terminal
#### 2.2 Type the following command and press Enter:
```python 
pip install imbalanced-learn
```
---
## **Solution Structure**

### The **[12.ML_Credit_Risk](https://github.com/LUTOV001/12.ML_Credit_Risk)** repository in GitHub contains the solution components. The repository consists of the following folders and contents as described below:
 
###   1. Resources : Contains the .csv file with the credit lending data which serve as the basis for the analysis. 
###   2. gitignore : Instructions for which files/file types to exclude from the sync process between GitHub and the local environment.
###   3. README.md : The present file containing this outline of the challenge and its components.
###   4. *ml_credit_risk_resampling.ipynb* : This is the Jupyter Notebook with the code for the core challenge solution, analysis and conclusions based on the data available in the Resources folder.
###   5. final_report.md : Contains the findings and recommendations from the challenge
###
---
## **User Instructions**
### 1. Launch the Jupyter Lab from the GitBash terminal using the following command line:
```python 
jupyter lab
```
### 2. From the Jupyter Lab terminal, navigate to the location of the ***ml_credit_risk_resampling.ipynb*** notebook and open it
### 3. Reset the Kernel and
### 4. Run the steps from the top and in sequence verifying the results as per the comments in the notebook, including outputs on the screen such as dataframe listing/on screen printing and generated reports, such as the confusion matrix and the classification reports to assess the quality of the models and the answers to the specific questions in the challenge.
####
---
## **Credits**

### Prepared by Luis Torres 
### [LUTOV001](https://github.com/LUTOV001)
### June 2023
