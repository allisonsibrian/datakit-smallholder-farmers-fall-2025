# Allison Sibrian - Challenge 1 Weather Pattern Analysis

## Overview
 This project analyzes whether weather patterns can predict the types of questions farmers ask. By translating farmer SMS messages from local languages (Swahili, Luganda, and Runyankole) and combining them with ERA5 weather data, I built a model to predict spikes in farmer inquiries.

*(Note: Due to the massive dataset size (21M rows), this analysis was conducted on a stratified 0.5% sample.)*

## Research Questions
- Question 1: Do specific weather events trigger predictable spikes in farmer questions?
- Question 2: Is there a temporal lag between the weather event and the farmer's question (e.g., biological pest lifecycles)?
- Question 3: Can machine learning models predict the volume of farmers' questions based solely on country-level weather data?

## Methodology

### Data Sources
- Producers Direct Dataset: Obtained de-duplicated farmer questions split by language (English, Swahili, Luganda, Runyankole).
- ERA5 Climate Reanalysis Data: Monthly aggregates for Total Precipitation (prcp), Maximum Temperature (tasmax), and Minimum Temperature (tasmin) for Kenya, Uganda, and Tanzania.
- Global Historical Climatology Network daily (GHCNd): Ground station data (GHCNd) was explored initially but excluded due to inconsistent reporting. ERA5 satellite data was selected to ensure continuous temporal coverage.

### Approach
1. **Step 1**: Data processing, loading, and initial exploration
2. **Step 2**: Stratified Sampling (0.5%) and Batch Translation 
3. **Step 3**: Cleaning and Topic Categorization
4. **Step 4**: Aggregation & Feature Engineering
5. **Step 5**: Visualizations and Predictive Modeling

### Tools and Technologies
- **Programming Language**: Python 3.11
- **Key Libraries**: pandas, numpy, duckdb, matplotlib, seaborn, nltk, scikit-learn, etc. 

## Use of Generative AI

### Tools Used
- **Gemini (Google's AI model).**: Used to preprocess the 21M row raw dataset, ghcnd_all.tar.gzfile, handle the stratified sampling logic in Google Colab, and perform batch translation of local languages. Also utilized to refine the Random Forest TimeSeriesSplit validation strategy.
- **Human-Created**: All analysis logic, interpretation of visualizations, validation, and final strategic conclusions.

## Key Findings

### Lagged Rainfall (1 Month) is One of the Leading Predictors for 'Pest & Disease' Questions 
The model identified 1-month Lagged Rainfall as significantly more predictive than current rainfall.

- Biological Mechanism: Rainfall triggers vegetation growth for Pests to incubate and Farmers notice ~ 4 weeks later.

**Implications for Producers Direct:**
- To create a pest alert system following this analysis, it would be best to send alerts 3-4 weeks after heavy rainfall events.
- To improve on this system, this model can be refined to use weekly aggregations and intake more data if there are no computational constraints for analysis.

### Strong Predictive Success for 'Pests & Disease' and 'Market' Topics
The model for achieved a "Strong" performance rating, meaning the prediction error (RMSE) was lower than the standard deviation of the test set.

- Pest & Disease Topics: R^2 = 0.18$. Weather patterns explain 18% of the variance in pest questions.
- Market Questions Topics: The model also successfully predicted market activity (RMSE 22.31), likely correlating with harvest cycles.
- Limitation: Livestock and Crop questions showed higher variance; the weather model struggled to capture these fluctuations, suggesting economic factors may be the primary driver.

**Implications for Producers Direct:**
- There is a strong confidence in using the model as a baseline for predicting these topics. This model can be built upon and refined by incorporating weekly aggregation and regional data, which can eventually be used for future alert automated systems.
- Livestock and Crop questions showed higher variance; the weather model struggled to capture these fluctuations. Further investigations should be pursued to understand if these topics are driven by other factors (i.e, economic).

## Visualizations

### Feature Importance for 'Pests & Disease' Questions
![Visualization 1](feature_importances.png)

**Interpretation**: 
This chart illustrates the decision logic of the Random Forest model.
- Baseline: 'Year' and 'Month' set the baseline volume, confirming that Platform Growth and Seasonality drive majority of question volume.
- 1-Month Lagged Rainfall appears as one of the top environmental predictors. This confirms that weather events impact farmer behavior around a ~ 4-week delay, validating the "Incubation Period" hypothesis.

*(Note: Time-series visualizations of predicted vs. actual volume is available in the analysis notebook, showing that while the model captures the trend, it fails to predict the sharp spikes seen in the original dataset.This is expected, as the model relies on country-level weather averages, which lack the resolution to predict localized spikes)*

## Limitations and Challenges

### Data Limitations
- Weather and Questions were averaged at the country level. Averaging to the country-level leaves out micro-climates, and limits the model's ability to predict the exact volume of topic question count.
- Training on aggregated monthly data points limited the model's ability to learn non-linear patterns.

### Technical Challenges
- Translating 21.5 million rows was not possible due to computational constraints. I used a 0.5% sampling strategy per language group as it was a necessary trade-off between translation quality and processing time.
- Some translations resulted in hallucinations (e.g., "Attorney General"). This required implementing keyword filtering to obtain usable data. 

## Next Steps and Recommendations

### For Further Analysis
1.**Weekly Aggregation:** To expand and create a robust pest and disease alert system, it would be best to move from monthly to weekly aggregation. A weekly model would likely increase the R^2 score significantly.
2.**Regional Integration:** To expand this analysis, incorporating user location would allow for better forecasting, as this country-level analysis is masking micro-climates that occur in a country.
3.**Crop Specificity:** Splitting and further specifying topic questions would help (i.e., 'Crops') as different crops have different weather sensitivities.

### For Producers Direct
Utilizing the prediction model to create a robust alert systemn can be done by specifying feature attributes. Feature importance confirms that Seasonality (Month) and Lagged Rainfall are the strongest signals for targeting interventions.

## Contact and Collaboration

**Author**: Allison Sibrian
**GitHub**: @allisonsibrian

**Collaboration Welcome**: 
- Open to feedback and suggestions
- Happy to collaborate on related analyses
- Available to answer questions about this approach

## Acknowledgments
- Thanks to Bashir Alsuty for the de-duplicated data split by language files, and Steven Yan for the Comet Scores on translation models for Swahili, Luganda, and Runyankole, as they were used in my pre-processing stage.
---

**Last Updated**: December 14, 2025
