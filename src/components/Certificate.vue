<template>
  <div id="certificate" class="section">
    <div id="cert-container" class="page-container">
      <h1 class="header">CERTIFICATE</h1>

      <div id="cert-box">
        <swiper class="swiper" :options="swiperOption">
          <swiper-slide v-for="(cert, i) in certPic" :key="i">
            <div>
              <a :href="certPic[i].path" target="_blank">
                <img class="cert-img" :src="certPic[i].path" alt />
              </a>
            </div>
          </swiper-slide>
          <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
      </div>
    </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 30,
        autoplay: {
          delay: 4000,
          disableOnInteraction: true,
        },
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
      },
      certPic: [
        { path: require("../assets/Certificate/Coursera - SQL-1.png") },
        { path: require("../assets/Certificate/Piriya Chaigul - Python.png") },
        {
          path: require("../assets/Certificate/Datacamp - Data Manipulation with dplyr-1.png"),
        },
        {
          path: require("../assets/Certificate/Datacamp - Intermediate Data ggplot2-1.png"),
        },
        {
          path: require("../assets/Certificate/Datacamp - Intermediate SQL-1.png"),
        },
        {
          path: require("../assets/Certificate/Datacamp - Introduce SQL-1.png"),
        },
        {
          path: require("../assets/Certificate/Datacamp - Introduce to R-1.png"),
        },
        {
          path: require("../assets/Certificate/Datacamp - Introduction ggplot2-1.png"),
        },
        {
          path: require("../assets/Certificate/Datacamp - Joining Data SQL-1.png"),
        },
        {
          path: require("../assets/Certificate/Datacamp - Reshaping Data tidyr-1.png"),
        },
        { path: require("../assets/Certificate/Datacamp - R-track-1.png") },
        {
          path: require("../assets/Certificate/Datacamp - Visualization R-1.png"),
        },
      ],
    };
  },
};
</script>

<style scoped>
#cert-container {
  margin-top: 80px;
}

.cert-img {
  width: 300px;
  margin: 10px 0px 80px 0px;
}

#cert-box {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-wrap: wrap;
}
</style>
