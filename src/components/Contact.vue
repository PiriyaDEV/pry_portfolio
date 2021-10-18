<template>
  <div id="contact" class="section">
    <div id="contact-container" class="page-container">
      <h1 class="header">CONTACT ME</h1>

      <div id="contact-box" class="section">
        <div v-for="(contact, i) in contactInfo" :key="i">
          <div>
            <img class="contact-cir-icon" :src="contactInfo[i].path" alt />
            <h1 class="nm-text">{{contactInfo[i].name}}</h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contactInfo: [
        {
          name: "Github",
          path: require("../assets/contact-icon/github.png"),
        },
        {
          name: "Email",
          path: require("../assets/contact-icon/mail.png"),
        },
        {
          name: "Line",
          path: require("../assets/contact-icon/line.png"),
        },
        {
          name: "Facebook",
          path: require("../assets/contact-icon/face.png"),
        }
      ]
    };
  },
};
</script>

<style scoped>
#contact {
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
  margin: 80px 0px 100px 0px;
}
</style>
