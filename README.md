# 🚀 Maven Return to Space Challenge


### 📖 Overview
This project was my entry for the [**Maven Return to Space Challenge**](https://mavenanalytics.io/challenges/maven-return-to-space-challenge) hosted by Maven Analytics.  

I built a Power BI dashboard to explore the evolution of global space missions from 1957 to 2022 between different countries, companies, and rockets.

The goal was to create a **single-page visual story** highlighting mission growth, success rates, leading countries and organizations, and the evolution of rocket technology.

---

### 🎯 Project Objective
- Build a single-page visual or dashboard
- Which rocket (by name, cost, or size) is the true champion of space? 
- Which decade or time period had the highest success rate, the most launches, or the most bang-for-its-buck in terms of space exploration?
- Which country or organization has quietly dominated the space race over the long term, and what does their winning strategy look like?
- ...or anwser a compelling question of my own.

---

### 🗄 Dataset Summary
- Single Table
- 4,631 records 
- 9 fields
- Geospatial & Time elements

---

### Repo Files ###

- Raw Data [space_missions.csv](https://github.com/jtschroer/Maven_Challenge_2025_11/blob/main/space_missions.csv)
- Raw Data Dictionary [space_missions_data_dictionary.csv](https://github.com/jtschroer/Maven_Challenge_2025_11/blob/main/space_missions_data_dictionary.csv)
- Power BI Desktop [return_to_space.pbix](https://github.com/jtschroer/Maven_Challenge_2025_11/blob/main/return_to_space.pbix)

---

### 🧩 Core DAX Measures

| Measure | Formula | Description |
|---|---|---|
| Total Launches | `COUNTROWS(SpaceMissions)` | Total recorded missions |

---

### 🔍 Key Insights
- Winning Team: USA had 1,468 successful missions, followed closely by Russia with 1,416.
- Top Company: RVSN USSR leads with 1,777 successful launches, significantly ahead of competitors.
- Golden Era: The 1970s had the highest number of missions (1,012), driven primarily by Russia’s 604 launches.
- Mission Success: Humanity achieved an overall success rate of 92.7%, maintained steadily since the 1980s.
- Best Shuttle: Cosmos-3 (11K65M) had the highest number of successful missions; Voskhod was second.
- Cost Efficiency: Rocket 3 had the lowest cost per mission at $2.5M; Ceres-1 was nearly twice as expensive at $4.9M.

---

### 📝 Lessons Learned
This was my first challenge project, and I really enjoyed completing it. Although the challenge was intended to take a month, I completed it in just two days after discovering it shortly before the deadline.

The project was a great refresher on element placement. I focused heavily on ensuring even spacing around edges and between visuals, and I learned that shift-arrow movement depends on zoom level. Aligning everything perfectly required several attempts, but the experience will make future layout adjustments much smoother.

Capturing the final screenshot proved challenging due to my unconventional canvas size; exporting as a PDF skewed the report’s dimensions. For future projects, I plan to stick with more standard canvas sizes.

Lastly, I noticed areas for improvement in the layout: some text blocks are larger than necessary, and the “Total Successful Missions by Decade” visual is somewhat redundant.

Overall, this project was a valuable learning experience, and I look forward to applying these lessons in the December challenge.

---

### 🖼 Dashboard Preview

**Dashboard Snapshot**  
<img width="1000" alt="Dashboard Preview" alt="Dashboard Screenshot" src="https://github.com/user-attachments/assets/829578ae-6c3e-49fb-86f2-c84f01492692" />
