---
layout: default
title: Nasal Phones Across Tongues
---

<!-- Include required external resources for fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,600;1,400&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">

<style>
  /* Scope all custom variables to this specific page wrapper so it doesn't break your site's global nav */
  .typology-wrapper {
    --ink:     #1a1714;
    --ink-mid: #6b6560;
    --ink-faint:#b8b3ae;
    --paper:   #f7f4ef;
    --paper-2: #efeae3;
    --accent:  #2a5fa8;
    --accent-r:#b83030;
    --rule:    #d9d3cb;
    
    font-family: 'DM Sans', sans-serif;
    background: var(--paper);
    color: var(--ink);
    font-size: 16px;
    line-height: 1.7;
    margin: 0;
    padding: 0;
  }

  .typology-wrapper *, .typology-wrapper *::before, .typology-wrapper *::after { 
    box-sizing: border-box; 
  }

  /* ── HEADER ─────────────────────────────────── */
  .typology-header {
    border-bottom: 1px solid var(--rule);
    padding: 4rem 2rem 3rem;
    max-width: 780px;
    margin: 0 auto;
  }

  .typology-wrapper .eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--ink-mid);
    margin-bottom: 1.2rem;
  }

  .typology-wrapper h1 {
    font-family: 'Lora', serif;
    font-size: clamp(1.8rem, 4vw, 2.6rem);
    font-weight: 600;
    line-height: 1.2;
    margin-bottom: 1.2rem;
    letter-spacing: -0.01em;
    border: none;
  }

  .typology-wrapper .subtitle {
    font-size: 1.05rem;
    color: var(--ink-mid);
    max-width: 580px;
    line-height: 1.65;
    margin-bottom: 2rem;
  }

  .typology-wrapper .meta-pills { display: flex; flex-wrap: wrap; gap: 8px; }

  .typology-wrapper .pill {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border: 1px solid var(--rule);
    border-radius: 2px;
    color: var(--ink-mid);
    background: var(--paper-2);
  }

  .typology-wrapper .pill.link {
    color: var(--accent);
    border-color: #a8c0e8;
    background: #eef3fb;
    text-decoration: none;
  }

  .typology-wrapper .pill.link:hover { background: #dce8f7; }

  /* ── MAIN LAYOUT ─────────────────────────────── */
  .typology-main {
    max-width: 780px;
    margin: 0 auto;
    padding: 0 2rem 5rem;
  }

  .typology-wrapper section { margin-top: 3.5rem; }

  .typology-wrapper h2 {
    font-family: 'Lora', serif;
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 0.9rem;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid var(--rule);
  }

  .typology-wrapper p { margin-bottom: 1rem; color: var(--ink); }
  .typology-wrapper p:last-child { margin-bottom: 0; }
  .typology-wrapper em { font-family: 'Lora', serif; font-style: italic; }

  /* ── STAT CARDS ──────────────────────────────── */
  .typology-wrapper .stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--rule);
    border: 1px solid var(--rule);
    margin: 2rem 0;
  }

  .typology-wrapper .stat {
    background: var(--paper);
    padding: 1.4rem 1.2rem;
    text-align: center;
  }

  .typology-wrapper .stat-number {
    font-family: 'Lora', serif;
    font-size: 2.2rem;
    font-weight: 600;
    color: var(--accent);
    line-height: 1;
    display: block;
    margin-bottom: 6px;
  }

  .typology-wrapper .stat-label {
    font-size: 12px;
    color: var(--ink-mid);
    line-height: 1.4;
    font-weight: 300;
  }

  /* ── MAP IFRAME ──────────────────────────────── */
  .typology-wrapper .map-wrap {
    margin: 1.5rem 0 0.75rem;
    position: relative;
    z-index: 1;
  }

  .typology-wrapper .map-caption {
    font-size: 12.5px;
    color: var(--ink-mid);
    font-style: italic;
    line-height: 1.5;
    padding-top: 0.5rem;
  }

  /* ── BAR CHARTS ──────────────────────────────── */
  .typology-wrapper .charts {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    margin: 1.5rem 0;
  }

  .typology-wrapper .chart-block h3 {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink-mid);
    margin-bottom: 1rem;
    border: none;
  }

  .typology-wrapper .bar-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 9px;
  }

  .typology-wrapper .bar-label {
    font-size: 12.5px;
    color: var(--ink-mid);
    min-width: 68px;
    text-align: right;
    line-height: 1.3;
  }

  .typology-wrapper .bar-track {
    flex: 1;
    height: 20px;
    background: var(--paper-2);
    border-radius: 1px;
    overflow: hidden;
    position: relative;
  }

  .typology-wrapper .bar-fill {
    height: 100%;
    border-radius: 1px;
    transition: width 1s cubic-bezier(.1
