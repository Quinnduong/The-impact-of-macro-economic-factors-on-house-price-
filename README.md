This project explores the relationships between house prices in the U.S. and various macroeconomic factors, analyzing data from 1987 to 2021. By employing econometric modeling techniques, it identifies key drivers such as stock prices, consumer price index (CPI), disposable income, unemployment rate, and interest rates, and assesses their effects on the housing market.

## Project Overview

### Objectives:

Identify the macroeconomic determinants of U.S. house prices.

Regression equation: <img width="677" alt="Screenshot 2024-09-18 at 1 52 19 PM" src="https://github.com/user-attachments/assets/806c8fad-ae2a-457f-aef2-1a014c9b5957">

Build and test econometric models to quantify these relationships.

Provide insights into which factors are most influential in explaining house price variations.

### Data:

Time frame: January 1987 - December 2021

Source: Public datasets from Kaggle, World Bank, and FRED.

Variables: House Price Index, Stock Price Index, Consumer Price Index, Population, Real Disposable Income, Unemployment Rate, Mortgage Rate, and Real Interest Rate.

Results Summary

### Key Findings:
Income Per Capita and Unemployment Rate were the strongest predictors of house prices, explaining 92% of the variation in the House Price Index.

Stock prices and CPI had significant positive effects on house prices.

A higher unemployment rate correlates with lower house prices.

Mortgage and real interest rates have negative relationships with house prices.

Addressing multicollinearity and serial correlation was essential in refining the regression models.

### Methodologies and Analysis:

<img width="806" alt="Screenshot 2024-09-18 at 1 06 23 PM" src="https://github.com/user-attachments/assets/7a1c5de4-7e7f-448f-bc08-b537c488266d">

Descriptive Statistics: Summarizes the eight economic indicators across the 420 months studied.

<img width="935" alt="Screenshot 2024-09-18 at 1 07 34 PM" src="https://github.com/user-attachments/assets/e1d9a9c7-df2b-4490-8543-f3fc7fc470a3">

Correlation Matrix: Highlights strong relationships between variables, particularly between the Consumer Price Index, Population, and Disposable Income.

Regression Results: Display the impact of each variable on house prices. 

![image](https://github.com/user-attachments/assets/edc83c5f-af35-4b64-8631-1e3a3d4fce7c)

Although, overall, it appears that all the models have good performance of how each factor impacts on house price and they are also significant with very small p-values. 
In this case, Model 5 has the highest R-squared value so it would be considered the best-fitting model among the ones we've presented.

Since Unemployment_Rate has a very weak correlation with other independent variables, we consider adding this variable in Model 5, which is Model 6. 

![image](https://github.com/user-attachments/assets/77a75194-af5d-4b43-b882-483f63e6dc52)

Table IV demonstrates a comparison table of Model 5 and Model 6.
We can notice that Model 6 has a better performance since all the independent variables in this model are significant at 1% and it also has a slightly higher R-squared.
With Model 6, in terms of magnitude, on average, 1% increase in Income_Per_Capita is associated with a 2.091% increase in the dependent variable (loghpi), holding all else as constant. Here, when we add another independent variable, the coefficient estimate of in Income_Per_Capita does not change. 
On average, a one-unit increase in Unemployment_Rate is associated with a 1.2% decrease in the dependent variable (loghpi), holding all else as constant.
Model:

<img width="393" alt="Screenshot 2024-09-18 at 1 19 03 PM" src="https://github.com/user-attachments/assets/ebaa122f-d724-478f-9e25-4dbb218acb3d"> 

Assumption: No serial correlation. Conduct testing for autocorrelation by using Durbin-Watson test and AR1 (graphic method)

Hypothesis Testing:

<img width="205" alt="Screenshot 2024-09-18 at 1 20 30 PM" src="https://github.com/user-attachments/assets/e392c423-9e8d-4710-9968-091c1bb00bb5">



DW TEST

<img width="511" alt="Screenshot 2024-09-18 at 1 38 09 PM" src="https://github.com/user-attachments/assets/444ecbaf-0af2-4a39-885f-3b768073b4bf">

AR1: 

<img width="729" alt="Screenshot 2024-09-18 at 1 21 52 PM" src="https://github.com/user-attachments/assets/95bbffdd-f366-42c7-a622-ecd17c25c7c6">

 
Correcting for the autocorrelation: 

First Differencing Method

<img width="493" alt="Screenshot 2024-09-18 at 1 41 22 PM" src="https://github.com/user-attachments/assets/33d0558b-403b-497d-ae29-4d1d217b2429">

Prais_winsten Method:

<img width="459" alt="Screenshot 2024-09-18 at 1 42 48 PM" src="https://github.com/user-attachments/assets/63f21a41-acfe-49d5-a0a5-b3410f444b69">

Test for Homoscesdasticity using the BreuschPagan test: 

Hypothesis Test: H0: Homoscedasticity, Ha:Heteroscedasticity 

The result of the Breusch-Pagan test indicates that we also reject the null hypothesis which means we detect 
heteroscedasticity since we achieve a very small p-value (4.141e-07). 

##Solution: Robust standard error

The model was checked for multicollinearity, autocorrelation, and heteroscedasticity. Adjustments were made using the Newey-West method for robust standard errors.


















