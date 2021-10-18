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
          bracket: "Mhesi/Nxpo",
          links: [
            { name: "Facebook", path: "https://www.aiforall.or.th" },
            {
              name: "Website",
              path: "https://www.facebook.com/AIThaiSmartbyAIForAll",
            },
          ],
          type: "wordpress",
          description:
            "Blog website for project “AI for ALL” giving information, news and knowledge about AI for Thai people. Provided by NXPO and PMU",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.46 2.png"),
            },
            {
              path: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.46 3.png"),
            },
            {
              path: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.48 1.png"),
            },
            {
              path: require("../assets/work/ai/Screen Shot 2564-04-05 at 23.49 1.png"),
            },
          ],
        },
        {
          name: "Riche’ Place",
          bracket: "Riche Development",
          links: [
            {
              name: "Website",
              path: "https://richedevelopment.com",
            },
          ],
          type: "wordpress",
          description:
            "Real estate website for “Riche Place” provided by Procon & system company limited",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/richeplace/Screen Shot 2564-04-05 at 23.52 1.png"),
            },
            {
              path: require("../assets/work/richeplace/Screen Shot 2564-04-05 at 23.52 3.png"),
            },
            {
              path: require("../assets/work/richeplace/Screen Shot 2564-04-05 at 23.53 1.png"),
            },
            {
              path: require("../assets/work/richeplace/Screen Shot 2564-04-05 at 23.53 3.png"),
            },
          ],
        },
        {
          name: "Learning Connect",
          bracket: "Connextion",
          links: [
            {
              name: "Website",
              path: "https://learningconnext.com/",
            },
          ],
          type: "wordpress",
          description:
            "Real estate Website for learning center “Learning Connext” learning sources for kids, family and community",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.57 1.png"),
            },
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.57 2.png"),
            },
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.58 1.png"),
            },
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.59 1.png"),
            },
          ],
        },
        {
          name: "TMLCC Website",
          bracket: "Thailand Machine Learning for Chemistry Competition",
          links: [
            {
              name: "Website",
              path: "https://tmlcc.cseathai.org/",
            },
          ],
          type: "webdev",
          description:
            "Vue.js Registration Website for the competitor in Thailand Machine Learning for Chemistry Competition. Users can create teams and follow news, files and videos via their own dashboard. Currently there are 1069 active users in the system",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.57 1.png"),
            },
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.57 2.png"),
            },
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.58 1.png"),
            },
            {
              path: require("../assets/work/Learning Connext/Screen Shot 2564-04-05 at 23.59 1.png"),
            },
          ],
        },
        {
          name: "Banyen Chatbot",
          bracket: "Banyen SCG’s Team",
          // links: [
          //   {
          //     name: "Website",
          //     path: "https://tmlcc.cseathai.org/",
          //   },
          // ],
          type: "chatbot",
          description:
            "Receiving product order and stock management for client by team “Banyen” by Siam Cement Group",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/Banyen Chatbot (SCG)/Screenshot_20200330_234401_jp.naver.line.png"),
            },
            {
              path: require("../assets/work/Banyen Chatbot (SCG)/Screenshot_20200330_234419_jp.naver.line.png"),
            },
            {
              path: require("../assets/work/Banyen Chatbot (SCG)/Screenshot_20200330_234508_jp.naver.line.png"),
            },
            {
              path: require("../assets/work/Banyen Chatbot (SCG)/Screenshot_20200330_234522_jp.naver.line.png"),
            },
          ],
        },
        {
          name: "CC CPE BOT",
          bracket: "Computer Exploration Project",
          // links: [
          //   {
          //     name: "Website",
          //     path: "https://tmlcc.cseathai.org/",
          //   },
          // ],
          type: "chatbot",
          description:
            "Gives information about Department of Computer Engineering Receiving the top score on a final project for course Computer Exploration",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
          ],
        },
        {
          name: "CPE Night 2021",
          bracket: "Vue.js Website",
          links: [
            {
              name: "Github",
              path: "https://github.com/PiriyaDEV/cpe-night-website",
            },
            {
              name: "Website (Only Frontend)",
              path: "https://cpenight-demo.netlify.app/ ",
            },
          ],
          type: "webdev",
          description:
            "Website One-page of the event CPE night 2021. Using for promote the event, gives the information of the event and user account function for buying the gifts and tickets (Event Cancelled during COVID-19 situation)",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
          ],
        },
        {
          name: "Friendzone",
          bracket: "Computer Exploration Project",
          links: [
            {
              name: "Github",
              path: "https://github.com/PiriyaDEV/friendzone_app",
            },
            {
              name: "Website (Only Frontend)",
              path: "https://friendzone-app.netlify.app/",
            },
          ],
          type: "webdev",
          description:
            "This project will gather people that have the same interest and meet up. We virtualize the real system and experiences for this project. Which consists of creating a meetup event room, rating event, chat system and more. Users are able to redeem their points in exchange for their discount with our partners. Including a function that will analyse data for a role “analyzer” for business and marketing opportunities.",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
          ],
        },
        {
          name: "Blood Donation Website",
          bracket: "MAN AND ETHICS OF LIVING Project",
          links: [
            {
              name: "Github",
              path: "https://github.com/PiriyaDEV/blood_donation",
            },
            {
              name: "Website",
              path: "https://cpe2-blooddonation.netlify.app/",
            },
          ],
          type: "webdev",
          description:
            "This project is called 'Blood donation campaign during COVID-19 for people who want to donate'. The website includes a video about how to prepare before blood donation. The knowledge about COVID-19 impact on blood supply, the suggestion when you receive the COVID-19 vaccine, and the criteria for who can donate blood. Also, there is the question to check about COVID-19 symptoms and the suggestion when you have COVID-19 symptoms to make donating as safe as possible.",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
            {
              path: require("../assets/work/CC CPE Chatbot/74389094_103253587814504_8015177829316558848_n.png"),
            },
          ],
        },
      ],
      swiperOption: {
        slidesPerView: 1,
        spaceBetween: 30,
        // autoplay: {
        //   delay: 4000,
        //   disableOnInteraction: true,
        // },
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
