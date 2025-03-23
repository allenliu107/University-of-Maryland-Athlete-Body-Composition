# University-of-Maryland-Athlete-Body-Composition
**An interactive Power BI dashboard used by coaches from the University of Maryland to track athlete body composition over time.**
Tools Used: Microsoft Fabric (Power BI, Azure Data Factory, Apache Spark)

The University of Maryland has 20 Division 1 teams which encompasses over 550 student athletes. To maximize the competitivenes of all teams, coaches use tools such as body composition scans in order to help enhance athlete performance and health. As an analyst I was tasked to build tools and visualisations that can provide coaches the insights they need to elevate their teams.

The scope of this project encompassed a general Power BI dashboard for all teams as well as a specific report for the football team. 
# Data Collection and Processing
Athletes were scanned using a Dual-energy absorptiometry also known as DEXA which provided information on body composition, bone mineral density, fat distribution, and total body weight. 

Afterwards a data pipeline using the DEXA API transferred and stored the data into Azure Blob Storage. After Blob all data and reporting utilized Microsoft’s Fabric service which is an all-in-one cloud data analytics platform that combined their existing technologies such as OneLake, Azure Data Factory, and Power BI Reporting. 

First, a pipeline from the Data Factory was used to copy new blob data into a Lake House. Second, notebooks using Apache Spark were used to transform the structure of data for reporting as well as update existing data. Finally, A SQL Analytics Endpoint was created, exposing the data to a Semantic Model, which was then used by a Power BI report for visualization and analysis.

# Data Modeling
The data follows a snowflake schema with “Measures(2)” as the fact table that contains every record of an athlete body scan as well as any DAX measures. The “Date” and “Athletes” table are dimensions with “Athletes” having a sub-dimension called “Profiles" that contains the position of each athlete.
![Screenshot 2025-03-23 at 7 01 25 PM](https://github.com/user-attachments/assets/6f81f406-99f5-4f95-a10f-f4b86cd2c65f)
# Data Visuals and Analytics

**1. Body Fat Percentage Trends:**
Tracking changes in body fat percentage (BF%) over time to assess conditioning progress.

**2. Lean Mass Development:**
Analyzing lean mass changes across different body regions (arms, legs, trunk) to evaluate strength gains.

**3. Position Group Body Composition:**
Comparing muscle mass and fat distribution among different position groups to identify trends.

**4. Bone Mineral Density (BMD) Insights:**
Examining BMD changes over time to monitor bone health and injury risk.

**5. Fat Mass Distribution:**
Investigating visceral vs. subcutaneous fat levels and their impact on performance.

**6. Symmetry & Imbalances:**
Identifying arm and leg muscle imbalances that may affect performance and injury risk.

**7. Weight Fluctuations & Performance:**
Assessing how weight changes correlate with performance improvements or declines.

**8. Seasonal Body Composition Patterns:**
Analyzing whether body composition shifts occur based on training phases or competition season.

**9. Team-Level Composition Changes:**
Measuring team-wide trends in body fat, lean mass, and weight to guide training programs.

**10. Conditional Flags for Athlete Monitoring:**
Implementing automated alerts based on critical thresholds in body composition data.

## Date to Date Comparison (1)
Compare the average metrics for each position group across two different dates.
![Screenshot 2025-03-23 at 6 27 35 PM](https://github.com/user-attachments/assets/e2c3da3b-144e-4368-b97f-619cadd736e2)
## Date to Date Comparison (2)
Compare the rosters across the two dates.
![Screenshot 2025-03-23 at 6 39 35 PM](https://github.com/user-attachments/assets/5dc393b3-f85f-4ba2-93d4-f32967c60723)
## Individual Change
View changes in individual athlete body metrics from last scan grouped by position.
![Screenshot 2025-03-23 at 6 46 21 PM](https://github.com/user-attachments/assets/7b8c5575-9458-4b11-84eb-1c921e371a25)
## Team Report
View changes in team averages grouped by position as well as KPIs when evaluating team.
![Screenshot 2025-03-23 at 7 03 05 PM](https://github.com/user-attachments/assets/aab4321e-b9f4-43d7-a134-5fa4927c5f83)

