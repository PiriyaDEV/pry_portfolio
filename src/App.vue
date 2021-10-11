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
export default {};
</script>

<style>
@import url("https://use.typekit.net/zqk6rjr.css");
@import url("https://fonts.googleapis.com/css2?family=Mitr:wght@300;400;500&display=swap");

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
  background-size: 300px !important;
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
}
@media screen and (max-width: 1440px) {
  .page-container,
  .navbar-container {
    width: 1024px;
    max-width: 1024px;
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
}
@media screen and (max-width: 600px) {
}
@media screen and (max-width: 414px) {
  .page-container,
  .navbar-container {
    width: 374px;
    max-width: 374px;
  }
}
@media screen and (max-width: 375px) {
  .page-container,
  .navbar-container {
    width: 355px;
    max-width: 355px;
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
