<template>
  <div id="contact" class="section">
    <div id="contact-container" class="page-container">
      <h1 class="header">CONTACT ME</h1>

      <div id="contact-box" class="section">
        <div v-for="(contact, i) in contactList" :key="i">
          <div>
            <img
              class="contact-cir-icon"
              src="../assets/mockup-cir.png"
              alt=""
            />
            <h1 class="nm-text">LINE</h1>
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
      contactList: 6,
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
