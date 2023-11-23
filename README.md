# Humberside Incident & Fire Incident Analysis: Unveiling Trends and Patterns (Q3 2009 - Q3 2023)


- ***Causes of Fire - What are the primary causes of fire incidents in the community?***
- ***Temporal Patterns - Are there specific days or times of the week when fire incidents are more likely to occur?***
- ***Geospatial Analysis - Can we identify geographical hotspots where fire incidents are more concentrated?***
- ***Incident Type Distribution - What is the distribution of incident types, and are there trends or patterns?***
- ***Ignition Sources - What are the most common sources of ignition leading to fire incidents?***


By identifying hotspots and understanding incident types the analysis contributes to informed decision-making, fostering a more proactive and effective approach to community fire safety.


### Data Source
Dataset can be found under this link
[Humberside Dataset](https://data-humbersidefrs.opendata.arcgis.com/search)

![SS](https://github.com/kac123451/Fire-Incident-Analysis_Humberside/blob/main/1.png)


**Dataset contains 36 columns and 175504 rows (4 816 651 records)**
- **X**              - represent spatial coordinates x - easting
- **Y**               - represent spatial coordinates y - northing
- **OBJECTID**               - unique ID 
- **Incident_Ref**               - identifier for each incident
- **Time_Of_Call**               - Represents the date and time when the incident was reported.
- **Day_Of_Week**,	**Hour**, **Day**,	**Month**,	**Year**               - Various components of the date and time of the incident.
- **Incident_Type**,	**Inc_Description**,	**Inc_Type**               - These columns describe the type and description of the incident.
- **Fire_Cause, Primary_Fire_Main_Cause, Primary_Fire_Ignition_Source_Ca, Primary_Fire_Ignition_Source_De, Primary_Fire_Ignition_Source_Po, Primary_Fire_Item_Ignited_Categ, Primary_Fire_Item_Ignited_Descr**               - These columns seem related to the causes and sources of fires. However there is a lot of blank records
- **FA_SS_Description_lvl_1, FA_SS_Description_lvl_2, FA_SS_Description_lvl_3, FA_SS_Description_lvl_4**              - More description about Call Reasons, Actions taken, Services provided, Causes of fire
- **Property_lvl_2, Property_lvl_3, Property_lvl_4, Property_lvl_5**               - Descriptions of the property affected by the incident
- **Authority, 	Ward, SOA, OA**               - Administrative and geographic information about the incident, such as the authority, ward, and various codes like SOA (Statistical Output Area) and OA (Output Area).
- **X_Easting**               - rounded to the nearest whole number value of X
- **Y_Northing**               - rounded to the nearest whole number value of Y
- **LONGITUDE**               - corresponding geographic coordinates
- **LATITUDE**               - corresponding geographic coordinates

While the dataset appears sorted, it contains some blank records that warrant attention. To gain a comprehensive understanding of the data and facilitate effective analysis, we will transform the dataset into a structured table. Utilizing the Power Query Editor, we can delve deeper into the intricacies of the data.


- **Conversion to Table**               - facilites efficient data manipulation
- **Power Query Editor Exploration**    - gain insights into the dataset, ensuring a thorough examination of its contents
- **Column Optimization**               - remove columns that do not contribute significantly to our goals
- **Columns Removed**: Incident_Ref, Property_lvl_2, Property_lvl_3, Property_lvl_4, Property_lvl_5, SOA, OA, X_Easting, Y_Easting


#### Null Value Handling:
- Replace null values with "Unknown" in text columns to retain valuable information. **Note that "Fire_Cause" is not dataset-wide, and its percentage will be assessed separately.**
#### Data Integrity Checks: 
- Verify data formats, 
- Trim columns for consistency.
#### Final Checks:
- Ensure all changes align with data integrity standards.
- Load Data: Once checks are completed, close and load the processed data.



- Number of Columns: 27
- Number of Rows: 175,504 (4,738,605 records)

![SS](https://github.com/kac123451/Fire-Incident-Analysis_Humberside/blob/main/2.png)

Analysis (SQL)



Key takeaways: [Visualisations](https://public.tableau.com/app/profile/kacper.sarwuta/viz/UKHumbersideIncidentFireIncidentAnalysis2009-Q32023/Dashboard1?publish=yes)

- **Total Incidents**: A comprehensive analysis of fire incidents from 2009 to October 2023 in Humberside, UK, reveals a total of **175,503**</span> incidents.
- **Regional Focus** - Kingston Upon Hull: Kingston Upon Hull emerged as the focal point, experiencing the majority of incidents with a total of **68,529**.
- **Peak Incident Hours**: The analysis pinpointed peak incident hours, notably from **7:00 to 7:59 pm** and **8:00 to 8:59 pm**, during which **12,414 and 12,220** incidents occurred, respectively.
- **Incident Type Distribution**: The most prevalent incident type was fire, constituting **44.2%** of the total incidents, followed by alarm **22.9%** and humanitarian assistance **22%**.
- **Record-Breaking Quarter**: Q3 2022 marked a significant milestone, setting a new record **2,357** for total **Fire incidents** since 2009.
- **Fire Incidents in Kingston Upon Hull:** Kingston Upon Hull recorded the highest number of fire incidents, reaching **32,723** incidents.
- **Unknown Fire Cause**: A notable observation is that **47.5%** of total incidents (**36,846 incidents**) had an unknown fire cause.
- **Top Fire Cause**: Among identified causes, the leading cause was the deliberate bringing together of heat sources and combustibles, contributing to **7,426** fire incidents.
- **Fire Ignition Sources**: The primary ignition sources were cooking appliances **3,505**, naked flames **2,452**, and vehicles **2,348** incidents.


![SS](https://github.com/kac123451/Fire-Incident-Analysis_Humberside/blob/main/3.png)
















