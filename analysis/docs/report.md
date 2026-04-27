# Model 1 Simple Linear Regression

R² = 0.752

Adjusted R² = 0.740

RMSE = 3,876 EVs

Slope = +62.1 EVs per station

Pearson r = 0.867

p-value = < 0.0001

Total charging stations alone explain 75% of the variation in EV registrations across Maryland counties. For every additional charging station in a county, roughly 62 more EVs are registered there. The relationship is highly significant (F p < 0.0001) and the strong Pearson r (0.867) confirms a robust linear association — but since this is a cross-sectional snapshot, causality cannot be confirmed. Station availability may attract EV buyers, high EV populations may attract station investment, or both.

# Model 2 Multiple Linear Regression

R² = 0.821

Adjusted R² = 0.803

RMSE = 3,290 EVs

β — Level 2 Stations = +108.1 ***

β — DC Fast Stations = -245.5 *

F-statistic = p3.37 × 10⁻⁸

Splitting charger types improves R² by +0.069 and cuts RMSE by ~600 EVs over Model 1. Level 2 stations are strongly and positively associated with registrations. DC Fast stations carry a negative coefficient.

The negative β on DC Fast stations (−245.5, p = 0.030) is weird but explainable. This is a suppressor effect: DC Fast chargers are concentrated along highway corridors (I-95, I-270, US-50) serving long-distance travelers, not residents. Rural counties like Garrett, Dorchester, and Kent have DC Fast stations for through-traffic but fewer than 200 registered EVs each. Once Level 2 coverage is controlled for, DC Fast density becomes inversely associated with residential EV density.
Takeaway: DC Fast chargers are highway infrastructure. Level 2 chargers at homes and workplaces are what actually drives residential adoption.

<img width="537" height="125" alt="Screenshot 2026-04-27 at 1 54 53 PM" src="https://github.com/user-attachments/assets/3f6e910c-e78f-4bf7-9245-256eb2335fcf" />

Model 2 is the stronger specification because of better fit, lower prediction error, and it surfaces the charger-type distinction that Model 1 cannot detect.
