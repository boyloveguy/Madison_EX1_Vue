<template>
  <section style="background-color: var(--primary-color-black)">
    <div class="body-say-bg reveal">
      <div class="flex-box body-say-layout">
        <div class="half-screen">
          <h1 class="body-say-title">WHAT OUR CLIENTS SAY</h1>
          <p>TESTIMONIALS</p>
        </div>
        <div class="half-screen pos-relative">
          <div class="body-say-card-container">
            <div class="body-say-card-slide">
              <div class="body-say-card" style="padding: 48px; background: #417505">
                <div class="body-say-card-header flex-box">
                  <img src="../assets/images/OvalWoman.png" alt="image" />
                  <div style="margin: 26px">
                    <h2>HELENA BRAUER</h2>
                    <p>Apple Inc.</p>
                  </div>
                </div>
                <div class="body-say-card-content">
                  <p>
                    What looked like a small patch of purple grass, above five
                    feet square, was moving across the sand in their direction.
                    When it came near enough he perceived that it was not grass;
                    there were no blades, but only purple roots. The roots were
                    revolving, for each small plant in the whole patch, like the
                    spokes of a rimless wheel.
                  </p>
                </div>
              </div>
              <div class="body-say-card" style="padding: 48px; background: #9013fe">
                <div class="body-say-card-header flex-box">
                  <img src="../assets/images/OvalMan.png" alt="image" />
                  <div style="margin: 26px">
                    <h2>KAY TOTLEBEN</h2>
                    <p>Microsoft.</p>
                  </div>
                </div>
                <div class="body-say-card-content">
                  <p>
                    What looked like a small patch of purple grass, above five
                    feet square, was moving across the sand in their direction.
                    When it came near enough he perceived that it was not grass;
                    there were no blades, but only purple roots. The roots were
                    revolving, for each small plant in the whole patch, like the
                    spokes of a rimless wheel.
                  </p>
                </div>
              </div>
              <div class="body-say-card" style="padding: 48px; background: #ff564f">
                <div class="body-say-card-header flex-box">
                  <img src="../assets/images/OvalWoman.png" alt="image" />
                  <div style="margin: 26px">
                    <h2>HELENA BRAUER</h2>
                    <p>Apple Inc.</p>
                  </div>
                </div>
                <div class="body-say-card-content">
                  <p>
                    What looked like a small patch of purple grass, above five
                    feet square, was moving across the sand in their direction.
                    When it came near enough he perceived that it was not grass;
                    there were no blades, but only purple roots. The roots were
                    revolving, for each small plant in the whole patch, like the
                    spokes of a rimless wheel.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div>
    <div class="body-say-bg-logo" style="padding-bottom: 0 !important">
      <div class="body-features-btn-container" style="padding: 0px">
        <button @click="prevSlide()" class="body-stay-btn-left" style="margin-right: 3px">
          <img src="../assets/images/Triangle-left.svg" alt="image" />
        </button>
        <button @click="nextSlide()" class="body-stay-btn-right">
          <img src="../assets/images/Triangle-right.svg" alt="image" />
        </button>
      </div>
      <hr style="margin: 87px 0 73px 0" />
      <div class="logo-container reveal">
        <a href="https://www.atlassian.com/" target="_blank"><img src="../assets/images/Atlassian-Logo.png"
            alt="image" /></a>
        <a href="https://slack.com/" target="_blank"><img class="slack-logo" src="../assets/images/Slack-logo.png"
            alt="image" /></a>
        <a href="https://www.dropbox.com/" target="_blank"><img class="dropbox-logo"
            src="../assets/images/dropbox-logo.png" alt="image" /></a>
        <a href="https://www.shopify.com/vn" target="_blank"><img src="../assets/images/Shopify_Logo.png"
            alt="image" /></a>
        <a href="https://www.google.com.vn/?hl=vi" target="_blank"><img class="google-logo"
            src="../assets/images/Google-Logo.png" alt="image" /></a>
      </div>
      <hr style="margin-top: 87px" />
    </div>
  </div>
</template>

<style>
.body-say-card-container {
  position: absolute;
  top: -100px;
  overflow-x: hidden;
  width: 49.56vw;
}

.body-say-card-slide {
  display: grid;
  gap: 30px;
  grid-template-columns: 1fr 1fr 1fr;
  transition: transform 0.5s ease-in-out;
}

.body-say-card {
  width: 518px;
}

.body-say-bg-logo {
  margin-top: 150px;
}

.body-say-card-header {
  margin-bottom: 107px;
}

.body-say-card-header h2 {
  margin: 0;
  text-wrap: wrap;
}

.body-say-card-header p {
  font-family: var(--font-DM);
  font-weight: 400;
  font-size: 16px;
  line-height: 32px;
  margin: 0;
}

.logo-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-container a {
  height: 100px;
  display: flex;
  align-items: center;
}

.logo-container img {
  -webkit-filter: grayscale(100%);
  filter: brightness(0%);
  width: 170px;
}

.logo-container img:hover {
  filter: brightness(100%);
  transform: scale(130%);
  transition: 0.3s;
}

.slack-logo {
  width: 150px !important;
}

.dropbox-logo {
  width: 200px !important;
}

.google-logo {
  width: 140px !important;
}

.body-features-layout,
.body-projects-layout,
.body-post-layout {
  gap: 30px;
}
</style>

<script setup>
// Slide Say
let slideIndexSay = 1;

function showSlidesSay(n) {
  const slides = document.querySelector(".body-say-card-slide");
  const slidesCount = document.querySelectorAll(".body-say-card").length;
  const card = document.querySelector(".body-say-card");

  if (n > slidesCount) {
    slideIndexSay = 1;
  }

  if (n < 1) {
    slideIndexSay = slidesCount;
  }
  slides.style.transform = `translateX(${(-card.offsetWidth - 30) * (slideIndexSay - 1)}px)`;
}

function prevSlide() {
  showSlidesSay((slideIndexSay -= 1));
}

function nextSlide() {
  showSlidesSay((slideIndexSay += 1));
}

setInterval(nextSlide, 3000);
</script>