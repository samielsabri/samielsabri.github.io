---
layout: default
title: FIFA 2026 Socio-Spatial Impact Analysis
---

# FIFA 2026 Socio-Spatial Impact Analysis: Generation 2026

<div style="display: flex; flex-wrap: wrap; gap: 30px; align-items: flex-start;">

  <div style="flex: 1; min-width: 320px;">
    <h3>Advancing Youth Agency, Safety, and Rights</h3>
    
    <p>
      Developed during a strategic consultancy with <strong>Maximum City</strong>, this research supports 
      <em>Generation 2026</em>—a global initiative by the <strong>Centre for Sport and Human Rights</strong>.
    </p>

    <blockquote style="border-left: 5px solid #2c3e50; padding-left: 15px; font-style: italic; color: #34495e;">
      "Through Generation 2026, the Centre is working with partners to advance youth agency, 
      safety, and rights ahead of, during, and after the World Cup 2026."
    </blockquote>

    <p>
      <strong>The Policy Challenge:</strong> Large-scale international events create complex 
      socio-economic pressures on host cities. To protect vulnerable populations, municipal 
      stakeholders require a granular understanding of the "catchment areas" around major 
      event sites. Standard administrative boundaries often mask hyper-local vulnerabilities, 
      hindering effective resource deployment and safety protocols.
    </p>

    <h4>Strategic Deliverables:</h4>
    <ul>
      <li><strong>Granular Risk Assessment:</strong> Multi-scale spatial modeling to identify high-density newcomer and youth zones.</li>
      <li><strong>Evidence-Based EDI:</strong> A visual framework representing "Human Rights" as a spatialized, measurable municipal metric.</li>
      <li><strong>Stakeholder Integration:</strong> Data products designed for high-level briefing and operational use by City of Toronto partners.</li>
    </ul>
  </div>

  <div style="flex: 1.5; min-width: 400px;">
    <div style="border: 2px solid #2c3e50; border-radius: 12px; overflow: hidden; box-shadow: 0 10px 20px rgba(0,0,0,0.15);">
      <iframe src="/dashboards/fifa_onmarg.html" width="100%" height="700px" style="border:none;"></iframe>
    </div>
    <div style="margin-top: 15px; text-align: right;">
      <a href="/dashboards/fifa_onmarg.html" target="_blank" style="background: #2c3e50; color: white; padding: 12px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; transition: background 0.3s;">Launch Full-Screen Research Portal ↗</a>
    </div>
  </div>

</div>

---

### Technical Methodology & Research Integrity

#### Addressing the MAUP: Context-Aware Spatial Grain
In urban policy research, results often shift based on how boundaries are drawn. This is known as the **Modifiable Areal Unit Problem (MAUP)**. Analyzing marginalization at a broad neighborhood level (158 zones) can "smooth out" critical pockets of need. To mitigate this, I developed a custom population-weighted model to evaluate three distinct buffer scales (500m, 750m, 1km):

* **High-Density Urban Core (500m):** In walkable areas like Fort York or Nathan Phillips Square, a 500m radius captures the immediate "lived reality" and pedestrian safety concerns, particularly critical for children and youth with smaller independent mobility ranges.
* **Low-Density/Suburban Context (1km):** For sites with lower residential density, a 1km catchment more accurately captures the population interacting with the site.
* **Sensitivity Analysis:** This approach allowed City stakeholders to observe how marginalization quintiles shifted as the "impact zone" expanded, providing a more robust basis for policy decisions.

#### Software Stack & Professional Implementation
* **Data Engineering:** Utilized **R (`sf`, `tidyverse`, `readxl`)** to automate the cleaning and joining of the <strong>2021 Ontario Marginalization Index (ON-Marg)</strong> with Statistics Canada spatial data.
* **GIS Processing:** Conducted spatial intersections and population-weighted averaging to ensure statistical rigor across varying census tract geometries.
* **Operational Integration:** While this dashboard serves as a portfolio demonstration, the underlying data layers and logic were designed to be integrated into <strong>internal ESRI ArcGIS environments</strong> for use by municipal planning and safety teams.

---

### Project Impact
This work demonstrates a commitment to the **Toronto Public Service** values of excellence and public service. By translating global human rights goals into site-specific spatial intelligence, this analysis ensures that the "success of the City" during FIFA 2026 is measured by its ability to protect and empower its most vulnerable residents.
