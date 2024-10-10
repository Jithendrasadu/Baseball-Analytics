# Baseball-Analytics

# Predicting Home Run Rate in MLB Pitchers

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Preliminary Analysis](#preliminary-analysis)
4. [Model Selection](#model-selection)
5. [Random Forests](#random-forests)
6. [Conclusion](#conclusion)

---

## 1. Introduction <a name="introduction"></a>

### Importance of Regression in Sports:
- **Team Performance:** Understanding and improving overall team performance.
- **Player Performance:** Fine-tuning and optimizing player performance.
- **Insights for Decision Making:** Clear, concise insights can be used to evaluate and improve player performance.
- **Score Prediction:** Accurately predicting performance metrics like scores.

### Question of Interest:
- What factors under a pitcher’s control contribute to their home run rate?
- **Significance:** Minimizing home runs is crucial for pitchers in baseball, and understanding these factors is key to improving performance.

---

## 2. Dataset Overview <a name="dataset-overview"></a>

### Dataset Snapshot:
- The dataset captures various metrics related to MLB pitchers and their performance.
- **16 variables** in total, focusing on factors such as:
  - Mean exit velocity allowed on contact
  - Mean launch angle allowed on contact
  - Barrel rate (a combination of exit velocity and launch angle)
  - Percentage of contact at 95+ MPH
  - Pitch location metrics like percentage of pitches thrown down the middle of the plate, and those low, up, or out of the zone.

### Dataset Parameters in Focus:
- The dataset provides insights on how pitchers control factors like pitch location and how they affect home run rates.
- **Dependent Variable:** "HR_rate" represents the home run rate for each pitcher.
  
### Data Source:
- The data was sourced from Major League Baseball’s advanced statistics database, [Baseball Savant](http://baseballsavant.mlb.com).

---

## 3. Preliminary Analysis <a name="preliminary-analysis"></a>

### Key Exploratory Steps:
- **Histograms and Summary Statistics:** To identify basic trends in Home Run Rate.
- **Boxplots:** To detect outliers in the dataset.
- **Scatter Plots and Correlation:** Exploring relationships between different variables.
- **Regression Models:** Understanding how variables influence the home run rate.

### Key Findings:
- Significant variables impacting home run rate include exit velocity, barrel rate, and pitch location metrics.

---

## 4. Model Selection <a name="model-selection"></a>

### Initial Model:
- Developed with all available variables.
- **Statistical Significance:** Only 4 variables were statistically significant.
- **Model Performance:**
  - **Multiple R-Squared:** 87.45%
  - **Residual Standard Error:** 0.421 on 357 degrees of freedom (df)
  - **High VIF:** Variables like ‘oz swing percent’ and ‘zone swing ratio’ had high Variance Inflation Factor (VIF).

### Reduced Model:
- Removed high VIF variables.
- **Statistical Significance:** 5 variables remained significant.
- **Improved Model Performance:**
  - **Multiple R-Squared:** 96.32%
  - **Residual Standard Error:** 0.228 on 358 df

### Final Model:
- Further refined by removing ‘zone swing ratio.’
- **Multiple R-Squared:** 96.32%
- **Residual Standard Error:** 0.228 on 357 df

### Residual Analysis:
- **QQ Plot of Standardized Residuals:** Shows a normal distribution, with slight deviations in the tails.
- **Log Transformed Residuals:** Improved normality in one tail, but not perfect.

---

## 5. Random Forests <a name="random-forests"></a>

### Random Forest Model:
- A Random Forest regression model was applied after excluding non-significant variables.
- **Cross-Validation (CV) and Training:** Final model trained using cross-validation.

### Model Performance:
- **Root Mean Square Error (RMSE):** 0.1854826
- **R-Squared:** 0.982332
- **Mean Absolute Error (MAE):** 0.133049
- **Key Factors:** Plate appearances (pa), exit velocity, and home runs had a significant impact on a pitcher’s home run rate.

---

## 6. Conclusion <a name="conclusion"></a>

### Key Insights:
- **Random Forest Model:** Demonstrated strong predictive power with high accuracy.
- **Significant Variables:** Exit velocity, barrel rate, and pitch location metrics were critical in predicting home run rates.
  
### Implications:
- **Player Development Strategies:** Tailored training programs can be developed to focus on minimizing home run rates.
- **Scouting and Recruitment:** Teams can refine scouting processes by focusing on players who excel in key metrics like exit velocity and pitch location.
  
### Final Takeaway:
By understanding the factors that contribute to home run rates, teams can strategize more effectively to enhance pitcher performance and minimize home runs.

---
