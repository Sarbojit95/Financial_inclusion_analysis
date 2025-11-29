<img width="475" height="228" alt="image" src="https://github.com/user-attachments/assets/d5f20bb3-90ef-4283-8b19-935e9f7bd295" />

What Drives Financial Inclusion Around the World?

Access to financial services has become an essential foundation for economic stability and opportunity. Having a bank account or mobile money account makes it possible for people to save securely, access credit, receive wages, and participate more fully in the economy.

But across the world, the level of financial inclusion varies dramatically. What explains these differences? And can we use data to predict account ownership more effectively?

Using the World Bank’s Development Indicators, I explored which social, economic, and digital factors are most strongly linked to financial inclusion. I also built a predictive model to estimate a country’s account ownership rate using these indicators.

This article summarizes the key insights in a non-technical way.

Business Questions

The analysis aimed to answer four practical questions:

Which factors are most strongly associated with financial account ownership?

How do digital access and socioeconomic conditions relate to inclusion levels?

What are the most important features used by the predictive model?

What would the model predict for a hypothetical country profile?

Each question is addressed below along with supporting visuals and results.

1. Which factors are most strongly associated with account ownership?

I first examined correlations and scatter plots between each indicator and account ownership. Some variables showed very clear upward trends, especially:

GDP per capita

Domestic credit to the private sector

Internet usage

School enrollment

Urban population share

Countries with higher income levels, better digital connectivity, and stronger access to education tended to show significantly higher account ownership rates.

Referenced visualization: Correlation heatmap + feature-target scatter plots

2. How do socioeconomic and digital factors influence inclusion?

To understand broader patterns, I reviewed the distribution of each key feature. Several variables showed a wide spread across countries, especially GDP per capita and digital access indicators.

The scatter plots revealed:

Internet usage has a strong increasing relationship with financial inclusion.

Countries with higher life expectancy and school enrollment also tend to have stronger account ownership.

Inflation behaves irregularly, with no strong linear pattern.

These findings support the idea that financial inclusion rises alongside broader social and economic development.

Referenced visualization: Histograms and scatter plots

3. Which features matter most in the predictive model?

To identify the most influential variables, I used feature importance from Random Forest and SHAP (Shapley values).

The consistently strongest features were:

Log GDP per capita

Log domestic credit to private sector

Internet usage

Secondary school enrollment

Urban population share

These features repeatedly ranked at the top across different models, giving confidence that they meaningfully explain account ownership differences.

Referenced visualization: Random Forest feature importance + SHAP summary plot

4. What does the model predict for a hypothetical country?

To see how the model behaves in practice, I created a fictional country with moderate income, improving digital access, and solid education and urbanization levels.

The model predicted an account ownership rate of about:

74 percent

This result is consistent with what we see in real-world data for countries with similar profiles. The estimate suggests that stronger digital connectivity and higher education levels can help push financial inclusion upward even when income levels are not extremely high.

Referenced visualization: Prediction output table

Conclusion

The analysis shows that financial inclusion is closely linked to a country’s economic strength, financial sector development, digital access, and educational outcomes. These factors collectively shape people’s ability to participate in the formal financial system.

While no model is perfect, the predictive approach provides a useful tool for estimating a country’s likely account ownership rate using only a handful of indicators. This can support policymakers, researchers, and development planners who want to understand where improvements could have the most impact.

Acknowledgements

The dataset comes from the World Bank’s World Development Indicators.
The analysis and code were completed independently as part of the Udacity Data Scientist Nanodegree.
