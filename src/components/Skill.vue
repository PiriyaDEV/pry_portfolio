<template>
  <div id="skill" class="section">
    <div id="skill-container" class="page-container">
      <h1 class="header">SKILL SUMMARY</h1>

      <div id="skill-box" v-for="(skill, i) in skillList" :key="i">
        <div>
          <img class="yl-bullet" src="../assets/Ellipse_32x.png" alt="" />
        </div>

        <div>
          <h1 class="title">USER INTERFACE & DESIGN</h1>
        </div>

        <div v-for="(skill, i) in skillIcon" :key="i">
          <img class="skill-cir-icon" src="../assets/mockup-cir.png" alt="" />
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
      skillList: 4,
      skillIcon: 4,
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
  width: 260px;
  position: absolute;
  left: -100px;
  top: 0px;
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
</style>
