# What Factors Are Associated With Airbnb Prices and Performance Across London?
## Project Overview
This project investigates the factors that are associated with Airbnb listing prices across London.
The analysis aims to examine how location, property characteristics, host characteristics and guest ratings are associated with listing prices, with the aim being to identify the factors that have the strongest relationship with price.

## Dataset
The dataset has `92,638` listings and `90` features that cover listings across London. \
For the analysis, a subset of variables was selected to reduce the dimensionality of the regression model. 

| Variable | Description |
|---|---|
| `price` | Listing price per night |
| `neighbourhood_cleansed` | London neighbourhood |
| `property_type` | Type of property |
| `room_type` | Type of room |
| `accommodates` | Maximum number of guests |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `beds` | Number of beds |
| `host_is_superhost` | Whether the host has Superhost status |
| `hosts_time_as_host_years` | Length of time the host has been active |
| `review_scores_rating` | Average guest rating |

## Methodology
This analysis consists of:
* Data cleaning and missing-value investigation
* Exploration of listing price distributions
* Log transformation of listing prices
* Analysis of property and location characteristics
* Analysis of host characteristics
* Analysis of guest ratings
* Spearman rank correlations
* Welch’s t-test
* Random Forest regression
* Model evaluation using MAE, RMSE and R²
* Regression diagnostics including linearity, homoscedasticity, normality and multicollinearity
  

## Key Findings:
### Property Characteristics
Property characteristics showed some of the strongest associations with listing prices
* Neighbourhoods that are in more central areas tend to have higher median listing prices.
* `Accommodates` had a very strong positive relationship with median price (`ρ = 0.94`)
* Larger numbers of bedrooms and bathrooms are associated with higher prices.
* Entire properties tend to have substantially higher median pricing than room liustings
* Property type also showed considerable variation in median price.

### Host Characteristics
* `Superhost` listings had a higher median price than non-superhost listings
* A Welch's t-test showed a statistically significant difference in the mean log-price between the two groups
* Host experience showed a little association with price, suggesting that the price of a listing is more associated with market forces than host experience.


### Guest Ratings
Guest ratings had a statistically significant but very weak relationship with log-price. 
* Spearman ρ = 0.065
* p < 0.001

This suggests that ratings have a limited explanatory power compared to property and host characteristics for listing price. 

### Model Performance
Model Performance

The Random Forest regression model was evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE) and R².

A DummyRegressor was also used as a baseline to determine whether the Random Forest model provided an improvement over a simple benchmark.

## Limitations
* The dataset contains substantial missing data for several variables, meaning some features could not be used for every analysis.
* The analysis identifies associations rather than causal relationships. Other factors may influence the observed relationships between listing characteristics and price.
* One extreme price anomaly was removed, but other unusually high-priced listings were retained because it was not possible to determine whether they represented genuine luxury properties or data errors.
* The analysis is specific to Airbnb listings across London and may not generalise to other cities or markets.
* The model only uses the selected features. Other factors such as amenities, seasonality, availability and proximity to attractions may also influence listing prices.
* Guest ratings are heavily concentrated towards the upper end of the scale, limiting the variation available for analysing their relationship with price.

## Tools Used
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Scikit-learn
* Jupyter Notebook
