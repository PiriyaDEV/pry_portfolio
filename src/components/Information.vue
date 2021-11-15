<template>
  <div>
    <div id="navbar-mobile" class="section">
      <div class="navbar-container">
        <a
          href="#work-project"
          v-smooth-scroll="{
            duration: 1000,
            offset: -50,
            updateHistory: false,
          }"
          class="nm-text nav-text"
          >Work & Project</a
        >
        <h1
          href="#skill"
          v-smooth-scroll="{
            duration: 1000,
            offset: 70,
            updateHistory: false,
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
            updateHistory: false,
          }"
          class="nm-text nav-text"
        >
          Contact
        </h1>
      </div>
    </div>
    <div id="information" class="section">
      <div id="information-container" class="page-container">
        <div id="navbar">
          <a
            href="#work-project"
            v-smooth-scroll="{
              duration: 1000,
              offset: 70,
              updateHistory: false,
            }"
            class="nm-text nav-text"
            >Work & Project</a
          >
          <h1
            href="#skill"
            v-smooth-scroll="{
              duration: 1000,
              offset: 70,
              updateHistory: false,
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
              updateHistory: false,
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
            <span class="role-text">WEBSITE DEV.</span> <br />
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

#navbar-mobile {
  display: none;
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

@media screen and (max-width: 1410px) {
  #yellow-circle {
    width: 450px;
    left: -225px;
    bottom: 0px;
    z-index: 1;
  }

  #blue-circle {
    width: 750px;
    right: -200px;
    bottom: 0px;
    z-index: 1;
  }

  #pf-pic {
    width: 335px;
    right: 0px;
    bottom: 0px;
  }

  #information-container {
    padding-bottom: 100px;
  }
}

@media screen and (max-width: 1280px) {
  #yellow-circle {
    width: 350px;
    left: -255px;
    bottom: 0px;
    z-index: 1;
  }

  #blue-circle {
    width: 650px;
    right: -350px;
    bottom: 50px;
    z-index: 1;
  }

  #information-container {
    padding-bottom: 100px;
  }
}

@media screen and (max-width: 820px) {
  #information-container {
    padding-bottom: 100px;
    margin-top: 50px;
  }

  #yellow-circle {
    width: 350px;
    left: -255px;
    bottom: 0px;
    z-index: 1;
  }

  #navbar {
    display: none;
  }

  #navbar-mobile {
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10000;
    position: fixed;
    width: 100%;
    background-color: #ffffff;
    -webkit-box-shadow: 0 0px 5px #e5e3e3;
    -moz-box-shadow: 0 0px 5px #e5e3e3;
    box-shadow: 0 0px 5px #e5e3e3;
    padding: 22px 0px 18px 0px;
  }

  #navbar-mobile > div {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
  }

  .nav-text {
    margin: 0px;
  }

  /* #study-section {
    display: block;
  } */

  .bg-text {
    font-size: 4em;
  }

  .bg-text {
    line-height: 70px;
  }

  #blue-circle {
    width: 550px;
    right: -350px;
    bottom: 0px;
    z-index: 1;
  }

  #pf-pic {
    width: 235px;
    position: absolute;
    right: 0px;
    bottom: 0px;
  }
}

@media screen and (max-width: 650px) {
  #study-section {
    display: block;
  }

  .yellow-btn {
    margin-bottom: 20px;
  }

  .bg-text {
    line-height: 60px;
  }

  #blue-circle {
    width: 450px;
    right: -250px;
    bottom: 0px;
    z-index: 1;
  }

  #yellow-circle {
    width: 250px;
    left: -155px;
    bottom: 0px;
    z-index: 1;
  }
}

@media screen and (max-width: 550px) {
  #information-container {
    padding-bottom: 300px;
  }

  #yellow-circle {
    width: 230px;
    left: -175px;
    bottom: 0px;
    z-index: 1;
  }

  #blue-circle {
    width: 320px;
    right: -250px;
    bottom: 0px;
    z-index: 1;
  }

  #pf-pic {
    width: 205px;
    position: absolute;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
    bottom: 0px;
  }

  .bg-text {
    /* font-size: 3.75em; */
  }
}

@media screen and (max-width: 400px) {
  #yellow-circle {
    width: 200px;
    left: -155px;
    bottom: 0px;
    z-index: 1;
  }

  #blue-circle {
    width: 300px;
    right: -250px;
    bottom: 0px;
    z-index: 1;
  }
}
</style>
