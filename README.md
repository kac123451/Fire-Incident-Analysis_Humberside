# Fire-Incident-Analysis_Humberside

In this analysis we will trying to answer these questions:

Causes of Fire - What are the primary causes of fire incidents in the community?
Temporal Patterns - Are there specific days or times of the week when fire incidents are more likely to occur?
Geospatial Analysis - Can we identify geographical hotspots where fire incidents are more concentrated?
Incident Type Distribution - What is the distribution of incident types, and are there trends or patterns?
Ignition Sources - What are the most common sources of ignition leading to fire incidents?

as it provides actionable insights into: 
- temporal, spatial, and causal patterns of fire incidents in Kingston upon Hull.
- enabling the fire and rescue service to optimize resource allocation.
- enhance preventive measures.
and most importantly
- improve overall community safety.
By identifying hotspots and understanding incident types the analysis contributes to informed decision-making, fostering a more proactive and effective approach to community fire safety.

First step is to find open dataset which we can find under this link
[Humberside Dataset](https://data-humbersidefrs.opendata.arcgis.com/search)

We can download Locations and updated Incidents 

Screen1()

Dataset contains 36 columns and 175504 rows (4 816 651 records)
X - represent spatial coordinates x - easting
Y - represent spatial coordinates y - northing
OBJECTID - unique ID 
Incident_Ref - identifier for each incident
Time_Of_Call - Represents the date and time when the incident was reported.
Day_Of_Week,	Hour, Day,	Month,	Year - Various components of the date and time of the incident.
Incident_Type	Inc_Description	Inc_Type - These columns describe the type and description of the incident.
Fire_Cause, Primary_Fire_Main_Cause, Primary_Fire_Ignition_Source_Ca, Primary_Fire_Ignition_Source_De, Primary_Fire_Ignition_Source_Po, Primary_Fire_Item_Ignited_Categ, Primary_Fire_Item_Ignited_Descr, - These columns seem related to the causes and sources of fires. However there is a lot of blank records
FA_SS_Description_lvl_1, FA_SS_Description_lvl_2, FA_SS_Description_lvl_3, FA_SS_Description_lvl_4 - More description about Call Reasons, Actions taken, Services provided, Causes of fire
Property_lvl_2, Property_lvl_3, Property_lvl_4, Property_lvl_5 -Descriptions of the property affected by the incident
Authority, 	Ward, SOA, OA - Administrative and geographic information about the incident, such as the authority, ward, and various codes like SOA (Statistical Output Area) and OA (Output Area).
X_Easting                           - rounded to the nearest whole number value of X
Y_Northing                          - rounded to the nearest whole number value of Y
LONGITUDE    - corresponding geographic coordinates
LATITUDE     - corresponding geographic coordinates


Dane wyglądają na uporządkowane z wyjątkiem wielu brakujących recordów,
Dataset looks sorted but there is some blank records
Lets modidfy our dataset into Table and use Power Query Editor for deep understanding data
Lets start from removing columns which won't be usefull for our goal:
Incident_Ref, Property_lvl_2, Property_lvl_3, Property_lvl_4, Property_lvl_5, SOA, OA, X_Easting, Y_Easting

We just going to replace null values with Unknown for Text columns as there is still valuable information in other columns and we dont want to lose that data, we have to remember that Fire_Cause is not related to entire dataset and we will check what % of entire dataset contains Fire Cause later.
Split Time_Of_Call for Date_of_call and Time_of_call for data normalization
Last checks:
Check formats, Trim columns
Close & Load data

27 columns 175504 rows (4 738 605 records)



Humberside Station Locations
We don't have Authority which then we can use for reference, but we can use Link column which contains this information.

Using =TEXTSPLIT(K2,"/")
Copy & Paste values and we just need to do small corrections 

=IF(L2 = "north-lincolnshire", "North Lincolshire", IF(L2 = "hull", "City Of Kingston Upon Hull", IF(L2 = "east-riding", "East Riding Of Yorkshire", IF(L2 = "north-east-lincolnshire", "North East Lincolnshire"))))

Remove not needed columns and we are ready!

Lets import data to SSMS SQL Server Management Studio


Depends on Region From 68 to 80% Fire Causes are Unknown!

















