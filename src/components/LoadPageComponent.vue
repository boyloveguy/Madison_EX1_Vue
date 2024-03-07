<template>
    <div class="preloader"></div>
</template>

<script setup>
import $ from "jquery"

// Animation Scroll
function reveal() {
    let reveals = document.querySelectorAll(".reveal");

    for (let i = 0; i < reveals.length; i++) {
        let windowHeight = window.innerHeight;
        let elementTop = reveals[i].getBoundingClientRect().top;
        let elementVisible = 150;

        if (elementTop < windowHeight - elementVisible) {
            reveals[i].classList.add("activeAnimation");
        } else {
            reveals[i].classList.remove("activeAnimation");
        }
    }
}

window.addEventListener("scroll", reveal);


//Load Page
$(document).ready(function () {
    const getLoadPage = document.querySelector(".preloader")
    $(window).on('load', function () {
        setTimeout(() => {
            // getLoadPage.remove();
            getLoadPage.classList.add("inactive");
        }, 2000)
    })

})
</script>

<style>
.reveal {
    position: relative;
    transform: translateY(150px);
    opacity: 0;
    transition: 1.5s all ease;
}

.reveal.activeAnimation {
    transform: translateY(0);
    opacity: 1;
}

main {
    animation: showUp;
    animation-duration: 2s;
    animation-delay: 2s;
}

.preloader {
    background: white url(../assets/images/load-page.gif) no-repeat center center;
    height: 100vh;
    width: 100vw;
    position: fixed;
    z-index: 100;
}
</style>