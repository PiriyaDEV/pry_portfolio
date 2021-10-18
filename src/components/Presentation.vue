<template>
  <div id="presentation" class="section">
    <div id="ps-container" class="page-container">
      <h1 class="header">PROJECT PRESENTATION</h1>

      <div id="video-section">
        <div>
          <iframe
            src="https://www.youtube.com/embed/YE_ZMvekCIU?rel=0"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
        <div>
          <iframe
            src="https://www.youtube.com/embed/NFnu3ilvuHs?rel=0"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
#ps-container {
  margin-top: 80px;
}

#video-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

iframe {
  box-shadow: rgba(0, 0, 0, 0.1) 0px 0px 5px 0px,
    rgba(0, 0, 0, 0.1) 0px 0px 1px 0px;
  width: 460px;
  height: 265px;
}
</style>
