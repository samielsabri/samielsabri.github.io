---
layout: page
title: "2023 Ontario Wildfires"
keywords: "Environmental Health · 2025"
stack: "R · Leaflet · sf · ECCC NAPS · CWFIS"
links:
  - label: "Interactive map"
    url: "/dashboards/wildfire_air_quality_gta.html"
---

In June 2023, I was in Toronto when the sky turned orange. My phone showed an air quality alert and my asthma flared up after not having any issues for many years. Because of my longstanding interest in climate and health, I wanted to figure out *how bad* it actually was and *how we actually measure what happened to people's health*. What does the epidemiological infrastructure look like for an event like this? Who was the most affected, and did the public health response work? It started as coursework during my MSc in Epidemiology at Oxford and grew from there, informed by conversations with researchers at Public Health Ontario who were doing the same work at a much larger scale.

This project quantifies what the wildfires meant for the air that Greater Toronto Area residents breathed across the summer of 2023, using hourly PM2.5 monitoring data from Ontario's MECP network and fire perimeter data from the Canadian National Fire Database.

<!-- STATS GRID -->
<div style="display: flex; flex-wrap: wrap; background: #f5f0ea; border: 1px solid #ddd6cc; margin: 2rem 0; font-family: sans-serif;">
  <div style="flex: 1 1 22%; text-align: center; padding: 1.75rem 1.25rem; border-right: 1px solid #ddd6cc; box-sizing: border-box;">
    <span style="display: block; font-size: 2.6rem; font-weight: 600; color: #c0392b; line-height: 1; margin-bottom: 0.7rem; font-family: Georgia, serif;">15M</span>
    <span style="font-size: 0.9rem; color: #6b6560;">hectares burned nationally</span>
  </div>
  <div style="flex: 1 1 22%; text-align: center; padding: 1.75rem 1.25rem; border-right: 1px solid #ddd6cc; box-sizing: border-box;">
    <span style="display: block; font-size: 2.6rem; font-weight: 600; color: #c0392b; line-height: 1; margin-bottom: 0.7rem; font-family: Georgia, serif;">7×</span>
    <span style="font-size: 0.9rem; color: #6b6560;">the historical annual mean</span>
  </div>
  <div style="flex: 1 1 22%; text-align: center; padding: 1.75rem 1.25rem; border-right: 1px solid #ddd6cc; box-sizing: border-box;">
    <span style="display: block; font-size: 2.6rem; font-weight: 600; color: #c0392b; line-height: 1; margin-bottom: 0.7rem; font-family: Georgia, serif;">10×</span>
    <span style="font-size: 0.9rem; color: #6b6560;">WHO 24h PM2.5 guideline exceeded at peak</span>
  </div>
  <div style="flex: 1 1 22%; text-align: center; padding: 1.75rem 1.25rem; box-sizing: border-box;">
    <span style="display: block; font-size: 2.6rem; font-weight: 600; color: #c0392b; line-height: 1; margin-bottom: 0.7rem; font-family: Georgia, serif;">$1.28B</span>
    <span style="font-size: 0.9rem; color: #6b6560;">health cost in Ontario — one week alone</span>
  </div>
</div>

---
 
## The data
 
Two distinct smoke events hit the GTA that summer. The chart below shows daily mean PM2.5 averaged across ten Ontario MECP monitoring stations, May through July 2023. The WHO 24-hour guideline is 15 μg/m³; Ontario's reference level is 27 μg/m³.
 
<!-- TIME SERIES CHART EMBED -->
<div style="margin: 1.5rem 0; border: 1px solid #ddd6cc; border-radius: 4px; overflow: hidden;">
  <img src="/assets/img/gta_pm25_timeseries.png" alt="GTA daily mean PM2.5, May–July 2023" style="width: 100%; display: block;" />
</div>
<p style="font-size: 0.82rem; color: #888; margin-top: -0.5rem; font-family: sans-serif;">
  Source: Air Quality Ontario / Ontario MECP. WHO 24h guideline: 15 μg/m³. Ontario CAAQS reference: 27 μg/m³.
</p>
On baseline days, GTA mean PM2.5 rarely exceeded 15 μg/m³. During peak smoke days it exceeded 50 μg/m³ on a daily average, with individual station hourly peaks above 100 μg/m³ — more than ten times the WHO guideline. The two events have different profiles: the first sharper and more concentrated, the second longer-sustained. That difference turns out to matter, as I'll come back to.
 
The interactive map below shows peak PM2.5 at each station during both events. Toggle between events; zoom out to see where the fires were.
 
<!-- INTERACTIVE MAP EMBED -->
<iframe src="/dashboards/wildfire_air_quality_gta.html" width="100%" height="540px" style="border: 1px solid #ddd6cc; border-radius: 4px; margin: 1.5rem 0; display: block;"></iframe>
<div style="margin-top: 15px; text-align: center;">
    <a href="/dashboards/wildfire_air_quality_gta.html" target="_blank" style="background: #2c3e50; color: white; padding: 12px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Launch Full-Screen Dashboard ↗</a>
  </div>



<p style="font-size: 0.82rem; color: #888; margin-top: -0.5rem; font-family: sans-serif;">
  PM2.5 data: Ontario MECP AQHI network. Fire perimeters: Canadian National Fire Database (CWFIS / NRCan).
</p>
 
The second event recorded higher peak concentrations at most stations. For example, Brampton recorded its highest single-station reading of the summer (196µg/m³) during this event. However, it did not produce a proportionate surge in ED visits. A quasi-experimental study by Chen et al. (2025) from Public Health Ontario documented a 23.6% surge in asthma ED visits during Event 1 but found no consistent increase during Event 2. Their interpretation: people who sought medications during the first event were better protected, and advisory adherence improved. This is a rare natural experiment with a built-in comparator — direct evidence that timely risk communication, when acted upon, reduces acute burden. The harder question it raises is: acted upon by whom?
 
---

## Public health implications

The epidemiological evidence linking PM2.5 to acute respiratory and cardiovascular outcomes is well-established. Emergency department visits for asthma exacerbations, COPD, and acute myocardial infarction all increase in the days following elevated PM2.5 events. Ontario's own syndromic surveillance data from the 2023 season, analysed through the province's ACES system and CIHI's NACRS dataset, documented measurable increases in respiratory ED presentations during the June smoke events — the first major Ontario-specific evidence base of this kind.

Several features of wildfire smoke health risk make it distinct from other air quality threats:

* **Transboundary and episodic**: Unlike stationary industrial pollution, wildfire smoke arrives rapidly, with little warning, from sources hundreds of kilometres away. The standard monitoring and advisory frameworks were designed for local, predictable pollution sources.
* **Differential vulnerability**: Indigenous communities, older adults, people with pre-existing respiratory and cardiovascular conditions, outdoor workers, and newcomer populations with limited information access face disproportionate risk. Toronto and Peel Region, in particular, are among the most diverse populations in Canada, with large newcomer communities, which warrants targeted communication and intervention strategies.
* **Cumulative seasonal burden**: The 2023 season involved not one but multiple sustained exposure windows across May through July. Cumulative effects on lung function and cardiovascular health are poorly understood at the population level and represent a critical evidence gap.


As climate projections indicate that seasons like 2023 will become increasingly frequent, local public health units have a central role in translating this epidemiological evidence into actionable risk management: targeted advisories, equity-informed messaging, clean air space designation, and integration of wildfire smoke response into existing heat and air quality emergency frameworks.

---

## Data and methods

All data are open-access and fully reproducible.

* **PM2.5 monitoring data**: Hourly readings from Ontario MECP's AQHI monitoring network, accessed via Air Quality Ontario (`airqualityontario.com`). Ten GTA stations used: Toronto Downtown, Toronto East, Toronto North, Toronto West, Brampton, Mississauga, Oakville, Milton, Newmarket, Oshawa. Daily means computed from hourly values with a minimum of 18 valid hourly observations.
* **Fire perimeter data**: Canadian National Fire Database (CWFIS / Natural Resources Canada), large fires polygon dataset. Filtered to 2023; geometries simplified for web rendering. Ontario-specific analysis uses `SRC_AGENCY == "ON"`.
* **Analysis**: R with `tidyverse`, `sf`, `ggplot2`, `patchwork`, `maptiles`, `leaflet`. All code available on GitHub.

*Began as coursework in environmental epidemiology at Oxford; extended with primary data analysis and spatial visualisation. Views are my own.*
