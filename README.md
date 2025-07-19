# Analysis-of-datasets-in-Nutrition-Paradox
A Global View on Obesity and Malnutrition

# Overview:

This project simulates the role of a Data Analyst at a global health organization, focusing on the dual challenge of undernutrition and overnutrition worldwide. Using publicly available WHO data, the analysis involves examining obesity and malnutrition trends across various countries, age groups, and genders. The primary objective is to identify key patterns, disparities, and insights that can support the development of effective global health strategies. Ultimately, the goal is to help address the nutritional paradox—where both obesity is rising and malnutrition persists in different parts of the world.

# Business Use Cases

Nutrition Risk Monitoring: Identify countries with extremely high obesity or malnutrition levels, flagging them for public health intervention.
Demographic Disparity Analysis: Understand how gender and age groups contribute differently to obesity and malnutrition statistics.
Data-Driven Policy Planning: Help policymakers prioritize regions for funding and nutrition-related programs based on multi-dimensional data.
Comparative Region Analysis: Enable researchers to compare regional trends and draw correlations between health indicators and socio-economic conditions.
Public Health Reporting: Provide government or NGOs with a summarized SQL + Power BI dashboard showing country-level nutrition trends.

# Methods used in Data Collection:

Using WHO API URLs, Data scrapped for Obesity and Malnutrition.
Each dataset provides estimates by country, sex, year, and region, along with confidence intervals (upper and lower bounds).

# Preprocessing steps made for extracted Data Frame:

Loaded all 4 datasets.
Added a new column age_group to distinguish adults and children.
Combined the two obesity datasets into one dataframe called df_obesity.
Combined the two malnutrition datasets into one dataframe called df_malnutrition.
Filtered each dataset to include only records from the years 2012 to 2022

# Data Cleaning steps made for dataset:

Extracted specified columns(ParentLocation, Dim1, TimeDim, Low, High, NumericValue, SpatialDim, age_group) in each datasets

Renamed the extracted columns as 
TimeDim → Year
Dim1 → Gender
NumericValue → Mean_Estimate
Low → LowerBound
High → UpperBound
ParentLocation → Region
SpatialDim → Country

Changed the values of Gender column into meaningful categorical values.

Convertion of 3-letter country codes (ISO Alpha-3) into full country names in the Country column.

Created new column with values as
CI_Width = High - Low
obesity_level = Categorized obesity levels based on NumericValue(>= 30 → High, 25–29.9 → Moderate, < 25 → Low)
malnutrition_level = Categorized malnutrition levels based on NumericValue(>= 20 → High, 10–19.9 → Moderate, < 10 → Low)

Overall Column descriptions:
<img width="398" height="291" alt="Dataset" src="https://github.com/user-attachments/assets/9b895e47-82d3-4657-acc6-00595298d17f" />
