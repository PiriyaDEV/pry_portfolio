<template>
  <div id="work-project" class="section">
    <div id="wp-container" class="page-container">
      <div id="work-header">
        <h1 class="header">WORK EXPERIENCE & PROJECT</h1>
        <div class="section">
          <div id="work-icon" class="section">
            <i class="fa fa-briefcase"></i>
            <h1 class="sm-text">WORK</h1>
          </div>
          <div id="pj-icon" class="section">
            <i class="fa fa-book"></i>
            <h1 class="sm-text">PROJECT</h1>
          </div>
        </div>
      </div>

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
          name: "Asia Pacific Symposium on Safety​ 2023",
          works: "work",
          type: "webdev",
          description:
            "APSS 2023 website, developed using react.js and strapi as CMS, is a platform for researchers and engineers in industrial safety, occupational health, and environmental protection to present their research, discuss related topics, and foster professional relationships.",
          icon: [
            { path: require("@/assets/skill-icon/react.png") },
            { path: require("@/assets/skill-icon/strapi.jpeg") },
            { path: require("@/assets/skill-icon/tailwind.png") },
          ],
          images: [
            {
              path: require("../assets/work/2023/che/pic-1.png"),
            },
            {
              path: require("../assets/work/2023/che/pic-2.png"),
            },
            {
              path: require("../assets/work/2023/che/pic-3.png"),
            },
            {
              path: require("../assets/work/2023/che/pic-4.png"),
            },
            {
              path: require("../assets/work/2023/che/pic-5.png"),
            },
          ],
        },
        {
          name: "KMUTT Health Care Unit Website",
          works: "work",
          type: "webdev",
          description:
            "The KMUTT Health Care Unit website has been developed using React.js with Strapi as the CMS. As a dedicated platform for the university's Health Care Unit, the website showcases all of the services, news, and activities of the unit, providing students and faculty members with a comprehensive and easily accessible resource.",
          icon: [
            { path: require("@/assets/skill-icon/react.png") },
            { path: require("@/assets/skill-icon/strapi.jpeg") },
            { path: require("@/assets/skill-icon/tailwind.png") },
          ],
          images: [
            {
              path: require("../assets/work/2023/hcu/pic-1.png"),
            },
            {
              path: require("../assets/work/2023/hcu/pic-2.png"),
            },
            {
              path: require("../assets/work/2023/hcu/pic-3.png"),
            },
            {
              path: require("../assets/work/2023/hcu/pic-4.png"),
            },
            {
              path: require("../assets/work/2023/hcu/pic-5.png"),
            },
          ],
        },
        {
          name: "Nursing Association of Thailand Eastern Website",
          works: "work",
          type: "webdev",
          description:
            "The Nursing Association of Thailand Eastern Branch's website has been created using the latest web technologies such as React.js with Strapi as the CMS. This website is dedicated to providing information about the services, news, and work of the association, serving as a comprehensive and easily accessible resource for its members and the public.",
          icon: [
            { path: require("@/assets/skill-icon/react.png") },
            { path: require("@/assets/skill-icon/strapi.jpeg") },
            { path: require("@/assets/skill-icon/tailwind.png") },
          ],
          images: [
            {
              path: require("../assets/work/2023/eastnurse/pic-1.png"),
            },
            {
              path: require("../assets/work/2023/eastnurse/pic-2.png"),
            },
            {
              path: require("../assets/work/2023/eastnurse/pic-3.png"),
            },
            {
              path: require("../assets/work/2023/eastnurse/pic-4.png"),
            },
            {
              path: require("../assets/work/2023/eastnurse/pic-5.png"),
            },
          ],
        },
        {
          name: "Quantum Experience Website",
          works: "work",
          type: "webdev",
          description:
            "The Quantum Experience website has been developed using React.js with Strapi as the CMS. QX is a research unit under the Faculty of Science, King Mongkut's University of Technology Thonburi, which was formed by physicists and computer engineers who aim to understand the fundamental nature of quantum information and quantum computing through the integration of other technologies such as machine learning and high-performance computing. The objective is to transfer knowledge and develop human resources to prepare Thailand for the arrival of quantum technology.",
          icon: [
            { path: require("@/assets/skill-icon/react.png") },
            { path: require("@/assets/skill-icon/strapi.jpeg") },
            { path: require("@/assets/skill-icon/tailwind.png") },
          ],
          links: [
            {
              name: "Facebook",
              path: "https://www.facebook.com/qxkmutt/",
            },
            {
              name: "Website",
              path: "https://qx.kmutt.ac.th/",
            },
          ],
          images: [
            {
              path: require("../assets/work/2023/qx/pic-1.png"),
            },
            {
              path: require("../assets/work/2023/qx/pic-2.png"),
            },
            {
              path: require("../assets/work/2023/qx/pic-3.png"),
            },
            {
              path: require("../assets/work/2023/qx/pic-4.png"),
            },
            {
              path: require("../assets/work/2023/qx/pic-5.png"),
            },
          ],
        },
        {
          name: "SOFA HOUSE Music Website",
          works: "work",
          type: "webdev",
          description:
            "The SOFA HOUSE Music website has been developed using React.js and SQL to create a database. This website serves as a portfolio for the SOFA HOUSE music team, showcasing all of the music that the team has produced and providing users with an immersive and engaging listening experience.",
          icon: [
            { path: require("@/assets/skill-icon/react.png") },
            { path: require("@/assets/skill-icon/strapi.jpeg") },
            { path: require("@/assets/skill-icon/tailwind.png") },
          ],
          links: [
            {
              name: "Facebook",
              path: "https://www.facebook.com/sofahouse.th",
            },
            {
              name: "Website",
              path: "https://sofahousemusic.com/",
            },
          ],
          images: [
            {
              path: require("../assets/work/2023/sofa/pic-1.png"),
            },
            {
              path: require("../assets/work/2023/sofa/pic-2.png"),
            },
            {
              path: require("../assets/work/2023/sofa/pic-3.png"),
            },
            {
              path: require("../assets/work/2023/sofa/pic-4.png"),
            },
            {
              path: require("../assets/work/2023/sofa/pic-5.png"),
            },
          ],
        },
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
          works: "work",
          type: "wordpress",
          description:
            "Blog website for project “AI for ALL” giving information, news and knowledge about AI for Thai people. Provided by NXPO and PMU",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/ai/Screen Shot 2564-10-18 at 18.01.27.png"),
            },
            {
              path: require("../assets/work/ai/Screen Shot 2564-10-18 at 18.02.25.png"),
            },
            {
              path: require("../assets/work/ai/Screen Shot 2564-10-18 at 18.02.11.png"),
            },
            {
              path: require("../assets/work/ai/Screen Shot 2564-10-18 at 18.02.54.png"),
            },
            {
              path: require("../assets/work/ai/Screen Shot 2564-10-18 at 18.01.59.png"),
            },
          ],
        },
        {
          name: "Hari Hari Ramen",
          bracket: "QR code Ramen Restuarant System",
          links: [
            {
              name: "Github",
              path: "https://github.com/PiriyaDEV/harihari-ramen",
            },
          ],
          works: "project",
          type: "webdev",
          description:
            "React.js project for the ramen restuarant that allow User to order the food by login via QR Code to entered the table. User can order the customise ramen that will change the image according the choice that user select. Also have a system for Staff to managing the system.",
          icon: [
            { path: require("@/assets/skill-icon/react.png") },
            { path: require("@/assets/skill-icon/njs.png") },
            { path: require("@/assets/skill-icon/sql.png") },
          ],
          images: [
            {
              path: require("../assets/work/ramen/Screen Shot 2564-11-15 at 18.15.30.png"),
            },
            {
              path: require("../assets/work/ramen/Screen Shot 2564-11-15 at 18.15.34.png"),
            },
            {
              path: require("../assets/work/ramen/Screen Shot 2564-11-15 at 18.15.39.png"),
            },
            {
              path: require("../assets/work/ramen/Screen Shot 2564-11-15 at 18.15.46.png"),
            },
            {
              path: require("../assets/work/ramen/Screen Shot 2564-11-26 at 07.45.40.png"),
            },
            {
              path: require("../assets/work/ramen/Screen Shot 2564-11-26 at 07.45.10.png"),
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
          works: "project",
          type: "webdev",
          description:
            "This project will gather people that have the same interest and meet up. We virtualize the real system and experiences for this project. Which consists of creating a meetup event room, rating event, chat system and more. Users are able to redeem their points in exchange for their discount with our partners. Including a function that will analyse data for a role “analyzer” for business and marketing opportunities.",
          icon: [
            { path: require("@/assets/skill-icon/vue.png") },
            { path: require("@/assets/skill-icon/njs.png") },
            { path: require("@/assets/skill-icon/sql.png") },
          ],
          images: [
            {
              path: require("../assets/work/fz/Screen Shot 2564-10-18 at 18.13.20.png"),
            },
            {
              path: require("../assets/work/fz/Screen Shot 2564-10-18 at 18.14.38.png"),
            },
            {
              path: require("../assets/work/fz/Screen Shot 2564-10-18 at 18.14.46.png"),
            },
            {
              path: require("../assets/work/fz/Screen Shot 2564-10-18 at 18.14.53.png"),
            },
            {
              path: require("../assets/work/fz/Screen Shot 2564-10-18 at 18.15.08.png"),
            },
            {
              path: require("../assets/work/fz/Screen Shot 2564-10-18 at 18.15.14.png"),
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
          works: "project",
          type: "webdev",
          description:
            "Website One-page of the event CPE night 2021. Using for promote the event, gives the information of the event and user account function for buying the gifts and tickets (Event Cancelled during COVID-19 situation)",
          icon: [
            { path: require("@/assets/skill-icon/vue.png") },
            { path: require("@/assets/skill-icon/njs.png") },
            { path: require("@/assets/skill-icon/sql.png") },
          ],
          images: [
            {
              path: require("../assets/work/cpn/Screen Shot 2564-10-18 at 18.10.51.png"),
            },
            {
              path: require("../assets/work/cpn/Screen Shot 2564-10-18 at 18.11.02.png"),
            },
            {
              path: require("../assets/work/cpn/Screen Shot 2564-10-18 at 18.11.08.png"),
            },
            {
              path: require("../assets/work/cpn/Screen Shot 2564-10-18 at 18.11.14.png"),
            },
            {
              path: require("../assets/work/cpn/Screen Shot 2564-10-18 at 18.11.21.png"),
            },
          ],
        },
        {
          name: "TMLCC Website",
          bracket: "Thailand Machine Learning for Chemistry Competition",
          works: "work",
          type: "webdev",
          description:
            "Vue.js Registration Website for the competitor in Thailand Machine Learning for Chemistry Competition. Users can create teams and follow news, files and videos via their own dashboard. Currently there are 1069 active users in the system",
          icon: [
            { path: require("@/assets/skill-icon/vue.png") },
            { path: require("@/assets/skill-icon/njs.png") },
            { path: require("@/assets/skill-icon/sql.png") },
          ],
          images: [
            {
              path: require("../assets/work/tmlcc/Screen Shot 2564-10-18 at 18.09.18.png"),
            },
            {
              path: require("../assets/work/tmlcc/Screen Shot 2564-10-18 at 18.09.26.png"),
            },
            {
              path: require("../assets/work/tmlcc/Screen Shot 2564-10-18 at 18.09.42.png"),
            },
            {
              path: require("../assets/work/tmlcc/Screen Shot 2564-10-18 at 18.09.49.png"),
            },
            {
              path: require("../assets/work/tmlcc/Screen Shot 2564-10-18 at 18.10.09.png"),
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
          works: "work",
          type: "wordpress",
          description:
            "Real estate website for “Riche Place” provided by Procon & system company limited",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/riche/Screen Shot 2564-10-18 at 18.03.43.png"),
            },
            {
              path: require("../assets/work/riche/Screen Shot 2564-10-18 at 18.04.00.png"),
            },
            {
              path: require("../assets/work/riche/Screen Shot 2564-10-18 at 18.04.09.png"),
            },
            {
              path: require("../assets/work/riche/Screen Shot 2564-10-18 at 18.04.25.png"),
            },
            {
              path: require("../assets/work/riche/Screen Shot 2564-10-18 at 18.04.43.png"),
            },
          ],
        },
        {
          name: "Learning Connext",
          bracket: "Connextion",
          works: "work",
          type: "wordpress",
          description:
            "Real estate Website for learning center “Learning Connext” learning sources for kids, family and community",
          icon: [
            { path: require("@/assets/skill-icon/wp.png") },
            { path: require("@/assets/skill-icon/elem.png") },
          ],
          images: [
            {
              path: require("../assets/work/lc/Screen Shot 2564-04-05 at 23.57 1.png"),
            },
            {
              path: require("../assets/work/lc/Screen Shot 2564-04-05 at 23.57 2.png"),
            },
            {
              path: require("../assets/work/lc/Screen Shot 2564-04-05 at 23.58 1.png"),
            },
            {
              path: require("../assets/work/lc/Screen Shot 2564-04-05 at 23.59 1.png"),
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
          works: "work",
          type: "chatbot",
          description:
            "Receiving product order and stock management for client by team “Banyen” by Siam Cement Group",
          icon: [
            { path: require("@/assets/skill-icon/df.png") },
            { path: require("@/assets/skill-icon/ggs-2.png") },
            { path: require("@/assets/skill-icon/gs-2.png") },
          ],
          images: [
            {
              path: require("../assets/work/by/1.png"),
            },
            {
              path: require("../assets/work/by/2.png"),
            },
            {
              path: require("../assets/work/by/3.png"),
            },
            {
              path: require("../assets/work/by/4.png"),
            },
            {
              path: require("../assets/work/by/5.png"),
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
          works: "project",
          type: "chatbot",
          description:
            "Gives information about Department of Computer Engineering Receiving the top score on a final project for course Computer Exploration",
          icon: [
            { path: require("@/assets/skill-icon/df.png") },
            { path: require("@/assets/skill-icon/fb-2.png") },
            { path: require("@/assets/skill-icon/gs-2.png") },
          ],
          images: [
            {
              path: require("../assets/work/cc/1.png"),
            },
            {
              path: require("../assets/work/cc/2.png"),
            },
            {
              path: require("../assets/work/cc/3.png"),
            },
            {
              path: require("../assets/work/cc/4.png"),
            },
            {
              path: require("../assets/work/cc/5.png"),
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
          works: "project",
          type: "webdev",
          description:
            "This project is called 'Blood donation campaign during COVID-19 for people who want to donate'. The website includes a video about how to prepare before blood donation. The knowledge about COVID-19 impact on blood supply, the suggestion when you receive the COVID-19 vaccine, and the criteria for who can donate blood. Also, there is the question to check about COVID-19 symptoms and the suggestion when you have COVID-19 symptoms to make donating as safe as possible.",
          icon: [
            { path: require("@/assets/skill-icon/vue.png") },
            { path: require("@/assets/skill-icon/fb-2.png") },
          ],
          images: [
            {
              path: require("../assets/work/bd/Screen Shot 2564-10-18 at 18.12.12.png"),
            },
            {
              path: require("../assets/work/bd/Screen Shot 2564-10-18 at 18.12.19.png"),
            },
            {
              path: require("../assets/work/bd/Screen Shot 2564-10-18 at 18.12.22.png"),
            },
            {
              path: require("../assets/work/bd/Screen Shot 2564-10-18 at 18.12.27.png"),
            },
            {
              path: require("../assets/work/bd/Screen Shot 2564-10-18 at 18.12.29.png"),
            },
          ],
        },
        {
          name: "Beauty Life Website",
          bracket: "Website Project about PWD people.",
          links: [
            {
              name: "Github",
              path: "https://github.com/PiriyaDEV/pwd-website",
            },
            {
              name: "Website",
              path: "https://beautylife.netlify.app/",
            },
          ],
          works: "project",
          type: "webdev",
          description:
            "This project will study and give information about the people with disability (PWD). We will develop a website to share information about this group of people. The website includes interview text about PWD’s lives, experience, what PWD wants along, knowledge about PWD, statistical information, rights of PWD, etc.",
          icon: [
            { path: require("@/assets/skill-icon/react.png") },
            { path: require("@/assets/skill-icon/fb-2.png") },
          ],
          images: [
            {
              path: require("../assets/work/beautylife/Screen Shot 2564-11-15 at 17.58.08.png"),
            },
            {
              path: require("../assets/work/beautylife/Screen Shot 2564-11-15 at 17.58.15.png"),
            },
            {
              path: require("../assets/work/beautylife/Screen Shot 2564-11-15 at 17.58.21.png"),
            },
            {
              path: require("../assets/work/beautylife/Screen Shot 2564-11-15 at 17.58.27.png"),
            },
            {
              path: require("../assets/work/beautylife/Screen Shot 2564-11-15 at 17.58.36.png"),
            },
          ],
        },
      ],
      swiperOption: {
        slidesPerView: 1,
        spaceBetween: 30,
        simulateTouch: false,
        autoplay: {
          delay: 10000,
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
#work-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
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

.fa {
  font-size: 3em;
  margin-right: 10px;
  color: #737373;
}

#work-icon {
  margin-right: 25px;
}

/* #work-icon > h1,
#pj-icon > h1 {
  color: #c4c4c4;
} */

@media screen and (max-width: 1280px) {
  #work-template,
  #work-header {
    display: block;
  }

  .header {
    margin-bottom: 5px;
  }

  #work-icon {
    margin-right: 30px;
  }

  #work-header > div {
    justify-content: flex-start;
    margin-bottom: 20px;
  }

  #wp-container {
    overflow: hidden;
  }

  #tag-section {
    flex-wrap: wrap;
  }

  #tag-section > div {
    margin-bottom: 15px;
  }

  #work-section {
    margin: 20px 0px;
  }
}

@media screen and (max-width: 820px) {
  #wp-container {
    margin-top: 30px;
  }
}

@media screen and (max-width: 414px) {
  #work-header > div {
    justify-content: center;
  }

  #tag-section > div {
    margin-bottom: 30px;
    margin-right: 0px;
  }
}
</style>
