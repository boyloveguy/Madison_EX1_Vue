<template>
  <header>
    <!-- Nav BAR -->
    <section>
      <div class="navbar">
        <div class="header-bg flex-box" style="justify-content: space-between">
          <div class="header-logo"><a href="#header-content" class="header-logo-link">
              <span class="header-logo-A">A</span>
              <span class="header-logo-G">G</span>
              <span class="header-logo-E">E</span>
              <span class="header-logo-N">N</span>
              <span class="header-logo-C">C</span>
              <span class="header-logo-Y">Y</span>
            </a></div>
          <div class="nav-right flex-box">
            <nav class="nav-link full-width">
              <div class="nav-link-container">
                <a class="nav-option" href="#about">About</a>
                <a class="nav-option" href="#portfolio" style="margin: 0px 60px">Portfolio</a>
                <a class="nav-option" href="#contact">Contact</a>
              </div>
              <div id="sidebar" class="sidebar">
                <a href="javascript:void(0)" class="close-btn" @click="closeSidebar()">❌</a>
                <a href="#about">About</a>
                <a href="#portfolio">Portfolio</a>
                <a href="#contact">Contact</a>
              </div>
              <div class="header-menu-icon">
                <img class="sidebar_toggler" @click="openSidebar()" src="../assets/images/menu.svg" alt="image" />
              </div>
            </nav>
          </div>
        </div>
      </div>
      <div class="header-bg">
        <!-- HEADER-CONTENT -->
        <div id="header-content">
          <div class="pos-relative header-content-container header-active"
            style="z-index: 1; width: 100%; padding-top: 70px">
            <div class="header-content">
              <h1 class="header-title">WE CREATE AMAZING SITES WITH EASE</h1>
              <div class="flex-box">
                <img src="../assets/images/Object.png" alt="image" />
                <h1 class="header-disctiption">
                  A PEEP AT SOME DISTANT ORB HAS POWER TO RAISE AND PURIFY
                </h1>
              </div>
            </div>
            <div class="header-img-container">
              <img class="header-shadow-img" src="../assets/images/combined-shape.png" alt="image" />
              <img class="header-bg-img" src="../assets/images/Rectangle.png" alt="image" />
              <img class="header-img" src="../assets/images/Bitmap.png" alt="image" />
            </div>
          </div>
          <div class="pos-relative header-content-container" style="z-index: 1; width: 100%; padding-top: 70px">
            <div class="header-content">
              <h1 class="header-title">
                HELLO WORLD! HELLO WORLD! HELLO WORLD!
              </h1>
              <div class="flex-box">
                <img src="../assets/images/Object.png" alt="image" />
                <h1 class="header-disctiption">
                  HELLO WORLD!HELLO WORLD!HELLO WORLD!HELLO WORLD!
                </h1>
              </div>
            </div>
            <div class="header-img-container">
              <img class="header-shadow-img" src="../assets/images/combined-shape.png" alt="image" />
              <img class="header-bg-img" src="../assets/images/Rectangle.png" alt="image" />
              <img class="header-img" src="../assets/images/Bitmap.png" alt="image" />
            </div>
          </div>
        </div>
      </div>
    </section>
  </header>
</template>

<script setup>

// Function to open the sidebar
function openSidebar() {
  document.getElementById("sidebar").style.width = "250px";
}

// Function to close the sidebar
function closeSidebar() {
  document.getElementById("sidebar").style.width = "0";
}

// handle to close the sidebar when click out side
window.addEventListener("click", (e) => {
  const sidebar = document.getElementById("sidebar");
  if (e.target.id !== "sidebar" && e.target.className !== "sidebar_toggler") {
    sidebar.style.width = "0";
  }
});
</script>

<style>
.header-bg,
.body-advantage-bg,
.body-features-bg,
.body-projects-bg,
.body-say-bg,
.body-post-bg,
.body-say-bg-logo {
  width: var(--primary-width-screen);
  margin: 0 auto;
}

.navbar {
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: var(--primary-color-black);
  margin: 0 auto;
  position: fixed;
  z-index: 5;
  width: 100vw;
}

.header-logo a {
  color: white;
  font-size: 24px;
  font-weight: 700;
  line-height: 32px;
  cursor: pointer;
}

.nav-right {
  width: 30%;
}

.nav-link {
  font-family: "DM Sans", sans-serif;
  display: flex;
  justify-content: end;
  align-items: center;
}

.nav-link-container {
  width: 100%;
  display: flex;
  justify-content: end;
  align-items: center;
}

.header-menu-icon {
  display: none;
}

.nav-option {
  color: white;
  text-decoration: none;
}

.header-content {
  padding-top: 100px;
  position: absolute;
}

.header-content-container {
  display: none;
}

.header-active {
  display: block;
  animation-name: showSide;
  animation-duration: 2s;
}

.header-title {
  font-family: "Inknut Antiqua", serif;
  color: white;
  font-weight: 900;
  font-size: 72px;
  width: 70%;
  line-height: 80px;
}

.header-disctiption {
  padding-left: 40px;
  color: white;
  font-weight: 400;
  font-size: 16px;
  line-height: 32px;
  letter-spacing: 3px;
  width: 35%;
}

.header-img-container {
  position: absolute;
  left: calc(42%);
  top: 550px;
}

.header-shadow-img {
  position: absolute;
  z-index: -2;
  top: -5.8rem;
  right: -41.5rem;
}

.header-bg-img {
  position: absolute;
  z-index: -1;
}

.header-img {
  position: absolute;
  z-index: -1;
  top: 50px;
  left: -50px;
}

.header-menu-icon {
  margin-left: 60px;
  cursor: pointer;
}

.sidebar {
  height: 100%;
  width: 0;
  position: fixed;
  top: 0;
  right: 0;
  background-color: black;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
  color: white;
}

.sidebar a {
  padding: 8px 8px 8px 32px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
  transition: 0.3s;
}

.sidebar a:hover {
  color: #f1f1f1;
}

.sidebar .close-btn {
  position: absolute;
  top: 10px;
  font-size: 20px;
  margin-right: 50px;
}

/* Button styles */
.open-sidebar-btn {
  cursor: pointer;
  padding: 10px;
  background-color: #4caf50;
  color: #fff;
  border: none;
  border-radius: 4px;
}

.nav-option:hover {
  transform: scale(130%);
  color: var(--primary-btn-color);
  transition: 0.5s;
}

.header-logo:hover {
  transform: scale(130%);
  transition: 0.5s;
}

.header-logo:hover span:nth-child(1) {
  color: #179fd3;
}

.header-logo:hover span:nth-child(2) {
  color: #58a749;
}

.header-logo:hover span:nth-child(3) {
  color: #fd8321;
}

.header-logo:hover span:nth-child(4) {
  color: #f22c7f;
}

.header-logo:hover span:nth-child(5) {
  color: #e8f22c;
}

.header-logo:hover span:nth-child(6) {
  color: #a02cf2;
}
</style>
