<template>
  <div id="certificate" class="section">
    <div id="cert-container" class="page-container">
      <h1 class="header">CERTIFICATE</h1>

      <div id="cert-box">
        <div v-for="(cert, i) in certPic" :key="i">
          <a :href="certPic[i].path" target="_blank">
            <img :src="certPic[i].path" alt />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            certPic: [
            { path: require("../assets/Certificate/Coursera - SQL-1.png") },
            { path: require("../assets/Certificate/Piriya Chaigul - Python.png") },
            { path: require("../assets/Certificate/Datacamp - Data Manipulation with dplyr-1.png") },
            { path: require("../assets/Certificate/Datacamp - Intermediate Data ggplot2-1.png") },
            { path: require("../assets/Certificate/Datacamp - Intermediate SQL-1.png") },
            { path: require("../assets/Certificate/Datacamp - Introduce SQL-1.png") },
            { path: require("../assets/Certificate/Datacamp - Introduce to R-1.png") },
            { path: require("../assets/Certificate/Datacamp - Introduction ggplot2-1.png") },
            { path: require("../assets/Certificate/Datacamp - Joining Data SQL-1.png") },
            { path: require("../assets/Certificate/Datacamp - Reshaping Data tidyr-1.png") },
            { path: require("../assets/Certificate/Datacamp - R-track-1.png") },
            { path: require("../assets/Certificate/Datacamp - Visualization R-1.png") },
          ],
        }
    },
}
</script>

<style scoped>
#cert-container {
  margin-top: 80px;
}

#cert-box > div > a > img {
  width: 300px;
  margin: 10px 25px 10px 0px;
}

#cert-box {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-wrap: wrap;
}
</style>