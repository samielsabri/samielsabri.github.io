---
layout: page
title: "Outbreak Surveillance in Toronto Healthcare Institutions"
keywords: "Infectious Disease · Surveillance · 2026"
stack: "R · GitHub Actions · moving epidemic method · Kaplan–Meier · Chart.js · Leaflet"
links:
  - label: "GitHub"
    url: "https://github.com/samielsabri/toronto_healthcare_institutions_outbreaks"
---

Hospitals, long-term care homes and retirement homes in Toronto must report
respiratory and enteric outbreaks to Toronto Public Health, and the City
publishes every declared outbreak as open data, refreshed each Thursday. The
data are public, but there is no ready-made view of the season: how this week
compares with past years, which pathogens are driving it, whether the
influenza season has started, or which homes keep having outbreaks. This
project is the routine surveillance a public health unit would run on these
data: an automated weekly pipeline, a dashboard, and documented methods with
honest limitations.

<!-- STATS GRID -->
<div style="display: flex; flex-wrap: wrap; background: #f5f0ea; border: 1px solid #ddd6cc; margin: 2rem 0; font-family: sans-serif;">
  <div style="flex: 1 1 30%; text-align: center; padding: 1.75rem 1.25rem; border-right: 1px solid #ddd6cc; box-sizing: border-box;">
    <span style="display: block; font-size: 2.6rem; font-weight: 600; color: #c0392b; line-height: 1; margin-bottom: 0.7rem; font-family: Georgia, serif;">7,097</span>
    <span style="font-size: 0.9rem; color: #6b6560;">outbreaks since January 2016, across 12 respiratory seasons</span>
  </div>
  <div style="flex: 1 1 30%; text-align: center; padding: 1.75rem 1.25rem; border-right: 1px solid #ddd6cc; box-sizing: border-box;">
    <span style="display: block; font-size: 2.6rem; font-weight: 600; color: #c0392b; line-height: 1; margin-bottom: 0.7rem; font-family: Georgia, serif;">230</span>
    <span style="font-size: 0.9rem; color: #6b6560;">facilities, geocoded with the City's own address register</span>
  </div>
  <div style="flex: 1 1 30%; text-align: center; padding: 1.75rem 1.25rem; box-sizing: border-box;">
    <span style="display: block; font-size: 2.6rem; font-weight: 600; color: #c0392b; line-height: 1; margin-bottom: 0.7rem; font-family: Georgia, serif;">Weekly</span>
    <span style="font-size: 0.9rem; color: #6b6560;">automatic update every Thursday, with a saved snapshot of each refresh</span>
  </div>
</div>

<!-- INTERACTIVE DASHBOARD (served from the project repository's GitHub Pages
     site, so it is always the latest weekly build) -->
<div style="margin: 2rem 0;">
  <iframe
    src="/toronto_healthcare_institutions_outbreaks/"
    width="100%"
    height="760px"
    style="border: 1px solid #ddd6cc; border-radius: 4px; display: block;">
  </iframe>
  <div style="margin-top: 0.8rem; text-align: center;">
    <a href="/toronto_healthcare_institutions_outbreaks/" target="_blank"
       style="background: #2c3e50; color: white; padding: 10px 22px;
              border-radius: 6px; text-decoration: none; font-weight: 600;
              font-family: sans-serif; font-size: 0.85rem;">
      Open the full-screen dashboard ↗
    </a>
  </div>
</div>
<p style="font-size: 0.82rem; color: #888; font-family: sans-serif;
   margin-top: -0.3rem;">
  Pick a season, setting and outbreak type, move the week slider or press
  play. The map shows facilities with an outbreak active that week; the tabs
  show this season against past ranges, the pathogen mix, influenza and RSV
  season onset, outbreak duration, repeat outbreaks, a facility's history and
  the outbreak table. Data: City of Toronto Open Data, <i>Outbreaks in Toronto
  Healthcare Institutions</i> (Open Government Licence – Toronto). Unofficial;
  not produced or endorsed by Toronto Public Health.
</p>

---

## The pipeline

Every Thursday, about two hours after the City refreshes the data, a GitHub
Action downloads all eleven annual files and saves a dated snapshot of the
current year's file. The City overwrites its files each week, so these
snapshots are the only way to see later how long outbreaks take to be
reported and what is edited afterwards. The run then checks the files
against the expected schema and the reference tables, rebuilds the cleaned
dataset, runs the test suite and publishes the dashboard. If a column is
renamed or a new pathogen label appears, the run stops and opens a GitHub
issue that says exactly what changed.

## Free-text records data cleaning

The source is one row per outbreak per ward, typed by hand over ten years.
Once in a while, pathogen labels drift. For example, *Norovirus-like* becomes *Norovirus* in 2023,
*Coronavirus* becomes *Coronavirus\** in 2020 to separate seasonal
coronaviruses from COVID-19, and co-detections move from one row with two
agents to two separate rows. 101 raw labels are mapped to eleven analysis
groups in a reviewed lookup table. Facility addresses, with their typos,
abbreviations and ward suffixes, are normalized and matched to the City's
Address Points register. The match itself exposed an address that does not
exist and had split one home into two facilities.

## Pre vs Post-Pandemic comparisons

Outbreak counts roughly doubled after 2020, and most of that is not disease.
COVID-19 added hundreds of outbreaks a season, outbreaks are now declared
ward by ward (about 1.4 wards per facility episode, up from 1.1), and almost
every respiratory outbreak now has a pathogen identified (none was identified
in 26–29% in 2018 and 2019, against 1–4% since 2020). So the dashboard never 
pools the eras: each season is compared separately with a pre-pandemic and a post-pandemic range. 
Season onset for influenza and RSV uses the moving epidemic method, the approach
ECDC and WHO Europe use. Outbreak duration uses Kaplan–Meier so that
outbreaks still open are not counted as short ones.

## Limitations

There are no case counts, attack rates or deaths, so everything is at the
outbreak-level. Counts, therefore, reflect testing and reporting practices as well
as disease activity. Facilities are not ranked, because there are no bed
counts to compare them fairly. The most recent weeks are provisional and how
much they grow will be measured from the weekly snapshots as they
accumulate. Every methodological choice is recorded in the
[decisions log](https://github.com/samielsabri/toronto_healthcare_institutions_outbreaks/blob/main/reports/decisions.md).
