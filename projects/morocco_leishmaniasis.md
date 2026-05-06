---
layout: page
title: "Predicting Leishmaniasis Outbreaks in Morocco"
keywords: "Infectious Disease · Climate & Health · 2025"
stack: "Python · XGBoost · SHAP · Google Earth Engine · Folium"
links:
  - label: "GitHub"
    url: "https://github.com/samielsabri/morocco_leishmaniasis"
---

In 2019, I contracted cutaneous leishmaniasis during my time in Costa Rica. Luckily, I had access to treatment, but for many communities where it is endemic, it is truly a neglected disease. 
Neglected by global health funding and surveillance systems, and by predictive tools that exist for other vector-borne diseases. My home country, Morocco, has tracked cases of its last neglected 
tropical disease (NTD) at the province level for at least two decades. This project builds a risk model trained on this data, satellite climate observations, and the known ecology of 
*Phlebotomus papatasi* sandfly transmission. The full data pipeline, from bilingual Arabic-French PDF extraction to interactive choropleth, is open source.


<!-- INTERACTIVE DASHBOARD -->
<div style="margin: 2rem 0;">
  <iframe 
    src="/dashboards/leish_dashboard.html" 
    width="100%" 
    height="620px" 
    style="border: 1px solid #ddd6cc; border-radius: 4px; display: block;">
  </iframe>
  <div style="margin-top: 0.8rem; text-align: center;">
    <a href="/dashboards/leish_dashboard.html" target="_blank" 
       style="background: #2c3e50; color: white; padding: 10px 22px; 
              border-radius: 6px; text-decoration: none; font-weight: 600;
              font-family: sans-serif; font-size: 0.85rem;">
      Launch Full-Screen Dashboard ↗
    </a>
  </div>
</div>
<p style="font-size: 0.82rem; color: #888; font-family: sans-serif; 
   margin-top: -0.3rem;">
  Province-level cutaneous leishmaniasis incidence per 100,000 population, 
  2003–2023. Use the slider or play button to animate through years. 
  Toggle between reported incidence and model predictions. 
  Hover a province for case counts and residuals.
  Data: Morocco Ministry of Health · Climate: CHIRPS / ERA5-Land / MODIS via GEE.
</p>

---

## The disease and its ecology

Cutaneous leishmaniasis in Morocco is caused by *Leishmania major*, transmitted 
by the sandfly *Phlebotomus papatasi*, with the fat sand rat *Meriones shawi* as 
the primary rodent reservoir. Its epidemiology follows a predictable ecological 
chain: rainfall triggers vegetation growth in arid pre-Saharan zones, which fuels 
rodent population booms, which amplifies sandfly breeding, which reaches humans 
— typically with a lag of one to three years. Outbreaks alternate with multi-year 
remissions. Between 2000 and 2016, Morocco recorded over 31,000 cases nationally, 
concentrated in a handful of endemic provinces in the south and east.

The disease is not random but clusters geographically, responds to climate, and 
is predictable in ways that existing surveillance infrastructure does not fully exploit.

---

## Data pipeline

Morocco's Ministry of Health publishes case counts in bilingual Arabic-French PDF tables, with province names 
that vary in spelling across editions, administrative boundaries that changed in 
the 2015 reform, and newly-created provinces that split from historical parents 
at different points between 2004 and 2012. Building the panel required:

- **Custom PDF extraction** in Python (`pdfplumber`), with bbox-based column 
  detection to handle the bilingual table layout and a canonical province name 
  map covering all spelling variants across 20 years of publications
- **Administrative reform harmonisation**: the 2015 reform created 12 new regions 
  from 16 old ones. Provinces were reassigned but not dissolved — a crosswalk 
  table maps every province to both its pre- and post-2015 regional identity
- **Split-province handling**: 18 provinces created after 2004 were absorbed into 
  their historical parents for longitudinal modelling consistency, with a separate 
  raw panel preserved for recent-year mapping
- **Climate extraction via Google Earth Engine**: monthly CHIRPS rainfall, 
  ERA5-Land temperature, and MODIS NDVI extracted per province polygon using 
  `reduceRegions()`, covering 2001–2023 to allow up to 3-year climate lags
- **Population interpolation**: linear interpolation between the 2004, 2014, and 
  2024 census anchor years to compute annual incidence rates per 100,000

The full pipeline runs end-to-end from `main.py` and is documented at every step.

---

## Model

The modelling target is `log1p(incidence per 100,000)`. Only the 29 provinces with 
historically endemic transmission (ever exceeding 5 cases/100k in the training 
period) are modelled — this keeps the model focused on explaining variation *within* 
the endemic belt, rather than trivially distinguishing rural endemic provinces from 
urban ones.

Features fall into three groups:

- **Province baseline**: historical mean log1p incidence over 2003–2019, computed 
  on training data only. Captures structural endemic risk without encoding 
  administrative labels.
- **Climate signals**: annual and dry-season (June–September) totals for CHIRPS 
  rainfall, ERA5 temperature, and MODIS NDVI — each with 1, 2, and 3-year lags. 
  Wet-season (October–March) totals, peak rainfall month, summer temperature 
  maximum, and NDVI range round out the feature set.
- **Anomaly features**: z-score deviation of each climate variable from each 
  province's long-run mean. Captures whether *this year* is anomalously wet or 
  hot for *this province*, not just in absolute terms.

Training used an expanding-window temporal cross-validation over 12 folds 
(minimum 5 training years per fold), with a grid search over 144 hyperparameter 
combinations evaluated on CV RMSE. The hold-out test set is 2020–2023 — years 
the model never saw.

<!-- BEESWARM -->
<div style="margin: 1.5rem 0; border: 1px solid #ddd6cc; border-radius: 4px; 
overflow: hidden;">
  <img src="/assets/img/leish_shap_beeswarm.png" 
  alt="SHAP beeswarm — Morocco CL risk model" style="width: 100%; display: block;" />
</div>
<p style="font-size: 0.82rem; color: #888; margin-top: -0.5rem; font-family: 
sans-serif;">
  SHAP beeswarm plot showing feature contributions across all province-years. 
  Colour indicates feature value (red = high, blue = low). Province baseline 
  anchors structural risk; lagged dry-season rainfall and temperature drive 
  year-to-year variation.
</p>

The SHAP beeswarm reveals a coherent biological signal. Province baseline dominates 
structural risk as expected. Below it, dry-season rainfall at 1, 2, and 3-year 
lags clusters together with lagged temperature and NDVI features — the satellite 
fingerprint of the vegetation-rodent-sandfly transmission chain operating across 
multiple years. The 3-year lag featuring prominently is consistent with the 
biological literature: rainfall in year T triggers rodent population growth in 
year T+1, sandfly amplification in T+2, and epidemic transmission in T+3.

---

## Results

**Hold-out performance (2020–2023, unseen during training):**
- Pearson r = 0.77
- R² = 0.53
- Median absolute error = 6.2 cases/100k

<!-- PRED VS ACTUAL -->
<div style="margin: 1.5rem 0; border: 1px solid #ddd6cc; border-radius: 4px; 
overflow: hidden;">
  <img src="/assets/img/leish_pred_vs_actual.png" 
  alt="Predicted vs actual incidence" style="width: 100%; display: block;" />
</div>
<p style="font-size: 0.82rem; color: #888; margin-top: -0.5rem; font-family: 
sans-serif;">
  Predicted vs actual incidence per 100,000. Blue = training set, orange = 
  cross-validation, red = hold-out (2020–2023). 1:1 line shown dashed.
</p>

The model performs well for climate-driven outbreaks. The 2008–2010 epidemic wave 
— which followed anomalously high rainfall in endemic provinces — was well 
anticipated by the lagged climate features. The largest residual, Zagora 2018 
(actual: ~1,900/100k, predicted: ~620/100k), is instructive precisely *because* 
the model missed it.

---

## The outbreak the model couldn't predict — and what that tells us

Zagora 2018 is the model's largest residual by a wide margin. My first instinct 
was a data entry error. It wasn't. A 2019 paper in *PLOS Neglected Tropical 
Diseases* (El Hamouchi et al.) documented 4,402 confirmed cases in Zagora between 
October 2017 and March 2018 — a figure that aligns exactly with my surveillance 
data.

The critical finding: the climate signal going into this outbreak was *negative*. 
Zagora's 2016 rainfall anomaly was −0.72σ and 2017 was −1.70σ — among the driest 
years in the 21-year record. The model correctly interpreted these conditions as 
low risk. The outbreak happened anyway.

El Hamouchi et al. identified the proximate driver: an explosion in *Meriones 
shawi* rodent reservoir density, linked to the deceleration of vector control 
measures following the post-2010 remission period. Once control programmes are 
scaled back after a multi-year lull, accumulated susceptibility in both the rodent 
and human populations creates conditions for severe re-emergence — invisible to 
satellite climate data.

This points to a genuine ceiling on climate-based early warning, and also to its 
most defensible use case. Compare the two major Zagora outbreaks:

| Outbreak | Climate signal | Model | Driver |
|---|---|---|---|
| 2008–2010 | Strong positive anomaly 1–2 years prior | Good | Climate-driven |
| 2017–2018 | Negative anomaly in preceding years | Poor | Control programme relaxation |

Climate models provide actionable early warning for rainfall-driven outbreaks — 
the majority of epidemic years in the dataset. For susceptibility-driven outbreaks, 
they must be paired with surveillance of vector control programme continuity and 
rodent reservoir indices.

---

## Province-level explainability: Chichaoua, 2023

<!-- WATERFALL -->
<div style="margin: 1.5rem 0; border: 1px solid #ddd6cc; border-radius: 4px; 
overflow: hidden;">
  <img src="/assets/img/leish_waterfall_chichaoua_2023.png" 
  alt="SHAP waterfall — Chichaoua 2023" style="width: 100%; display: block;" />
</div>
<p style="font-size: 0.82rem; color: #888; margin-top: -0.5rem; font-family: 
sans-serif;">
  SHAP waterfall for Chichaoua, 2023 — a year the model never saw during training. 
  Actual: 133.3/100k. Predicted: 101.7/100k.
</p>

Chichaoua is one of Morocco's most persistently endemic provinces, in the 
Marrakech-Tensift foothills. For 2023 — a completely unseen hold-out year — the 
model predicted 101.7 cases per 100,000 against an actual of 133.3, a 24% error.

The waterfall shows how the prediction is assembled. The province baseline (+1.8) 
anchors it at Chichaoua's structural risk level. Lagged dry-season rainfall 
(+0.09 at lag1, +0.07 at lag2) and lagged NDVI (+0.06) push the prediction higher, 
reflecting wet conditions in 2021–2022. A negative annual rainfall anomaly (−0.06) 
partially offsets — 2023 itself was drier than usual — but the reservoir dynamics 
built up in prior years dominate. This is the biological mechanism made legible.

---

## Data and methods

All data are open-access. The full pipeline is reproducible from `main.py`.

- **Surveillance data**: Morocco Ministry of Health *Santé en Chiffres* (2003–2015) 
  and *Maladies à Déclaration Obligatoire* tables (2016–2023). Extracted from PDFs 
  using custom Python pipeline; province name harmonisation via canonical map.
- **Climate**: CHIRPS v2.0 daily precipitation (summed monthly), ERA5-Land monthly 
  mean 2m temperature, MODIS MOD13A3 monthly NDVI. Extracted via Google Earth 
  Engine `reduceRegions()` at 5km resolution per province polygon.
- **Population**: Morocco HCP census anchors (2004, 2014, 2024), linearly 
  interpolated. Province boundaries from geoBoundaries MAR-ADM2.
- **Model**: XGBoost regressor. Target: log1p(incidence/100k). Expanding-window 
  temporal CV, 12 folds. Grid search over 144 hyperparameter combinations. 
  Hold-out: 2020–2023.
- **Explainability**: SHAP TreeExplainer.
- **Stack**: Python — `pdfplumber`, `geopandas`, `xgboost`, `shap`, `folium`, 
  `earthengine-api`.

*This project began after I contracted leishmaniasis in 2022. Views are my own.*
