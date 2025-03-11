# County-Level Analysis of Electric Vehicle Adoption in Washington State

## Project Background

As a data analyst, I've undertaken this project to analyze the relationship between electric vehicle (EV) adoption, political leaning, median income, and voter turnout in Washington State counties.  This is a *personal project* using publicly available data, not affiliated with any specific company. However, I'm approaching it as if I were working for a hypothetical organization with an interest in understanding these trends. Let's imagine I'm working for a non-profit organization focused on promoting sustainable transportation and informed civic engagement.

**Hypothetical Organization:**  "Sustainable Washington"

*   **Industry:**  Environmental Advocacy / Non-Profit
*   **Key Business Metrics:**
    *   **EV Adoption Rate (per 1000 residents):**  A key indicator of the organization's success in promoting sustainable transportation.
    *   **Voter Turnout:**  A measure of civic engagement, a core organizational goal.
    *  **Number of policy changes related to EV adoption:** Shows how effective the organization is to reach its goals.

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

### Correlation between EV Adoption and Political Leaning

*   **A positive correlation exists between the percentage of Democrat votes in a county and the EV adoption rate.** Conversely, there is a negative correlation between the percentage of Republican votes and EV adoption.



*   **Main insight 3:**  Even when controlling for income (as seen in the scatter plots), the relationship between political leaning and EV adoption persists. On the EV Adoption vs Median Salary by County scatter plot, we observe a tendency for Democratic-leaning counties (blue points) to cluster above the overall trendline, while Republican-leaning counties (red points) tend to cluster below it. This suggests a potential effect of political leaning on EV adoption that is not solely explained by income differences, and that factors beyond income, such as environmental attitudes, likely play a role.



*  **Main insight 4:** This correlation is stronger in counties with higher median income.

[Visualization - Include a screenshot of your scatter plot showing EV adoption vs. Democrat/Republican vote percentage, with points colored by winning party.]

### Category 3: Correlation between EV Adoption and Income

*   **Main insight 1:** There is a strong positive correlation between median household income and EV adoption rates.  Higher-income counties tend to have significantly more EVs per 1000 residents.
*   **Main insight 2:**  The R-squared value for this correlation is [Insert Value from your R-Squared measure], indicating [Explain the strength of the correlation based on the R-squared value - e.g., "a moderately strong positive relationship"].
*   **Main insight 3:**  This relationship holds true even when considering political leaning.
*   **Main insight 4**: [Insert Value from your Card visual] is the state's median salary.

[Visualization - Include a screenshot of your scatter plot showing EVs per 1000 vs. Median Salary, with points colored by winning party.]

### Category 4: Correlation between Voter Turnout and other factors

*    **Main Insight 1:** Voter turnout is correlated with the other variables.
*    **Main Insight 2:** Voter turnout has a slight positive correlation with median income.
*    **Main Insight 3:** Counties with a high voter turnout slightly correlate with the EV adoption rate.
*   **Main insight 4:** [Insert Value from your Card visual] is the state's voter turnout.

[Visualization: Scatter plot of Voter Turnout vs. Median Salary and scatter plot of EV Adoption vs Voter Turnout]

## Recommendations

Based on the insights and findings above, we would recommend the [stakeholder team] (Sustainable Washington, in our hypothetical scenario) to consider the following:

*   **Targeted Outreach:**  Focus outreach and education efforts on lower-income counties and Republican-leaning counties to address the disparities in EV adoption. Tailor messaging to address specific concerns and barriers in these communities.
*   **Policy Advocacy:**  Advocate for policies that make EVs more affordable and accessible, such as tax credits, rebates, and expanded charging infrastructure, particularly in underserved areas.
*   **Partnerships:**  Collaborate with local organizations and community leaders in lower-adoption counties to build trust and promote EV awareness.
*   **Messaging Strategy:**  Highlight the economic benefits of EVs (e.g., lower fuel and maintenance costs) in addition to their environmental benefits, particularly when communicating with audiences in lower-income or Republican-leaning areas.
*   **Voter Engagement:** Continue efforts to increase voter turnout, as higher civic engagement may be linked to greater environmental awareness and support for sustainable policies.

## Assumptions and Caveats

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

*   **Data Accuracy:** The analysis relies on the accuracy and completeness of the publicly available datasets. Any errors or omissions in the source data would impact the results.
*   **Correlation vs. Causation:**  The analysis identifies correlations, but these do not necessarily imply causation. Other factors not included in the data could be influencing the observed relationships.
*   **Simplified Party Affiliation:**  The analysis simplifies political leaning into "Democrat" and "Republican," which doesn't capture the full spectrum of political views.
* **Static Data**: Since we only have 2024 election data, it can't be used to study trends, and only one year is considered.
* **EV Data Limitation:** We have considered any EV in the EV dataset, even though some have 0 for their electric range.
