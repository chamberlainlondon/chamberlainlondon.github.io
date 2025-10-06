---
title: "Seoul 2025: Streetlight Stories"
collection: photography
permalink: /photography/may-term-abroad
excerpt: 'I took this collection of photographs during my study abroad trip to Seoul, South Korea in May 2025.'
venue: ''
date: '2025-05-01'
layout: default

captions:
  - num: 1
    text: "Seongsu Station, Seoul Subway Line 2"
  - num: 2
    text: "Entrance to Dongmyo Flea Market"
  - num: 3
    text: "Inscriptions in Ansan Mountain Rocks"
  - num: 4
    text: "Starfield Library in Starfield Coex Mall"
  - num: 5
    text: "Dongmyo Flea Market Vintage Clothing Stores"
  - num: 6
    text: "Building in Mapo-dong, Mapo District"
  - num: 7
    text: "Han River with Friends"
  - num: 8
    text: "View Overlooking Ansan Mountain"
  - num: 9
    text: "National Museum of Korea Inflatable Statue"
  - num: 10
    text: "Milwaukee Garage Door"
  - num: 11
    text: "Lanterns in Jogyesa Temple"
  - num: 12
    text: "Kei Truck in Mapo-dong, Mapo District"
  - num: 13
    text: "N Seoul Tower at Night with May Term Cohort"
---

<style>
#seoul-scroll-gallery {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 90vh;
  background: var(--background-color, #f9f9f9);
}

#seoul-scroll-gallery figcaption {
  margin-top: 0.5rem;
  font-size: 0.95rem;
  font-family: inherit;
  text-align: left;
  color: rgba(141, 163, 184, 0.85); /* ✨ soft blue-grey */
  letter-spacing: 0.02em;
}

#seoul-scroll-gallery .scroll-container {
  display: flex;
  overflow-x: auto;
  overflow-y: hidden;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;
  padding: 3rem 3rem 3rem 5rem; /* left padding for border space */
  gap: 2rem;
  justify-content: flex-start;
  align-items: flex-start;
  scroll-behavior: smooth;
  border-left: 4px solid rgba(0, 0, 0, 0.1);
  scroll-padding-left: 5rem; /* ✅ key line: accounts for left padding */
}

/* Horizontal scroll container */
#seoul-scroll-gallery .scroll-container {
  display: flex;
  overflow-x: auto;
  overflow-y: hidden;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;
  padding: 3rem 3rem 3rem 5rem; /* ← extra left padding */
  gap: 2rem;
  justify-content: flex-start;
  align-items: flex-start;
  scroll-behavior: smooth;
  border-left: 4px solid rgba(0, 0, 0, 0.1); /* optional subtle border */
}

#seoul-scroll-gallery .scroll-item {
  flex: none;
  scroll-snap-align: start;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  min-width: 40vw;
}

#seoul-scroll-gallery figure {
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

#seoul-scroll-gallery .scroll-item img {
  max-height: 70vh;
  max-width: 85vw;
  width: auto;
  height: auto;
  object-fit: contain;
  border-radius: 12px;
  background: #f2f2f2;
  box-shadow: 0 4px 18px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  display: block;
}

#seoul-scroll-gallery .scroll-item img:hover {
  transform: scale(1.03);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
}

/* ✨ Caption styling */
#seoul-scroll-gallery figcaption {
  margin-top: 0.5rem;
  font-size: 0.95rem;
  color: var(--text-color, #333);
  font-family: inherit;
  text-align: left;
}
</style>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const container = document.querySelector('#seoul-scroll-gallery .scroll-container');
  if (container) container.scrollTo({ left: 0, behavior: "instant" });
});
</script>

<div id="seoul-scroll-gallery">
  <div class="scroll-container">

{% for item in page.captions %}
  <div class="scroll-item">
    <figure>
      <img src="/images/photography/south_korea/seoul/seoul_{{ item.num }}.jpeg" alt="{{ item.text }}">
      <figcaption>{{ item.text }}</figcaption>
    </figure>
  </div>
{% endfor %}

  </div>
</div>
