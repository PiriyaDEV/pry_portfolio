<template>
  <div id="information" class="section">
    <div id="information-container" class="page-container">
      <div id="navbar">
        <a
          href="#work-project"
          v-smooth-scroll="{
            duration: 1000,
            offset: 70,
            updateHistory: true,
          }"
          class="nm-text nav-text"
          >Work & Project</a
        >
        <h1
          href="#skill"
          v-smooth-scroll="{
            duration: 1000,
            offset: 70,
            updateHistory: true,
          }"
          class="nm-text nav-text"
        >
          Skill
        </h1>
        <h1
          href="#contact"
          v-smooth-scroll="{
            duration: 1000,
            offset: 70,
            updateHistory: true,
          }"
          class="nm-text nav-text"
        >
          Contact
        </h1>
      </div>

      <div id="name-section">
        <p class="bg-text">
          HELLO, <br />
          I'm <span class="name-text">Piriya Chaigul</span> <br />
          <span class="role-text">FRONTEND DEV.</span> <br />
        </p>
      </div>

      <div id="study-section">
        <div class="yellow-btn">
          <h1 class="nm-text">NOW...</h1>
        </div>
        <div>
          <h1 class="nm-text">STUDY @ COMPUTER ENGINEERING KMUTT</h1>
        </div>
      </div>

      <img id="pf-pic" src="../assets/pd-pic.png" alt="" />
    </div>
    <img id="yellow-circle" src="../assets/Subtraction_12x.png" />
    <img id="blue-circle" src="../assets/Ellipse_12x.png" />
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
#information {
  position: relative;
}

#information-container {
  z-index: 2;
  position: relative;
  padding-bottom: 200px;
}

#navbar {
  margin-top: 30px;
  display: flex;
  align-items: center;
}

.nav-text {
  margin-right: 90px;
  cursor: pointer;
  text-decoration: none;
  color: #1a1a1a;
}

.name-text {
  font-weight: 400;
}

.role-text {
  font-weight: 500;
}

.bg-text {
  line-height: 90px;
}

#study-section {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.yellow-btn {
  margin-right: 25px;
}

#yellow-circle {
  width: 550px;
  position: absolute;
  left: -225px;
  bottom: 0px;
  z-index: 1;
}

#blue-circle {
  width: 850px;
  position: absolute;
  right: -200px;
  bottom: 0px;
  z-index: 1;
}

#pf-pic {
  width: 435px;
  position: absolute;
  right: 0px;
  bottom: 0px;
}
</style>
