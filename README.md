# Collision Severity Prediction
**CPEN 355 - Final Project** 

Machine Learning Model for Vehicle Collision Analysis

---

## Overview
Machine Learning (ML) is transforming industries by analyzing complex datasets and generating accurate predictions. This project presents a **Gradient Boosting Regression model using XGBoost** to predict the severity of **vehicle collisions** based on various environmental and vehicle-specific factors.

Our model helps assess accident severity by analyzing:

1. **Time of day & season**  
2. **Weather & road conditions**  
3. **Vehicle type & year of manufacture**  

The project demonstrates advanced **data processing, model training, and hyperparameter tuning** techniques, making it a strong addition to any data science portfolio.

---

## Key Results
The model performed well for **injury predictions** but had limitations in **fatality predictions**, as shown below:

| Model | RMSE (↓ Better) | R² Score (↑ Better) | Mean of Test Data |
|--------|----------------|----------------------|--------------------|
| **Injury Model** | 0.5800 | 0.2923 | 0.7454 |
| **Fatality Model** | 0.1006 | 0.0528 | 0.0094 |

**Conclusion:** The model can predict injuries with reasonable accuracy, but fatalities are difficult to model due to class imbalance.

---

## Tech Stack & Tools
**Machine Learning:** XGBoost, Scikit-Learn  
**Data Processing:** Pandas, NumPy  
**Visualization:** Matplotlib, Seaborn  
**Development:** Python, Google Colab  

---

## Dataset
- **Source:** [Canadian Open Government - National Collision Database](https://tc.canada.ca/en/road-transportation/statistics-data/canadian-motor-vehicle-traffic-collision-statistics-2022)
- **Years Used:** 2016-2019
- **Size:** ~1 million cleaned data points

---

## Installation & Usage
1. Download the ipynb file & open in Google colab
2. Unzip data.zip and add data files to "sample data" in colab
3. run the program

---

## Model Architecture
The model follows a **Gradient Boosting approach** using XGBoost, where multiple weak decision tree models are combined to enhance prediction accuracy.

**Hyperparameter Tuning:**
- `n_estimators = 50 (injuries) , 100 (fatalities)`
- `max_depth = 7`
- `learning_rate = 0.094 (injuries) , 0.031 (fatalities)`

**Why Two Models?**
- Injuries & fatalities differ significantly in distribution.
- A single multi-output model resulted in poor performance.
- Two separate models provided better results.

---

## Evaluation Metrics
- **Root Mean Squared Error (RMSE):** Measures error magnitude (lower is better).
- **R² Score:** Represents the proportion of variance explained (higher is better).

---

## Lessons Learned & Challenges
**Data Imbalance:** Fatalities were rare compared to injuries, making predictions harder.  
**Hyperparameter Tuning:** Extensive tuning improved injury predictions but had limited impact on fatality predictions.  
**Feature Engineering:** Dropping irrelevant features (e.g., passenger age) improved efficiency.  
**Boosting Algorithms:** Experimented with `gbtree`, `gblinear`, and `dart`—`gbtree` performed best.  

---

## Contributors
**Dominic Bongiorno** - Data Processing & Modeling  
**Maddy Paulson** - Model Optimization & Hyperparameter Tuning  
**Jake Rubin** - Data Cleaning & Feature Engineering  

---

## References
1. Transport Canada, [Collision Statistics 2022](https://tc.canada.ca/en/road-transportation/statistics-data/canadian-motor-vehicle-traffic-collision-statistics-2022)  
2. Iranitalab & Khattak, "Comparison of ML Methods for Crash Prediction", *Accident Analysis & Prevention*, 2017.  
3. Usman, Fu & Miranda-Moreno, "Injury Severity Analysis", *Journal of Modern Transportation*, 2016.  

## Acronyms
| **Acronym** | **Description**                               |
|-------------|-----------------------------------------------|
| C_YEAR      | Year                                          |
| C_MNTH      | Month                                         |
| C_WDAY      | Weekday                                       |
| C_HOUR      | Hour                                          |
| C_SEV       | Collision severity                            |
| C_VEHS      | Number of vehicles involved                   |
| C_CONF      | Collision description (what happened)         |
| C_RCFG      | Road configuration                            |
| C_WTHR      | Weather conditions                            |
| C_RSUR      | Road surface condition                        |
| C_RALN      | Road alignment                                |
| C_TRAF      | Traffic control device                        |
| V_ID        | Vehicle ID                                    |
| V_TYPE      | Vehicle type                                  |
| V_YEAR      | Vehicle year                                  |
| P_ID        | Person ID                                     |
| P_ISEV      | Person injury severity                        |
| C_CASE      | Collision case identifier                     |
