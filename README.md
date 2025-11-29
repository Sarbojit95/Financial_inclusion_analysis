Financial Inclusion Prediction Using World Bank Indicators

Project Motivation

Financial inclusion is an important measure of how well people can access formal financial services such as bank accounts, savings, and mobile money. Many countries still show large gaps in account ownership, and understanding the factors behind these differences can help policymakers target improvements.

In this project, I use World Bank Development Indicators to explore the socioeconomic and digital factors related to financial account ownership. The goal is to understand which variables matter most and to build a regression model that can predict the percentage of adults who own an account in a given country.

This project follows the CRISP-DM process: understanding the data, preparing it, exploring patterns, building models, evaluating them, and drawing conclusions.

Project Files

The repository contains the following files:

financial_inclusion_analysis.ipynb
The main Jupyter notebook with all steps: data cleaning, exploratory analysis, feature engineering, model building, evaluation, and interpretation.

WDI_Data.csv
The dataset used for modeling is downloaded by selecting some features from the original World Bank indicators dataset.

blog_post.md
It contains the blog post neccessary for the project.

README.md
This document explaining the project motivation, setup, results, and acknowledgements.

(Additional images or plots may appear in the repo if needed for the blog post or documentation.)

Libraries Used

The project uses standard Python data-science libraries:

pandas

numpy

matplotlib

seaborn

scikit-learn

xgboost

shap

These were used for data preparation, visualization, modeling, and model interpretation.

Summary of the Analysis

After cleaning and restructuring the data, I focused on predicting:

Account ownership at a financial institution or with a mobile-money-service provider (% of population ages 15+).

I created engineered features (log-transformed GDP per capita and domestic credit, plus an interaction between internet usage and urban population), handled missing values, and scaled the numerical features where appropriate.

Exploratory analysis showed that financial inclusion is strongly associated with income level, credit availability, internet access, education, and urbanization. Several features showed clear increasing patterns when compared to account ownership.

Multiple regression models were tested using cross-validation and GridSearchCV. The best test-set performance came from the Random Forest Regressor, with the following approximate scores:

R² ≈ 0.72

MAE ≈ 9.05

RMSE ≈ 13.25

These results indicate that the model can explain a significant portion of global variation in account ownership using only a small set of indicators.

SHAP plots and feature importances show that the most influential factors were:

log GDP per capita

log domestic credit to private sector

internet usage (% of population)

school enrollment (secondary % gross)

urban population (%)

Predictive Scenario

I created a hypothetical country profile to test the model’s behavior. The model predicted that this country would have an account ownership rate of around 74 percent. This aligns with the characteristics of countries that have moderate income, improving internet access, and relatively strong education levels.

This scenario demonstrates how the model could support policy analysis by estimating expected financial inclusion levels based on measurable indicators.

Acknowledgements

The dataset was obtained from the World Bank Development Indicators resource.
I referred to common Python documentation, StackOverflow responses, and general data-science references where needed. All modeling, analysis, and writing were completed independently for this project.
