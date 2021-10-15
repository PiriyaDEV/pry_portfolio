<template>
  <div id="work-project" class="section">
    <div id="wp-container" class="page-container">
      <h1 class="header">WORK EXPERIENCE & PROJECT</h1>

      <div id="tag-section">
        <div :class="allColor" @click="clickFilter(`all`)">
          <h1 class="sm-text">All</h1>
        </div>
        <div :class="webdevColor" @click="clickFilter(`webdev`)">
          <h1 class="sm-text">Website DEV</h1>
        </div>
        <div :class="wordpressColor" @click="clickFilter(`wordpress`)">
          <h1 class="sm-text">Wordpress</h1>
        </div>
        <div :class="chatbotColor" @click="clickFilter(`chatbot`)">
          <h1 class="sm-text">Chatbot</h1>
        </div>
      </div>

      <swiper class="swiper" :options="swiperOption">
        <swiper-slide v-for="(work, i) in worksDisplay" :key="i">
          <div id="work-section" v-for="item in work" :key="item.name">
            <WorkTemplate class="work-template" :workInfo="item" />
          </div>
        </swiper-slide>
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
  computed: {
    allColor() {
      return this.clickType == "all" ? "blue-btn" : "l-blue-btn";
    },
    webdevColor() {
      return this.clickType == "webdev" ? "blue-btn" : "l-blue-btn";
    },
    wordpressColor() {
      return this.clickType == "wordpress" ? "blue-btn" : "l-blue-btn";
    },
    chatbotColor() {
      return this.clickType == "chatbot" ? "blue-btn" : "l-blue-btn";
    },
    worksDisplay: function () {
      let workList = this.works;
      let worksDisplay = [];
      let block = [];

      // all , webdev , chatbot , wordpress
      if (this.clickType != "all") {
        workList = workList.filter((work) => work.type == this.clickType);
      }

      workList.forEach((work) => {
        block.push(work);

        if (block.length == 2) {
          worksDisplay.push(block);
          block = [];
        }
      });

      if (block.length == 1) {
        worksDisplay.push(block);
      }

      return worksDisplay;
    },
  },
  data() {
    return {
      clickType: "all",
      works: [
        {
          name: "AI FOR ALL",
          links: [
            { path: "https://www.aiforall.or.th" },
            { path: "https://www.facebook.com/AIThaiSmartbyAIForAll/" },
          ],
          type: "webdev",
          description:
            "Blog website for project “AI for ALL” giving information, news and knowledge about AI for Thai people. Provided by NXPO and PMU",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/wp.png") },
          ],
        },
        {
          name: "Riche’ Place",
          links: [{ path: "https://richedevelopment.com" }],
          description:
            "Real estate website for “Riche Place” provided by Procon & system company limited",
        },
        {
          name: "Learning Connect",
          links: [{ path: "https://learningconnext.com/" }],
          type: "webdev",
          description:
            "Website for learning center “Learning Connext” learning sources for kids, family and community",
        },
        {
          name: "TMLCC Website",
          links: [
            { path: "https://tmlcc.cseathai.org/" },
            { path: "https://www.facebook.com/AIThaiSmartbyAIForAll/" },
          ],
          type: "webdev",
          description:
            "Vue.js Registration Website for the competitor in Thailand Machine Learning for Chemistry Competition. Users can create teams and follow news, files and videos via their own dashboard. Currently there are 1069 active users in the system",
        },
        {
          name: "Banyen Chatbot",
          links: null,
          type: "chatbot",
          description:
            "Receiving product order and stock management for client by team “Banyen” by Siam Cement Group",
        },
      ],
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
  methods: {
    clickFilter(value) {
      this.clickType = value;
    },
  },
  watch: {},
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
