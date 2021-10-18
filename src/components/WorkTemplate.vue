<template>
  <div id="work-template">
    <img class="yl-bullet" src="../assets/Ellipse_32x.png" alt />

    <div id="information">
      <h1 class="title">{{ workInfo.name }}</h1>
      <h1 class="bracket">({{ workInfo.bracket }})</h1>

      <div class="skill-cir">
        <div v-for="(skill, i) in workInfo.icon" :key="i">
          <img class="skill-cir-icon" :src="workInfo.icon[i].path" alt />
        </div>
      </div>

      <p class="p-text">{{ workInfo.description }}</p>

      <div v-if="workInfo.links != null">
        <h1 class="p-text" v-for="(link, i) in workInfo.links" :key="i">
          {{ workInfo.links[i].name }} :
          <a class="link-text" :href="workInfo.links[i].path" target="_blank">
            {{ workInfo.links[i].path }}
          </a>
        </h1>
      </div>
    </div>

    <div>
      <vueper-slides
        autoplay
        :arrows="false"
        :touchable="false"
        :fixed-height="true"
      >
        <vueper-slide
          v-for="(slide, i) in workInfo.images"
          :key="i"
          :image="workInfo.images[i].path"
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
  props: ["workInfo"],
  data() {
    return {};
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

.title {
  margin-top: 0px;
  margin-bottom: 0px;
}

.skill-cir {
  display: flex;
  align-items: center;
}

.skill-cir-icon {
  width: 50px;
  border-radius: 50%;
}

.vueperslides {
  margin-top: 20px;
}
</style>
