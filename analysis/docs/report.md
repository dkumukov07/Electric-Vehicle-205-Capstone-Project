# Model Analysis: EV Adoption Rate

## Purpose

The goal of this model is to understand what factors are related to higher EV adoption across Maryland counties.

Instead of using raw EV totals, I used **EV per capita** so counties can be compared more fairly. Larger counties naturally have more people, chargers, and EVs, so using per capita helps control for county size.

## Model Used


EV_per_Capita ~ Stations_per_1000 + Median_Income


## Variables

**EV_per_Capita**
Measures EV adoption relative to population.

**Stations_per_1000**
Measures charging station access per 1,000 residents.

**Median_Income**
Measures the typical household income in each county.

## Results

```text
R² = 0.685
Adjusted R² = 0.654
Stations_per_1000 coefficient = +0.0114
Stations_per_1000 p-value = 0.148
Median_Income coefficient = +2.723e-07
Median_Income p-value = 0.000
RMSE = 0.0052
```

## Interpretation

The model explains about **68.5% of the variation** in EV adoption rates across counties.

**Stations per 1,000 residents** has a positive coefficient, meaning counties with more charging access tend to have higher EV adoption. However, the p-value is **0.148**, so this relationship is not statistically significant.

**Median income** is positive and statistically significant. This means higher-income counties tend to have higher EV adoption rates.

The p-value shows the relationship is meaningful.

## Regression Assumption Checks

For the final multiple linear regression model:

**EV_per_Capita ~ Stations_per_1000 + Median_Income**

I checked the main regression assumptions to make sure the model results were reasonable to interpret.

# 1. Linearity
A residuals vs fitted values plot was used to check whether the relationship between the predictors and EV adoption was approximately linear. The residuals were mostly centered around zero, with no major curved pattern, so the linearity assumption was considered reasonably met.

# 2. Normality of Residuals
A Q-Q plot of standardized residuals was used to check whether the residuals were approximately normally distributed. Most points followed the diagonal line, with a few deviations at the upper end. This suggests the normality assumption was mostly reasonable, but not perfect.

# 3. Equal Variance
The residuals vs fitted values plot and the Breusch-Pagan test were used to check whether the residuals had roughly equal spread. The assumption was considered reasonably met if the residual spread did not show a major funnel shape and the Breusch-Pagan p-value was above 0.05.

# 4. Independence
Each Maryland county was treated as one separate observation. The Durbin-Watson statistic was also used as a basic check for residual independence. Since this is county-level cross-sectional data, independence is a reasonable assumption, but nearby counties may still share regional patterns.

# 5. Multicollinearity
Variance Inflation Factor (VIF) was used to check whether the predictors were too highly related. Since the final model only used Stations_per_1000 and Median_Income, VIF helped confirm whether each predictor contributed separate information.

Overall, the assumptions were reasonably met. However, because the model only includes 23 Maryland counties, the regression results should be interpreted as evidence of patterns rather than proof of causation.

## Main Takeaway

This model suggests that EV adoption is not only about charging infrastructure. Once population is accounted for, **income becomes the stronger predictor of EV adoption rate**.

Charging access still has a positive relationship, but income appears to explain adoption more clearly in this model.

## Conclusion

After adjusting for population, EV adoption in Maryland appears to be strongly connected to income. This suggests that affordability and economic access are important parts of the EV transition, not just the number of charging stations.
