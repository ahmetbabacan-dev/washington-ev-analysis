# Project 1 Steps

## Step 1: Data Cleaning and Preprocessing (Microsoft Excel)

### Washington_Election_Results.csv (Original file name: 20241105_allcounties)

  Here are the first couple of rows of the file before any cleaning:

  ![elections-before-csv](https://github.com/user-attachments/assets/de353dc6-d0f2-4267-8610-15af367bc131)

* The dataset contains all candidates from all parties for both state and federal-level elections, and since I only need the presidential candidates, I selected Data > Filter and selected all of the options other than United States President/Vice President in the Race column to get every row that I don’t need. Then, I selected the second row and pressed Ctrl + Shift + Down Arrow to select all rows and used Home > Delete > Delete Sheet Rows to delete the rows.
* I selected the Race, Candidate, and JurisdictionName columns and used Home > Delete > Delete Sheet Columns to delete the columns.
* There are single space values in the Party column, which corresponded to the write-in candidates, but since we deleted the Candidate column, I replaced all of these single space values with “Write-in” using Ctrl + F > Replace. I made sure to select the “Match entire cell contents” option to avoid replacing other spaces in other cells.
* To bring the PercentageOfTotalVotes values between 0 and 1 to enable easier calculations and analysis, I applied the =D2/100 formula in cell F2 to all rows. Then, I copied the entire F column and pasted the values only to eliminate the formulas. I deleted the original column and named the new column PercentageOfTotalVotes.

  Here are the first couple of rows of the file after cleaning:

  ![elections-after-csv](https://github.com/user-attachments/assets/1ffd38bf-6951-4715-a2c7-33fed59c0b63)

### Washington_Population_2024.csv (Original file name: ofm_april1_population_final.xlsx)

  Here are the first couple of rows of the file before any cleaning:

  ![population-before](https://github.com/user-attachments/assets/9c1b006b-9d97-4b59-9bb5-ccc8042ecadb)

* Since I only need the county-level population data and not anything more granular, I filtered the Jurisdiction column using a Custom Filter with “ends with ‘County’” and “does not contain ‘incorporated’” to leave only the 39 county rows.

  ![population-filter](https://github.com/user-attachments/assets/297cbe8f-67a8-4bb2-ac9d-ecd6c9f03240)

* Then I copied the County and 2024 Population Estimate columns and pasted the values into another sheet and formatted it as a table.
* Finally, I deleted the original sheets since I don’t need the information in them.

  Here are the first couple of rows of the file after cleaning:

  ![population-after](https://github.com/user-attachments/assets/59cc68af-35df-4b4c-8fa8-d01180c1677c)

### Washington_Electric_Vehicle_Population_Data (Original file name: Electric_Vehicle_Population_Data)

  Here are the first couple of rows of the file before any cleaning:

  ![ev-before](https://github.com/user-attachments/assets/156fccdb-0c0e-43f8-9f2a-3e479e74d20d)

1. I deleted the VIN (1-10), City, Postal Code, Legislative District, DOL Vehicle ID, Vehicle Location, Electric Utility, 2020 Census Tract, City, Electric Range, and Clean Alternative Fuel Vehicle (CAFV) Eligibility columns.
2. Base MSRP column could’ve been useful, but since approximately 98.6% of the values (228,926 out of 232230) are 0, I deleted the column.
3. Since the analysis is only about Washington State, I selected Data > Filter and selected all of the options other than WA in the State column to get every row that I don’t need. Then, I selected the second row and pressed Ctrl + Shift + Down Arrow to select all rows and used Home > Delete > Delete Sheet Rows to delete the rows. Then, I deleted the State column since all the remaining values are WA.

  Here are the first couple of rows of the file after cleaning:

  ![ev-after](https://github.com/user-attachments/assets/fa7f39bc-462e-48f2-a402-90f43c58555d)

### US_County_Median_Income

  Here are the first couple of rows of the file before any cleaning:

  ![income-before](https://github.com/user-attachments/assets/3f34e0b0-64fd-4f09-9e8a-bd41cc4cf30b)

1. I deleted the information rows on the top and bottom of the file to leave only the table.
2. I deleted the United States and Washington rows since I only need the county-level data.
3. I deleted the FIPS column since I don’t need the counties' FIPS codes.

  Here are the first couple of rows of the file after cleaning:

  ![income-after](https://github.com/user-attachments/assets/dfffbb94-4ca9-4357-879c-726db26acf1f)

## Step 2: Data Transformation

1. I loaded all CSV files into Power BI using Home > Get Data > Text/CSV and selected Transform Data.
2. Renamed the queries to reflect their content better.
3. To remove the “County” words at the end of the cells in the County column of the Washington_Median_Income_by_County query, I selected the County column, used Split Column > By Delimiter, and chose Space as the delimiter and right-most delimiter. Then I deleted the column with all the “County” cells and renamed the original column back to “County” from “County.1”.
4. I deleted the “Rank within US” column of the Washington_Median_Income_by_County query since it isn’t useful for my analysis.
5. I renamed the “Value (Dollars)” column to “Median Salary”.
6. I wanted to group every other Party column value other than "Democratic Party Nominees" and "Republican Party Nominees" as "Other", with their Votes and PercentageOfTotalVotes values also summed/grouped. To achieve this, I used Add Column > Custom Column and added a Custom Column to classify parties into "Democrat", "Republican", and "Other" with the following formula: `if [Party] = "Democratic Party Nominees" then "Democrat"
else if [Party] = "Republican Party Nominees" then "Republican"
else "Other"` . Then, I selected the County and Party Grouped columns and used Home > Group By. I entered the following settings to achieve the desired output:

![party group by](https://github.com/user-attachments/assets/2ed81727-c746-40ed-ac23-afaaa89bc13d)

After this, I changed the Party Grouped column's type to text, Total Votes to Whole Number, and renamed Party Grouped to Party.

7. To discern how much of the population is registered voters, I downloaded the Washington Secretary of State's Voter Demographics Tables from here
