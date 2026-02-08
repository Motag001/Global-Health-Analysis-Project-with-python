# Global Health Statistics Project (Health Analysis) - README

## Project Objective

The primary objective of this project is to perform a comprehensive health analysis using global health statistics. This involves exploring various aspects of disease prevalence, mortality, healthcare access, and their socio-economic and temporal trends across different countries and disease categories.

## Dataset Details

The analysis is based on the **'Global Health Statistics.csv'** dataset, which contains detailed information on various health metrics, diseases, and socio-economic indicators across multiple countries and years.

## Methodologies Used

### Data Cleaning and Preprocessing

Initial data completeness checks revealed a single row with missing values across several columns (`Hospital Beds per 1000`, `Treatment Type`, `Average Treatment Cost (USD)`, `Availability of Vaccines/Treatment`, `Recovery Rate (%)`, `DALYs`, `Improvement in 5 Years (%)`, `Per Capita Income (USD)`, `Education Index`, `Urbanization Rate (%)`). This row was dropped to ensure data integrity for subsequent analysis, reducing the dataset size from 70217 to 70216 entries.

### Data Validity and Logic Checks

Several logical checks were performed to ensure data validity:
- No records were found where 'Recovery Rate (%)' was greater than 100.
- No records were found with negative values for 'Mortality Rate (%)', 'Healthcare Access (%)', 'Doctors per 1000', or 'Hospital Beds per 1000'.
- All 'Year' entries were within the expected range of 2000-2024.
- No records showed zero or unrealistically high 'Average Treatment Cost (USD)' (e.g., above $70,000).

### Outlier Detection

Outlier analysis was conducted using the Interquartile Range (IQR) method (specifically, 3 * IQR for extreme outliers) for key numerical features:
- **Average Treatment Cost (USD)**: No extreme outliers were identified.
- **DALYs (Disability-Adjusted Life Years)**: No extreme outliers were identified.
- **Mortality Rate (%)**: No extreme outliers were identified.

This indicates that the dataset is relatively clean and does not contain data points that fall drastically outside the typical range for these critical metrics.

## Univariate & Distribution Analysis

### Disease & Population Overview
- The frequency of different **Disease Categories** was analyzed to identify the most common types of diseases in the dataset.
- The distribution of diseases across various **Age Groups** and the **proportion of records by Gender** were examined to understand demographic patterns in health data.

### Health Metric Distributions
- Histograms were generated to visualize the distribution of key health metrics:
    - **Prevalence Rate (%)**: Showed the frequency distribution of disease occurrence.
    - **Mortality Rate (%)**: Illustrated the spread of fatality rates across the dataset.
    - **Recovery Rate (%)**: Presented the distribution of patient recovery success.
    - **Average Treatment Cost (USD)**: Displayed the distribution of treatment expenses.
These visualizations provide insights into the central tendency, spread, and shape of these critical health indicators.

## Geographical Health Analysis

### Country-Level Burden
- **Highest Total DALYs**: Identified countries with the highest total Disease-Adjusted Life Years, indicating the greatest overall disease burden.
- **Highest Average Mortality Rates**: Pinpointed countries experiencing the highest average mortality rates.
- **Lowest Average Healthcare Access**: Highlighted countries with the lowest average healthcare access, suggesting potential disparities in health infrastructure.

### Regional Inequality
- **Mortality Rate Variation by Income Level**: Analysis showed only slight variations in average mortality rates across different income brackets (High, Upper-Middle, Low, Lower-Middle Income), suggesting that per capita income alone might not be a strong determinant of average mortality rates in this dataset.
- **Mortality in High-Income Countries**: No consistent trend of uniformly low mortality rates was observed in high-income countries. Specific high-income nations showed a range of mortality rates, implying that individual country-specific health policies and disease prevalence play significant roles.
- **Countries with High Prevalence and Low Mortality**: Several countries were identified with high disease prevalence rates (above Q3) but relatively low mortality rates (below Q1). Examples include Canada (Tuberculosis), Brazil (Ebola), Nigeria (Diabetes), France (Polio), China (Cancer, Hepatitis), and Turkey (Hepatitis). These cases suggest effective treatment, prevention strategies, or the nature of the diseases themselves lead to lower fatality despite widespread occurrence.
- **Visualizations**: Bar charts displayed average mortality rates by income bracket, and scatter plots illustrated the relationship between prevalence and mortality rates, colored by income bracket, confirming a general distribution rather than clear clusters for income levels.

## Temporal (Time-Series) Analysis

### Trends Over Time
- **Global Prevalence Rate**: A line plot showed the trend of the average global prevalence rate over the years.
- **Global Mortality Rate**: A line plot displayed the trend of the average global mortality rate over the years, revealing overall patterns of increase or decrease.
- **Disease Category Improvement**: The average 'Improvement in 5 Years (%)' was calculated for each disease category, identifying those with the strongest average improvement (e.g., 'Bacterial' diseases showing the highest average improvement).

### Disease-Specific Trends
- **Greatest Mortality Reduction**: Diseases with the most significant mortality reduction were identified by comparing their average mortality rates in the earliest and latest years. Top diseases included Cancer, Alzheimer's Disease, Malaria, Diabetes, and Tuberculosis, showing reductions ranging from 0.388% to 0.263%.
- **Little or No Improvement**: Diseases showing 'Improvement in 5 Years (%)' values less than or equal to 0.5% were identified as having little to no progress. This included Parkinson's Disease, Leprosy, Ebola, Rabies, Diabetes, Hypertension, Malaria, Hepatitis, Polio, and Alzheimer's Disease, all registering 0.0% improvement in 5 years.
- **Consistency of Improvements Across Countries**: Analysis of the average 'Improvement in 5 Years (%)' by country indicated that healthcare improvements are relatively consistent across countries. The average improvement rates ranged narrowly from approximately 4.938% (UK) to 5.078% (Canada), suggesting a widespread rather than concentrated distribution of improvements.
- **Visualizations**: Line plots illustrated the mortality rate trends for selected diseases with significant reduction, and bar charts displayed the improvement rates for diseases showing little to no progress.

## Disease Burden & Impact Analysis

### DALYs & Impact
- **Highest Total DALYs Contribution**: Diseases like Parkinson's Disease, Tuberculosis, and Malaria were identified as having the highest total DALYs, indicating their significant long-term impact on health and productivity.
- **Low Mortality Rate but Very High DALYs**: Several diseases were found to have low mortality rates (below Q1) but very high DALYs (above Q3), such as HIV/AIDS (e.g., in France, 0.44% mortality, 3757 DALYs) and various diseases across different countries, suggesting conditions that cause chronic disability rather than immediate fatality.
- **Average DALYs Across Age Groups**: Analysis showed how disease burden (DALYs) differs across age groups, providing insights into which populations are most affected by long-term health issues.

### Disease Category Comparison
- **Average DALYs by Disease Category**: 'Autoimmune' disease category exhibited the highest average DALYs (2525.66), indicating the highest long-term disability impact among categories.
- **Communicable vs. Non-Communicable Diseases**: After classifying diseases into 'Communicable' and 'Non-Communicable' types:
    - **Communicable diseases** had an average DALYs of 2504.19 and an average mortality rate of 5.06%.
    - **Non-Communicable diseases** had a slightly higher average DALYs of 2505.49 but a slightly lower average mortality rate of 5.03%.
    - This suggests a very similar overall burden between the two broad categories.
- **Visualizations**: Bar charts were used to compare average mortality rates and DALYs by disease category, as well as to highlight the burden comparison between communicable and non-communicable diseases.

## Disease Burden & Impact Analysis

### DALYs & Impact
- **Highest Total DALYs Contribution**: Diseases like Parkinson's Disease, Tuberculosis, and Malaria were identified as having the highest total DALYs, indicating their significant long-term impact on health and productivity.
- **Low Mortality Rate but Very High DALYs**: Several diseases were found to have low mortality rates (below Q1) but very high DALYs (above Q3), such as HIV/AIDS (e.g., in France, 0.44% mortality, 3757 DALYs) and various diseases across different countries, suggesting conditions that cause chronic disability rather than immediate fatality.
- **Average DALYs Across Age Groups**: Analysis showed how disease burden (DALYs) differs across age groups, providing insights into which populations are most affected by long-term health issues.

### Disease Category Comparison
- **Average DALYs by Disease Category**: 'Autoimmune' disease category exhibited the highest average DALYs (2525.66), indicating the highest long-term disability impact among categories.
- **Communicable vs. Non-Communicable Diseases**: After classifying diseases into 'Communicable' and 'Non-Communicable' types:
    - **Communicable diseases** had an average DALYs of 2504.19 and an average mortality rate of 5.06%.
    - **Non-Communicable diseases** had a slightly higher average DALYs of 2505.49 but a slightly lower average mortality rate of 5.03%.
    - This suggests a very similar overall burden between the two broad categories.
- **Visualizations**: Bar charts were used to compare average mortality rates and DALYs by disease category, as well as to highlight the burden comparison between communicable and non-communicable diseases.

## Summary:

### Data Analysis Key Findings

*   **Data Integrity:** The initial dataset, comprising 70,217 entries, was cleaned by removing one row with missing values, resulting in 70,216 valid entries. Data validity checks confirmed no illogical values (e.g., recovery rates > 100% or negative health metrics) and no extreme outliers were found for 'Average Treatment Cost (USD)', 'DALYs', or 'Mortality Rate (%)'.
*   **Geographical Disparities:** Analysis identified countries with the highest total Disability-Adjusted Life Years (DALYs), highest average mortality rates, and lowest average healthcare access. There were only slight variations in average mortality rates across different income brackets, and high-income countries did not consistently show uniformly low mortality rates.
*   **Effective Management Cases:** Several countries were found to have high disease prevalence rates (above Q3) but relatively low mortality rates (below Q1), such as Canada (Tuberculosis), Brazil (Ebola), Nigeria (Diabetes), France (Polio), China (Cancer, Hepatitis), and Turkey (Hepatitis). This suggests effective treatment or prevention strategies are in place for these specific diseases in those regions.
*   **Temporal Trends & Improvements:**
    *   'Bacterial' diseases exhibited the highest average improvement in 5 years.
    *   Significant mortality reductions were observed for diseases like Cancer, Alzheimer's Disease, Malaria, Diabetes, and Tuberculosis, with reductions ranging from 0.263% to 0.388%.
    *   However, diseases such as Parkinson's Disease, Leprosy, Ebola, and Rabies showed little to no improvement (0.0% improvement in 5 years).
    *   Average healthcare improvements were found to be relatively consistent across countries, with average improvement rates ranging narrowly from approximately 4.938% (UK) to 5.078% (Canada).
*   **Disease Burden:**
    *   Parkinson's Disease, Tuberculosis, and Malaria contributed to the highest total DALYs.
    *   Diseases like HIV/AIDS (e.g., 0.44% mortality, 3757 DALYs in France) and others demonstrated low mortality rates but very high DALYs, indicating a significant long-term impact through chronic disability rather than immediate fatality.
    *   The 'Autoimmune' disease category showed the highest average DALYs (2525.66).
    *   Communicable diseases had an average DALYs of 2504.19 and an average mortality rate of 5.06%, while non-communicable diseases had a slightly higher average DALYs (2505.49) but a slightly lower average mortality rate (5.03%), suggesting a very similar overall burden between the two categories.

### Insights or Next Steps

*   **Targeted Interventions:** Investigate the specific healthcare policies, treatment protocols, or socio-economic factors in countries with high disease prevalence but low mortality to understand and replicate their success in other regions facing similar challenges.
*   **Focus on Chronic Disability:** Given the significant DALYs contribution from diseases with low mortality, future analysis should delve deeper into the long-term care needs, economic impact, and quality of life implications associated with these conditions to develop targeted support systems.
