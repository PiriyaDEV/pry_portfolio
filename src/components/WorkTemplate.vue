<template>
  <div id="work-template">
    <img id="yl-bullet" src="../assets/Ellipse_32x.png" alt="" />

    <div id="information">
      <h1 class="title">TITLE</h1>

      <div class="skill-cir">
        <div v-for="(skill, i) in skillList" :key="i">
          <img src="../assets/mockup-cir.png" alt="" />
        </div>
      </div>

      <p class="p-text">
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s, when an unknown printer took a galley of type and
        scrambled it to make a type specimen book. It has survived not only five
        centuries, but also the leap into electronic typesetting, remaining
        essentially unchanged. It was popularised in the 1960s with the release
        of Letraset sheets containing Lorem Ipsum passages, and more recently
        with desktop publishing software like Aldus PageMaker including versions
        of Lorem Ipsum.
      </p>
    </div>

    <div>
      <vueper-slides
        autoplay
        :arrows="false"
        :touchable="false"
        :fixed-height="true"
      >
        <vueper-slide
          v-for="(slide, i) in slides"
          :key="i"
          :image="slide.image"
        />
      </vueper-slides>
    </div>
  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from "vueperslides";
import "vueperslides/dist/vueperslides.css";
export default {
  components: {
    VueperSlides,
    VueperSlide,
  },
  data() {
    return {
      skillList: 4,
      slides: [
        {
          image: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.46 2.png"),
        },
        {
          image: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.46 3.png"),
        },
        {
          image: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.48 1.png"),
        },
        {
          image: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.49 1.png"),
        },
      ],
    };
  },
};
</script>

<style scoped>
#work-template {
  display: grid;
  grid-template-columns: 0.2fr 4.5fr 3fr;
  grid-gap: 25px;
  grid-auto-rows: auto;
  align-items: flex-start;
}

#yl-bullet {
  margin-top: 7px;
}

.title {
  margin-top: 0px;
}

.skill-cir {
  display: flex;
  align-items: center;
}

.skill-cir > div > img {
  width: 50px;
  margin-right: 20px;
}

.vueperslides {
  margin-top: 20px;
}
</style>
