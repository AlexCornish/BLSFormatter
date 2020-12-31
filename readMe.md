# BLS Formatter
## How to use?
1. Select a BLS (Bureau of Labour Services) dataset. Commodity (WP) or Industry (PC)
2. Select a time period format for the output.
  - Monthly: The default, how the data is originally received from the BLS. Monthly Values.
  - Quarterly: The monthly data will be split into the 4 Quarters with each of them averaged to find the quarterly values.
  - Yearly: The monthly data will be averaged to find the yearly value. 
3. Choose which other options you would like applied to the output.
  - Drop M13: (Monthly only) Drops all M13 periods from the dataset
  - Format Time Period as YYYY-MM-01: (Monthly only) Takes the Period and Year columns and replaces them with the YYYY-MM-01 format.
  - Add Seasonal Code: (Monthly only) Adds the seasonal code from the series_id column as a separate row.
  - Add Year-Over-Year: (Monthly only) Adds year-over-year differences for values.
  - Add Percentage Change Between Period: Adds a column of the differences between the period and the previous period.
  - Add Labels for Each Level: Adds the descriptive labels for the series_id parts.
  - Split ID Values: Splits the series_id column into its two component parts.
  - Formats Dataframe Wide: Formats the dataframe in the wide format. 
 4. Press save
  - Wait until the savebox appears and choose the save location / file name
  
## Technical Documentation
### Dependencies
