#Project Overview

This project analyzes recent congressional and presidential election results in Illinois' 12th Congressional District, identifying winning candidates, vote percentages, and voter turnout. By integrating demographic data across the district’s counties, we explore how factors such as age, ethnicity, and socioeconomic status influence voter behavior and election outcomes. Our methodology includes data collection from official sources, exploratory data analysis, and rigorous data cleaning to ensure accuracy. The findings provide insights into electoral dynamics, highlighting the interplay between demographics and voter engagement.

##Methodology Summary 

1. Data Collection
• Source: American Community Survey (ACS) 2022 data, redistricting data hub & data USA, OpenSecrets
• Focus Areas: Population, age distribution, income, race and ethnicity, poverty rates, and election voter counts, turnouts and election political parties funding.
2. Data Retrieval
• Demographic Data: Utilized the tidycensus R package for extracting relevant variables. o Total Population: Variable B01003_001.
o Age Distribution: Variables B01001_001, B01001_002, B01001_026.
o Race and Ethnicity: Variables B02008_001 to B02013_001.
o Medium Income • Economic Data:
o Median Household Income: Variable B19013_001.
o Poverty Rates: Variable B17001A_002. • Housing Data:
o Total Housing Units: Variable B25001_001. • Election Funding
3. Data Cleaning
• Validation: Checked for missing or inconsistent data entries to ensure accuracy.
• Standardization: Standardized variable formats for consistency across datasets, such as converting income values to a common currency format and ensuring demographic
categories were uniformly defined.
• Outlier Removal: Identified and addressed any outliers that could skew analysis, focusing
on extreme values in income and population metrics.
• Missing or Inconsistent Aggregations: Missing values at the county level (e.g., missing
demographic information for a county), are handled by imputing using the average of neighboring counties or based on historical data. Also, used external data sources to fill in the gaps (e.g., census data).
• Date and Temporal Alignment: Ensured that the temporal dimensions of the county-level data align with your present-level data.
• Geospatial Consistency: Ensured that the county-level data uses a consistent identifier (e.g., county FIPS code or name) that will allow for proper merging.
4. Data Analysis
• Population Characteristics: Analyzed racial composition, income levels, and poverty rates.
• Election Funding: Analyzed funding to political parties over multiple years and inference relationships to election results.
5. Similar Districts Identification
• Data Collection: Similar ACS variables were retrieved for all congressional districts.
• Data Transformation: Numeric conversions and summarization were applied.
• Similarity Assessment: Compared population, median income, and poverty rate; ranked
districts based on the smallest absolute differences.
• Election Context: Included recent election results for additional insights.
7. Model Selection and Training
In this phase of the project, appropriate algorithms were chosen based on the nature of the problem and the characteristics of the dataset. The selection was guided by the specific task at hand:
• For Regression Tasks: Algorithms such Random Forest were considered, as they are commonly used for predictive modeling in regression scenarios.
• For Classification Tasks: Algorithms like Logistic Regression and k-Nearest Neighbors (kNN) were evaluated, depending on the complexity and nature of the data.
The dataset was split into training and testing sets to evaluate model performance. A typical 80(2016 to 2020) / 20 (2022) split was used, ensuring that the training data was large enough to build a robust model while reserving sufficient data for testing.
To further validate the models and assess their ability to generalize, k-fold cross-validation was employed. This technique helped ensure that the models did not overfit the training data and performed consistently across different subsets of the dataset.
8. Model Evaluation
In this phase, the model's performance was assessed using a range of appropriate evaluation metrics tailored to the type of problem being addressed:
• For Regression Models: Performance was evaluated using metrics such as Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and R-squared, which measure the accuracy of the predictions and the goodness of fit to the data.
• For Classification Models: The evaluation focused on metrics like Accuracy, Precision, Recall, F1-score, and ROC-AUC, which provide insights into the model's ability to correctly classify instances, balance false positives and false negatives, and handle imbalanced classes.
Finally, the performance of different models was compared across the chosen evaluation metrics. The model that demonstrated the best overall performance was selected based on its ability to meet the specific goals of the project while minimizing errors and maximizing predictive accuracy.
8. Results Interpretation
• Visualizations: Used visualizations (e.g., graphs, charts) to derive insights and predictions effectively.
• Reports and Documentation: Prepared a detailed report that explains the methodology, results, assumptions, and limitations. Included model interpretability and explain ability.
The analysis is comprehensive, capturing essential characteristics of the district while highlighting similar districts for comparative context. Future studies could benefit from additional historical and local issue analyses.

- project_osna_demographic_data.Rmd - contains EDA for demographic data of Illinois 12 district.                
- project_osna_electoral_data.Rmd - contains EDA for electoral data of Illinois 12 district.                           
- project_osna_spatial_analysis.qmd - displays the boundaries of the precincts for Illinois 12 district.
- Funding.ipynb - contains election funding analysis for Illinois 12 district.
- OSNA_CWINNER.ipynb - congressional elections prediction in Illinois 12 district.                     
- OSNA_PWINNER.ipynb - presidential elections prediction in Illinois 12 district.
- CWINNER_VT.ipynb - congressional elections voter turnout prediction in Illinois 12 district.
- PWINNER_VT.ipynb - presidential elections voter turnout prediction in Illinois 12 district.
