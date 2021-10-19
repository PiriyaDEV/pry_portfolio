<template>
  <div id="app">
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"
    />
    <router-view />
  </div>
</template>

<script>
import Vue from "vue";
import vueSmoothScroll from "vue2-smooth-scroll";
Vue.use(vueSmoothScroll);
export default {};
</script>

<style>
@import url("https://use.typekit.net/zqk6rjr.css");
@import url("https://fonts.googleapis.com/css2?family=Mitr:wght@200;300;400;500&display=swap");

body,
html,
input,
textarea,
button {
  padding: 0;
  margin: 0;
  font-family: "Mitr", sans-serif;
  font-size: 8px;
  overflow-x: hidden;
  color: #1a1a1a;
}

.section {
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 2;
}
.page-container {
  width: 1440px;
  max-width: 1440px;
  padding: 0;
}
.navbar-container {
  width: 1440px;
  max-width: 1440px;
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1001;
  padding: 0;
}

/* Button */
.yellow-btn {
  background-color: #fcb43e;
  border-radius: 25px;
  line-height: 0px;
  padding: 2.5px 25px;
  width: fit-content;
  color: #ffffff;
}

.blue-btn {
  background-color: #4960ac;
  border-radius: 25px;
  line-height: 0px;
  padding: 7px 40px;
  width: fit-content;
  color: #ffffff;
  cursor: pointer;
}

.l-blue-btn {
  background-color: #e0eaf1;
  border-radius: 25px;
  line-height: 0px;
  padding: 7px 40px;
  width: fit-content;
  cursor: pointer;
}

/* Text */
.nm-text {
  font-size: 2.5em;
  font-weight: 300;
}

.sm-text {
  font-size: 2em;
  font-weight: 300;
}

.p-text {
  font-size: 1.75em;
  font-weight: 300;
}

.bg-text {
  font-size: 6.25em;
  font-weight: 300;
}

.header {
  font-size: 4.5em;
  font-weight: 400;
}

.title {
  font-size: 4.25em;
  font-weight: 300;
}

.bracket {
  color: #aebcc5;
  font-weight: 200;
  font-size: 3.5em;
  margin-bottom: 10px;
  margin-top: 0px;
}

.link-text {
  text-decoration: none;
  color: #4960ac;
}

.yl-bullet {
  margin-top: 7px;
}

.skill-cir-icon {
  width: 50px;
  margin-right: 20px;
}

/* Slide */
.vueperslides__arrow svg {
  stroke-width: 2px !important;
}

.vueperslides__bullet .default {
  background-color: rgba(0, 0, 0, 0.3) !important;
  /* border: none !important; */
  border-width: 1px !important;
  /* box-shadow: none !important; */
  transition: 0s !important;
}

.vueperslides__bullet--active .default {
  background-color: #fcb43e !important;
}

.vueperslides--fixed-height {
  height: 300px !important;
}

.vueperslide {
  background-size: cover !important;
  background-origin: border-box !important;
  background-size: 400px !important;
  background-color: #4960ac !important;
  background-repeat: no-repeat;
}

.swiper-wrapper {
  transition-duration: 2s !important;
}

.swiper-pagination-bullet {
  width: 13px !important;
  height: 13px !important;
  margin: 0px 7px !important;
  --swiper-theme-color: #4960ac !important;
}

@media screen and (max-width: 1920px) {
  .page-container,
  .navbar-container {
    width: 1280px;
    max-width: 1280px;
  }
}
@media screen and (max-width: 1650px) {
  .vueperslide {
    background-size: 350px !important;
  }
}
@media screen and (max-width: 1440px) {
  .page-container,
  .navbar-container {
    width: 1024px;
    max-width: 1024px;
  }

  .vueperslide {
    background-size: 300px !important;
  }
}

@media screen and (max-width: 1280px) {
  .vueperslide {
    background-size: 350px !important;
  }
}

@media screen and (max-width: 1100px) {
  /* Text */
  .nm-text {
    font-size: 2em;
  }

  /* .sm-text {
    font-size: 1.5em;
  } */

  /* .p-text {
    font-size: 1.25em;
  } */

  .bg-text {
    font-size: 5.75em;
  }

  .header {
    font-size: 4em;
  }

  .title {
    font-size: 3.75em;
  }

  .bracket {
    font-size: 3em;
  }

  .blue-btn,
  .l-blue-btn {
    padding: 5px 25px;
  }
}

@media screen and (max-width: 1024px) {
  .page-container,
  .navbar-container {
    width: 960px;
    max-width: 960px;
    padding-left: 20px;
    padding-right: 20px;
  }
}
@media screen and (max-width: 768px) {
  .page-container,
  .navbar-container {
    width: 720px;
    max-width: 720px;
  }
}
@media screen and (max-width: 767px) {
  .page-container,
  .navbar-container {
    width: 720px;
    max-width: 720px;
  }

  /* Text */
  .nm-text {
    font-size: 1.75em;
  }

  /* .sm-text {
    font-size: 1.5em;
  } */

  /* .p-text {
    font-size: 1.25em;
  } */

  .bg-text {
    font-size: 5.5em;
  }

  .header {
    font-size: 3.75em;
  }

  .title {
    font-size: 3.5em;
  }

  .bracket {
    font-size: 2.75em;
  }
}

@media screen and (max-width: 680px) {
  .blue-btn,
  .l-blue-btn {
    padding: 5px 40px;
  }
}

@media screen and (max-width: 414px) {
  .page-container,
  .navbar-container {
    width: 374px;
    max-width: 374px;
  }

  .swiper-pagination-bullet {
    margin: 0px 4px !important;
  }

  .vueperslide {
    background-size: 270px !important;
  }

  .vueperslides--fixed-height {
    height: 270px !important;
  }

  .header {
    text-align: center;
  }

  .blue-btn,
  .l-blue-btn {
    width: 100%;
    text-align: center;
    margin-right: 0px;
  }

  /* Text */
  .nm-text {
    font-size: 1.5em;
  }

  /* .sm-text {
    font-size: 1.5em;
  } */

  /* .p-text {
    font-size: 1.25em;
  } */

  .bg-text {
    font-size: 5.25em;
  }

  .header {
    font-size: 3.25em;
  }

  .title {
    font-size: 3em;
  }

  .bracket {
    font-size: 2.5em;
  }
}
@media screen and (max-width: 375px) {
  .page-container,
  .navbar-container {
    width: 355px;
    max-width: 355px;
  }

  .vueperslide {
    background-size: 240px !important;
  }
}
@media screen and (max-width: 360px) {
  .page-container,
  .navbar-container {
    width: 335px;
    max-width: 335px;
  }
}
</style>
