# Climate-Driven Agricultural Insights: NLP & Predictive Modeling for East Africa

![Python](https://img.shields.io/badge/Python-3.11-blue) ![Data](https://img.shields.io/badge/Data-ERA5%20%7C%20SMS-green) ![Partner](https://img.shields.io/badge/Partner-DataKind%20%7C%20Producers%20Direct-orange)

## Project Overview
**Hosted by:** DataKind & Producers Direct  
**Role:** Volunteer Data Scientist

This project analyzes **21 million SMS messages** from smallholder farmers in East Africa (Kenya, Uganda, and Tanzania). 
By integrating **ERA5 Satellite Climate Reanalysis data** with a multilingual Natural Language Processing (NLP) pipeline, I investigated how climate patterns and seasonality drive farmer inquiries.

---

## Project Context: What is a DataKit?
This research was conducted as part of a **DataKind DataKit**.

> _"A DataKit™ is a work-ready set of data, software, and innovation questions, curated by DataKind... All learnings, ideas, and insights resulting from this DataKit will be aggregated and used to expand impact in the financial inclusion and economic opportunity sector."_

**The Dataset Source (WeFarm / Producers Direct):**
Producers Direct acquired this dataset from WeFarm, a peer-to-peer SMS platform. The archive represents 7 years of agricultural activity, including:

*   **7.6 Million+** farmer questions across 4 languages (English, Swahili, Luganda, Runyankole).
*   **17.2 Million+** responses and 200,000+ farming tips.
*   **Demographic Data** covering key agricultural regions in East Africa.

**The Challenge:**
Producers Direct needed to extract actionable patterns from this unstructured text. My research focused on determining if external climate factors (Rainfall/Temperature) could be used to forecast spikes in specific topics like "Pest & Disease."

---

## Key Research Outcomes

### [Challenge 1: Predictive Modeling](Challenge%201%20_Weather%20Patterns/allisonsibrian/README.md)
*   **The Model:** Random Forest Regressor using ERA5 weather features.
*   **The Finding:** While **Seasonality (Month)** is the primary driver of question volume, **1-Month Lagged Rainfall** emerged as one of the top *environmental* predictors ($R^2=0.18$ for 'Pests & Disease' Question Topics).
*   **Future Application:** With further refinement (weekly aggregation), this 4-week lag signal could trigger automated SMS alerts to warn farmers of impending pest incubation periods.
*   **[Read the Full Analysis](Challenge%201%20_Weather%20Patterns/allisonsibrian/README.md)**


### [Challenge 2: Seasonality & NLP](Challenge%202_Seasonality/allisonsibrian/README.md)
*   **The Finding:** Farmer engagement does *not* peak during the primary planting season ("Long Rains"). Instead, it spikes during the **Short Rains/Post-Harvest** window (Aug–Nov).
*   **The Baseline:** This insight offers a data-driven hypothesis for resource allocation.
*   **Future Application:** With further refinement, incorporating the **full dataset** (beyond stratified sampling) and including **stronger translation models** (validated by native-speakers), these insights could guide services to target farmers' needs during the post-harvest handling and second-season preparation season.
*   **[Read the Full Analysis](Challenge%202_Seasonality/allisonsibrian/README.md)**

---

## Visual Highlight
| **Predictive Logic (Challenge 1)** | **Regional Insights (Challenge 2)** |
| :---: | :---: |
| ![Feature Importance](Challenge%201%20_Weather%20Patterns/allisonsibrian/feature_importances.png) | ![Regional Heatmap](Challenge%202_Seasonality/allisonsibrian/word_frequencies_countries.png) |
| **Figure 1:** Feature Importance showing **1-Month Lagged Rainfall** as one of top predictors. | **Figure 2:** Regional heatmap revealing distinct crop priorities (e.g., **Tomato** in Uganda vs. **Maize** in Kenya). |

---

## Tech Stack
*   **Data Processing:** `pandas`, `duckdb`, `Google Colab` (Handling 7.6M+ rows).
*   **Machine Learning:** `scikit-learn` (Random Forest, TimeSeriesSplit).
*   **NLP:** `nltk`, `Google Gemini` (Batch translation for local languages).
*   **ERA5 Reanalysis Data**

---
## Contact
**Email**: @allisonnsibrian@gmail.com