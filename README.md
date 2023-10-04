# Tableau-challenge
This repository consists of the code and raw files used for data preparation for a Citi Bike Data Analysis Tableau Challenge 
Citi Bike is a privately owned public bicycle sharing system serving the New York City boroughs of the Bronx, Brooklyn, Manhattan, and Queens, as well as Jersey City, New Jersey. They often publish their monthly trip data on their website. I have analysed data for the summer months of June and July 2022 and 2023 for Jersey City. 

#### Tableau Published page:
`https://public.tableau.com/views/CitiBikeRideAnalysis-JCJune-July2022-2023/Dashboard-CitiBikeRideAnalysis2022-23June-July?:language=en-GB&:display_count=n&:origin=viz_share_link`

#### Repository contents
- **Resources** folder with files used
- **Citi Bike Ride Analysis - JC June-July 2022 - 2023.twbx** Tableau workbook download
- **JCcitibikeDatasetPrep.ipynb** - Jupiter notebook with Data preperation
- **JCcitibikestripdata06-07-2022-23.zip** - Zipped output file
  
### The analysis is divided into following segments:

**1) Station Analysis:**
Start and End Ride Stations by popularity based on number of rides, Popular start end station pairs and average duration of trips by time of day which can also be used to find the popular stations at that time of day.

**2) Map of Start and End Station:**
Two maps with all locations of start and end stations on two separate maps

**3) Rider Analysis:**
Comparison of Total number and percentage of riders by type - Member and Casual, number of riders using classic vs electric bikes, number of rides by time of day and average duration of rides per day between 2022 and 2023. 

#### Data used:
Four zip files consisting data from June-July 2022 and 2023 for Jersey City were used from `https://citibikenyc.com/system-data`

#### Data Preperation in Jupyter Notebook:

**1) File merge**
All 4 files were concatenated into one dataframe.

**2) Dataset analysis**
It was found that there were missing station details and multiple coordinates for a single location. There was a bike type called docked_bike from which it was unclear as to the type of bike they were. It was also found that ride start and end timestamp were same for some of the data and end timetamp was smaller than start timestamp in some cases.

**3) Data cleaning**
Unique coordinates were added to each station id by picking one of the many assiciated coordinates. Data with missing information was removed as it was only 2% of the entire dataset. Bike_type 'docked_bike' was retained as it had all other data complete against the entries.

**4) Adding Time of Day to data**
Time of day was evaluated for each start timestamp and added as an additional column to the data

#### Calculated Fields in Tableau:
Ride duration in hours calculated using below formula:
**DATEDIFF('second', [Started At],[Ended At])/3600**
Total number of Rides calculated with below Aggregate function:
**COUNT([JCcitibikestripdata06-07-2022-23.csv])**
Start and End Longitudes were converted to Geographic usage type

#### Contents created:
- Two maps one each for Start and End Station locations
- Seven Visualisations
- Three main Dashboards and a few more for creating story board
- One Tableau Story board

#### Story contents:
Please note that the analysis are covered in the Tableau story board for each element and also below

**1) Introduction**

**2) Data Preparation** 
 - Data Preparation in Jupyter Notebook
 - Calculated Fields in Tableau
   
**3) Station analysis**
 - Start and End Station **Maps**
 - Top 10 Start Stations -  Graph and analysis
 - Top 10 End Stations -  Graph and analysis
 - Most Popular Start- End Station Pair -  Chart and analysis
 - Time of Day Analysis & Popular Start End Station Pairs by time of day
 - **Dashboard:** Top Start and End stations and pairs
   
**4) Rider analysis**
 - Member vs Casual 2022-2023 - Chart and analysis
 - Average Ride Duration comparison 2022-2023 - Chart and analysis
 - Number of Rides by Time of Day - Graph and analysis
 - Classic vs Electric Bikes - Graph and analysis
 - **Dashboard:** Rider Analysis

**5) Analysis - Maps, Dashboards and Visualisations**






