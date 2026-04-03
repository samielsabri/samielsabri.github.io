---
layout: default
title: Nasal Phones Across Tongues
---

# Nasal Phones Across Tongues

**Phonosemantics · Linguistic Typology · April 2024**  
`R` · `Logistic Regression` · `Permutation Testing` · `Leaflet`

Does the word for "nose" tend to *sound* nasal across languages — or is that just a coincidence of English? A cross-linguistic analysis of 242 languages across 40 families using logistic regression and permutation testing. This personal project was not part of any contract or academic exercise, but purely to satisfy a question I have had since I was a child.

*Links: [↗ GitHub](https://github.com/samielsabri/phonosemantic_typology_analysis) · [↗ Live Shiny app](https://samielsabri.shinyapps.io/nose_typology_app/)*

---

## The question

One of the foundational principles of modern linguistics is the *arbitrariness of the sign*: the sounds of a word bear no inherent relationship to its meaning. Nothing about the word "cat" tells you it refers to a small furry animal. However, a growing body of typological research finds more examples of possible sound symbolism — places where sound and meaning appear non-randomly linked.

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

This pattern holds across unrelated language families, suggesting it isn't simply inherited from a common ancestor.

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
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 20%; background: #b83030;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">20%</span>
    </div>
  </div>

  <!-- Chart 2 -->
  <div style="flex: 1 1 45%; min-width: 250px;">
    <h3 style="font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: #6b6560; margin-bottom: 1rem; font-family: monospace;">Nasal phone in "nose" — Indo-European</h3>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">Present</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 88%; background: #2a5fa8;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">~88%</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">Absent</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 12%; background: #b83030;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">~12%</span>
    </div>
  </div>

  <!-- Chart 3 -->
  <div style="flex: 1 1 45%; min-width: 250px;">
    <h3 style="font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: #6b6560; margin-bottom: 1rem; font-family: monospace;">Nasal count per word</h3>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">0 nasals</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 20%; background: #6b6560;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">~48</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">1 nasal</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 66%; background: #2a5fa8;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">~160</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">2 nasals</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 12%; background: #2a5fa8;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">~29</span>
    </div>
  </div>

  <!-- Chart 4 -->
  <div style="flex: 1 1 45%; min-width: 250px;">
    <h3 style="font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase; color: #6b6560; margin-bottom: 1rem; font-family: monospace;">Nasal onset position — IE languages</h3>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">Onset</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 78%; background: #2a5fa8;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">~78%</span>
    </div>
    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 9px;">
      <span style="font-size: 12.5px; color: #6b6560; min-width: 68px; text-align: right;">Not onset</span>
      <div style="flex: 1; height: 20px; background: #efeae3; border-radius: 2px;"><div style="height: 100%; border-radius: 2px; width: 22%; background: #6b6560;"></div></div>
      <span style="font-size: 12px; color: #6b6560; min-width: 34px; font-family: monospace;">~22%</span>
    </div>
  </div>

</div>

Contrast: across all languages with a nasal, the nasal more often falls in the coda/rhyme (e.g. Arabic */ænf/*, Turkish */burun/*) than at the onset.

---

## Methodology

Two approaches were used to assess whether nasal phone presence in words for "nose" is non-random:

* **Logistic regression** modelled the probability of a nasal phone as a function of language family membership, number of phones, and number of syllables. Word length is a necessary control: longer words are simply more likely to contain any given phone by chance.
* **Permutation testing** assessed robustness without parametric assumptions. Language family labels were shuffled 10,000 times and the test statistic recalculated each time, generating a null distribution. The observed statistic was then compared against it.

> **Benchmarking note:** Because nasal phones (/m/, /n/, /ŋ/) appear in over 94%, 78%, and 63% of the world's languages respectively, and tend to be high-frequency sounds within each language, we cannot directly estimate a "baseline" rate of nasal occurrence in arbitrary words. The permutation test sidesteps this by asking: is the pattern more structured than chance shuffling of family labels would produce?

---

## Results

| Term | Estimate | Odds ratio | p-value | Significance |
| :--- | :--- | :--- | :--- | :--- |
| (Intercept) | −0.382 | 0.683 | 0.555 | |
| Indo-European (vs. other) | +0.980 | 2.67× | 0.092 | marginal |
| Number of phones | +0.923 | 2.52× | <0.001 | \*\*\* |
| Number of syllables | −1.326 | 0.27× | 0.002 | \*\* |

*Table data based on the logistic regression model.*

The permutation test yielded *p* = 0.024, confirming the pattern is unlikely under the null hypothesis of random nasal distribution.

Indo-European membership increases the odds of a nasal phone by 2.67× but this effect does not reach conventional significance — meaning we cannot claim IE languages are categorically different, only that the overall cross-linguistic trend is real. The two families significantly less likely to feature nasal phones are Sino-Tibetan (e.g. Mandarin *bízi*) and Northeast Caucasian (e.g. Chechen).

Phonetic complexity effects are intuitive: more phones → more chances for a nasal (positive); more syllables → each syllable carries fewer phones on average, diluting the density (negative).

---

## What this means

The results support a modest but real phonosemantic bias: across language families with no shared ancestor, the word for "nose" is drawn toward nasal sounds more than chance would predict. The articulatory logic is appealing because nasal phones are produced by directing airflow through the nose, mirroring the body part they name. This would make "nose" a case of *sound iconicity* rather than pure arbitrariness.

The finding also has a methodological implication: controlling for word length is essential in any phonosemantic analysis. A long word like */dægunu/* (Latvian) contains a nasal almost by accident; a short word like */nun/* (Bambara) is far more likely to reflect an underlying symbolic tendency.

Limitations are still significant: the Indo-European bias in available data persists despite efforts to broaden sampling, and the absence of phone-frequency corpora for most languages makes it impossible to estimate a true baseline rate. The permutation workaround is principled but not a substitute for that data.
