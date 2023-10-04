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
- Start and End Ride Stations by popularity based on number of rides, Popular start end station pairs and average duration of trips by time of day which can also be used to find the popular stations at that time of day.

**2) Map of Start and End Station:**
- Two maps with all locations of start and end stations on two separate maps

**3) Rider Analysis:**
- Comparison of Total number and percentage of riders by type - Member and Casual, number of riders using classic vs electric bikes, number of rides by time of day and average duration of rides per day between 2022 and 2023. 

#### Data used:
- Four zip files consisting data from June-July 2022 and 2023 for Jersey City were used from `https://citibikenyc.com/system-data`

#### Data Preperation in Jupyter Notebook:

**1) File merge**
- All 4 files were concatenated into one dataframe.

**2) Dataset analysis**
- It was found that there were missing station details and multiple coordinates for a single location. There was a bike type called docked_bike from which it was unclear as to the type of bike they were. It was also found that ride start and end timestamp were same for some of the data and end timetamp was smaller than start timestamp in some cases.

**3) Data cleaning**
- Unique coordinates were added to each station id by picking one of the many assiciated coordinates. Data with missing information was removed as it was only 2% of the entire dataset. Bike_type 'docked_bike' was retained as it had all other data complete against the entries.

**4) Adding Time of Day to data**
- Time of day was evaluated for each start timestamp and added as an additional column to the data

#### Calculated Fields in Tableau:
- Ride duration in hours calculated using below formula:
**DATEDIFF('second', [Started At],[Ended At])/3600**
- Total number of Rides calculated with below Aggregate function:
**COUNT([JCcitibikestripdata06-07-2022-23.csv])**
- Start and End Longitudes were converted to Geographic usage type

#### Contents created:
- Two maps one each for Start and End Station locations
- Seven Visualisations
- Two main Dashboards excluding one for maps and a few for creating story board
- One Tableau Story board

#### Story contents:
- Please note that the analysis are covered in the Tableau story board for each element and also below

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
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/682dbbd7-9eca-4cd6-970c-99f1beebbd31)

### Details and Analysis
#### Map
- The two Maps are added to a Dahsboard may be filtered by Year/Month. Selecting a start stations on first Map gives all associated End stations on the second Map. 
- The Markers are Light blue for Start stations and Dark blue in colour for End stations.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/a2dba432-d277-465e-b596-0a0734996d62) ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/09a61c2e-f95e-4358-90ca-736cfaa52e34)
- The size of the markers indicates the number of rides - the larger the marker, the more visited is the station.
- Sections are marked by zip code.
- Clicking on a start location gives station name and number of rides information.
- The Map can be filtered by Month Year combination.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/ac050e02-2844-41fa-b372-17a8cb8729c8)
- Clicking on a start station in one map gives the corresponding end station on the other map.

#### Visualisations
- Apart from the maps there are 2 main Tableau dashboard
    - Main page with statistics and Station analysis
      ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/52867704-7fa4-46cd-ab84-a23a106041b6)

    - Rider Analysis
      ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/32d46ce7-8c9e-4555-9794-5d7e7d3630fd)

##### Analysis of Map and first Dashboard
- Statistics
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/21e0f230-bf8b-407d-b786-09d8d0ce4063)

- From the maps and verified by first 3 graphs/chart it can be seen that **Grove St Path** was the top Start station.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/2efb6b71-aeb6-4051-8888-87c8a99d2669)

- It was the top start station for each year individually a well. Hoboken and South Waterfront were 2nd and 3rd alternatively for both years.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/cbf15bc3-90e3-436b-b5e5-84c11d019793)
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/ba22b57a-c892-4f35-8ab3-67e39d5fcd3e)

- **Popular End stations list was very similar to popular Start stations**.
  ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/ef231dec-0903-47e8-9996-8b740be87473)
![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/abc05ed7-8393-42cf-9d14-b8f1dc1e0fae)

- **Most popular Start - End Station Pair** were found to be **12 & Sinatra Dr N and South Waterfront Walkway - Sinatra Drive & St** 1.
  ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/83fbcd3f-ce3b-48fb-b7f8-be2c28592d76)

- Maximum number of Riders starting from **Grove St Park ended their ride at Marin Light Rail station and vice-versa. Hamilton Park - Grove St Path was the other popular pair.**
- It was also worth noting that a lot of riders start and end their trip on the same station.
  
- **It was worth noting that the busiest stations are those that are near ferry (Banks of Hudson river) or rail stations indicating daily commutes by riders between New York and Jersey City for work.**
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/d64c5a21-983c-4b2a-8d60-01d91b496236)
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/1bc315bc-2dd5-4a24-92f5-8ada8852852f)
  
- **Recommendation:** These stations should be the first candidates for improvement of facilities or increase in resources.

##### Analysis of second Dashboard

- Member percentage by number of rides taken has increased from 2022 to 2023.
- **Recommendations:** The steps taken to increase membership should continue as it seems to be working.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/a5a22050-e2ec-4e65-aec7-77d268b4d907)

- **Average Ride Duration has reduced from 2022 to 2023**. More analysis on potential reasons like more people taking bikes only for work commutes and less for leisure, increase in costs, more competitors in the market, affordability of owning bikes, or an increase in number of electric bikes taking shorter time durations.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/a7a79ca1-0b6a-4616-ab80-622bc3b50d86)
  
- **It can be seen from the previous dashboard that the number of rides has also reduced** along with the average ride duration.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/5eb2e88b-d59d-4c58-9c93-ce4281d8c060)
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/b8965114-f1bf-4385-ad4f-d55c59916bb6)
  
- Number of **Morning Rides have increased from last year compared to Afternoon** probably indicating increasing back to work.
- ![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/999d2b0e-332b-4491-96ac-32368e952bb1)

- Total number of **electric bike rides has reduced from last year** considerably. 
![image](https://github.com/jyojay/Tableau-challenge/assets/132628129/6e68349e-ae87-49f4-8c64-1a1c974cdca3)

- Reasons like **safety concerns, difficulty of maintenance, increase in membership fees and increase in the competition from other bike sharing services or private electric bike owners which could affect the satisfaction and demand of its users. The excluded bike type "docked_bike" might be the missing data to these numbers but it is not clear for a person not living in that area or having used the service.** https://www.nytimes.com/2023/06/21/nyregion/e-bike-lithium-battery-fires-nyc.html
- Citi Bike's electric fleet makes up just 20 percent of its bikes in New York City, despite significantly higher demand for the rides: In 2019, the operator said each pedal-assist e-bike was rented out for three times as many trips per day as a "classic" non-electric bike.https://nyc.streetsblog.org/2023/09/19/say-good-bye-to-the-free-citi-bike-e-bike-loophole
- **Recommendations:** Reasons as stated above would need to be monitored closely to improve these statistics considering Citi Bike had increased its electric bike fleet during this period. https://www.bicycling.com/news/a39945527/citi-bike-new-e-bike-nyc-bikeshare/
















