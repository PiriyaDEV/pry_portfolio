<template>
  <div id="mainpage">
    <Information />
    <WorkProject />
    <Presentation />
    <Certificate />
    <Skill />
    <!-- <Certificate /> -->
    <Contact />
  </div>
</template>

<script>
import Information from "../components/Information.vue";
import WorkProject from "../components/WorkProject.vue";
import Skill from "../components/Skill.vue";
import Contact from "../components/Contact.vue";
import Presentation from "../components/Presentation.vue"
import Certificate from "../components/Certificate.vue"
export default {
  components: {
    Information,
    WorkProject,
    Skill,
    Contact,
    Presentation,
    Certificate
  },
};
</script>

<style scoped></style>
