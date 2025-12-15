# Allison Sibrian - Challenge 2 Seasonality Analysis

## Overview
This project analyzes the seasonality of farmers' questions across Kenya, Uganda, and Tanzania. By correlating farmer question volume with ERA5 weather data and performing NLP keyword analysis on a split dataset (English vs. Local Languages), I identify distinct seasonal keywords for each region.

## Research Questions
- Question 1: Do farmer questions align with their countries' farming seasonal calendar?
- Question 2: Can we identify distinct seasonal farming words for each country based on farmer question data? 
- Question 3: How does language (English vs. Local Languages (Swahili, Luganda, Ryunakole)) influence the types of seasonal questions asked?

## Methodology

### Data Sources
- Producers Direct Dataset: Obtained de-duplicated farmer questions split by language (English, Swahili, Luganda, Runyankole).
- ERA5 Climate Reanalysis Data: Monthly aggregates for Total Precipitation (prcp), Maximum Temperature (tasmax), and Minimum Temperature (tasmin) for Kenya, Uganda, and Tanzania.

### Approach
1. **Step 1**: Data Splitting: Created two comparison groups:The "English Baseline" (Kenya/Uganda) and the "Local Language Group" (Stratified sample of Swahili, Luganda, Runyankole).
3. **Step 2**: Weather Validation: Overlayed ERA5 precipitation data against each country and group question volume to compare farmer question volume to climate events.
5. **Step 3**: NLP & Cleaning
6. **Step 4**: Keyword Extraction
7. **Step 5**: Heatmap Visualizations

### Tools and Technologies
- **Programming Language**: Python 3.11
- **Key Libraries**: pandas, numpy, matplotlib, seaborn

## Key Findings

### Farmer Question Volume Peaks During Short Rains/Post-Harvest
Overlaying the ERA5 data with each country's farmer questions reveals when question volume spiked in relation to precipitation data.

**Kenya & Uganda:**
- Question Volume peaks in the second half of the year (August–November).
- This aligns with the end of Harvest 1 and the start of the "Short Rains" (Planting Season 2).
- Although the "Long Rains" are the primary season, farmers ask more questions during the "Short Rains" and transition periods.

**Tanzania:**
- Question Volume peaks in May (Masika Rains) and November (Vuli Rains).
- Activity is concentrated towards the end of the rain cycles.

**Implications for Producers Direct:**
- Question volume is highest in the second half of the year, suggesting farmers are seeking information for post-harvest handling and second-season preparation.
- Focusing primarily on the 'Long Rains' leaves farmers unsupported during the critical post-harvest months.

### Distinct Seasonal Keywords Per Country
Heatmap analysis reveals distinct agricultural priorities by region.

**Kenya:**
- 'Maize', 'Cow', and 'Chicken' appear as the top keywords.
- 'Maize' frequency peaks during the Transition period (September) and Second Planting Season (Oct-Dec).

**Uganda:**
- 'Tomato' appears as a top crop, distinct from the other regions.
- 'Plant' queries peak during Season 1 (March-May), suggesting farmers use this time for crop selection decisions.

**Tanzania:**
- 'Seed' is a dominant topic, particularly during the transition months (Sept), suggesting a specific need for input support.

**Implications for Producers Direct:**
- Since 'Maize' and 'Chicken' dominate simultaneously, this serves as a baseline to investigate whether farmers are practicing integrated mixed farming.
- Specific keywords like 'Tomato' (Uganda) and 'Seed' (Tanzania) suggest that the platform would benefit from tagging questions by crop category.

## Visualizations

### Rainfall vs. Question Volume
![Visualization 1](Kenya_qprcp.png)
![Visualization 2](Uganda_qprcp.png)
![Visualization 3](Tanzania_qprcp.png)

**Interpretation**: 
These visualizations overlay ERA5 precipitation data with Farmer Question Volume.

- Question Volume tends to peak during the second half of the year (Kenya/Uganda), while it peaks during the Masika Rains for Tanzania.

### Regional Heatmap
![Visualization 4](word_frequencies_countries.png)

**Interpretation**: 
This heatmap displays the Top 10 word frequencies per region.

- Distinct regional keywords appear: 'Rice' and 'Seed' in Tanzania, 'Tomato' in Uganda, and 'Maize/Cow' in Kenya.

## Limitations and Challenges

### Data Limitations
- The Uganda (Translated) dataset contained significant non-agricultural noise (e.g., "future", "seat"), resulting in lower signal clarity compared to the English dataset.
- The English dataset is larger than the Local dataset, requiring normalization (Frequency per 1K) to allow for valid visual comparison.

## Next Steps and Recommendations

### For Further Analysis
1. Future iterations should utilize stronger local-language models validated by native speakers to reduce noise.
2. Implement Latent Dirichlet Allocation (LDA) to categorize generic questions into specific themes.
3. Expand analysis to utilize the whole dataset instead of the current 0.5% translated samples.

### For Producers Direct
Data shows question volume peaks during the harvest and transition periods rather than the primary planting season. Producers Direct should investigate questions during this season and be ready to prioritize post-harvest handling and second-season preparation to meet farmers' needs.

## Contact and Collaboration

**Author**: Allison Sibrian
**GitHub**: @allisonsibrian

**Collaboration Welcome**: 
- Open to feedback and suggestions
- Happy to collaborate on related analyses
- Available to answer questions about this approach

## Acknowledgments
- Built upon work by Conrad Keyclamp's heatmap visualizations in Challenge 2

---

**Last Updated**: December 14, 2025
