<template>
  <div id="work-template">
    <img class="yl-bullet yl-pc" src="../assets/Ellipse_32x.png" alt />

    <div id="information">
      <div id="title-header">
        <img class="yl-res yl-bullet" src="../assets/Ellipse_32x.png" alt />
        <h1 class="title">{{ workInfo.name }}</h1>
        <i v-if="workInfo.works == `work`" class="fa fa-briefcase"></i>
        <i v-else class="fa fa-book"></i>
      </div>

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

.yl-res {
  display: none;
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

#title-header {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.fa {
  font-size: 3em;
  margin-left: 15px;
  color: #737373;
  margin-top: 3px;
}

@media screen and (max-width: 1280px) {
  .yl-pc {
    display: none;
  }

  .skill-cir-icon {
    width: 40px;
  }

  .yl-res {
    display: initial;
    margin-top: 0px;
    margin-right: 15px;
    width: 30px;
  }
}

@media screen and (max-width: 680px) {
  .yl-res {
    width: 20px;
  }

  .skill-cir-icon {
    width: 30px;
  }
}

@media screen and (max-width: 414px) {
  .bracket {
    margin: 15px 0px;
  }

  .p-text {
    margin: 20px 0px;
  }
}
</style>
