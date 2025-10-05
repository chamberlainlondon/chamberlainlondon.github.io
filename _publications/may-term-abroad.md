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
/* 🔒 Styles scoped to this page only */
#seoul-scroll-gallery {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 90vh;
  background: var(--background-color, #f9f9f9);
}

/* Horizontal scrolling container */
#seoul-scroll-gallery .scroll-container {
  display: flex;
  overflow-x: auto;
  overflow-y: hidden;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;
  padding: 3rem 0;
  gap: 2rem;
  justify-content: center;
  align-items: center;
}

/* Each photo + caption container */
#seoul-scroll-gallery .scroll-item {
  flex: none;
  scroll-snap-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-width: 40vw;
  min-height: 500px; /* ensures container exists even before image loads */
  position: relative;
}

/* Image settings */
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
  opacity: 0;
  transition: opacity 0.4s ease-in-out, transform 0.3s ease;
}

/* Fade in smoothly once loaded */
#seoul-scroll-gallery .scroll-item img.loaded {
  opacity: 1;
}

#seoul-scroll-gallery .scroll-item img:hover {
  transform: scale(1.03);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
}

/* Captions (blank for now) */
#seoul-scroll-gallery figcaption {
  text-align: center;
  margin-top: 0.75rem;
  font-size: 0.9rem;
  color: #555;
  min-height: 1.2rem;
}
</style>

<script>
/* JavaScript to ensure fade-in only after load */
document.addEventListener("DOMContentLoaded", function() {
  const imgs = document.querySelectorAll('#seoul-scroll-gallery img');
  imgs.forEach(img => {
    img.addEventListener('load', () => img.classList.add('loaded'));
    img.addEventListener('error', () => {
      img.classList.add('loaded');
      img.style.opacity = 0.4;
      img.style.filter = 'blur(2px)';
    });
  });
});
</script>

<div id="seoul-scroll-gallery">
  <div class="scroll-container">

{% assign seoul_images = "1,2,3,4,5,6,7,8,9,10,11,12,13" | split: "," %}
{% for i in seoul_images %}
  <div class="scroll-item">
    <figure>
      <img src="/images/photography/south_korea/seoul/seoul_{{ i }}.jpeg" alt="Seoul photo {{ i }}" loading="lazy">
      <figcaption></figcaption>
    </figure>
  </div>
{% endfor %}

  </div>
</div>
