<template>
  <div id="certificate" class="section">
    <div id="cert-container" class="page-container">
      <h1 class="header">CERTIFICATE</h1>

      <div id="cert-box">
        <swiper class="swiper" :options="swiperOption">
          <swiper-slide v-for="(cert, i) in certPic" :key="i">
            <div class="section">
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
        slidesPerView: 1,
        spaceBetween: 20,
        breakpoints: {
          980: {
            slidesPerView: 3,
            spaceBetween: 30,
          },
          500: {
            slidesPerView: 2,
            spaceBetween: 20,
          },
        },
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
  width: 330px;
  margin: 10px 0px 80px 0px;
}

#cert-box {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-wrap: wrap;
}

@media screen and (max-width: 1650px) {
  .cert-img {
    width: 300px;
  }
}
@media screen and (max-width: 1280px) {
  .cert-img {
    width: 200px;
  }

  #cert-container {
    overflow: hidden;
  }
}

@media screen and (max-width: 500px) {
  .cert-img {
    width: 300px;
  }

  .swiper-pagination-bullet {
    width: 5px !important;
    height: 5px !important;
  }
}
</style>
