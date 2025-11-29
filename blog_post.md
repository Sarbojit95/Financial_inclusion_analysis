<img width="475" height="228" alt="image" src="https://github.com/user-attachments/assets/d5f20bb3-90ef-4283-8b19-935e9f7bd295" />

What Drives Financial Inclusion Around the World?

Access to financial services has become an essential foundation for economic stability and opportunity. Having a bank account or mobile money account makes it possible for people to save securely, access credit, receive wages, and participate more fully in the economy.

But across the world, the level of financial inclusion varies dramatically. What explains these differences? And can we use data to predict account ownership more effectively?

Using the World Bank’s Development Indicators, I explored which social, economic, and digital factors are most strongly linked to financial inclusion. I also built a predictive model to estimate a country’s account ownership rate using these indicators.

This article summarizes the key insights in a non-technical way.

Business Questions

The analysis aimed to answer four practical questions:

What factors are most strongly associated with higher financial account ownership among countries?

Does digital access play an important role in predicting account ownership??

Can we build a model that reliably estimates account ownership for a country based on its economic and digital indicators?

What would the model predict for a hypothetical country profile?

Each question is addressed below along with supporting visuals and results.

Q1. Which factors are most strongly associated with account ownership?

Based on the shap model outputs and correlation plots above, the variable most strongly associated with higher account ownership is GDP per capita. It both has highest SHAP value and also shows strongest positive correlation with target. Hence Countries with higher income levels tend to have much higher financial inclusion. Other features like domestic credit to the private sector, Internet usage, school enrollment, and urban population also show a meaningful positive association according to SHAP plots, suggesting that these also help drive financial account ownership to a certain extent.

<img width="1040" height="391" alt="image" src="https://github.com/user-attachments/assets/ed2ef6f5-4c3b-4b2b-85f2-97e1f4fe6797" />
<img width="617" height="326" alt="image" src="https://github.com/user-attachments/assets/6f8a2f14-410a-4ccf-b64b-c06fd66affea" />



Q2. How do digital factors influence inclusion?

The correlation plots and the shap plots in previous question show that digital access plays an important role. Internet usage has one of the highest correlations with account ownership, and it remains a predictor in the tree-based models and in the SHAP values. While mobile subscriptions also help, they do not appear to be as strong as internet usage. Overall, the results suggest that improving access to digital connectivity can support financial inclusion.

<img width="1388" height="1235" alt="image" src="https://github.com/user-attachments/assets/d54b0276-30da-4d50-8fa6-c4514d74a364" />
<img width="1040" height="391" alt="image" src="https://github.com/user-attachments/assets/c8b9fa55-6c41-48c2-817e-9212fce1e9bf" />


Q3. Can we build a model that reliably estimates account ownership for a country based on its economic and digital indicators?

Using several regression models (Random Forest, Gradient Boosting, Ridge, Lasso, etc.), the Random Forest model performed the best, achieving an R² of about 0.72 on the test set. This means the model can explain roughly 72% of the variation in account ownership between countries. The most influential predictors in the model were log-transformed GDP per capita, log domestic credit, internet usage, school enrollment, and urban population. This shows that a predictive model can indeed be used to estimate financial inclusion levels using publicly available indicators.

<img width="378" height="236" alt="image" src="https://github.com/user-attachments/assets/de457228-0af3-4cc1-947a-23976b683250" />


Q4. What does the model predict for a hypothetical country?

To demonstrate how the model can be used in practice, consider a hypothetical country that wants to estimate its expected level of financial account ownership. Let this country have the following characteristics:

GDP per capita: 7,500 USD

Domestic credit to private sector: 60 percent of GDP

Internet usage: 65 percent of the population

Urban population: 55 percent

School enrollment (secondary): 85 percent

Life expectancy: 72 years

Mobile subscriptions: 110 per 100 people

The model has predicted the value of 74.19

The model estimates that this hypothetical country would have an account ownership rate of about 74 percent among adults. This value is consistent with the patterns observed in the dataset, where countries with moderate income levels, improving digital access, and reasonable levels of education and urbanization tend to fall in the 70–80 percent range.

A predicted value of around 74 percent suggests that the country is performing fairly well in terms of financial inclusion, but there is still room for progress. The relatively strong internet usage, secondary school enrollment, and life expectancy help push the prediction upward, while the moderate levels of GDP per capita and domestic credit keep the estimate below the highest-performing countries.

This example shows how the model can be used to estimate a country’s likely financial inclusion level based on measurable economic and demographic indicators. It provides a way for policymakers to assess where they stand and identify which improvements—such as expanding digital access or strengthening the financial sector—could potentially increase account ownership further.

Conclusion

The analysis shows that financial inclusion is closely linked to a country’s economic strength, financial sector development, digital access, and educational outcomes. These factors collectively shape people’s ability to participate in the formal financial system.

While no model is perfect, the predictive approach provides a useful tool for estimating a country’s likely account ownership rate using only a handful of indicators. This can support policymakers, researchers, and development planners who want to understand where improvements could have the most impact.

Acknowledgements

The dataset comes from the World Bank’s World Development Indicators.
The analysis and code were completed independently as part of the Udacity Data Scientist Nanodegree.
