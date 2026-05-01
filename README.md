# Electric Vehicle Data205 Capstone Project
# Author: Damir Kumukov
# Project Overview
Electric vehicle registrations across Maryland grew by almost 88% between early 2024 and February 2026, from ~72,000 to over 136,000 vehicles statewide. But the main question this project investigates is:
Are charging stations being built fast enough to keep up with EV adoption, and does charger type and income level change that answer?
To answer this, I merged three datasets, did exploratory data analysis across all 23 Maryland counties, and built three regression models linking EV registrations to charging infrastructure and median household income.
# Datasets Used
EV Registration Data (MDOT/MVA)
Monthly data from 2020-2025
County-level EV counts
Used for trend analysis
Alternative Fuel Stations (U.S Department of Energy)
Snapshot from February 2026
Includes station locations and charger types
Used to measure infrastructure availability
Maryland Income Table (National Institute on Minority Health and Health Disparities)
Had median household income from all 23 counties in MD 
# Tools Used in This Project
Python was used for all analysis and visualization. The main libraries used were pandas for data manipulation, matplotlib and seaborn for visualizations, scipy and statsmodels for statistical testing and regression modeling
# Analysis
The exploratory data analysis looks at EV growth over time, the gap between EV registrations and charging station counts, the relationship between income and EV adoption, and how charger type distribution varies by county. An importantfeature throughout the analysis that I made is the EV per station ratio, which captures how much demand pressure each county's infrastructure is absorbing.

Three regression models were built. The first is a simple linear regression predicting EV registrations from total charging stations. The second is a multiple linear regression using Level 2 and DC Fast station counts separately as predictors. The third adds median household income as an additional predictor with total charging stations.

The most notable finding from the modeling is a negative coefficient on DC Fast stations in Model 2. This is because DC Fast chargers are placed along highways for long distance travelers rather than residents, so counties with more DC Fast stations are not necessarily counties with high residential EV adoption. Once Level 2 coverage is controlled for, DC Fast density becomes associated with local EV registration counts.

# Key Findings
Charging stations are the strongest predictor of EV adoption across Maryland counties, explaining about 75% of the variation on their own. Splitting by charger type improves that to 82% and shows that Level 2 stations drive residential adoption while DC Fast stations serve a different purpose entirely. Adding income improves the model further but income is not statistically significant on its own once charging stations are accounted for, probably because wealthier counties also tend to have more stations.
The infrastructure gap is most severe in the counties with the highest adoption. Montgomery County has the most EVs in the state and the worst ratio of EVs to charging stations, which points to a policy problem that high income and strong EV demand alone cannot solve.




