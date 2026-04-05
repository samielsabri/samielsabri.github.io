---
layout: page
title: FIFA 2026 Socio-Spatial Impact Analysis
keywords: "rban Health · Health Equity · April 2025"
stack: "R · GIS · Leaflet · ON-MARG · Statistics Canada Census"
---

### Advancing Youth Agency, Safety, and Rights

Developed during a strategic consultancy with [Maximum City](https://maximumcity.ca), this research supports *Generation 2026* – a global initiative by the [Centre for Sport and Human Rights](https://www.sporthumanrights.org/what-we-do/generation-2026-advancing-safer-youth-inclusive-sports). The project aims to advance youth agency, safety, and rights ahead of, during, and after the FIFA World Cup 2026. 

By mapping the Ontario Marginalization Index (ON-Marg) against proposed fan sites, this tool provides the "fresh perspectives on complex issues" required for strategic municipal program development and equitable resource allocation.

---

<div style="width: 100%; margin: 30px 0;">
  <div style="border: 2px solid #2c3e50; border-radius: 12px; overflow: hidden; box-shadow: 0 10px 20px rgba(0,0,0,0.15);">
    <iframe src="/dashboards/fifa_onmarg.html" width="100%" height="800px" style="border:none;"></iframe>
  </div>
  <div style="margin-top: 15px; text-align: center;">
    <a href="/dashboards/fifa_onmarg.html" target="_blank" style="background: #2c3e50; color: white; padding: 12px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Launch Full-Screen Dashboard ↗</a>
  </div>
</div>

---

### Technical Methodology & Research Integrity

#### Addressing the MAUP: Context-Aware Spatial Grain
In urban policy research, results often shift based on how boundaries are drawn. This is known as the **Modifiable Areal Unit Problem (MAUP)**. To ensure data accuracy for City of Toronto stakeholders, I developed a custom population-weighted model to evaluate three distinct buffer scales:

* **High-Density Urban Core (500m):** In walkable areas like Fort York, a 500m radius captures the immediate "lived reality" and pedestrian safety concerns. This is particularly critical for children and youth with smaller independent mobility ranges.
* **Low-Density/Suburban Context (1km):** For sites with lower residential density, a 1km catchment more accurately captures the population interacting with the site.
* **Sensitivity Analysis:** This approach allows stakeholders to observe how marginalization quintiles shift as the "impact zone" expands, providing a robust basis for policy and budgetary proposals.

#### Software Stack & Professional Implementation
* **Data Engineering:** Utilized **R (`sf`, `tidyverse`)** to automate the cleaning and joining of the 2021 Ontario Marginalization Index (ON-Marg) with Statistics Canada spatial data.
* **GIS Processing:** Conducted spatial intersections and population-weighted averaging to ensure statistical rigor across varying census tract geometries.
* **Operational Integration:** While this dashboard serves as a portfolio demonstration, the underlying data layers and logic were designed to be integrated into internal ESRI ArcGIS environments for use by municipal planning and safety teams.

---

### Project Impact
This work demonstrates a commitment to the **Toronto Public Service** values of excellence and public service. By translating global human rights goals into site-specific spatial intelligence, this analysis ensures that the "success of the City" during FIFA 2026 is measured by its ability to protect and empower its most vulnerable residents.
