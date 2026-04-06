---
layout: page
title: Linguify – A Full-Stack Spotify Language Analytics Dashboard
stack: "Full-Stack·  Web-Development ·  API · Python · SQL · JavaScript · HTML · CSS · Data Visualization"
links:
  - label: "Web-App (not active)"
    url: "https://samielsabri.github.io/projects/linguify"
---
Linguify is a full-stack web application that allows users to analyze the linguistic diversity of their Spotify libraries. By processing track metadata and lyrics, the app generates a comprehensive language profile, identifying bilingual tracks and providing tools for lyric-based language learning

<style>
  .gallery-container {
    display: flex;
    gap: 15px;
    background: #1a1a1a;
    padding: 20px;
    border-radius: 12px;
    font-family: sans-serif;
    align-items: flex-start;
  }

  /* Main Viewport */
  .main-view {
    position: relative;
    flex-grow: 1;
    background: #000;
    border-radius: 8px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 400px;
  }

  .main-view img {
    max-width: 100%;
    max-height: 500px;
    display: none; /* Hidden by default, toggled by JS */
  }

  .main-view img.active {
    display: block;
  }

  /* Navigation Buttons */
  .nav-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(255,255,255,0.2);
    color: white;
    border: none;
    padding: 15px 10px;
    cursor: pointer;
    font-size: 20px;
    transition: 0.3s;
    z-index: 10;
  }

  .nav-btn:hover { background: rgba(255,255,255,0.5); }
  .prev { left: 0; border-radius: 0 5px 5px 0; }
  .next { right: 0; border-radius: 5px 0 0 5px; }

  /* Vertical Thumbnails */
  .thumb-sidebar {
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 100px;
    max-height: 500px;
    overflow-y: auto;
  }

  .thumb-sidebar img {
    width: 100%;
    height: 60px;
    object-fit: cover;
    border-radius: 4px;
    cursor: pointer;
    opacity: 0.5;
    transition: 0.3s;
    border: 2px solid transparent;
  }

  .thumb-sidebar img.active-thumb {
    opacity: 1;
    border-color: #4CAF50;
  }
</style>

<div class="gallery-container">
  <div class="main-view">
    <button class="nav-btn prev" onclick="changeSlide(-1)">&#10094;</button>

    <!-- Fixed: Removed extra class/onclick from the main image -->
    <img class="active" src="/assets/img/Linguify/linguify_home_first_time copy.png">
    <img src="/assets/img/Linguify/linguify_home copy.png">
    <img src="/assets/img/Linguify/linguify_home_table copy.png">
    <img src="/assets/img/Linguify/linguify_map copy.png">
    <img src="/assets/img/Linguify/linguify_language_grid copy.png">
    <img src="/assets/img/Linguify/linguify_home_table copy.png">
    <img src="/assets/img/Linguify/linguify_songs_by_language copy.png">
    <img src="/assets/img/Linguify/linguify_song_info copy.png">
    <img src="/assets/img/Linguify/linguify_analyze copy.png">
    <img src="/assets/img/Linguify/linguify_analyze_2 copy.png">
    <img src="/assets/img/Linguify/linguify_analyze_modal copy.png">
    <img src="/assets/img/Linguify/linguify_mobile.png">
    
    <button class="nav-btn next" onclick="changeSlide(1)">&#10095;</button>
  </div>

  <div class="thumb-sidebar">
    <img src="/assets/img/Linguify/linguify_home_first_time copy.png" class="active-thumb" onclick="currentSlide(0)">
    <img src="/assets/img/Linguify/linguify_home copy.png" onclick="currentSlide(1)">
    <img src="/assets/img/Linguify/linguify_home_table copy.png" onclick="currentSlide(2)">
    <img src="/assets/img/Linguify/linguify_map copy.png" onclick="currentSlide(3)">
    <img src="/assets/img/Linguify/linguify_language_grid copy.png" onclick="currentSlide(4)">
    <img src="/assets/img/Linguify/linguify_home_table copy.png" onclick="currentSlide(5)">
    <img src="/assets/img/Linguify/linguify_songs_by_language copy.png" onclick="currentSlide(6)">
    <img src="/assets/img/Linguify/linguify_song_info copy.png" onclick="currentSlide(7)">
    <img src="/assets/img/Linguify/linguify_analyze copy.png" onclick="currentSlide(8)">
    <img src="/assets/img/Linguify/linguify_analyze_2 copy.png" onclick="currentSlide(9)">
    <img src="/assets/img/Linguify/linguify_analyze_modal copy.png" onclick="currentSlide(10)">
    <img src="/assets/img/Linguify/linguify_mobile.png" onclick="currentSlide(11)">
  </div>
</div>

<script>
  let slideIndex = 0;

  function showSlide(n) {
    const slides = document.querySelectorAll(".main-view img");
    const thumbs = document.querySelectorAll(".thumb-sidebar img");
    
    if (n >= slides.length) slideIndex = 0;
    if (n < 0) slideIndex = slides.length - 1;
    
    slides.forEach(img => img.classList.remove("active"));
    thumbs.forEach(t => t.classList.remove("active-thumb"));
    
    slides[slideIndex].classList.add("active");
    thumbs[slideIndex].classList.add("active-thumb");
  }

  function changeSlide(n) {
    showSlide(slideIndex += n);
  }

  function currentSlide(n) {
    showSlide(slideIndex = n);
  }

  // THIS FIXES THE INITIAL LOAD:
  window.onload = function() {
    showSlide(slideIndex);
  };
</script>

<div style="display: flex; flex-wrap: wrap; background: #f7f4ef; border: 1px solid #d9d3cb; margin: 2rem 0; font-family: sans-serif;">
  <div style="flex: 1 1 30%; text-align: center; padding: 2rem 1.5rem; border-right: 1px solid #d9d3cb; box-sizing: border-box;">
    <span style="font-size: 0.95rem; color: #6b6560;">Status Update: Due to recent restrictive changes in the Spotify Web API for independent developers, Linguify is currently in a "Read-Only" portfolio state. At its peak, the platform supported over 100 active users during its initial feedback phase</span>
  </div>
</div>



## Technical Stack

* Backend: Flask (Python) following Clean Architecture principles to decouple business logic from external APIs.

* Frontend: React and Tailwind CSS for a responsive, dark-mode dashboard.

* Database & APIs: Spotify Web API (OAuth 2.0), Musixmatch/Genius API, SQL for Database Query

* Data Visualization: Custom Charting (Chart.js), Dynamic Dashboards, Mapbox SDK for geospatial visualization

* State Management & Parallel Processing: Real-time analysis progress tracking for large libraries (e.g., "Liked Songs" analysis)

To ensure high accuracy in language classification, I implemented a multi-layered detection pipeline:

* Natural Language Processing: Initial language detection performed on song lyrics.

* Heuristics Programming: When NLP certainty scores fell below a specific threshold, the system automatically fell back on secondary heuristics, such as artist metadata and album-level language tags, to resolve ambiguities.

* Scalability: Designed the backend to manage long-running tasks, providing users with estimated analysis times for large libraries.

## Key Features
1. Automated Library Analysis
The application analyzes user libraries (up to 1000 songs across 28+ languages in test cases) to determine favorite languages and listening habits. It handles long-running data tasks by providing users with estimated analysis times and progress updates.

2. Geospatial Musical Footprint
Using Mapbox, I developed an interactive global map that pins the origin of a user's music library. This allows users to visualize their geographical "musical footprint" across different continents.

3. Lyric-Integrated Learning
Linguify bridges data and education by allowing users to interact with song lyrics.

** Metadata: Displays language families and speaker populations (e.g., "Italian: Romance Family, 65 million speakers").

** Learning Tools: Users can select lyric lines to generate flashcard decks or custom Spotify playlists for immersion (coming soon).


