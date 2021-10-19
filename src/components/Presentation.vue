<template>
  <div id="presentation" class="section">
    <div id="ps-container" class="page-container">
      <h1 class="header">PROJECT PRESENTATION</h1>

      <div id="video-container">
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

#video-container {
  margin-top: 30px;
}

iframe {
  box-shadow: rgba(0, 0, 0, 0.1) 0px 0px 5px 0px,
    rgba(0, 0, 0, 0.1) 0px 0px 1px 0px;
  width: 600px;
  height: 365px;
}

@media screen and (max-width: 1440px) {
  iframe {
    width: 460px;
    height: 265px;
  }
}

@media screen and (max-width: 980px) {
  iframe {
    width: 430px;
    height: 235px;
  }
}

@media screen and (max-width: 940px) {
  #video-section {
    display: block;
  }

  #video-section > div:nth-child(1) {
    margin-bottom: 30px;
  }

  iframe {
    width: 630px;
    height: 305px;
  }

  #video-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}

@media screen and (max-width: 820px) {
  #ps-container {
    margin-top: 30px;
  }
}

@media screen and (max-width: 768px) {
  iframe {
    width: 100%;
    height: 305px;
  }

  #video-container {
    display: inherit;
  }
}

@media screen and (max-width: 414px) {
  iframe {
    height: 245px;
  }
}
</style>
