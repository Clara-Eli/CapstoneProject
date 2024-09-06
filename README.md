# CapstoneProject
# Impact of Air Pollution on Lung Cancer Rates in the United States

## Project Overview

**Start and End Dates:** May 13, 2024 - July 30, 2024

This project analyzes the relationship between air pollution levels and lung cancer rates across various counties in the United States. Our goal is to determine how different air pollutants (PM2.5, PM10, SO2, NO2, O3, CO, and others) impact lung cancer rates and identify the most significant pollutants contributing to lung cancer incidence. The findings will assist public health officials and policymakers in developing targeted strategies to reduce air pollution and its adverse effects.

## Objectives

- **Identify significant predictors** of lung cancer rates.
- **Inform public health policies** and strategies to mitigate air pollution's health impacts.

## Business Value

The insights from this analysis will help public health officials and policymakers:
- Prioritize interventions.
- Allocate resources efficiently.
- Create targeted strategies to reduce air pollution and improve public health.

## Methodology

### Data Collection

- Gathered data on air pollution levels and lung cancer rates across U.S. counties.

### Data Cleaning

- Addressed missing values and outliers to ensure data quality.

### Exploratory Data Analysis (EDA)

- Conducted statistical analysis and visualizations to explore data patterns and correlations.
- Initial findings revealed weak correlations between individual pollutants and lung cancer rates.

### Hypothesis Testing

- Formulated and tested hypotheses based on initial findings.

### Modeling

- **Models Considered:**
  - Multiple Linear Regression
  - Random Forest Regression
  - XGBoost Regression
- **Features:**
  - PM2.5, PM10, SO2, NO2, O3, CO, Diesel Particulate Matter, CS2
  - Environmental Quality Indicators
  - Urbanization level
  - Average Annual Cancer Incidence
  - Limited Terrain Data

### Key Milestones

- **May 13, 2024:** Project Kickoff
- **June 3, 2024:** Data Cleaning and Preprocessing Completed
- **June 10, 2024:** Initial EDA Completed
- **July 8, 2024:** Correlation Analysis and Hypothesis Testing Completed
- **July 30, 2024:** Final Report Submission

## Discovery (EDA) and Design Documents

The initial analysis included descriptive statistics, correlation analysis, and visualizations to identify patterns and correlations in the data. Outliers were trimmed to improve data quality and focus on typical values. The EDA revealed weak correlations between individual air pollutants and lung cancer rates, suggesting that other factors might also play significant roles.

- **Dataset:** 2602 rows and 34 columns containing air pollution levels and lung cancer rates across U.S. counties.

### Issues and Considerations

- **Missing Data:** Several columns have missing values.
- **Outliers:** There are outliers in both air pollutant levels and lung cancer rates.
- **Data Quality:** Overall high, but further cleaning may be required.

### Summary Statistics

**Previous to Trimming:**

- **Lung Cancer Rates:**
  - Min = 12.9
  - Max = 169.9
  - Mean = 69.17
  - Median = 68.6
  - Std = 17.42

**After Trimming:**

- **Lung Cancer Rates:**
  - Min = 26.2
  - Max = 110.8
  - Mean = 67.9
  - Median = 67.9
  - Std = 15.2

### Target Variable Analysis

**Distribution of Lung Cancer Rates:**

- The histogram illustrates the distribution of lung cancer rates with outliers removed. The distribution remains approximately normal, with a peak around the 60-70 range.

**Box Plot of Lung Cancer Rates:**

- The box plot displays the median, interquartile range, and outliers of lung cancer rates after trimming. The median rate remains around 67.

### Descriptive Statistics for Predictors

**PM2.5:**
- Min: 2.4
- Max: 16.2
- Mean: 9.88
- Median: 9.9
- Std: 2.23

**Distribution of PM2.5:**

- The histogram shows the distribution of PM2.5 levels after outliers were trimmed, with a peak around the 10-12 range.

**Box Plot of PM2.5:**

- The box plot summarizes PM2.5 levels, showing the median, interquartile range, and outliers after trimming.

### Correlation and Cross-tabulation

**Correlation Heatmap:**

- Utilized to visually represent the correlation matrix between air pollutants and lung cancer rates. Revealed weak correlations with some pollutants like NO2 and O3 showing slightly higher correlations.

**Correlation Heatmap of all Numerical Values:**

- Showed significant relationships between air pollutants and lung cancer rates, with PM2.5 and NO2 having the highest correlations.

### Comparative Analysis of Scatter Plots

**Before Trimming Outliers:**
- Scatter plots of PM2.5, PM10, SO2, NO2, O3, and CO vs. Lung Cancer Rates showed a general positive trend with significant spread.

**After Trimming Outliers:**
- Scatter plots showed clearer positive correlations with reduced noise.

## Models and Features Considered

**Models:**
- Multiple Linear Regression
- Random Forest Regression
- XGBoost Regression

**Features:**
- Pollutants: PM2.5, PM10, SO2, NO2, O3, CO, Diesel Particulate Matter, CS2
- Environmental Quality Indicators (EQI)
- Urbanization level (UCI)
- Average Annual Cancer Incidence (AAC)
- Limited Terrain Data (LTD)

**Proposed Models:**
- XGBoost was selected for its superior performance in handling complex interactions and robustness to overfitting.

### Final Model and Output

**Final Model:** XGBoost

**Features and Importance:**
- PM2.5, UCI, and Diesel emissions were identified as the most impactful features.

**Training and Test Datasets:**
- Split into 70% training and 30% test datasets.

**Model Performance:**

**Table 1: Performance Metrics for Training Data**
| Model          | MSE   | RMSE  | R2    | Accuracy | Precision | Recall | F1 Score |
|----------------|-------|-------|-------|----------|-----------|--------|----------|
| Linear Regression | 0.0184 | 0.1355 | 0.9853 | 0.9816 | 0.9816 | 0.9816 | 0.9816 |
| Random Forest   | 0.0096 | 0.0981 | 0.9923 | 0.9904 | 0.9904 | 0.9904 | 0.9904 |
| XGBoost         | 0.0044 | 0.0661 | 0.9965 | 0.9956 | 0.9956 | 0.9956 | 0.9956 |

**Table 2: Performance Metrics for Test Data**
| Model          | MSE   | RMSE  | R2    | Accuracy | Precision | Recall | F1 Score |
|----------------|-------|-------|-------|----------|-----------|--------|----------|
| Linear Regression | 0.0315 | 0.1774 | 0.9751 | 0.9685 | 0.9687 | 0.9685 | 0.9686 |
| Random Forest   | 0.0315 | 0.1774 | 0.9751 | 0.9685 | 0.9687 | 0.9685 | 0.9686 |

**Analysis:**
- The model showed good performance metrics with high accuracy, precision, recall, and F1 scores. The AUC of 0.60 suggests room for improvement in class discrimination.

## Conclusion, Next Steps, and Business Impact/Value

### Conclusion

- Certain air pollutants, particularly PM2.5, Diesel emissions, and urbanization levels, significantly influence lung cancer rates. The XGBoost model provided robust predictions, though class discrimination could be improved.

### Next Steps

- Incorporate more granular data on air pollution.
- Test more advanced models.
- Explore temporal dynamics of air pollution and lung cancer rates.
- Integrate additional external datasets.

### Business Impact/Value

- Insights can guide public health officials in developing targeted strategies to reduce air pollution and improve public health outcomes.

## Appendix

**Code and Diagrams/Visualizations:**

- **Data Preprocessing Code**
- **Summary Statistics**
- **Comparative Analysis of Scatter Plots**
- **Model Implementation Code**

