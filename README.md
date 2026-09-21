# Medical Charges Prediction

## 📌 Project Overview

A machine learning regression project that predicts medical charges for a customer based on their available characteristics.

The project focuses on understanding how linear regression works behind the scenes before using machine learning libraries to build the final models.

The notebook begins with a simple model using one feature and progressively introduces additional features as the regression process is explored. 
It clearly shows the impact of different machine learning concepts and data features on the estimate.

## 🎯 Problem Statement

Medical charges can vary significantly between customers depending on their individual characteristics.

The objective of this project is to build a regression model that can predict a customer's medical charges based on relevant features in the dataset.

The project also aims to understand the underlying mechanics of linear regression before relying on pre-built machine learning implementations.

## 📊 Dataset

The columns in the data are: 

| Column | Description |
| --- | --- |
| age | Customer age |
| sex | Gender |
| bmi | body mass index - derived from height and weight to estimate whether the body carries healthy weight |
| children | Amount of customer's children |
| smoker | Does the person smoke? yes or no |
| region | Place the record was created |
| charges | The price charged to the customer. (Target) |

## 🔎 Exploratory Data Analysis

The dataset is explored to understand the distribution of features and relationships between them and medical charges.

The findings are:
- Most of the data is on 18 and 19 year olds
- Most people have a bmi between 27 to 33 which is overweight
- Smokers spend more on medical charges compared to non-smokers
- The distribution of medical charges is right skewed with a long tail
- For non-smokers, no relationship exists between bmi and charges but for smokers a positive relationship exists

Visualizations used are histograms, boxplots, scatterplot, violin plot and heat map

## 📐 Understanding Linear Regression

Rather than immediately using a machine learning library, we first explore how linear regression 
works mathematically and computationally

#### Regression Function

A custom function is created to interpret the regression equation used by the linear regression algorithm.

The function demonstrates how predictions are generated using the features, weight and intercept.

The estimate is represented as:

```prediction = weight × feature + intercept```

#### Manually Fitting the Regression Line

The regression line is manually adjusted by changing:
- Weight
- Intercept

This demonstrates how the linear regression algorithm calculates the line of best fit used to produce estimates with minimal error.

## 📉 Model Loss

A user-defined Root Mean Squared Error (RMSE) function is implemented to measure the difference between the model's predictions and the actual medical charges.

This provides an understanding of how a regression model's loss/error can be calculated without relying on a machine learning library.

The RMSE is then used to assess how well different regression lines fit the observed data.

## 🔄 Modeling Progression

The project follows a gradual progression:

1. Understanding the regression equation   
2. Custom prediction function predicting one feature(age)  
3. Manually adjust weight and intercept  
4. Understand model loss  
5. Custom RMSE function  
6. OLS Linear Regression and SGD Regression  
7. Add more features  
8. Encode categorical columns  
9. Scale numerical columns  
10. Train final model  
11. Compare model performance

This progression connects the mathematical concepts behind linear regression with their implementation in machine learning libraries.

## 📈 Model Results

| Model | Features Used | RMSE |
| --- | --- | --- |
| Manual Regression | age of non-smokers | 4956 |
| OLS Regression | age of non-smokers | 4662 |
|   | age, bmi of non-smokers | 4662 |
|   | age, bmi, children of non-smokers | 4608 |
|   | age, bmi, children, sex(encoded), region(encoded) of non-smokers | 4573 |
|   |    |    |
|   | age of smokers | 10711 |
|   | age, bmi, children of smokers | 5718 |
|   | age, bmi, children, sex(encoded), region(encoded) of smokers | 5668 |
|   |    |    |
|   | age, bmi, children all | 11355 |
|   | age, bmi, children, smoker(encoded) all | 6056 |
|   | age, bmi, children, smoker(encoded), sex(encoded) all | 6056 |
|   | age, bmi, children, smoker(encoded), sex(encoded), region(encoded) all | 6041 |
|   | normalized(age, bmi, children), encoded(smoker, sex, region) all | 6041 |
| SGD Regression | age of non-smokers | 5097 |

The OLS model performed better than the SGD.  
The best score achieved after encoding and scaling all the cleaned data is 6041

## 💡 Key Learning Outcomes

Through the project, the following concepts are explored:
- How a linear regression algorithm generates predictions
- The role of weights and intercepts
- How changing model parameters affects predictions
- How regression error can be calculated using RMSE
- Manually fitting a regression line and its importance
- How OLS regression works through scikit-learn
- How SGD can be used for regression
- Impact of feature changes to a regression model
- The transition from manually implemented concepts to machine learning libraries

## 🚀 How to Run the Project

1. Clone the repository
```
https://github.com/gitcodmax/Prediction-of-medical-expenses.git
cd "project_folder"
```

2. Create a virtual environment
```
python -m venv venv
```

  Activate it on Windows:
  
```
venv\Scripts\activate
```
3. Install dependencies
```
 pip install pandas numpy scikit-learn matplotlib seaborn plotly
```

4. Run the notebooks  
Open the notebook using Jupyter Notebook or VS Code and execute them.

```                                          MMAX CODES                                                   ```
