# Project 1 Steps

## Step 1: Data Cleaning and Preprocessing

### Washington_Election_Results.csv (Original file name: 20241105_allcounties)

Here are the first couple of rows of the file before any cleaning:

![elections-before-csv](https://github.com/user-attachments/assets/de353dc6-d0f2-4267-8610-15af367bc131)

*  1. The dataset contains all candidates from all parties for both state and federal-level elections, and since I only need the presidential candidates, I selected Data > Filter and selected all of the options other than United States President/Vice President in the Race column to get every row that I don’t need. Then, I selected the second row and pressed Ctrl + Shift + Down Arrow to select all rows and used Home > Delete > Delete Sheet Rows to delete the rows.
2. I selected the Race, Candidate, and JurisdictionName columns and used Home > Delete > Delete Sheet Columns to delete the columns.
3. There are single space values in the Party column, which corresponded to the write-in candidates, but since we deleted the Candidate column, I replaced all of these single space values with “Write-in” using Ctrl + F > Replace. I made sure to select the “Match entire cell contents” option to avoid replacing other spaces in other cells.
4. To bring the PercentageOfTotalVotes values between 0 and 1 to enable easier calculations and analysis, I used the =D2/100 formula in cell F2 and applied it to all rows. Then, I copied the entire F column and pasted the values only to get rid of the formulas. I deleted the original column and named the new column PercentageOfTotalVotes.
5. *The “Party” and “Nominees” words in the Party column are unnecessary and take up space in the data model, so to remove them, I first created 2 more columns using Home > Insert > Insert Sheet Columns since the column will be split into 3 columns. Then I selected the Party column and used Data > Text to Columns using the Space delimiter to split the column into 3 columns. I deleted the last 2 columns with the “Party” and “Nominees” cell values.*
6. *Since the only remaining distinct values in the Party column are “Democratic” and “Republican”, we need to replace “Democratic” values with “Democrat”. To accomplish this, I created an empty column using Home > Insert > Insert Sheet Column and used `=IF(B2="Democratic", SUBSTITUTE(B2, "Democratic", "Democrat"), B2)` function. Then, I copied the entire C column and pasted the values only to get rid of the formulas. I deleted the original column and named the new column PercentageOfTotalVotes.*

ofm_april1_population_final

1. Since I only need the county-level population data and not anything more granular, I filtered the Jurisdiction column using a Custom Filter with “ends with ‘County’” and “does not contain ‘incorporated’” to leave only the 39 county rows.
2. Then I copied the County and 2024 Population Estimate columns and pasted the values into another sheet, and formatted it as a table.
3. Finally, I deleted the original sheets since I don’t need the information in them.

Electric_Vehicle_Population_Data

1. I selected VIN (1-10), Postal Code, Legislative District, DOL Vehicle ID, Vehicle Location, Electric Utility, 2020 Census Tract
2. Base MSRP column could’ve been useful but since approximately %98.6 of the values (228,926 out of 232230) are 0, I deleted the column.
3. Since the analysis is only about Washington State, I selected Data > Filter and selected all of the options other than WA in the State column to get every row that I don’t need. Then, I selected the second row and pressed Ctrl + Shift + Down Arrow to select all rows and used Home > Delete > Delete Sheet Rows to delete the rows.

US_County_Median_Income

1. I deleted the information rows on the top and bottom of the file to leave only the table.
2. I deleted the United States and Washington rows since I only need the county-level data.
3. I deleted the FIPS column since I don’t need the counties' FIPS codes.

Data Transformation

1. I loaded all CSV files into Power BI using Home > Get Data > Text/CSV and selected Transform Data.
2. Renamed the queries to reflect their content better.
3. To remove the “County” words at the end of the cells in the County column of the Washington_Median_Income_by_County query, I selected the County column, used Split Column > By Delimiter, and chose Space as the delimiter and right-most delimiter. Then I deleted the column with all the “County” cells and renamed the original column back to “County” from “County.1”.
4. I deleted the “Rank within US” column of the Washington_Median_Income_by_County query since it isn’t useful for my analysis.
5. I renamed the “Value (Dollars)” column to “Median Salary”.
6. I wanted to group every other Party column value other than "Democratic Party Nominees" and "Republican Party Nominees" as "Other", with their Votes and PercentageOfTotalVotes values also summed/grouped. To achieve this, I used Add Column > Custom Column and added a Custom Column to classify parties into "Democrat", "Republican", and "Other" with the following formula: `if [Party] = "Democratic Party Nominees" then "Democrat"
else if [Party] = "Republican Party Nominees" then "Republican"
else "Other"` . Then, I selected the County and Party Grouped columns and used Home > Group By. I entered the following settings to achieve the desired output.
