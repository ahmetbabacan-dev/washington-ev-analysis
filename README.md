# County-Level Analysis of Electric Vehicle Adoption in Washington State

## Project Background

As a data analyst, I've undertaken this project to analyze the relationship between electric vehicle (EV) adoption, political leaning, median income, and voter turnout in Washington State counties.  This is a *personal project* using publicly available data, not affiliated with any specific company. However, I'm approaching it as if I were working for a hypothetical organization with an interest in understanding these trends. Let's imagine I'm working for a non-profit organization focused on promoting sustainable transportation and informed civic engagement.

**Hypothetical Organization:**  "Sustainable Washington"

*   **Industry:**  Environmental Advocacy / Non-Profit
*   **Key Business Metrics:**
    *   **EV Adoption Rate (per 1000 residents):**  A key indicator of the organization's success in promoting sustainable transportation.
    *   **Number of policy changes related to EV adoption:** This shows how effective the organization is in reaching its goals.

Insights and recommendations are provided on the following key areas:

*   **Overall EV Adoption Trends:** Evaluation of general electric vehicle adoption trends across Washington state, focusing on top counties with the highest number of total EVs, and EV count per 1000 people along with the election results for each county.
*   **Correlation between EV Adoption and Political Leaning:** Analysis of the correlation between EV adoption rates and vote rates of major political parties.
*   **Correlation between EV Adoption and Income:** Analysis of the correlation between EV adoption rates and median household income.
*   **Correlation between Voter Turnout and other factors:** Analysis of the correlation between voter turnout rate, EV adoption rate, and median household income.

The steps taken in Microsoft Excel used to inspect and clean the data for this analysis can be found here [link].

The steps taken in Microsoft Power BI used to transform and visualize the data for this analysis can be found here [link].

An interactive Power BI dashboard used to report and explore sales trends can be found here [link].

## Data Structure & Initial Checks

The analysis uses four publicly available datasets:

*   **Washington_Election_Results_2024:**  2024 Washington State county-level election results. Contains data on votes for each party (Democrat, Republican) by county, including the total votes and percentage of total votes. [Data Source](https://results.vote.wa.gov/results/20241105/export.html)
*   **Washington_Electric_Vehicle_Population_Data:**  Information on electric vehicles registered in Washington State. Includes details on individual EVs, such as brand, model, model year, electric vehicle type, and county. [Data Source](https://catalog.data.gov/dataset/electric-vehicle-population-data)
*   **Washington_Median_Income_by_County:** Median household income by county in Washington State. [Data Source](https://hdpulse.nimhd.nih.gov/data-portal/social/table?socialtopic=030&socialtopic_options=social_6&demo=00011&demo_options=income_3&race=00&race_options=race_7&sex=0&sex_options=sexboth_1&age=001&age_options=ageall_1&statefips=53&statefips_options=area_states)
*   **Washington_Population_2024:**  2024 population estimates for Washington State counties. [Data Source](https://ofm.wa.gov/washington-data-research/population-demographics/population-estimates/april-1-official-population-estimates)

![entity relationship diagram](https://github.com/user-attachments/assets/5b679540-d22f-4646-864d-5825243252fa)

## Executive Summary

### Overview of Findings

This analysis reveals significant variations in EV adoption rates across Washington State counties, with a noticeable correlation between EV adoption, median income, and political leaning.  Higher-income counties tend to have higher EV adoption rates.  There's also a relationship between political leaning and EV adoption, with Democratic-leaning counties generally showing higher adoption rates, even when considering income.  Voter turnout also shows some positive correlation with EV adoption, but there is almost no correlation between voter turnout and income.

![overview1](https://github.com/user-attachments/assets/67382bc3-ec7d-4671-b905-bf49009d8bdc)

![overview2](https://github.com/user-attachments/assets/aa970796-050b-4f57-bb30-324436b98873)

## Insights Deep Dive

### Overall EV Adoption Trends

*   **EV adoption rates vary significantly across Washington State counties.** King County has the highest number of EVs by far, with more than 4 times more EVs than the second place, while many rural counties have significantly lower adoption rates.

![ev adoption map](https://github.com/user-attachments/assets/cbd58e11-a09e-4230-9b95-3d0f8c07672c)

*   **All 5 of the top 5 counties with the most electric vehicles are Democrat-leaning.** The statewide average EV adoption rate is 28.84 EVs per 1000 residents.

![top 5 counties](https://github.com/user-attachments/assets/b8eeb565-f9b3-492b-bd1e-c551aa59f648)

*   **Tesla is the most popular EV make in Washington State**, followed by Chevrolet, Nissan, Ford, and Kia.

![top 5 brands](https://github.com/user-attachments/assets/6cf926c7-45ff-49a9-9bff-0b3fee769500)

### Correlation between EV Adoption and Income

*   **A strong positive correlation exists between median household income and EV adoption rates.** Higher-income counties tend to have significantly more EVs per 1000 residents. The R-squared value for this correlation is 0.66, indicating a strong positive relationship".

![ev vs median salary2](https://github.com/user-attachments/assets/a16da4e9-e3b8-4851-b233-5580bbeb5c79)

### Correlation between EV Adoption and Political Leaning

*   **A positive correlation exists between the percentage of Democrat votes in a county and the EV adoption rate.** Conversely, there is a negative correlation between the percentage of Republican votes and EV adoption.

![ev vs democrat](https://github.com/user-attachments/assets/e5f8b4eb-f522-40af-a035-19123e87b5d8)

*   **Even when controlling for income (as seen in the scatter plots), the relationship between political leaning and EV adoption persists.** On the EV Adoption vs Median Salary by County scatter plot, we observe a tendency for Democratic-leaning counties (blue points) to cluster above the overall trendline. In contrast, Republican-leaning counties (red points) tend to cluster below it (highlighted with a green ellipse). This suggests a potential effect of political leaning on EV adoption that is not solely explained by income differences and that factors beyond income, such as environmental attitudes, likely play a role.

![ev vs median salary](https://github.com/user-attachments/assets/61431079-74d2-43b6-91d8-01f7e7548531)

### Which is the better predictor: Income or Political Leaning?

*   **While both income and political leaning have strong correlations with EV adoption, political leaning is a better predictor of EV adoption on the county level than income alone.** This is visible when we look at the correlation coefficients, which is 0.88 for EV adoption and Democrat vote percentage, and 0.66 for EV adoption and income.

*    **The percentage of Republican votes has a moderately negative correlation with income, meaning Republican-leaning counties tend to earn less.** This may explain the lower EV adoption in Republican-leaning counties, but the correlation between EV adoption and Democrat vote percentage is stronger than the correlation between Income and Republican vote percentage (with correlation coefficients of 0.88 vs -0.57, respectively), meaning as Democrat votes go up, EV adoption goes up along with it more than the median household income.

![salary vs republican](https://github.com/user-attachments/assets/f9a76fe5-8a02-4e87-9198-f2c75cb44a90)

## Recommendations

Based on the insights and findings above, we would recommend the [stakeholder team] (Sustainable Washington, in our hypothetical scenario) to consider the following:

*   **Targeted Outreach:**  Focus outreach and education efforts on lower-income counties and Republican-leaning counties to address the disparities in EV adoption. Tailor messaging to address specific concerns and barriers in these communities.
*   **Policy Advocacy:**  Advocate for policies that make EVs more affordable and accessible, such as tax credits, rebates, and expanded charging infrastructure, particularly in underserved areas.
*   **Partnerships:**  Collaborate with local organizations and community leaders in lower-adoption counties to build trust and promote EV awareness.
*   **Messaging Strategy:**  Highlight the economic benefits of EVs (e.g., lower fuel and maintenance costs) in addition to their environmental benefits, particularly when communicating with audiences in lower-income or Republican-leaning areas.

## Assumptions and Caveats

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

*   **Data Accuracy:** The analysis relies on the accuracy and completeness of the publicly available datasets. Any errors or omissions in the source data would impact the results.
*   **Correlation vs. Causation:**  The analysis identifies correlations, but these do not necessarily imply causation. Other factors not included in the data could be influencing the observed relationships.
*   **Simplified Party Affiliation:**  The analysis simplifies political leaning into "Democrat" and "Republican," which doesn't capture the full spectrum of political views.
*   **Static Data**: Since we only have 2024 election data, it can't be used to study trends, and only one year is considered.
*   **EV Data Limitation:** We have considered any EV in the EV dataset, even though some have 0 for their electric range.
