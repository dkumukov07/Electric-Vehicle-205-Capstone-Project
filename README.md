# Electric Vehicle Data 205 Capstone Project  
## Author: Damir Kumukov  

## Project Overview  

Electric vehicle registrations across Maryland have grown rapidly in recent years. Statewide EV registrations increased by almost 88% between early 2024 and February 2026, showing that EV adoption is becoming a major transportation trend in Maryland.

The main question this project investigates is:

**Are charging stations keeping up with EV adoption, and what factors help explain differences in EV adoption across Maryland counties?**

Originally, this project looked at raw EV totals, but raw totals can be misleading because larger counties naturally have more people, more vehicles, more charging stations, and more EVs. To make the analysis more fair, the final model focuses on **EV adoption per capita** and **charging stations per 1,000 residents**.

This allows counties to be compared by adoption rate and infrastructure access rather than just total size.


## Datasets Used  

### EV Registration Data  
**Source:** MDOT/MVA  
- Monthly county-level EV registration data  
- Used to measure EV adoption across Maryland counties  
- Used for trend analysis and county comparisons  

### Alternative Fuel Stations Dataset  
**Source:** U.S. Department of Energy  
- Charging station snapshot from February 2026  
- Includes station locations and charger information  
- Used to measure charging infrastructure availability  

### Maryland Median Income Data  
**Source:** National Institute on Minority Health and Health Disparities  
- Median household income by Maryland county  
- Used to test whether income is related to EV adoption  

### Maryland Population by County  
**Source:** Data Montgomery  
- Population data for Maryland counties  
- Used to create normalized variables such as EV per capita and stations per 1,000 residents  

## Tools Used  

Python was used for all data cleaning, analysis, modeling, and visualization.

Main libraries used:

- pandas  
- numpy  
- matplotlib  
- seaborn  
- statsmodels  
- scipy  

## Data Cleaning  

Several cleaning steps were needed before analysis:

- Standardized county names across datasets  
- Converted station addresses into county-level data  
- Merged EV, charging station, income, and population datasets by county  
- Filtered the data to focus on EVs only  
- Created the EV-to-charger ratio  
- Created EV adoption rate using EVs per capita  
- Created charging access rate using stations per 1,000 residents  

The final dataset allowed each Maryland county to be compared using EV adoption, charging infrastructure, income, and population.

## Analysis  

The exploratory analysis looked at:

- EV growth over time  
- EV adoption differences by county  
- Charging station availability by county  
- EV-to-charger ratios  
- Charging infrastructure gaps  
- Median income and EV adoption  
- Charging access relative to population  

One important metric used in the project was the **EV-to-charger ratio**, which shows how much demand pressure each county’s charging infrastructure is handling. A higher ratio means more EVs are sharing each charging station.

For the final model, I used a rate-based regression approach instead of raw totals. This helped avoid the problem of larger counties dominating the results simply because they have larger populations.

## Final Model  
The final regression model was:

EV_per_Capita ~ Stations_per_1000 + Median_Income

Where:

EV_per_Capita = EV_Total / Population

Stations_per_1000 = (Charging_Stations / Population) * 1000

Why This Model Was Used

This model gives a fairer comparison between counties because it accounts for population size.

Instead of asking: Which counties have the most EVs?
The model asks: Which counties have higher EV adoption relative to their population, and how are charging access and income related to that adoption?
# Model Results
The model explained about 68.5% of the variation in EV adoption rates across Maryland counties.
# Charging Access
Stations per 1,000 residents had a positive coefficient, meaning counties with more charging access tended to have higher EV adoption rates. However, this variable was not statistically significant in the final model.
This means charging infrastructure still has a positive relationship with EV adoption, but the model does not provide strong enough evidence to say it is the strongest predictor once population and income are considered.
# Median Income
Median household income was positive and statistically significant.
This suggests that higher-income counties tend to have higher EV adoption rates. In this model, income was the stronger predictor of EV adoption rate.
# Key Findings
EV adoption is growing quickly across Maryland
EV adoption is not evenly distributed across counties
Large counties have high EV totals, but per capita analysis gives a fairer comparison
Charging access has a positive relationship with EV adoption, but it was not statistically significant in the final model
Median income was the strongest predictor of EV adoption rate
EV adoption appears to be both an infrastructure issue and an affordability issue
Some counties with high EV demand still face infrastructure pressure, shown by high EV-to-charger ratios
# Montgomery County Context
Montgomery County has the highest EV totals in Maryland and plays an important role in the overall EV story. However, because Montgomery County is also one of the largest and wealthiest counties in the state, raw EV totals alone do not fully explain adoption patterns.
The per capita model helps show that EV adoption should be understood not only by total registrations, but also by population size, charging access, and income.
External factors may also help explain Montgomery County’s EV leadership, including:
Strong county climate goals
Higher median household income
Dealership partnerships and EV promotion programs
Greater public awareness and policy support
Stronger demand for clean transportation options
# Main Conclusion
This project shows that Maryland’s EV transition is more complex than simply building more charging stations.
Charging infrastructure matters, but after adjusting for population, median income appears to be the stronger predictor of EV adoption rate. This suggests that affordability and economic access play a major role in which counties adopt EVs more quickly.
Overall, the project shows that Maryland’s EV future depends on both infrastructure planning and equitable access. Counties need enough chargers to support demand, but EV adoption will also depend on whether residents can afford to participate in the transition.
