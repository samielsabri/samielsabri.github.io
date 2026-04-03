---
layout: default
title: Nasal Phones Across Tongues
---

# Nasal Phones Across Tongues

**Phonosemantics · Linguistic Typology · April 2024**[cite: 2]  
`R` · `Logistic Regression` · `Permutation Testing` · `Leaflet`[cite: 2]

Does the word for "nose" tend to *sound* nasal across languages — or is that just a coincidence of English?[cite: 2] A cross-linguistic analysis of 242 languages across 40 families using logistic regression and permutation testing[cite: 2].

*Links: [↗ GitHub](https://github.com/samielsabri/phonosemantic_typology_analysis) · [↗ Live Shiny app](https://samielsabri.shinyapps.io/nose_typology_app/)*[cite: 2]

---

## The question

One of the foundational principles of modern linguistics is the *arbitrariness of the sign*: the sounds of a word bear no inherent relationship to its meaning[cite: 2]. Nothing about the word "cat" tells you it refers to a small furry animal[cite: 2]. Yet a growing body of typological research finds cracks in this principle — places where sound and meaning appear non-randomly linked[cite: 2].

The word for "nose" is a striking candidate[cite: 2]. In English it starts with /n/[cite: 2]. In French: *nez*[cite: 2]. Spanish: *nariz*[cite: 2]. Hindi: *nāk*[cite: 2]. But are these patterns real across unrelated language families, or just an artefact of shared Indo-European ancestry?[cite: 2] This project tests that question across 242 languages from 40 families[cite: 2].

**Key Stats:**
* **242** languages in the dataset[cite: 2]
* **40** language families sampled[cite: 2]
* **80%** have a nasal phone in their word for "nose"[cite: 2]

---

## Interactive map

Each marker represents one language[cite: 2]. Hover for the language name; click for the IPA transcription of its word for "nose."[cite: 2] Blue = nasal phone present, red = absent[cite: 2].

<iframe src="/dashboards/nose_sound_symbolism_dashboard.html" width="100%" height="500px" style="border: 1px solid #d9d3cb; border-radius: 4px; margin-top: 1rem; margin-bottom: 0.5rem;"></iframe>

*Data sourced from Google Translate, Bing Translate, Glosbe, and specialist dictionaries for underrepresented languages[cite: 2]. IPA transcriptions consulted where available; secondary literature used to confirm suspected nasals in Latin-script data[cite: 2].*

---

## What the data show

The 80% figure is striking on its own, but raw prevalence isn't the finding — the finding is that this pattern holds across unrelated language families, suggesting it isn't simply inherited from a common ancestor[cite: 2].

* **Nasal phone in "nose" (All languages):** Present: 80% | Absent: 20%[cite: 2]
* **Nasal phone in "nose" (Indo-European only):** Present: ~88% | Absent: ~12%[cite: 2]
* **Nasal count per word (All languages):** 0 nasals: ~48 | 1 nasal: ~160 | 2 nasals: ~29 | 3 nasals: ~5[cite: 2]
* **Nasal onset position (Indo-European):** Onset: ~78% | Not onset: ~22%[cite: 2]. Contrast: across all languages with a nasal, the nasal more often falls in the coda/rhyme (e.g. Arabic */ænf/*, Turkish */burun/*) than at the onset[cite: 2].

---

## Methodology

Two approaches were used to assess whether nasal phone presence in words for "nose" is non-random:[cite: 2]

* **Logistic regression** modelled the probability of a nasal phone as a function of language family membership, number of phones, and number of syllables[cite: 2]. Word length is a necessary control: longer words are simply more likely to contain any given phone by chance[cite: 2].
* **Permutation testing** assessed robustness without parametric assumptions[cite: 2]. Language family labels were shuffled 10,000 times and the test statistic recalculated each time, generating a null distribution[cite: 2]. The observed statistic was then compared against it[cite: 2].

> **Benchmarking note:** Because nasal phones (/m/, /n/, /ŋ/) appear in over 94%, 78%, and 63% of the world's languages respectively, and tend to be high-frequency sounds within each language, we cannot directly estimate a "baseline" rate of nasal occurrence in arbitrary words[cite: 2]. The permutation test sidesteps this by asking: is the pattern more structured than chance shuffling of family labels would produce?[cite: 2]

---

## Results

| Term | Estimate | Odds ratio | p-value | Significance |
| :--- | :--- | :--- | :--- | :--- |
| (Intercept) | −0.382 | 0.683 | 0.555 | |
| Indo-European (vs. other) | +0.980 | 2.67× | 0.092 | marginal |
| Number of phones | +0.923 | 2.52× | <0.001 | *** |
| Number of syllables | −1.326 | 0.27× | 0.002 | ** |

*Table data based on the logistic regression model[cite: 2].*

The permutation test yielded *p* = 0.024, confirming the pattern is unlikely under the null hypothesis of random nasal distribution[cite: 2].

Indo-European membership increases the odds of a nasal phone by 2.67× but this effect does not reach conventional significance — meaning we cannot claim IE languages are categorically different, only that the overall cross-linguistic trend is real[cite: 2]. The two families significantly less likely to feature nasal phones are Sino-Tibetan (e.g. Mandarin *bízi*) and Northeast Caucasian (e.g. Chechen)[cite: 2].

Phonetic complexity effects are intuitive: more phones → more chances for a nasal (positive); more syllables → each syllable carries fewer phones on average, diluting the density (negative)[cite: 2].

---

## What this means

The results support a modest but real phonosemantic bias: across language families with no shared ancestor, the word for "nose" is drawn toward nasal sounds more than chance would predict[cite: 2]. The articulatory logic is appealing — nasal phones are produced by directing airflow through the nose, mirroring the body part they name[cite: 2]. This would make "nose" a case of *sound iconicity* rather than pure arbitrariness[cite: 2].

The finding also has a methodological implication: controlling for word length is essential in any phonosemantic analysis[cite: 2]. A long word like */dægunu/* (Latvian) contains a nasal almost by accident; a short word like */nun/* (Bambara) is far more likely to reflect an underlying symbolic tendency[cite: 2].

Limitations are significant: the Indo-European bias in available data persists despite efforts to broaden sampling, and the absence of phone-frequency corpora for most languages makes it impossible to estimate a true baseline rate[cite: 2]. The permutation workaround is principled but not a substitute for that data[cite: 2].
