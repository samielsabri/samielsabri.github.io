---
layout: default
title: Nasal Phones Across Tongues
---

<style>
  /* --- CUSTOM CSS FOR HTML COMPONENTS --- */
  .custom-stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    background: #f7f4ef;
    border: 1px solid #d9d3cb;
    margin: 2rem 0;
  }
  .custom-stat-box {
    text-align: center;
    padding: 2rem 1.5rem;
    border-right: 1px solid #d9d3cb;
  }
  .custom-stat-box:last-child {
    border-right: none;
  }
  .custom-stat-num {
    display: block;
    font-size: 2.8rem;
    font-weight: 600;
    color: #2a5fa8;
    line-height: 1;
    margin-bottom: 0.8rem;
    font-family: 'Lora', Georgia, serif;
  }
  .custom-stat-text {
    font-size: 0.95rem;
    color: #6b6560;
    line-height: 1.4;
  }

  /* Bar Charts */
  .custom-charts {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    margin: 1.5rem 0;
  }
  .custom-chart-block h3 {
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #6b6560;
    margin-bottom: 1rem;
    font-family: monospace;
  }
  .custom-bar-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 9px;
  }
  .custom-bar-label {
    font-size: 12.5px;
    color: #6b6560;
    min-width: 68px;
    text-align: right;
  }
  .custom-bar-track {
    flex: 1;
    height: 20px;
    background: #efeae3;
    border-radius: 2px;
  }
  .custom-bar-fill {
    height: 100%;
    border-radius: 2px;
    transition: width 1s cubic-bezier(.16,1,.3,1);
    width: 0%; /* Starts at 0 for animation */
  }
  .bg-presence { background: #2a5fa8; }
  .bg-absence  { background: #b83030; }
  .bg-neutral  { background: #6b6560; }
  .custom-bar-val {
    font-size: 12px;
    color: #6b6560;
    min-width: 34px;
    font-family: monospace;
  }

  /* Responsive fixes */
  @media (max-width: 600px) {
    .custom-stats-grid { grid-template-columns: 1fr; }
    .custom-stat-box { border-right: none; border-bottom: 1px solid #d9d3cb; }
    .custom-stat-box:last-child { border-bottom: none; }
    .custom-charts { grid-template-columns: 1fr; }
  }
</style>

# Nasal Phones Across Tongues

**Phonosemantics · Linguistic Typology · April 2024**  
`R` · `Logistic Regression` · `Permutation Testing` · `Leaflet`

Does the word for "nose" tend to *sound* nasal across languages — or is that just a coincidence of English? A cross-linguistic analysis of 242 languages across 40 families using logistic regression and permutation testing.

*Links: [↗ GitHub](https://github.com/samielsabri/phonosemantic_typology_analysis) · [↗ Live Shiny app](https://samielsabri.shinyapps.io/nose_typology_app/)*

---

## The question

One of the foundational principles of modern linguistics is the *arbitrariness of the sign*: the sounds of a word bear no inherent relationship to its meaning. Nothing about the word "cat" tells you it refers to a small furry animal. Yet a growing body of typological research finds cracks in this principle — places where sound and meaning appear non-randomly linked.

The word for "nose" is a striking candidate. In English it starts with /n/. In French: *nez*. Spanish: *nariz*. Hindi: *nāk*. But are these patterns real across unrelated language families, or just an artefact of shared Indo-European ancestry? This project tests that question across 242 languages from 40 families.

<!-- CUSTOM STATS HTML BLOCK -->
<div class="custom-stats-grid">
  <div class="custom-stat-box">
    <span class="custom-stat-num">242</span>
    <span class="custom-stat-text">languages in the dataset</span>
  </div>
  <div class="custom-stat-box">
    <span class="custom-stat-num">40</span>
    <span class="custom-stat-text">language families sampled</span>
  </div>
  <div class="custom-stat-box">
    <span class="custom-stat-num">80%</span>
    <span class="custom-stat-text">have a nasal phone in their word for "nose"</span>
  </div>
</div>
<!-- END STATS BLOCK -->

---

## Interactive map

Each marker represents one language. Hover for the language name; click for the IPA transcription of its word for "nose." Blue = nasal phone present, red = absent.

<!-- MAP IFRAME -->
<iframe src="/dashboards/nose_sound_symbolism_dashboard.html" width="100%" height="520px" style="border: 1px solid #d9d3cb; border-radius: 4px; margin: 1.5rem 0;"></iframe>

*Data sourced from Google Translate, Bing Translate, Glosbe, and specialist dictionaries for underrepresented languages. IPA transcriptions consulted where available; secondary literature used to confirm suspected nasals in Latin-script data.*

---

## What the data show

The 80% figure is striking on its own, but raw prevalence isn't the finding — the finding is that this pattern holds across unrelated language families, suggesting it isn't simply inherited from a common ancestor.

<!-- CUSTOM CHARTS HTML BLOCK -->
<div class="custom-charts">
  <div class="custom-chart-block">
    <h3>Nasal phone in "nose" — all languages</h3>
    <div class="custom-bar-row">
      <span class="custom-bar-label">Present</span>
      <div class="custom-bar-track"><div class="custom-bar-fill bg-presence" data-w="80%"></div></div>
      <span class="custom-bar-val">80%</span>
    </div>
    <div class="custom-bar-row">
      <span class="custom-bar-label">Absent</span>
      <div class="custom-bar-track"><div class="custom-bar-fill bg-absence" data-w="20%"></div></div>
      <span class="custom-bar-val">20%</span>
    </div>
  </div>

  <div class="custom-chart-block">
    <h3>Nasal phone in "nose" — Indo-European only</h3>
    <div class="custom-bar-row">
      <span class="custom-bar-label">Present</span>
      <div class="custom-bar-track"><div class="custom-bar-fill bg-presence" data-w="88%"></div></div>
      <span class="custom-bar-val">~88%</span>
    </div>
    <div class="custom-bar-row">
      <span class="custom-bar-label">Absent</span>
