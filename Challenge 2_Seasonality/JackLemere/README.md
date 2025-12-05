# Project Background

In this analysis, I wanted to answer the question of whether it was possible to map the farming calendar based on the types of questions being asked at certain times. The insights found primarily utilized the following data:

- Questions Asked: What was being asked by farmers and what key words were being used
- Time asked: The day, moth, year of when each question was asked
- Country: The geographical location from which the question came from

The majority of the data cleaning and analysis was done using Python with visualizations compiled using Tableau.


# Data Used

This analysis only uses the dataset provided by DataKind


# Summary

The following insights have been noted:

- Questions related to selling and general market related questions were found to be asked more frequently during harvest periods
- Similar relationship between market questions asked and time of year were found in both Uganda and Kenya
- The ratio of market-related questions and non market-related questions saw significant change each year

(IMAGE: DASHBOARD)

# Insights Deep Dive

By analyzing key word similarities, I was able to determine which questioned were likely related to be asking about selling goods. By labelling these questions, I could analyze the percentage of these questions compared to all other quesitons asked. I first wanted to know which months saw the highest percentages of market related questions. What I found was that the ratio of market related quesitons was higher during peak harvest months for both Uganda and Kenya. We were informed that in Kenya the harvest months ranged was from January-February and June-August while Uganda harvest periods were from December-February and June-August. It was found based on the graphs below that the where questions related to selling were most concentrated were in January and July for both Kenya and Uganda. This is what was expected as both Kenya and Uganda have similar harvesting periods, and farmers would be likely to want to sell harvested crops during harvest season. Crucially, this noticably relationship between the concentration of market related questions and harvest period times supports the idea that the farming calendar can be mapped based on the types of questions being asked.

[Sell Questions by Month (Kenya)]
[Sell Questions by Month (Uganda)]


When zooming in on this analysis and comparing by year, we can see that similar trends occur each year. The years 2018 and 2020 in particular have clear peaks in the concentration of selling related questions during harvest periods. Years 2017 and 2019 don't have as prominent of a correlation, but still have the two months with the highest concentration of market related questions fall within both harvest periods. 2021 saw this peak occur in May for reasons unknown, but may possibly have been related to unique weather and harvesting times that year.

[Sell Questions by Year (Kenya)]
[Sell Questions by Year (Uganda)]

# Analysis Process

The code for this analysis can be found in the 'Question Similarity Analysis.ipynb' notebook.

I first imported the data using pandas and filtered out columns unrelated to the question asked. I then began cleaning the question_content column by first creating a new column with the questions in all lowercase.



# Further Questions:

- Could this analysis include trends for specific crops?
- How would this analysis appear for questions related to other stages in the farming lifecycle including growing, pest control, and harvesting?

# Things That Did Not Work and Works in Progress

- I unfortunately ran out of time, but I would be very interested to try this type of analysis for the rest of the farming lifecycle outside of market related questions including planting, pest control, and harvesting. It would likely only require minor tweaking of the key words used to identify the question topic. 
- Another part of this analysis includes the 'LDA Topic Labeling.ipynb' notebook. Here I attempted to create an LDA model to categorize questions to determine if there were clusters of similar questions being asked. Using this technique ended up resulting in a low coherence score likely due to the low size of the questions asked and as a result could not be used with sufficient accuracy. Using alternative techniques or refining the process could result in achieving a more sufficient topic coherence.
