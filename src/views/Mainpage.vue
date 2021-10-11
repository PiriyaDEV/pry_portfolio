<template>
  <div id="mainpage">
    <Information />
    <WorkProject />
    <Skill />
    <Contact />
  </div>
</template>

<script>
import Information from "../components/Information.vue";
import WorkProject from "../components/WorkProject.vue";
import Skill from "../components/Skill.vue";
import Contact from "../components/Contact.vue";
export default {
  components: {
    Information,
    WorkProject,
    Skill,
    Contact,
  },
};
</script>

<style scoped></style>
