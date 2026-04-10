## Overview
This project uses two datasets to analyze whether charging infrastructure is keeping up with electric vehicle (EV) adoption in Maryland counties. The datasets include EV registration data from MDOT/MVA and charging station data from the Department of Energy. The goal of the cleaning pipeline is to transform both raw datasets into consistent, county-level formats that can be merged and used for analysis.

## EV Dataset Cleaning (MDOT/MVA)

The raw EV dataset contains monthly vehicle registration data by county and fuel type. These are the steps that were taken to clean and prepare this dataset:

- Converted the date column into a proper datetime format
- Standardized county names to ensure consistency
- Filtered the dataset to include only fully electric vehicles (filtered out plug-in hybrids since they do not rely entirely on charging stations)
- Converted vehicle counts to numeric values
- Aggregated data by county and month
- Created a new variable, EV_Total, representing total electric vehicles
- Extracted the most recent month of data to create a county-level snapshot

## Charging Station Dataset Cleaning (DOE)

The charging station dataset includes individual station records with location and charger details. The following cleaning steps were done:

- Filtered data to include only stations in Maryland
- Filtered for electric charging stations only
- Kept only active stations
- Cleaned and converted charger count columns (Level 1, Level 2, DC Fast) into numeric values
- Used latitude and longitude coordinates to assign each station to a county using spatial methods
- Standardized county names to match the EV dataset
- Aggregated the data to the county level

New variables were created:
- **Charging_Stations** (total number of stations)
- **Level2_Ports**
- **DC_Fast_Ports**
- **Total_Charging_Ports**

## Final Output

After cleaning both datasets, they were merged using the county field to create a final dataset. This dataset includes:

- EV adoption by county
- Charging infrastructure by county

An additional variable was created:
- **EV_per_Station**, which measures the ratio of EVs to charging stations
