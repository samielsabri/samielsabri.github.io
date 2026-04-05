---
layout: page
title: Impact of COVID-19 Pandemic on Physical Activity of Toronto's Youth
keywords: "Urban Health · Health Equity · September, 2023"
stack: "R · GIS · Ontario Parent Survey"
links:
  - label: "Read the Full Data Report (Maximum City)"
    url: "https://static1.squarespace.com/static/5a7a164dd0e628ac7b90b463/t/65a0ae51b1e83b5425106796/1705029205252/Play+and+Physical+Activity_+Findings+from+the+Third+Ontario+Parent+Survey+FINAL+Report.pdf"
---
### Project Overview
This research was the main output during my internship with the [Urban Data Science Corps (UDSC)](https://schoolofcities.utoronto.ca/learning-sofc/udsc/) at the University of Toronto's School of Cities. My placement was at the local consulting firm [Maximum City](https://maximumcity.ca). I analyzed data from the third Ontario Parent Survey (OPS3) to evaluate the physical activity and outdoor play levels of 2,093 children and youth (ages 5-17). Conducted in 2023, a year after major COVID-19 restrictions were lifted, the study investigated the intersection of children's health, urban density, and parental well-being.

### Key Findings
The following maps are extracted from the full report. Each Forward Sortation Area (FSA; based on postal code) is shaded by population density and marked by colored dots based on whether the average level of physical activity (moderate: MVP, low: LPA) or outdoor play (OA) is meeting target (yellow), under target (unmarked for legibility), or extremely under target (red).
<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; margin: 2rem 0;">

  <figure style="margin: 0;">
    <a href="/assets/img/Maximum City/Ontario Average MVPA Levels Compressed.jpg" target="_blank">
      <img src="/assets/img/Maximum City/Ontario Average MVPA Levels Compressed.jpg" 
           style="width: 100%; height: 250px; object-fit: contain; background-color: #f8f8f8; border-radius: 6px; border: 1px solid #d9d3cb;" 
           alt="Ontario Average MVPA Levels Map">
    </a>
    <figcaption style="margin-top: 8px; font-size: 0.9rem; color: #555; line-height: 1.4;">
      <strong>Average MVPA Levels (Ontario)</strong>: Regional distribution of moderate to vigorous physical activity targets by FSA.
    </figcaption>
  </figure>

  <figure style="margin: 0;">
    <a href="/assets/img/Maximum City/Ontario Average LPA Levels Compressed.jpg" target="_blank">
      <img src="/assets/img/Maximum City/Ontario Average LPA Levels Compressed.jpg" 
           style="width: 100%; height: 250px; object-fit: contain; background-color: #f8f8f8; border-radius: 6px; border: 1px solid #d9d3cb;" 
           alt="Ontario Average LPA Levels Map">
    </a>
    <figcaption style="margin-top: 8px; font-size: 0.9rem; color: #555; line-height: 1.4;">
      <strong>Average LPA Levels (Ontario)</strong>: Light physical activity performance across provincial forward sortation areas.
    </figcaption>
  </figure>

  <figure style="margin: 0;">
    <a href="/assets/img/Maximum City/Ontario Average OP Levels Compressed.jpg" target="_blank">
      <img src="/assets/img/Maximum City/Ontario Average OP Levels Compressed.jpg" 
           style="width: 100%; height: 250px; object-fit: contain; background-color: #f8f8f8; border-radius: 6px; border: 1px solid #d9d3cb;" 
           alt="Ontario Average OP Levels Map">
    </a>
    <figcaption style="margin-top: 8px; font-size: 0.9rem; color: #555; line-height: 1.4;">
      <strong>Average Outdoor Play (Ontario)</strong>: FSA-level analysis of outdoor play duration relative to health targets.
    </figcaption>
  </figure>

  <figure style="margin: 0;">
    <a href="/assets/img/Maximum City/ops2_toronto_rec_edited.png" target="_blank">
      <img src="/assets/img/Maximum City/ops2_toronto_rec_edited.png" 
           style="width: 100%; height: 250px; object-fit: contain; background-color: #f8f8f8; border-radius: 6px; border: 1px solid #d9d3cb;" 
           alt="Toronto Youth Recreation Access 2021 Map">
    </a>
    <figcaption style="margin-top: 8px; font-size: 0.9rem; color: #555; line-height: 1.4;">
      <strong>Youth Recreation Access in Toronto (2021)</strong>: Correlation between high-density FSAs and youth program availability during pandemic restrictions.
    </figcaption>
  </figure>

  <figure style="margin: 0;">
    <a href="/assets/img/Maximum City/ops3_toronto_rec_edited.png" target="_blank">
      <img src="/assets/img/Maximum City/ops3_toronto_rec_edited.png" 
           style="width: 100%; height: 250px; object-fit: contain; background-color: #f8f8f8; border-radius: 6px; border: 1px solid #d9d3cb;" 
           alt="Toronto Youth Recreation Access 2022 Map">
    </a>
    <figcaption style="margin-top: 8px; font-size: 0.9rem; color: #555; line-height: 1.4;">
      <strong>Youth Recreation Access in Toronto (2022)</strong>: Observed shift in activity targets following the lifting of local facility restrictions. 
    </figcaption>
  </figure>

  <figure style="margin: 0;">
    <a href="/assets/img/Maximum City/phys_act_oa_year_chisq.png" target="_blank">
      <img src="/assets/img/Maximum City/phys_act_oa_year_chisq.png" 
           style="width: 100%; height: 250px; object-fit: contain; background-color: #f8f8f8; border-radius: 6px; border: 1px solid #d9d3cb;" 
           alt="Physical Activity Comparison Bar Chart">
    </a>
    <figcaption style="margin-top: 8px; font-size: 0.9rem; color: #555; line-height: 1.4;">
      <strong>Yearly Progress (2021–2022)</strong>: Significant increase in meeting health targets across MVPA, LPA, and OP categories.
    </figcaption>
  </figure>

</div>

#### Children's Health and Age Disparities
Age was identified as the predictor variable with the largest impact on physical activity. Youth (ages 12-17) were significantly less likely to meet targets compared to younger children (ages 5-11). Only 1 in 20 children were extremely under target for vigorous activity, compared to 1 in 4 youth.

#### Urban Health and Population Density
Using GIS to map activity against population density, the study found that the relationship between the built environment and activity levels became less decisive in 2022 than in 2021. This suggests that the lifting of sports and recreation restrictions may have mitigated some previous urban-rural health inequities.

#### Health Equity and Gender
The data replicated findings from earlier surveys showing significant gender gaps. Males were more likely to meet Moderate to Vigorous Physical Activity (MVPA) targets, while females were significantly more likely to be extremely under target.

#### COVID-19 and Parental Factors
The study explored the "trickle-down" effect of parental behavior during the pandemic. Children whose parents increased their own physical activity or outdoor time during COVID-19 were significantly more likely to meet their own health targets. Conversely, parental concern regarding screen time management remained a strong predictor of child inactivity.

### Conclusion
The findings suggest that while overall activity levels improved as pandemic restrictions were lifted, targeted interventions are still required for youth and female children to ensure equitable health outcomes in Ontario.
