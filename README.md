# ImperialCollege
# Projected correlation of temperature and sea level rises


## NON-TECHNICAL EXPLANATION OF YOUR PROJECT

The aim of this project is to understand the correlation of projected temparatures and sea level rises in the UK that may pose risk to assets.
As the climate is changing, climate factors may influence one another and in turn, increases certain risks to assets. These risks have to be taken into consideration so that effective mitigation strategies are put into place to reduce these risks, and if not account them in the valuation of those assets. 
This project can be treated as a short proof of concept to test some assuptions.
The assumptions made are:
1. Increase of temperatures globally will increase sea level rises
2. Increase of temperatures globally will result into UK temperature increases

## PROBLEM DEFINITION

Given the nature of your project, this appears to be a regression problem. The goal is to predict continuous outcomes like changes in sea levels or asset values based on temperature projections, making regression the suitable method.

## DATA

The data used for this short project are downloaded from the UK MET Office Climate Data Portal. 
https://climatedataportal.metoffice.gov.uk/search?tags=UK%2520projections%2520temperature

## WHY 

I am passionate about climate change and how climate and nature related factors will influence assets across operations and supply chain.
With over 20 years of experience in the financial services, working with data to market, credit, counterparty, and compliance risk analytics intelligence for financial institutions and corporatations, the next step is incorporating climate and nature factors for effective decision making purposes.  
The machine learning algorithms covered in the Imperial College Business School Machine Learning and Artificial Intelligence course have provided a holistic understanding of a variety of algorithms (tools) available to assess and understand how to be used and when.


## MODEL 

Here are a few models that could be appropriate for this task, along with their pros and cons:

Linear Regression
Pros: Simple, interpretable, few hyperparameters.
Cons: Assumes a linear relationship; might be too simplistic for complex interactions in climate data.

Polynomial Regression
Pros: Can model non-linear relationships.
Cons: Prone to overfitting, especially with high-degree polynomials.

Decision Trees and Random Forests
Pros: Capable of capturing non-linear relationships, handle mixed data types well.
Cons: Can overfit, especially with deep trees; random forests have more hyperparameters to tune but are generally robust.

Gradient Boosting Machines (GBM)
Pros: Strong predictive power, handles various types of data, can capture complex patterns.
Cons: Many hyperparameters to tune, more prone to overfitting without careful tuning, less interpretable.

Support Vector Machines (SVM) for Regression
Pros: Effective in high-dimensional spaces, robust against overfitting in moderate-dimensional spaces.
Cons: Requires good choice of kernel and regularisation term, not very intuitive, computationally intensive for large datasets.


## MODEL SELECTION

For the purpose of this project, I have chosen polynomial regression for simplicity reasons but also to capture non-linear relationships


## HYPERPARAMETER OPTIMSATION

The hyperparameters that can be optimised are:
1. The degree of the polynomial is the most critical parameter to tune in polynomial regression:
Higher degrees allow the model to fit more complex, non-linear data but can lead to overfitting, especially if the degree is too high for the amount of data available.
Lower degrees provide a simpler model that might underfit complex datasets but will generalize better on unseen data.

In this case, we can start with two or three degrees.

2. Regularisation Technique: especially with higher degrees, it's advisable to use some form of regularization to prevent overfitting. 


## RESULTS

Summary insights: The model suggests that there is a strong correlation between the combined effect of UK and global temperatures and sea level rises. This could be crucial for planning and mitigation strategies in response to climate change, especially in predicting the impact on coastal and low-lying areas.

R² Score (0.991): This score is very close to 1, which indicates that the model explains nearly all of the variability in sea level anomalies around their mean. In other words, the model does an excellent job at capturing the relationship between the input temperatures and sea level changes.

Mean Squared Error (0.197): This is quite low, suggesting that the model's predictions are very close to the actual data points. The smaller the MSE, the closer the fit is to the data. 

By tuning the parameters, the optimal polynomial degree is 5 and best Ridge Alpha is 0.1

## CODE
The code can be viewed in this attached Jupyter Notebook file.

## NEXT STEPS

As part of next steps I would model the summer and winter UK temperaturs vs global temperatures. It seems that the average UK temperature will drop which alignes with the predictions of AMOC's beheviour. The melting of the ice sheets, will prevent AMOC warming up the UK. Understanding further the climate changes, will enable companies and the government take appropriate action and adjust operations, supply chain and infrastructure accordingly. This includes and not limited to investments, strategies and scope of projects.


