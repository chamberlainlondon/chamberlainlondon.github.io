---
title: "Seoul: Streetlight Stories"
collection: photography
permalink: /photography/may-term-abroad
excerpt: 'This collection is from my Valuation study abroad program in Seoul, South Korea during May 2025.'
venue: ''
date: 2025-05-01
layout: default
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
  justify-content: flex-start; /* ensure images flow left-to-right */
  align-items: center;
  scroll-behavior: smooth;
}

#seoul-scroll-gallery .scroll-item {
  flex: none;
  scroll-snap-align: start; /* snaps each image neatly to left edge */
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

<!-- JavaScript: scrolls to the first image on load -->
<script>
document.addEventListener("DOMContentLoaded", function() {
  const container = document.querySelector('#seoul-scroll-gallery .scroll-container');
  if (container) {
    container.scrollTo({ left: 0, behavior: "instant" });
  }
});
</script>

<div id="seoul-scroll-gallery">
  <div class="scroll-container">

{% assign seoul_images = "1,2,3,4,5,6,7,8,9,10,11,12,13" | split: "," %}
{% for i in seoul_images %}
  <div class="scroll-item">
    <figure>
      <img src="/images/photography/south_korea/seoul/seoul_{{ i }}.jpeg" alt="Seoul photo {{ i }}">
      <figcaption></figcaption>
    </figure>
  </div>
{% endfor %}

  </div>
</div>
