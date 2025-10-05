---
title: "Seoul: Streetlight Stories"
collection: photography
permalink: /photography/may-term-abroad
excerpt: 'This collection is from my Valuation study abroad program in Seoul, South Korea during May 2025.'
venue: ''
date: 2025-05-01
layout: default

captions:
  1: "Seoul_1"
  2: "Seoul_2"
  3: "Seoul_3"
  4: "Seoul_4"
  5: "Seoul_5"
  6: "Seoul_6"
  7: "Seoul_7"
  8: "Seoul_8"
  9: "Seoul_9"
  10: "Seoul_10"
  11: "Seoul_11"
  12: "Seoul_12"
  13: "Seoul_13"
---

<style>
#seoul-scroll-gallery {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 90vh;
  background: var(--background-color, #f9f9f9);
}

#seoul-scroll-gallery .scroll-container {
  display: flex;
  overflow-x: auto;
  overflow-y: hidden;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;
  padding: 3rem 0;
  gap: 2rem;
  justify-content: flex-start;
  align-items: center;
  scroll-behavior: smooth;
}

#seoul-scroll-gallery .scroll-item {
  flex: none;
  scroll-snap-align: start;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-width: 40vw;
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

#seoul-scroll-gallery figcaption {
  text-align: center;
  margin-top: 0.75rem;
  font-size: 0.9rem;
  color: #555;
  min-height: 1.2rem;
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

{% for key,value in page.captions %}
  <div class="scroll-item">
    <figure>
      <img src="/images/photography/south_korea/seoul/seoul_{{ key }}.jpeg" alt="{{ value }}">
      <figcaption>{{ value }}</figcaption>
    </figure>
  </div>
{% endfor %}

  </div>
</div>
