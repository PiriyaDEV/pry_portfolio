<template>
  <div id="skill" class="section">
    <div id="skill-container" class="page-container">
      <h1 class="header">SKILL SUMMARY</h1>

      <div id="skill-box" v-for="(skill, i) in skillInfo" :key="i">
        <div>
          <img class="yl-bullet" src="../assets/Ellipse_32x.png" alt />
        </div>

        <div>
          <h1 class="title">{{ skillInfo[i].name }}</h1>
        </div>

        <div v-for="(skill, i) in skillInfo[i].icon" :key="i">
          <img class="skill-cir-icon" :src="skill.path" alt />
        </div>
      </div>
    </div>
    <img id="blue-circle-2" src="../assets/Ellipse_132x.png" />
    <img id="yellow-circle-2" src="../assets/Subtraction_22x.png" />
    <img id="pf-art" src="../assets/piriya-vector-small.png" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      skillInfo: [
        {
          name: "SKILL NAME",
          icon: [
            { path: require("../assets/skill-icon/c.png") },
            { path: require("../assets/skill-icon/pyt.png") },
            { path: require("../assets/skill-icon/r.png") },
            { path: require("../assets/skill-icon/df.png") },
            { path: require("../assets/skill-icon/html-2.png") },
            { path: require("../assets/skill-icon/js-2.png") },
            { path: require("../assets/skill-icon/css-2.png") },
          ],
        },
        {
          name: "WEBSITE DEVELOPMENT",
          icon: [
            { path: require("../assets/skill-icon/vue.png") },
            { path: require("../assets/skill-icon/react.png") },
            { path: require("../assets/skill-icon/njs.png") },
            { path: require("../assets/skill-icon/sql.png") },
            { path: require("../assets/skill-icon/fb-2.png") },
          ],
        },
        {
          name: "CMS WITH WEBSITE",
          icon: [
            { path: require("../assets/skill-icon/wp.png") },
            { path: require("../assets/skill-icon/elem.png") },
          ],
        },
        {
          name: "USER INTERFACE & DESIGN",
          icon: [
            { path: require("../assets/skill-icon/figma.png") },
            { path: require("../assets/skill-icon/xd.png") },
            { path: require("../assets/skill-icon/ps.png") },
            { path: require("../assets/skill-icon/pr.png") },
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
#skill {
  position: relative;
}

#skill-container {
  margin-top: 40px;
  z-index: 2;
  padding-top: 100px;
  margin-bottom: 80px;
}

#blue-circle-2 {
  width: 240px;
  position: absolute;
  left: -130px;
  top: -50px;
  z-index: 1;
}

#yellow-circle-2 {
  width: 600px;
  position: absolute;
  right: -150px;
  bottom: 0px;
  z-index: 1;
}

#skill-box {
  display: flex;
  align-items: center;
  margin-top: 20px;
  margin-bottom: 60px;
}

.skill-cir-icon {
  margin: 0px 10px;
  width: 50px;
  border-radius: 50%;
}

.title {
  margin: 0px 20px 0px 0px;
}

.yl-bullet {
  margin-right: 20px;
}

#pf-art {
  width: 500px;
  position: absolute;
  right: -50px;
  bottom: -60px;
  z-index: 1;
}

@media screen and (max-width: 1410px) {
  #pf-art {
    width: 400px;
    right: -50px;
    bottom: -60px;
  }

  #blue-circle-2 {
    width: 140px;
    left: -80px;
    top: -50px;
  }

  #yellow-circle-2 {
    width: 500px;
    right: -150px;
    bottom: 0px;
  }
}

@media screen and (max-width: 1280px) {
  #yellow-circle-2 {
    width: 400px;
    right: -160px;
    bottom: 0px;
  }

  #blue-circle-2 {
    width: 140px;
    left: -80px;
    top: -20px;
  }

  #pf-art {
    width: 300px;
    right: -50px;
    bottom: -60px;
  }
}
</style>
