---
title: "The Fox Alliance AUM and Production Dashboard"
excerpt: "Utilized a database of over 224K entries to create a Power BI dashboard that visualized firm KPIs"
collection: portfolio
---
------
At [The Fox Alliance Wealth Advisors](https://www.foxalliancewealth.com/), I developed an internal Power BI dashboard that displays firm assets under management (AUM) and production metrics month-over-month (MoM), utilizing a database of over 224K entries.

### This dashboard displays:

<style>
  blockquote {
    padding: 10px;
    background-color: #f0f0f0;
    border-left: 5px solid #31708f;
    margin: 20px 0;
  }
</style>

> - Total firm AUM
> - Percent of total AUM managed by each advisor
> - MoM AUM growth
> - Total firm production
> - Percent of total production by product (investment) category
> - AUM and production correlation by advisor
> - AUM growth over time
> - Production growth over time

This dashboard is updated monthly, maintaining a live connection to ensure it displays the most up-to-date AUM and production information for every advisor in the firm. This project was my first experience using Power BI.

### Dashboard images:


<div style="overflow: hidden; text-align: center;">
  <div id="image-container" style="display: flex; transition: transform 0.5s;">
    <img class="image" src="https://chamberlainlondon.github.io/images/TFA Dashboard 1.png">
    <img class="image" src="https://chamberlainlondon.github.io/images/TFA Dashboard 2.png">
    <img class="image" src="https://chamberlainlondon.github.io/images/TFA Dashboard 3.png">
  </div>
  <div>
    <a onclick="scrollToNext()" class="btn">Next</a>
  </div>
</div>

<script>
  let currentIndex = 0;
  const images = document.getElementsByClassName("image");
  const container = document.getElementById("image-container");

  function scrollToNext() {
    container.style.transition = "transform 0.5s";
    currentIndex = (currentIndex + 1) % images.length;
    const scrollAmount = images[currentIndex].offsetLeft - container.scrollLeft;
    container.style.transform = `translateX(-${scrollAmount}px)`;
  }
</script>

<br>


<div style="text-align: center;">
  <figure>
    <img src="https://chamberlainlondon.github.io/images/TFA Dashboard 1.png" alt="Illustration of the TFA Dashboard Homepage">
    <figcaption>Dashboard Homepage</figcaption>
  </figure>
</div>

<div style="text-align: center;">
  <figure>
    <img src="https://chamberlainlondon.github.io/images/TFA Dashboard 2.png" alt="Illustration of the TFA Dashboard Historical AUM">
    <figcaption>Historical AUM Visualization</figcaption>
  </figure>
</div>

<div style="text-align: center;">
  <figure>
    <img src="https://chamberlainlondon.github.io/images/TFA Dashboard 3.png" alt="Illustration of the TFA Dashboard Historical Production">
    <figcaption>Historical Production Visualization</figcaption>
  </figure>
</div>







