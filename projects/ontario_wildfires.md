---
layout: page
title: "When the Sky Turned Orange"
keywords: "Environmental Health · 2025"
stack: "R · ggplot2 · Leaflet · sf · ECCC NAPS · CWFIS"
links:
  - label: "GitHub"
    url: "https://github.com/samielsabri"
  - label: "Interactive map"
    url: "/dashboards/wildfire_air_quality_gta.html"
---

The 2023 Canadian wildfire season was the most destructive on record — burning nearly 15 million hectares, over seven times the historical annual mean. For most Canadians, the crisis did not arrive as flames. It arrived as smoke. This project quantifies what that meant for the air that Greater Toronto Area residents breathed across the summer of 2023, using hourly PM2.5 monitoring data from Ontario's MECP network and fire perimeter data from the Canadian National Fire Database.

This work builds on academic research conducted as part of my MSc in Global Health Science and Epidemiology at Oxford, and on conversations with environmental health researchers at Public Health Ontario — including researchers working on Ontario's first major wildfire-health epidemiological studies following the 2023 season.

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

## The health problem

Fine particulate matter (PM2.5) — particles smaller than 2.5 micrometres — penetrates deep into the airways and enters the bloodstream. At sustained concentrations, it triggers inflammatory cascades that exacerbate asthma, COPD, and cardiovascular disease. Research suggests wildfire-specific PM2.5 may be up to ten times more harmful than PM2.5 from other sources due to its chemical composition, including polycyclic aromatic hydrocarbons and other combustion byproducts.

The WHO's 2021 revised guidelines set a 24-hour mean threshold of 15 μg/m³. Ontario's own CAAQS reference level is 27 μg/m³. During the peak June 5–7 smoke event, GTA monitoring stations recorded hourly readings exceeding 150 μg/m³ — more than ten times the WHO guideline, sustained across multiple hours.

Two distinct smoke events hit the GTA in summer 2023. The first, in early June, was driven by fires in Northern Ontario and Quebec. The second, in late June and early July, was longer-sustained and reached comparable peak concentrations.

---

## PM2.5 across the summer

The chart below shows daily mean PM2.5 averaged across all Ontario MECP monitoring stations in the GTA, from May through July 2023. Both smoke events are visible as sharp departures from otherwise moderate baseline air quality.

<!-- TIME SERIES CHART EMBED -->
<div style="margin: 1.5rem 0; border: 1px solid #ddd6cc; border-radius: 4px; overflow: hidden;">
  <img src="/assets/img/gta_pm25_timeseries.png" alt="GTA daily mean PM2.5, May–July 2023, showing two sharp peaks during the June and late June smoke events" style="width: 100%; display: block;" />
</div>

<p style="font-size: 0.82rem; color: #888; margin-top: -0.5rem; font-family: sans-serif;">
  Source: Air Quality Ontario / Ontario Ministry of the Environment, Conservation and Parks (MECP). WHO 24h guideline: 15 μg/m³. Ontario CAAQS reference: 27 μg/m³.
</p>

The shaded regions mark the two identified smoke events. Red points indicate days exceeding the Ontario reference level. The contrast between event and non-event periods is stark: on baseline days, GTA mean PM2.5 rarely exceeded 15 μg/m³; during peak smoke days it exceeded 50 μg/m³ on a daily average basis, with individual station hourly peaks well above 100 μg/m³.

---

## Spatial variation across the GTA

Not all parts of the GTA experienced the same exposure. The interactive map below shows peak PM2.5 recorded at each Ontario MECP monitoring station during the two smoke events. Circle size is proportional to peak concentration; colour encodes the US EPA AQI category.

<!-- INTERACTIVE MAP EMBED -->
<iframe src="/dashboards/wildfire_air_quality_gta.html" width="100%" height="560px" style="border: 1px solid #ddd6cc; border-radius: 4px; margin: 1.5rem 0; display: block;"></iframe>

<p style="font-size: 0.82rem; color: #888; margin-top: -0.5rem; font-family: sans-serif;">
  PM2.5 data: Ontario MECP AQHI network. Fire perimeters: Canadian National Fire Database (CWFIS / Natural Resources Canada). Toggle between smoke events; zoom out to see national fire extent.
</p>

Stations in the western GTA — Oakville, Milton, Mississauga — recorded the highest peak concentrations during both events, consistent with prevailing southwesterly wind patterns during smoke advection from Northern Ontario. Oshawa, at the eastern margin of the monitoring network, recorded substantially lower peaks.

---

## Two events, different profiles

<!-- BAR CHARTS -->
<div style="display: flex; flex-wrap: wrap; gap: 2rem; margin: 1.5rem 0; font-family: sans-serif;">

  <div style="flex: 1 1 45%; min-width: 260px;">
    <h3 style="font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: #6b6560; margin-bottom: 1rem; font-family: monospace;">Event 1 — Jun 5–7: peak station readings (μg/m³)</h3>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Oakville</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 100%; background: #8e44ad;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">193</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Milton</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 85%; background: #8e44ad;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">163</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Brampton</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 63%; background: #e74c3c;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">121</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Mississauga</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 73%; background: #e74c3c;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">141</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Oshawa</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 33%; background: #e74c3c;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">64</span>
    </div>
    <div style="margin-top: 10px; display: flex; gap: 12px; font-size: 10.5px; color: #888;">
      <span><span style="display:inline-block;width:10px;height:10px;background:#8e44ad;border-radius:2px;margin-right:4px;vertical-align:middle;"></span>Very unhealthy (&gt;150)</span>
      <span><span style="display:inline-block;width:10px;height:10px;background:#e74c3c;border-radius:2px;margin-right:4px;vertical-align:middle;"></span>Unhealthy (55–150)</span>
    </div>
  </div>

  <div style="flex: 1 1 45%; min-width: 260px;">
    <h3 style="font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: #6b6560; margin-bottom: 1rem; font-family: monospace;">Event 2 — Jun 27–Jul 2: peak station readings (μg/m³)</h3>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Brampton</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 100%; background: #8e44ad;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">196</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Milton</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 88%; background: #8e44ad;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">173</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Mississauga</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 79%; background: #8e44ad;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">155</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Oakville</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 72%; background: #8e44ad;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">141</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 8px;">
      <span style="font-size: 12px; color: #6b6560; min-width: 80px; text-align: right;">Newmarket</span>
      <div style="flex: 1; height: 18px; background: #f0ebe3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 60%; background: #e74c3c;"></div></div>
      <span style="font-size: 11px; color: #6b6560; min-width: 36px; font-family: monospace;">118</span>
    </div>
    <div style="margin-top: 10px; display: flex; gap: 12px; font-size: 10.5px; color: #888;">
      <span><span style="display:inline-block;width:10px;height:10px;background:#8e44ad;border-radius:2px;margin-right:4px;vertical-align:middle;"></span>Very unhealthy (&gt;150)</span>
      <span><span style="display:inline-block;width:10px;height:10px;background:#e74c3c;border-radius:2px;margin-right:4px;vertical-align:middle;"></span>Unhealthy (55–150)</span>
    </div>
  </div>

</div>

The second event was in some ways more concerning than the first: it lasted longer, affected a broader geographic footprint, and Brampton recorded its highest single-station reading of the summer (196 μg/m³) during this event — not the first. Both events represent sustained exposures well above any regulatory threshold.

---

## Public health implications

The epidemiological evidence linking PM2.5 to acute respiratory and cardiovascular outcomes is well-established. Emergency department visits for asthma exacerbations, COPD, and acute myocardial infarction all increase in the days following elevated PM2.5 events. Ontario's own syndromic surveillance data from the 2023 season, analysed through the province's ACES system and CIHI's NACRS dataset, documented measurable increases in respiratory ED presentations during the June smoke events — the first major Ontario-specific evidence base of this kind.

Several features of wildfire smoke health risk make it distinct from other air quality threats:

* **Transboundary and episodic**: Unlike stationary industrial pollution, wildfire smoke arrives rapidly, with little warning, from sources hundreds of kilometres away. The standard monitoring and advisory frameworks were designed for local, predictable pollution sources.
* **Differential vulnerability**: Older adults, people with pre-existing respiratory and cardiovascular conditions, outdoor workers, and newcomer populations with limited information access face disproportionate risk. Peel Region's population — among the most diverse in Canada, with large newcomer communities in Brampton and Mississauga — warrants targeted communication and intervention strategies.
* **Cumulative seasonal burden**: The 2023 season involved not one but multiple sustained exposure windows across May through July. Cumulative effects on lung function and cardiovascular health are poorly understood at the population level and represent a critical evidence gap.

As climate projections indicate that seasons like 2023 will become increasingly frequent, local public health units have a central role in translating this epidemiological evidence into actionable risk management: targeted advisories, equity-informed messaging, clean air space designation, and integration of wildfire smoke response into existing heat and air quality emergency frameworks.

---

## Data and methods

All data are open-access and fully reproducible.

* **PM2.5 monitoring data**: Hourly readings from Ontario MECP's AQHI monitoring network, accessed via Air Quality Ontario (`airqualityontario.com`). Ten GTA stations used: Toronto Downtown, Toronto East, Toronto North, Toronto West, Brampton, Mississauga, Oakville, Milton, Newmarket, Oshawa. Daily means computed from hourly values with a minimum of 18 valid hourly observations; sentinel values (−999, 9999) treated as missing.
* **Fire perimeter data**: Canadian National Fire Database (CWFIS / Natural Resources Canada), large fires polygon dataset. Filtered to 2023; geometries simplified for web rendering. Ontario-specific analysis uses `SRC_AGENCY == "ON"`.
* **Analysis**: R with `tidyverse`, `sf`, `ggplot2`, `patchwork`, `maptiles`, `leaflet`. All code available on GitHub.

*Note: This project began as academic coursework in environmental epidemiology at Oxford and was subsequently extended with additional data, spatial analysis, and public health framing. The views expressed are the author's own.*
