<template>
  <section id="portfolio">
    <div class="body-projects-bg reveal">
      <div class="flex-box body-projects-layout">
        <div class="half-screen">
          <h1 class="body-projects-title">CHECK OUR PROJECTS</h1>
        </div>
        <div class="half-screen">
          <p style="margin-left: 15px" class="body-projects-description">
            Minuteness of the parts formed a great hindrance to my speed,
            resolved, contrary to my first intention, to make the being.
            Minuteness of the parts formed a great hindrance to my speed,
            resolved, contrary to my first intention, to make the being.
          </p>
        </div>
      </div>
      <hr style="margin: 87px 0 73px 0" />
      <div class="grid-container">
        <div class="grid-item body-projects-menu">
          <h3 class="body-projects-menu-title">PORTFOLIO</h3>
          <div class="body-projects-menu-side">
            <button @click="changeTab('ALL', 'Tab')" class="body-projects-btn-active">
              All
            </button>
            <button @click="changeTab('DESIGN', 'Tab')">Design</button>
            <button @click="changeTab('DEVELOPMENT', 'Tab')">
              Development
            </button>
            <button @click="changeTab('BRANDING', 'Tab')">Branding</button>
            <button @click="changeTab('PRODUCTS', 'Tab')">Products</button>
          </div>
        </div>
        <div class="grid-item body-projects-menu-selection">
          <h3 class="body-projects-menu-title">PORTFOLIO</h3>
          <div class="body-projects-menu-side">
            <select @change="changeTab($event.target.value, 'Tab')">
              <option value="ALL">All</option>
              <option value="DESIGN">Design</option>
              <option value="DEVELOPMENT">Development</option>
              <option value="BRANDING">Branding</option>
              <option value="PRODUCTS">Products</option>
            </select>
          </div>
        </div>
        <div class="grid-container-card">
          <div class="grid-container-card body-projects-card-container"></div>
          <div class="text-center-x">
            <button class="btn-load_more" ref="loadMoreBtn" @click="handleLoadMore(typeTab)">LOAD MORE</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.body-projects-menu-side {
  display: grid;
  grid-template-rows: repeat(5, 1fr);
  gap: 10px;
  margin-top: 37px;
}

.body-projects-menu-side select {
  height: 48px;
  padding: 0px 10px;
}

.body-projects-menu-side option {
  height: 48px;
  padding: 0px 10px;
}

.body-projects-menu-selection {
  display: none;
}

.body-projects-menu-side button {
  background-color: white;
  border-radius: 3px;
  text-align: start;
  height: 48px;
  font-family: var(--font-DM);
  font-weight: 400;
  line-height: 32px;
  font-size: 16px;
}

.body-projects-btn-active {
  padding: 0 16px;
  background-color: var(--primary-color-black) !important;
  color: white;
}

.body-projects-card-bg {
  height: 416px;
  position: relative;
}

.body-projects-card-content {
  height: 100%;
  padding: 57px 48px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  width: 50%;
  position: absolute;
  z-index: 2;
}

.body-projects-card-content p,
.body-projects-menu-title,
.body-say-title+p {
  font-size: 16px;
  font-weight: 400;
  line-height: 32px;
  letter-spacing: 3px;
}

.body-projects-card-content h2 {
  font-family: var(--font-inknut);
  font-size: 40px;
  font-weight: 900;
  line-height: 48px;
  margin: 0;
}

.body-projects-card-bg img {
  position: absolute;
  bottom: 0;
  z-index: 0;
}

.btn-load_more {
  margin: 32px;
}

.grid-container-card {
  display: grid;
  row-gap: 47px;
}

.grid-container {
  display: grid;
  grid-template-columns: 1fr 5fr;
  gap: 10%;
}
</style>

<script setup>
import $ from "jquery"
import { ref, onMounted } from 'vue'

// Handle Click Menu
const handleChangeActiveBtn = () => {
  const btn = document.querySelectorAll(".body-projects-menu-side button")
  btn.forEach(element => {
    element.addEventListener("click", function () {
      document.querySelector(".body-projects-btn-active")?.classList.remove("body-projects-btn-active")
      element.classList.add("body-projects-btn-active")
    });
  });
}

// PROTFOLIO
let visibleItems = 2
let currentItem = 0
let typeTab = ref('ALL')

const changeTab = (nameTab, type) => {
  fetch("https://5ec914049ccbaf0016aa8bbf.mockapi.io/FrontEnd")
    .then((response) => {
      return response.json();
    })
    .then((data) => {
      switch (nameTab) {
        case "ALL":
          handleBanner(data, "ALL");
          break;
        case "DESIGN":
          handleBanner(data, "DESIGN");
          break;
        case "DEVELOPMENT":
          handleBanner(data, "DEVELOPMENT");
          break;
        case "BRANDING":
          handleBanner(data, "BRANDING");
          break;
        case "PRODUCTS":
          handleBanner(data, "PRODUCTS");
          break;
        default:
      }
    });
  if (type == "Tab") {
    visibleItems = 2;
    document.querySelector(".btn-load_more").classList.remove("inactive");
  }
};

const handleLoadMore = (type) => {
  changeTab(type, "LoadMore");
  visibleItems += 2;
};

const handleBanner = (data, type) => {
  $(".body-projects-card-container")?.empty();
  typeTab = type
  let count = 0;

  const result = data.filter((item) =>
    type == "ALL" ? true : item.type == type
  );

  for (let i = currentItem; i < data.length; i++) {
    if (data[i].type === type || type === "ALL") {
      showBanner(data[i]);
      count++;
      if (count > visibleItems - 1) {
        break;
      }
    }
  }
  if (visibleItems >= result.length) {
    $(".btn-load_more").addClass("inactive");
  }
};

const showBanner = (item) => {
  $(document).ready(function () {
    const cardContainer = $(".body-projects-card-container");

    cardContainer.append(`
        <div class="body-projects-card-bg flex-box" style="background-color: ${item.background_color}; color: ${item.color};">
            <div class="body-projects-card-content">
                <p>${item.type}</p>
                <h2>${item.title}</h2>
            </div>
            <div>
                <img style="${item.position}" src="${require('@/assets/images/' + item.image)}" alt="image">
            </div>
        </div>`);
  });
};



changeTab("ALL")
onMounted(() => {
  handleChangeActiveBtn()
})
</script>
