# University-of-Maryland-Athlete-Body-Composition

## An interactive Power BI dashboard used by coaches from the University of Maryland to track athlete body composition over time.
#
Tools Used: Microsoft Fabric (Power BI, Azure Data Factory, Apache Spark)

The University of Maryland has 20 Division 1 teams which encompasses over 550 student athletes. To maximize the competitivenes of teams, coaches use tools including body composition scans in order to help enhance athlete performance and health. As an analyst I was tasked to extract insights by building tools and visualisations that coaches can use to improve decisions made on individual athletes as well as on team level.

The scope of this project encompassed a general Power BI dashboard for all teams as well as a specific report for specifically the football team adn their 2024 Season. 

# Data Collection and Processing

Athletes were scanned using a Dual-energy absorptiometry also known as DEXA which provided information on body composition, bone mineral density, fat distribution, and total body weight. 

Afterwards a data pipeline using the DEXA API transferred and stored the data into Azure Blob Storage. After Blob all data and reporting utilized Microsoft’s Fabric service which is an all-in-one cloud data analytics platform that combined their existing technologies such as OneLake, Azure Data Factory, and Power BI Reporting. 

First, a pipeline from the Data Factory was used to copy new blob data into a Lake House. Second, notebooks using Apache Spark were used to transform the structure of data for reporting as well as update existing data. Finally, A SQL Analytics Endpoint was created, exposing the data to a Semantic Model, which was then used by a Power BI report for visualization and analysis.

# Data Modeling
The data follows a snowflake schema with “Measures(2)” as the fact table that contains every record of an athlete body scan as well as any DAX measures. The “Date” and “Athletes” table are dimensions with “Athletes” having a sub-dimension called “Profiles" that contains the position of each athlete.

# Data Visuals

## 
