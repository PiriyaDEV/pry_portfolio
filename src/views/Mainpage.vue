<template>
  <div id="mainpage">
    <Information />
    <WorkProject />
  </div>
</template>

<script>
import Information from "../components/Information.vue";
import WorkProject from "../components/WorkProject.vue";
export default {
  components: {
    Information,
    WorkProject,
  },
};
</script>

<style scoped></style>
