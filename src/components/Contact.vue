<template>
  <div id="contact" class="section">
    <div id="contact-container" class="page-container">
      <h1 class="header">CONTACT ME</h1>

      <div id="contact-box" class="section">
        <div v-for="(contact, i) in contactInfo" :key="i">
          <div>
            <div>
              <img
                @click="clickLink(contactInfo[i].link)"
                class="contact-cir-icon"
                :src="contactInfo[i].path"
                alt
              />
            </div>

            <h1 @click="clickLink(contactInfo[i].link)" class="nm-text">
              {{ contactInfo[i].name }}
            </h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    clickLink(value) {
      window.open(value, "_blank");
    },
  },
  data() {
    return {
      contactInfo: [
        {
          name: "Github",
          path: require("../assets/contact-icon/github.png"),
          link: "https://github.com/PiriyaDEV",
        },
        {
          name: "Email",
          path: require("../assets/contact-icon/mail.png"),
          link: "mailto:pd.piriya@gmail.com",
        },
        {
          name: "Line",
          path: require("../assets/contact-icon/line.png"),
          link: require("../assets/246247063_854548465093564_2198207823457485798_n.jpeg"),
        },
        {
          name: "Facebook",
          path: require("../assets/contact-icon/face.png"),
          link: "https://www.facebook.com/pdpiriya",
        },
      ],
    };
  },
};
</script>

<style scoped>
#contact {
  padding: 20px 0px 0px 0px;
  background-color: #4960ac;
}
.header,
.nm-text {
  color: #ffffff;
}

.contact-cir-icon {
  width: 50px;
  margin: 0px 35px;
}

.nm-text {
  text-align: center;
}

#contact-box {
  margin: 50px 0px 50px 0px;
}

#contact-box > div > div > img,
#contact-box > div > div > h1 {
  cursor: pointer;
}

@media screen and (max-width: 680px) {
  #contact-box {
    display: block;
    margin: 30px 0px;
  }

  .contact-cir-icon {
    width: 40px;
    margin: 0px 30px 0px 35px;
  }

  #contact-box > div > div {
    display: flex;
  }

  .nm-text {
    margin-top: 10px;
  }

  #contact-box > div {
    margin-bottom: 20px;
  }

  #contact {
    padding: 40px 0px 30px 0px;
    background-color: #4960ac;
  }
}
</style>
