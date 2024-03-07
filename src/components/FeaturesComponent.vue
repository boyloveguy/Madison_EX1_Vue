<template>
  <section id="about" style="background-color: var(--primary-color-black)">
    <div class="body-features-bg reveal">
      <div class="flex-box body-features-layout">
        <div class="half-screen">
          <h1 class="body-features-title">OUR CORE FEATURES</h1>
        </div>
        <div class="half-screen">
          <p style="margin-left: 15px" class="body-features-description">
            Minuteness of the parts formed a great hindrance to my speed,
            resolved, contrary to my first intention, to make the being.
            Minuteness of the parts formed a great hindrance to my speed,
            resolved, contrary to my first intention, to make the being.
          </p>
        </div>
      </div>
      <div
        class="flex-box slide-container"
        style="margin: 135px 0 80px 0; justify-content: space-between"
      >
        <div class="flex-box body-features-slide-card">
          <div class="flex-box body-features-cards">
            <div class="body-features-card" style="background-color: #9013fe">
              <div style="padding: 48px">
                <img src="../assets/images/icon-card-two.svg" alt="image" />
                <h3>WHITE LABEL</h3>
                <p class="body-features-card-description">
                  Minuteness of the parts formed a great hindrance to my speed,
                  resolved, contrary to my first intention, to make the being.
                </p>
              </div>
            </div>
            <div class="body-features-card" style="background-color: #417505">
              <div style="padding: 48px">
                <img src="../assets/images/icon-card-two.svg" alt="image" />
                <h3>CORE EXPORT</h3>
                <p class="body-features-card-description">
                  Minuteness of the parts formed a great hindrance to my speed,
                  resolved, contrary to my first intention, to make the being.
                </p>
              </div>
            </div>
            <div class="body-features-card" style="background-color: #f8e71c">
              <div style="padding: 48px">
                <img src="../assets/images/icon-card-two.svg" alt="image" />
                <h3>CORE EXPORT</h3>
                <p class="body-features-card-description">
                  Minuteness of the parts formed a great hindrance to my speed,
                  resolved, contrary to my first intention, to make the being.
                </p>
              </div>
            </div>
            <div class="body-features-card" style="background-color: #4ffffc">
              <div style="padding: 48px">
                <img src="../assets/images/icon-card-two.svg" alt="image" />
                <h3>CORE EXPORT</h3>
                <p class="body-features-card-description">
                  Minuteness of the parts formed a great hindrance to my speed,
                  resolved, contrary to my first intention, to make the being.
                </p>
              </div>
            </div>
            <div class="body-features-card" style="background-color: #ff564f">
              <div style="padding: 48px">
                <img src="../assets/images/icon-card-two.svg" alt="image" />
                <h3>CORE EXPORT</h3>
                <p class="body-features-card-description">
                  Minuteness of the parts formed a great hindrance to my speed,
                  resolved, contrary to my first intention, to make the being.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="text-center dot-container">
        <div
          @click="currentSlideOur(1)"
          class="body-features-slide first-dot active-highlight"
        ></div>
        <div @click="currentSlideOur(2)" class="body-features-slide"></div>
        <div @click="currentSlideOur(3)" class="body-features-slide"></div>
        <div @click="currentSlideOur(4)" class="body-features-slide"></div>
      </div>
    </div>
  </section>
</template>


<style>
.slide-container {
  overflow: hidden;
}

.body-features-cards {
  transition: transform 0.5s ease-in-out;
  gap: 30px;
}

.body-features-card {
  min-width: 50%;
}

.body-features-bg,
.body-projects-bg,
.body-say-bg {
  padding: 150px 0;
}

/* section,
.container-logo {
    width: 100vw;
} */

.body-features-title,
.body-features-description,
.body-features-card h3,
.body-features-card-description,
.body-say-title,
.body-say-title + p,
.body-say-card-header,
.body-say-card-content p,
.footer-title,
.footer-menu-title li,
.text-bg-black {
  color: white;
}

.dot-container {
  gap: 25px;
}

.first-dot {
  margin-left: 30px;
}

.last-dot {
  display: none;
}

.body-features-slide {
  border-radius: 50%;
  width: 15px;
  height: 15px;
  background-color: white;
  cursor: pointer;
  opacity: 30%;
}

.active-highlight {
  background-color: #9013fe;
  opacity: 100%;
}
</style>

<script setup>
import $ from "jquery";
import {onMounted} from 'vue'

let slideIndex = 2;

function showSlides(n) {
  const slides = document.querySelector(".body-features-cards");
  const slidesCount = document.querySelectorAll(".body-features-card").length;
  const card = document.querySelector(".body-features-card");

  if (n > slidesCount) {
    slideIndex = 1;
  }
  
  if (n < 1) {
    slideIndex = slidesCount;
  }
  
  slides.style.transform = `translateX(${
    (-card.offsetWidth - 30) * (slideIndex - 1)
  }px)`;
}

function currentSlideOur(n) {
  showSlides((slideIndex = n));
  const btn = document.querySelectorAll(".body-features-slide");

  document
    .querySelector(".active-highlight")
    ?.classList.remove("active-highlight");
  btn[n - 1]?.classList.add("active-highlight");

  btn.forEach((element) => {
    element.addEventListener("click", function () {
      document
        .querySelector(".active-highlight")
        ?.classList.remove("active-highlight");
      element.classList.add("active-highlight");
    });
  });
}

// Initial slide show
onMounted(()=>{
  showSlides(slideIndex)
})

// FULL Width Mobile
const widthMobile = window.matchMedia("(max-width: 1300px)")
onMounted(()=>{
if (widthMobile.matches) {
    $(".dot-container").append(`
    <div @click="currentSlideOur(5)" class="body-features-slide last-dot"></div>
    `)
  }
})
  
let count = 0
setInterval(() => {
    count++
    currentSlideOur(count)
    if (widthMobile.matches) {
        if (count > 4) {
            count = 0
        }
    } else {
        if (count > 3) {
            count = 0
        }
    }
}, 3000);
</script>