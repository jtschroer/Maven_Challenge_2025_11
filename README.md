# 🚀 Maven Return to Space Challenge


### 📖 Overview
This dashboard was created for the Maven Analytics Return to Space challenge to analyze global space missions from 1957 to 2022. The report evaluates mission volume, reliability, cost efficiency and top launch vehicles across countries, organizations and time periods.

The dashboard uses visual storytelling to highlight trends without relying on long-form text. Launch activity, success rate, leading rockets and regional performance can be understood at a glance. The data also reflects how the space industry grew during the Cold War and later into a wider international effort.

Challenge link: 
[https://mavenanalytics.io/challenges/maven-return-to-space-challenge](https://mavenanalytics.io/challenges/maven-return-to-space-challenge)

---

### 🎯 Project Objective
- Build a single-page visual or dashboard
- Which rocket (by name, cost, or size) is the true champion of space? 
- Which decade or time period had the highest success rate, the most launches, or the most bang-for-its-buck in terms of space exploration?
- Which country or organization has quietly dominated the space race over the long term, and what does their winning strategy look like?
- ...or answer a compelling question of my own.

---

### 🗄 Dataset Summary
- Single Table
- 4,631 records 
- 9 fields
- Geospatial & Time elements

---

### 📁 Repo Files ###

- Raw Data [space_missions.csv](https://github.com/jtschroer/Maven_Challenge_2025_11/blob/main/space_missions.csv)
- Raw Data Dictionary [space_missions_data_dictionary.csv](https://github.com/jtschroer/Maven_Challenge_2025_11/blob/main/space_missions_data_dictionary.csv)
- Power BI Desktop [return_to_space.pbix](https://github.com/jtschroer/Maven_Challenge_2025_11/blob/main/return_to_space.pbix)

---

### ⚙️ Data Preparation & Transformation (Power Query)
Data transformation focused on cleaning and standardizing key fields to ensure accuracy and readiness for analysis.

* **Geospatial Wrangling:** The composite `Location` field was split by delimiter, requiring a **conditional custom column** to reliably extract the **`Country`**. Manual text remediation (Find and Replace) was performed on specific sub-national entries (e.g., "Alaska") to enforce consistent country naming for mapping accuracy.
* **Financial Standardization:** The decimal values in the **`Price`** column (representing millions) were converted to their full monetary value by multiplying them by 1,000,000, ensuring accurate total cost calculations.
* **Model Optimization:** Unused columns were removed to simplify the data model and improve query performance.


---
### 🧩 DAX Measures  
Click to expand.
<details><BR>

- Average Mission Cost - *Returns the average cost of missions while excluding blanks.*
```DAX
Average Mission Cost =
DIVIDE(
    SUM(space_missions[Price]),
    CALCULATE(
        COUNTROWS(space_missions),
        NOT(ISBLANK(space_missions[Price]))
    )
)
```
<BR>

- Average Missions per Year - *Returns the average number of successful missions per year.*
```DAX
Average Missions per Year = DIVIDE([Total Successful Missions],DISTINCTCOUNT( space_missions[Year]))
```
<BR>

- Success Rate - *Percentage of successful missions.*
```DAX
Success Rate = [Total Successful Missions]/[Total Missions]
```
<BR>

- Total Missions - *Total number of missions.*
```DAX
Total Missions = count(space_missions[Mission])
```
<BR>

- Total Price (USD) - *Total cost of missions.*
```DAX
Total Price (USD) = SUM(space_missions[Price])
```
<BR>

-  Total Successful Missions - *Total number of successful missions.*
```DAX
Total Successful Missions = CALCULATE(
    COUNTROWS('space_missions'),
    'space_missions'[Mission Status] = "Success"
)
```
<BR>

-  Total Unsuccessful Missions - *Total number of unsuccessful missions.*
```DAX
Total Unsuccessful Missions = CALCULATE(
    COUNTROWS('space_missions'),
    'space_missions'[Mission Status] <> "Success"
)
```
<BR>

-  Year - *Year of mission.*
```DAX
Year = YEAR(space_missions[Date])
```
</details>


---

### 🔍 Key Insights
- The United States and Russia account for the highest number of successful missions with totals that are very close to each other.
- The 1970s had the greatest launch volume on record. Increased Russian activity during this period contributed heavily to the spike.
- RVSN USSR ranks as the highest volume launch organization overall. Its mission count stands well above other agencies or companies in the dataset.
- Global success rates settled at roughly 93 percent starting in the 1980s, which suggests significant improvements in reliability over time.
- Cosmos 3 (11K65M) shows the highest number of successful launches among all rockets tracked, with Voskhod placed second.
- Rocket 3 demonstrates the strongest cost performance based on cost per mission, and it operates at a lower average cost than comparable launch systems.

---

### 📝 Lessons Learned
This project helped sharpen my approach to dashboard clarity and visual communication. My initial design relied heavily on text to explain findings, but through iteration I shifted toward more visual storytelling, making the insights easier to understand at a glance. I also discovered how important canvas dimensions are when exporting to PDF, as a non-standard size resulted in distortion during export.

During development I experimented with parameter-driven filtering, but ultimately replaced it with streamlined Top 10 visuals. This not only improved usability, but also reduced development complexity and kept the report focused on the highest-value comparisons.

---

### 🖼 Dashboard Preview

**Dashboard Snapshot**  
<img width="1000" alt="Dashboard Preview" alt="Dashboard Screenshot" src="https://github.com/user-attachments/assets/829578ae-6c3e-49fb-86f2-c84f01492692" />
