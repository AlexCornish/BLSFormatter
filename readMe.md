# BLS Formatter
## How to run?
- From Desktop:
  - Click the desktop icon for BLS-Formatter.
- From Terminal:
  - Navigate to the BLS-Formatter directory.
  - Enter 'python qtTest.py' and press enter.
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
- There are two main external libraries used by this program. 
    - PyQT5 (For the GUI components of this program)
    - Pandas (For all the data processing)
### Files explained
- qtTest.py: The files that contains the GUI aspects along with some of the control components. 
- BLS_Request.py: Performs all of the BLS data requesting related functionality. Automated checking of data to see if the latest version is located in the file RawData, and pulling of the latest version of the BLS data if the latest version isn't locally downloaded. 
- Industry.py: Contains all the functions necessary for the formatting of the BLS industry data.
- Commodity.py: Contains all the functions necessary for the formatting of the BLS commodity data.
- RawData: The storage location for the downloaded BLS Data. The file can be deleted if you want to, but it will take longer next time the program starts up as it has to download all new data. 
### Foreseeable Issues
- I have tested as many combination of options as possible, but I may have missed something. Tracing it shouldn't be too difficult, but I'm reasonably certain the control flow logic is sound. 
- The dependencies may cause issues when new versions come out. 
- The program is relatively simple, so it should be difficult to find issues.
### Possible Improvements
- Automate the deletion of old BLS Data. Maybe keep the latest 3 months of each dataset or something like that. 
- Performance improvements: There's probably some places where minor improvements could be made, but the worst case processing time is about 10 seconds with all the options on the largest dataset, which I see as acceptable. You could probably shave another second off, but the amount of time this would take would probably not be worth it. 
- Could be expanded to other BLS datasets, if another department needs it. Add a new radio button to the top of the GUI, and a new class similar to the industry.py and commodity.py. Only downside is BLS_Request would need to be modified for it to work. 
