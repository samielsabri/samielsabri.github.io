---
layout: default
title: FIFA 2026 Socio-Spatial Impact Analysis
---

# Mapping hidden deprivation in north Oxford

**Deprivation analysis · Oxford, UK · 2026**  
`R` · `ONS Census 2021` · `IMD 2025` · `ONS Open Geography Portal`

Wolvercote Young People's Club (WYPC) serves young people aged 8–24 in Wolvercote and Cutteslowe, a north Oxford area perceived as affluent but containing real concentrations of disadvantage invisible to standard area statistics. I was commissioned to build the evidence base for their funding case.

---

## The problem

Standard deprivation analysis operates at LSOA level (~1,500 residents). In mixed neighbourhoods, LSOA averages wash out within-area inequality. A street of social housing next to owner-occupied terraces registers as moderately deprived, erasing the circumstances of both populations. This is a direct instance of the Modifiable Areal Unit Problem.

I moved the analysis to Output Area geography (~300 residents), the smallest available census unit, and benchmarked all indicators against Oxford city rather than national averages — a deliberate choice given Oxford's overall affluence.

---

## Original measures

To synthesise evidence across four deprivation dimensions (employment, housing, health, education) I designed a composite score:

**`n_hidden`** — dimensions where an OA is above both the Oxford average and its own LSOA average. This encapsulates deprivation a neighbourhood-level analysis cannot see.

---

## Maps

### Hidden deprivation score by Output Area

![Distribution of hidden deprivation (n_hidden) across Output Areas in the five target LSOAs](/assets/img/oa_hidden_n.png)

*Each OA is scored on the number of census deprivation dimensions where it exceeds both the Oxford city average and its own LSOA average. High scores identify acute need masked by neighbourhood-level statistics.*

---

### LSOA-level (IMD 2025) vs. OA-level (Census 2021) — side by side

![Comparative spatial analysis: LSOA IMD 2025 quintiles alongside OA Census 2021 deprivation quintiles, for each of the four deprivation dimensions](/assets/img/wypc_lsoa_oa_compare_gh.jpeg)

*The divergence between the two columns illustrates how much within-LSOA variation is lost when analysis stops at neighbourhood level.*


## Key findings

Health deprivation ranged from below 20% to nearly 49% across OAs within the same neighbourhood. Social renting concentrated above 70% in specific OAs while approaching zero in adjacent streets. Several OAs in Oxford 002G (Sunnymead) scored 4–5 out of 5 on `n_hidden` — their deprivation worse than both the city and their own neighbourhood average, and invisible to standard analysis.

The report gave WYPC a spatially precise funding case: not "our area has pockets of deprivation" but a demonstration of exactly where, on which dimensions, and why standard statistics had been missing it.
