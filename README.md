# University-of-Maryland-Athlete-Body-Composition
Tools Used: Microsoft Fabric (Power BI, Azure Data Factory, Apache Spark)
![image](https://github.com/user-attachments/assets/a43abb3a-d98c-413d-a245-ef9ecd94697c)

# Project Background
**An interactive Power BI dashboard used by coaches from the University of Maryland to track athlete body composition over time.**

The University of Maryland has 20 Division 1 teams which encompasses over 550 student athletes. To maximize the competitivenes of all teams, coaches use tools such as body composition scans in order to help enhance athlete performance and health. As an analyst I was tasked to build tools and visualisations that can provide coaches the insights they need to elevate their teams.

The scope of this project encompassed a general Power BI dashboard for all teams as well as a specific report for the football team. 
# Data Collection and Processing
Throughout the season, athletes undergo Dual-Energy X-ray Absorptiometry (DEXA) scans, which provide detailed data on body composition, bone mineral density, fat distribution, and total body weight. A data pipeline using the DEXA API transfers and stores the data into Azure Blob Storage and then using another pipeline is copied into Azure Data Studio. In Azure Data Studio, the data is structured using SQL queries, transforming raw tables into formatted tables. The processed data is then connected to Microsoft Fabric using Direct Lake, ensuring real-time access without requiring scheduled refreshes. Finally, a Semantic Model in Fabric organizes the data for Power BI, enabling interactive dashboards, insightful reporting, and advanced calculations.
![Screenshot 2025-03-23 at 8 22 43 PM](https://github.com/user-attachments/assets/e0a0071d-628a-4413-b5d8-c880db938868)

# Data Modeling
The data model follows a snowflake schema, with 'Measures(2)' serving as the fact table, containing every record of an athlete's body scan along with relevant DAX calculations. The 'Date' and 'Athletes' tables act as dimension tables, while 'Athletes' includes a sub-dimension called 'Profiles,' which stores each athlete's position.
![Screenshot 2025-03-23 at 7 01 25 PM](https://github.com/user-attachments/assets/6f81f406-99f5-4f95-a10f-f4b86cd2c65f)

# Data Visuals and Analytics
## Analytics and Dax Calculations
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

