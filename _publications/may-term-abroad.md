---
title: "Seoul: Streetlight Stories"
collection: photography
permalink: /photography/may-term-abroad
excerpt: 'This collection is from my Valuation study abroad program in Seoul, South Korea during May 2025.'
venue: ''
date: 2025-05-01
layout: default

# ✅ Captions stored as list of maps (GitHub Pages safe)
captions:
  - num: 1
    text: "Seoul_1"
  - num: 2
    text: "Seoul_2"
  - num: 3
    text: "Seoul_3"
  - num: 4
    text: "Seoul_4"
  - num: 5
    text: "Seoul_5"
  - num: 6
    text: "Seoul_6"
  - num: 7
    text: "Seoul_7"
  - num: 8
    text: "Seoul_8"
  - num: 9
    text: "Seoul_9"
  - num: 10
    text: "Seoul_10"
  - num: 11
    text: "Seoul_11"
  - num: 12
    text: "Seoul_12"
  - num: 13
    text: "Seoul_13"
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
