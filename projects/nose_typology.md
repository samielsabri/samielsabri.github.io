---
layout: default
title: Nasal Phones Across Tongues
---

# Nasal Phones Across Tongues

**Phonosemantics · Linguistic Typology · April 2024**  
`R` · `Logistic Regression` · `Permutation Testing` · `Leaflet`

Does the word for "nose" tend to *sound* nasal across languages — or is that just a coincidence of English? A cross-linguistic analysis of 242 languages across 40 families using logistic regression and permutation testing.

*Links: [↗ GitHub](https://github.com/samielsabri/phonosemantic_typology_analysis) · [↗ Live Shiny app](https://samielsabri.shinyapps.io/nose_typology_app/)*

---

## The question

One of the foundational principles of modern linguistics is the *arbitrariness of the sign*: the sounds of a word bear no inherent relationship to its meaning. Nothing about the word "cat" tells you it refers to a small furry animal. Yet a growing body of typological research finds cracks in this principle — places where sound and meaning appear non-randomly linked.

The word for "nose" is a striking candidate. In English it starts with /n/. In French: *nez*. Spanish: *nariz*. Hindi: *nāk*. But are these patterns real across unrelated language families, or just an artefact of shared Indo-European ancestry? This project tests that question across 242 languages from 40 families.

<!-- STATS GRID: Built with inline flexbox so Jekyll won't crash -->
<div style="display: flex; flex-wrap: wrap; background: #f7f4ef; border: 1px solid #d9d3cb; margin: 2rem 0; font-family: sans-serif;">
  <div style="flex: 1 1 30%; text-align: center; padding: 2rem 1.5rem; border-right: 1px solid #d9d3cb; box-sizing: border-box;">
    <span style="display: block; font-size: 2.8rem; font-weight: 600; color: #2a5fa8; line-height: 1; margin-bottom: 0.8rem; font-family: Georgia, serif;">242</span>
    <span style="font-size: 0.95rem; color: #6b6560;">languages in the dataset</span>
  </div>
  <div style="flex: 1 1 30%; text-align: center; padding: 2rem 1.5rem; border-right: 1px solid #d9d3cb; box-sizing: border-box;">
    <span style="display: block; font-size: 2.8rem; font-weight: 600; color: #2a5fa8; line-height: 1; margin-bottom: 0.8rem; font-family: Georgia, serif;">40</span>
    <span style="font-size: 0.95rem; color: #6b6560;">language families sampled</span>
  </div>
  <div style="flex: 1 1 30%; text-align: center; padding: 2rem 1.5rem; box-sizing: border-box;">
    <span style="display: block; font-size: 2.8rem; font-weight: 600; color: #2a5fa8; line-height: 1; margin-bottom: 0.8rem; font-family: Georgia, serif;">80%</span>
    <span style="font-size: 0.95rem; color: #6b6560;">have a nasal phone in their word for "nose"</span>
  </div>
</div>

---

## Interactive map

Each marker represents one language. Hover for the language name; click for the IPA transcription of its word for "nose." Blue = nasal phone present, red = absent.

<!-- MAP IFRAME -->
<iframe src="/dashboards/nose_sound_symbolism_dashboard.html" width="100%" height="520px" style="border: 1px solid #d9d3cb; border-radius: 4px; margin: 1.5rem 0;"></iframe>

*Data sourced from Google Translate, Bing Translate, Glosbe, and specialist dictionaries for underrepresented languages. IPA transcriptions consulted where available; secondary literature used to confirm suspected nasals in Latin-script data.*

---

## What the data show

The 80% figure is striking on its own, but raw prevalence isn't the finding — the finding is that this pattern holds across unrelated language families, suggesting it isn't simply inherited from a common ancestor.

<!-- BAR CHARTS: Built with inline HTML to bypass Markdown parser issues -->
<div style="display: flex; flex-wrap: wrap; gap: 2rem; margin: 1.5rem 0; font-family: sans-serif;">
  
  <!-- Chart 1 -->
  <div style="flex: 1 1 45%; min-width: 250px;">
    <h3 style="font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: #6b6560; margin-bottom: 1rem; font-family: monospace;">Nasal phone in "nose" — all languages</h3>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">Present</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 80%; background: #2a5fa8;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">80%</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">Absent</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 20%; background
