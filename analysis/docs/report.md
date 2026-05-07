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

## Main Takeaway

This model suggests that EV adoption is not only about charging infrastructure. Once population is accounted for, **income becomes the stronger predictor of EV adoption rate**.

Charging access still has a positive relationship, but income appears to explain adoption more clearly in this model.

## Conclusion

After adjusting for population, EV adoption in Maryland appears to be strongly connected to income. This suggests that affordability and economic access are important parts of the EV transition, not just the number of charging stations.
