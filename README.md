# Data Analyst Salary Estimator: Project Overview
- Built a model that estimates data analyst salaries with an (MAE of $12K).
- Scraped over 500 job listings from glassdoor using python and selenium.
- Extensive data cleaning was essential to refine the scraped data, making it suitable for accurate analysis and interpretation.
- Fine-tuned model parameters using GridSeachCV to achieve optimal performance.
- Deployed the trained model as a client-facing API using Flask.
***

## Table of Contents
- [Introduction](#Introduction)
- [Project Requirements and Prerequisites](#Project-Requirements-and-Prerequisites)
- [Methodology](#Methodology)
  - [Scraping Data](#Scraping-Data)
  - [Data Cleaning](#Data-Cleaning)
  - [Exploratory Data Analysis](#Exploratory-Data-Analysis)
  - [Building Model](#Building-Model)
  - [Model Evaluation](#Model-Evaluation)
  - [Deploying Model](#Deploying-Model)
***

## Introduction
Understanding the landscape of the Data Analyst job market, from typical salary ranges to the factors that drive them, is crucial for individuals navigating their careers. This project aims to shed light on these dynamics by collecting and rigorously analyzing a substantial dataset of Data Analyst job listings from Glassdoor. Beyond simply predicting compensation, a key focus of this endeavor is to visually represent the trends and relationships within the data, offering a clearer understanding of the forces shaping this evolving field.

The culmination of this project is a two-fold offering: a machine learning model capable of estimating Data Analyst salaries, and a suite of insightful data visualizations. The predictive model is deployed as a API via Flask, while the visualizations serve to reveal key market trends and provide a deeper understanding of the factors influencing salaries. Together, these components empower users with data-driven insights for more informed career decisions and a comprehensive view of the Data Analyst job market.
***

## Project Requirements and Prerequisites
This project requires the following tools and software packages:

### Tools:
`Python 3`: Necessary for Web scraping, data cleaning, EDA, and Building model

### Python Packages:
- `NumPy`, `Pandas`: For Data Cleaning, Manipulation, and Analysis.
- `Matplotlib`, `Seaborn`: For Data Visualization.
- `Sklearn`: For Data Preprocessing and Building regression models.
- `Statsmodels`: For Building regression model.
- `Selenium`: For Web scraping.
- `Flask`: For Productionization.

### Clone the Repository and Install Python Dependencies
1. Open terminal or command prompt and navigate to the directory where you want to store the project
```bash
cd directory_name
```
2. Run the code below to clone the repository
```bash
git clone https://github.com/Keshwar02/Data-Analyst-Salary-Estimator.git
```

3. Navigate to the project directory. This is necessary so that subsequent commands(like installing dependencies) are executed within the context of the project
```bash
cd repository_name
```

4. Installing Python Dependencies
```bash
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels selenium flask
```
***

## Methodology
This is an End-to-end ML project encompassing web scraping from a website with significant data inconsistencies, followed by rigorous data cleaning and preprocessing. Three different ML models were explored to build a salary estimation tool, which is then deployed for practical use.

Let's take a closer look at each stage of the methodology.

### Scraping Data
Job listings data was gathered from Glassdoor using Selenium and Python following features were extracted from Glassdoor Jobs
- Job title
- Company name
- Rating
- Location
- Salary estimate
- Company size
- Company type
- Founding year
- Sector
- Industry
- Revenue
***

### Data Cleaning
After scraping the data. Cleaned data to ensure its quality and consistency, thereby making it suitable for analysis and modeling. This process involved addressing inconsistencies and standardizing formats across the dataset. 

Extracted data has no missing values and duplicate records. Following changes were made:

- **Salary Parsing**
- **Creating 3 new columns from salary estimate column**
- **Transformed founded date into age of the company**
***

### Exploratory Data Analysis (EDA)
As the data clean and consistent, In this phase of the project we explore the data to uncover patters, relationships, and gain initial insights into Data Analyst job market and salary trends.

**Objectives in EDA**
- Analyze the distribution of job postings across different job titles.
- Determine the distribution of job postings across various seniority levels(e.g., Junior, Senior, Intern).
- Investigate the geographical distribution of available Data Analyst positions.
- Examine the distribution of key variables such as ratings, average salary, and company age.
- Analyze the correlation between features
- Visualize the frequency of different categories within the categorical features using bar plots.
- Summarize data using pivot tables, such as average salary by job title, seniority, etc.
***

### Building Model
In this part of the project aim to develop a predictive model to estimate Data Analyst salaries. This process include the following key steps:
1. First, Identify and select the most relevant features
2. Converting categorical variables into dummy variables
3. Dividing the dataset into training and testing sets to evaluate the model's performance on unseen data
4. Training and evaluating several regression models
   - **Linear Regression** - As a bseline model for perdiction.
   - **Lasso Regression** - Linear model with L1 regularization for feature sparsity.
   - **Random Forest Regressor** - Ensemble of decision trees for robust prediction
5. Fine-tuned Random Forest model parameters using GridSeachCV to achieve optimal performance.
***

### Model Evaluation
The performance of the trained models was evaluated using the Mean Absolute Error (MAE) metric. MAE was chosen as it provides a straightforward measure of the average absolute difference between the predicted and actual salaries, offering an easily interpretable understanding of the model's prediction accuracy.
- **MAE of Linear Regression :** $18.89K
- **MAE of Lasso Regression :** $19.93K
- **MAE of Random Forest Regressor :** $12.31K
***

### Deploying Model
To make the salary estimation model accessible, a client-facing API was developed using Flask. The API endpoint is designed to receive job listing details as input (as a list of values corresponding to the features used in the model) and, in response, returns the estimated salary predicted by the trained model. This allows for easy interaction with the model for real-time salary predictions.
