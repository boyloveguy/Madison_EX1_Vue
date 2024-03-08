<template>
  <section>
    <div class="body-advantage-bg">
      <div class="body-advantage-btn-container" style="padding: 150px 0px">
        <button @click="prevSlideHeader()" class="body-advantage-btn-left" style="margin-right: 3px">
          <img src="../assets/images/Triangle-left.svg" alt="image" />
        </button>
        <button @click="nextSlideHeader()" class="body-advantage-btn-right">
          <img src="../assets/images/Triangle-right.svg" alt="image" />
        </button>
        <span class="body-advantage-tab-page"></span>
      </div>
      <hr />
      <div class="flex-box body-advantage-layout reveal" style="padding: 150px 0px">
        <div class="body-advantage-video half-screen">
          <div class="body-advantage-video-banner text-center-x">
            <img class="bg-video" src="../assets/images/Image-Advantage.png" alt="image" />
            <button class="btn-play" @click="handlePlayVideo()">
              <img class="" src="../assets/images/play.svg" alt="image" />
            </button>
          </div>
          <div class="body-advantage-video-play"></div>
        </div>
        <div class="half-screen">
          <h1 class="body-advantage-title">LETS TAKE ADVANTAGE</h1>
          <P>ABLE CLOUD BENEATH WAS DISHED</P>
          <P style="margin: 30px 0">Best for active freelancers and designers who need more projects
            and premium features code and unlock more.</P>
          <div class="flex-box">
            <div class="btn-learn-more text-center">
              <a href="https://madison-technologies.com/" target="_blank">LEARN MORE</a>
            </div>
            <button class="services-btn">Explore Services</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.body-advantage-bg {
  background-color: var(--primary-color-white);
}

.body-advantage-btn-left,
.body-advantage-btn-right,
.body-stay-btn-left,
.body-stay-btn-right {
  background-color: var(--primary-btn-color);
  border: none;
  border-radius: 50%;
  padding: 16px 20px;
  display: inline-flex;
  justify-content: center;
  align-items: center;
}

.body-advantage-tab-page {
  font-weight: 700;
  font-size: 24px;
  line-height: 32px;
  margin-left: 15px;
  letter-spacing: 3px;
}

hr {
  border-color: black;
}

.body-advantage-title,
.body-features-title,
.body-projects-title,
.body-say-title {
  font-family: var(--font-inknut);
  font-size: 56px;
  font-weight: 900;
  line-height: 64px;
  margin: 0;
  text-transform: uppercase;
}

.body-advantage-title+p {
  font-size: 16px;
  font-weight: 400;
  line-height: 32px;
  letter-spacing: 3px;
  margin-top: 34px;
}

.body-advantage-title+p+p,
.body-features-description,
.body-features-card-description,
.body-projects-description,
.body-say-card-content p,
.body-post-card span,
.footer-menu-title li,
.text-bg-black {
  font-family: "DM Sans", sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 32px;
  color: var(--primary-text-description-color);
  opacity: 50%;
  margin-left: 0 !important;
}

.btn-learn-more,
.btn-load_more {
  background-color: var(--primary-btn-color);
  color: white;
  width: 170px;
  height: 48px;
  font-weight: 700;
  letter-spacing: 1px;
  font-size: 16px;
  line-height: 18.75px;
  cursor: pointer;
}

.btn-learn_more a {
  color: white;
}

.services-btn {
  width: 170px;
  height: 48px;
  background-color: white;
  font-family: "DM Sans", sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 32px;
  margin-left: 50px;
}

button {
  border: none;
  cursor: pointer;
}

button:hover,
.footer-logo img:hover,
.btn-learn-more:hover {
  opacity: 50%;
}

.body-advantage-video-banner {
  position: relative;
  left: -100px;
}

.btn-play {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 110px;
  background: none;
}

.inactive {
  display: none !important;
}

.active {
  display: block !important;
}

.body-advantage-video-play {
  display: none;
}
</style>

<script setup>
import $ from 'jquery';

// Slide Header
let currentHeader = 1;
const handleChangeHeader = (n) => {
  const countBanner = document.querySelectorAll(
    ".header-content-container"
  ).length;
  const banners = document.querySelectorAll(".header-content-container");
  if (n > countBanner) {
    currentHeader = 1;
  }

  if (n < 1) {
    currentHeader = countBanner;
  }

  banners.forEach((element) => {
    if (banners[currentHeader - 1] == element) {
      document
        .querySelector(".header-active")
        ?.classList.remove("header-active");
      element.classList.add("header-active");
    }
  });
  document.querySelector(".body-advantage-tab-page").innerHTML = `${currentHeader + "/" + countBanner
    }`;
};

function prevSlideHeader() {
  handleChangeHeader((currentHeader -= 1));
}

function nextSlideHeader() {
  handleChangeHeader((currentHeader += 1));
}

// Handle Play Video
const handlePlayVideo = () => {
  $(".body-advantage-video-banner").addClass("inactive");
  $(".body-advantage-video-play").addClass("active");
  $(".body-advantage-video-play").append(
    `<iframe height="400px" width="95%" src="https://www.youtube.com/embed/tgbNymZ7vqY?autoplay=1&mute=1"></iframe>`
  );
};

setTimeout(() => {
  setInterval(nextSlideHeader, 5000);
}, 2000)

</script>