---
layout: default
title: Maximum City Impact of COVID-19 Pandemic on Physical Activity of Toronto's Youth
---

# Maximum City: Impact of COVID-19 Pandemic on Physical Activity of Toronto's Youth
**Urban Health · Health Equity · September, 2023**

`R` · `GIS` · `Ontario Parent Survey`

## Project Overview
This research analyzes data from the third Ontario Parent Survey (OPS3) to evaluate the physical activity and outdoor play levels of 2,093 children and youth (ages 5-17). Conducted in 2022 as COVID-19 restrictions were lifted, the study investigates the intersection of children's health, urban density, and parental well-being.

<div style="margin: 30px 0; text-align: center;">
   <a href="https://static1.squarespace.com/static/5a7a164dd0e628ac7b90b463/t/65a0ae51b1e83b5425106796/1705029205252/Play+and+Physical+Activity_+Findings+from+the+Third+Ontario+Parent+Survey+FINAL+Report.pdf" 
      target="_blank" 
      style="background: #004a99; color: white; padding: 14px 28px; border-radius: 8px; text-decoration: none; font-weight: bold; box-shadow: 0 4px 6px rgba(0,0,0,0.1); transition: 0.3s;">
      Read the Full Data Report (Maximum City) ↗
   </a>
</div>

## Technical Skills
* Statistical Analysis: R (Chi-Square Analysis, Jonckheere’s Trend Test)
* Geospatial Mapping: QGIS (FSA-level population density and activity heatmaps)
* Mental Health Metrics: Scoring and integration of CESD-10 and GAD-7 scales
* Data Visualization: Longitudinal comparison of 2021 vs. 2022 health targets


## Research Pillars and Key Findings
The following maps are extracted from the full report. Each Forward Sortation Area (FSA; based on postal code) is shaded by population density and marked by colored dots based on whether the average level of physical activity (moderate: MVP, low: LPA) or outdoor play (OA) is meeting target (yellow), under target (unmarked for legibility), or extremely under target (red).
<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 15px; margin: 2rem 0;">
  <img src="/assets/img/Maximum City/Ontario Average MVPA Levels Compressed.jpg" style="width: 100%; height: 250px; object-fit: cover; border-radius: 6px; border: 1px solid #d9d3cb;">
  <img src="/assets/img/Maximum City/Ontario Average LPA Levels Compressed.jpg" style="width: 100%; height: 250px; object-fit: cover; border-radius: 6px; border: 1px solid #d9d3cb;">
  <img src="/assets/img/Maximum City/Ontario Average OP Levels Compressed.jpg" style="width: 100%; height: 250px; object-fit: cover; border-radius: 6px; border: 1px solid #d9d3cb;">
  <img src="/assets/img/Maximum City/ops2_toronto_rec_edited.png" style="width: 100%; height: 250px; object-fit: cover; border-radius: 6px; border: 1px solid #d9d3cb;">
  <img src="/assets/img/Maximum City/ops3_toronto_rec_edited.png" style="width: 100%; height: 250px; object-fit: cover; border-radius: 6px; border: 1px solid #d9d3cb;">
    <img src="/assets/img/Maximum City/phys_act_oa_year_chisq.png" style="width: 100%; height: 250px; object-fit: cover; border-radius: 6px; border: 1px solid #d9d3cb;">
</div>

### Children's Health and Age Disparities
Age was identified as the predictor variable with the largest impact on physical activity. Youth (ages 12-17) were significantly less likely to meet targets compared to younger children (ages 5-11). Only 1 in 20 children were extremely under target for vigorous activity, compared to 1 in 4 youth.

### Urban Health and Population Density
Using GIS to map activity against population density, the study found that the relationship between the built environment and activity levels became less decisive in 2022 than in 2021. This suggests that the lifting of sports and recreation restrictions may have mitigated some previous urban-rural health inequities.

### Health Equity and Gender
The data replicated findings from earlier surveys showing significant gender gaps. Males were more likely to meet Moderate to Vigorous Physical Activity (MVPA) targets, while females were significantly more likely to be extremely under target.

### COVID-19 and Parental Factors
The study explored the "trickle-down" effect of parental behavior during the pandemic. Children whose parents increased their own physical activity or outdoor time during COVID-19 were significantly more likely to meet their own health targets. Conversely, parental concern regarding screen time management remained a strong predictor of child inactivity.

## Conclusion
The findings suggest that while overall activity levels improved as pandemic restrictions were lifted, targeted interventions are still required for youth and female children to ensure equitable health outcomes in Ontario.
