<template>
  <div id="work-project" class="section">
    <div id="wp-container" class="page-container">
      <h1 class="header">WORK EXPERIENCE & PROJECT</h1>

      <div id="tag-section">
        <div class="blue-btn">
          <h1 class="sm-text">All</h1>
        </div>
        <div class="l-blue-btn">
          <h1 class="sm-text">Website DEV</h1>
        </div>
        <div class="l-blue-btn">
          <h1 class="sm-text">Wordpress</h1>
        </div>
        <div class="l-blue-btn">
          <h1 class="sm-text">Chatbot</h1>
        </div>
      </div>

      <swiper class="swiper" :options="swiperOption">
        <swiper-slide
          ><div id="work-section">
            <WorkTemplate class="work-template" />
            <WorkTemplate class="work-template" /></div
        ></swiper-slide>
        <swiper-slide
          ><div id="work-section">
            <WorkTemplate class="work-template" />
            <WorkTemplate class="work-template" /></div
        ></swiper-slide>
        <swiper-slide
          ><div id="work-section">
            <WorkTemplate class="work-template" />
            <WorkTemplate class="work-template" /></div
        ></swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
import WorkTemplate from "../components/WorkTemplate.vue";
export default {
  components: {
    WorkTemplate,
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: 1,
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
    };
  },
};
</script>

<style scoped>
#work-project {
}

.work-template {
  margin-bottom: 50px;
}

#wp-container {
  margin-top: 80px;
}

#tag-section {
  display: flex;
  align-items: center;
}

.blue-btn,
.l-blue-btn {
  margin-right: 30px;
}

#work-section {
  margin: 50px 0px;
}
</style>
