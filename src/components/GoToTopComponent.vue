<template>
    <button class="go-top-btn-beat" @click="topFunction()">⬆</button>
    <button class="go-top-btn-echo" @click="topFunction()">⬆</button>
</template>

<script setup>
import {onMounted} from 'vue'
// Handle Go To Top Btn 
onMounted(()=>{
let topBtnBeat = document.querySelector(".go-top-btn-beat");
let topBtnEcho = document.querySelector(".go-top-btn-echo");


function scrollFunction() {
    if (document.body.scrollTop > 800 || document.documentElement.scrollTop > 800) {
        topBtnBeat.style.display = "block";
        topBtnEcho.style.display = "block";
    } else {
        topBtnBeat.style.display = "none";
        topBtnEcho.style.display = "none";
    }
}

window.onscroll = function () { scrollFunction() };
})

// When the user clicks on the button, scroll to the top of the document
function topFunction() {
    document.body.scrollTop = 0;
    document.documentElement.scrollTop = 0;
}

</script>

<style>
.go-top-btn-beat {
    display: none;
    position: fixed;
    bottom: 20px;
    right: 30px;
    z-index: 99;
    font-size: 30px;
    border: none;
    outline: none;
    background-color: var(--primary-btn-color);
    color: white;
    padding: 13px 25px;
    border-radius: 50%;
    animation: beat 2s linear infinite;
}

.go-top-btn-echo {
    display: none;
    position: fixed;
    bottom: 20px;
    right: 30px;
    z-index: 99;
    font-size: 30px;
    border: none;
    outline: none;
    background-color: var(--primary-btn-color);
    color: white;
    padding: 13px 25px;
    border-radius: 50%;
    animation: echo 2s linear infinite;
}
</style>