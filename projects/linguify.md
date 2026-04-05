---
layout: default
title: Linguify – A Full-Stack Spotify Language Analytics Dashboard
---

# Linguify: A Full-Stack Spotify Language Analytics Dashboard
`Full-Stack` ·  `Web-Development` ·  `API` · `Python` · `SQL` · `JavaScript` · `HTML` · `CSS` · `Data Visualization` ·| [↗ Web-App (not active)](https://samielsabri.github.io/projects/linguify) 

Linguify is a full-stack web application that allows users to analyze the linguistic diversity of their Spotify libraries. By processing track metadata and lyrics, the app generates a comprehensive language profile, identifying bilingual tracks and providing tools for lyric-based language learning

** Status Update: Due to recent restrictive changes in the Spotify Web API for independent developers, Linguify is currently in a "Read-Only" portfolio state. At its peak, the platform supported over 100 active users during its initial feedback phase.**

<div style="
    display: flex; 
    overflow-x: auto; 
    scroll-snap-type: x mandatory; 
    scroll-behavior: smooth; 
    gap: 10px; 
    border-radius: 8px; 
    background: #1a1a1a; 
    padding: 10px;
">
  
  <div style="flex: 0 0 100%; scroll-snap-align: center;">
    <img src="/assets/img/Figure_7_Renewable_QGIS.png" style="width: 100%; border-radius: 4px; display: block;">
  </div>

  <div style="flex: 0 0 100%; scroll-snap-align: center;">
    <img src="/assets/img/Figure_8_Renewable_QGIS.png" style="width: 100%; border-radius: 4px; display: block;">
  </div>

  <div style="flex: 0 0 100%; scroll-snap-align: center;">
    <img src="/assets/img/renewable_energy_figure3.png" style="width: 100%; border-radius: 4px; display: block;">
  </div>

</div>

<p style="text-align: center; font-size: 0.8rem; color: #888; margin-top: 5px;">
  ← Swipe or scroll to view more →
</p>

## Technical Stack
** Frontend: React, Tailwind CSS

** Backend: Flask (Python) following Clean Architecture principles to decouple business logic from external APIs.

** Frontend: React and Tailwind CSS for a responsive, dark-mode dashboard.

** Database & APIs: Spotify Web API (OAuth 2.0), Musixmatch/Genius API, SQL for Database Query

** Data Visualization: Custom Charting (Chart.js), Dynamic Dashboards, Mapbox SDK for geospatial visualization

** State Management & Parallel Processing: Real-time analysis progress tracking for large libraries (e.g., "Liked Songs" analysis)

## Key Features
1. Automated Library Analysis
The application analyzes user libraries (up to 1000 songs across 28+ languages in test cases) to determine favorite languages and listening habits. It handles long-running data tasks by providing users with estimated analysis times and progress updates.

2. Geospatial Musical Footprint
Using Mapbox, I developed an interactive global map that pins the origin of a user's music library. This allows users to visualize their geographical "musical footprint" across different continents.


