# KEMBAI - Smallholder Farmer Data Analysis

## Overview
This analysis explores a large dataset of questions from smallholder farmers to identify key trends, topics, and languages. The goal is to extract actionable insights that can help Producers Direct better understand and serve the needs of these farmers. The analysis covers data exploration, cleaning, keyword extraction, and visualization, with a focus on financial inclusion and crop-related questions.

## Research Questions
- What are the most common languages used by the farmers?
- Who are the most active users in the dataset?
- What are the most frequently discussed topics, particularly concerning crops and finance?
- How can we segment the data to analyze specific areas of interest like financial inclusion or crop issues?

## Methodology

### Data Sources
- The primary dataset contains 21,541,705 rows of farmer questions and related metadata.

### Approach
1. **Step 1**: Data loading and initial exploration using Pandas and Dask to handle the large volume.
2. **Step 2**: Data cleaning and preprocessing, which included removing 20,908,750 duplicate rows.
3. **Step 3**: Analysis of language distribution and identification of top users and topics.
4. **Step 4**: Keyword extraction for financial and agricultural topics using custom scripts. The data was split by language, and keywords were generated for each.
5. **Step 5**: Visualization of the findings, including dashboards for financial and crop-related questions based on English keywords.

### Tools and Technologies
- **Programming Language**: Python
- **Key Libraries**: pandas, dask, pyspark
- **GenAI Tools Used**: 
    - **ChatGPT**: Assisted in writing code to count keywords.
    - **Gemini CLI**: Used for initial data exploration and extracting financial and agricultural keywords.
- **Other Tools**: Google Colab (for increased RAM and processing power).

## Use of Generative AI

### Tools Used
- **ChatGPT**: Used for generating Python code to perform keyword extraction and counting.
- **Gemini CLI**: Used to explore the data within the local environment and perform initial keyword extraction.

### Human Review Process
- All AI-generated code was reviewed, tested, and adapted for the specific needs of the analysis.
- AI-generated summaries and insights were validated against the raw data to ensure accuracy.

### AI-Assisted vs. Human-Created
- **AI-Assisted**: Code generation for data processing and keyword extraction.
- **Human-Created**: The overall project structure, analysis logic, interpretation of results, and the synthesis of the final report.

## Key Findings

### Finding 1: Language and Data Overview
The dataset is multilingual, with English (55.6%) and Swahili (30.09%) being the dominant languages. A significant number of questions (3.77%) were unanswered, and 2.94% of the rows were duplicates, which were removed during preprocessing.

**Implications for Producers Direct:**
- Engagement strategies should be tailored to at least English and Swahili speakers.
- The presence of other languages like Nyn (5.37%) and Luganda (3.2%) indicates a need for multilingual support.

### Finding 2: Top Topics of Interest
The most common topics discussed by farmers include maize, cattle, chicken, and tomatoes. This highlights the primary areas of focus for their agricultural activities.

**Implications for Producers Direct:**
- Resources and support can be prioritized around these key topics to meet the most immediate needs of the farmers.

### Finding 3: Financial and Crop-Specific Insights
Dashboards were generated for questions related to financial and crop topics using English keywords. This provides a focused view of the challenges and questions farmers have in these critical areas.

**Implications for Producers Direct:**
- These dashboards can be used to develop targeted financial literacy programs or crop-specific advisory services.

## Visualizations

### Top Topics
*(Visualization would be inserted here, showing the distribution of top topics like maize, cattle, chicken, etc.)*

**Interpretation**: This visualization shows the primary focus of farmer questions, indicating which agricultural products are most important to them.

### Language Distribution
*(Visualization would be inserted here, showing the percentage of each language used.)*

**Interpretation**: This chart illustrates the linguistic diversity of the user base, emphasizing the need for multilingual communication and support.

## Limitations and Challenges

### Data Limitations
- The analysis was primarily focused on English-language data due to the challenges of translation.
- A small percentage of data (2.2%) had a NULL language field.

### Methodological Limitations
- The keyword extraction was based on English words, which may not capture the full context of questions in other languages.
- No forecasting or predictive modeling was performed.

### Technical Challenges
- The large size of the dataset required the use of tools like Dask and Google Colab to manage memory and processing.

## Next Steps and Recommendations

### For Further Analysis
1. **Translate All Data**: Use open-source models to translate all non-English questions to create a complete, unified dataset for analysis.
2. **Develop Forecasting Models**: Create forecasting models to predict trends in farmer questions or agricultural issues.
3. **Build an Interactive Dashboard**: Develop a comprehensive, interactive dashboard that allows for dynamic exploration of the entire dataset.

### For Producers Direct
1. **Invest in Translation**: Support the translation of farmer questions to gain a more inclusive understanding of farmer needs.
2. **Develop Targeted Content**: Use the insights on top topics to create relevant and timely content, resources, and advisory services.
3. **Enhance Multilingual Support**: Expand support services to cover the primary languages identified in the analysis.

## Files in This Contribution

```
KEMBAI/
├── README.md (this file)
└── analysis_summary.md (derived from project work)
```

## How to Run This Analysis

### Prerequisites
Analysis was conducted using Python libraries such as pandas, dask, and pyspark in a Google Colab environment.

### Running the Analysis
The analysis involved a series of steps documented in the "Methodology" section, executed through custom scripts and notebooks. The primary data was processed to extract keywords and generate summary statistics.

## Contact and Collaboration

**Author**: KEMBAI
**GitHub**: [Your GitHub Handle]
**Slack**: [Your Slack Handle]

---

**Last Updated**: 2025-12-05
**Status**: Complete
