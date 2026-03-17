# Predicting Airbnb Listing Prices in London

## Overview

This project investigates what property and host characteristics are the strongest predictors of nightly Airbnb listing prices in London. A multiple linear regression model is developed using listing data sourced from [Inside Airbnb](https://insideairbnb.com), with a focus on both predictive accuracy and interpretability.

## Key Findings

- The model explains **72.5 of the variation** in log nightly prices on unseen test data (R-squared = 0.725), with no evidence of overfitting.
- **Location** is the dominant price driver. Listings in Westminster, Kensington and Chelsea, and the City of London command the largest prices.
- **Property size** matters substantially since each additional bedroom adds approximately 15% to the price and each additional person accommodated adds around 8% to the price.
- **Private rooms** are priced approximately 45% lower than entire homes.
- **Air conditioning** (+18.7%) and **elevator access** (+12.7%) are the strongest amenity predictors.

## Project Structure

| Document | Description |
| --- | --- |
| [index.Rmd](index.Rmd) | Project overview and research question |
| [01_data.Rmd](01_data.Rmd) | Data cleaning and preparation |
| [02_eda.Rmd](02_eda.Rmd) | Exploratory data analysis |
| [03_modelling.Rmd](03_modelling.Rmd) | Feature engineering and modelling |
| [04_assumptions.Rmd](04_assumptions.Rmd) | Regression assumption diagnostics |
| [05_evaluation.Rmd](05_evaluation.Rmd) | Results, limitations and conclusions |

## Data

Data is sourced from [Inside Airbnb](https://insideairbnb.com/get-the-data/) and is the London listings from September 2025. The raw data file is not included in this repository. To reproduce this analysis, download `listings.csv.gz` from the Inside Airbnb London page and place it in `data/raw`.

## Reproducing the Analysis

1. Clone the repository.
2. Open `london-airbnb-regression.Rproj` in RStudio.
3. Run `renv::restore()` to install all dependencies at the correct versions.
4. Knit each document in order from `index.Rmd` to `05_evaluation.Rmd`.

## Requirements

- R version 4.5.2 (2025-10-31 ucrt).
- RStudio.
- All package dependencies are managed via `renv` - see `renv.lock`.

## Limitations

The model applies to reviewed listings only and represents a snapshot of the London market in September 2025. Homoscedasticity and normality of residuals are both violated -- robust standard errors are used throughout. See [04_assumptions.Rmd](04_assumptions.Rmd) for full details.

## Author

James Thoburn