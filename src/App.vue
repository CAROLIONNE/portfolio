<template>
  <Nav @click="showMenu = !showMenu"/>
  <div class="home" v-if="showMenu">
    <!-- <img alt="logo" src=""> -->
    <div id="me">
      <img id="portrait" src="./assets/images/me.jpg" alt="Photo de moi" />
    </div>
    <div id="projects" v-for="project in projects" :key="project.id">
      <ProjectCard :project="project" />
    </div>
    <div id="contact">
        <ContactMe />
    </div>
  </div>
</template>

<script>
import Nav from "@/components/MenuBars.vue";
import projects from "@/assets/data_projects";
import ProjectCard from "@/components/ProjectCard.vue";
import ContactMe from "@/components/ContactMe.vue";

export default {
  data() {
    return {
      projects,
      showMenu: true
    };
  },
  components: {
    Nav, ProjectCard, ContactMe
  },
};
</script>
<style lang="scss">
@import "main.scss";
.home {
  display: flex;
  flex-wrap: wrap;
  border-radius: 1em;
  justify-content: space-around;
  gap: 1em 1.5em;
}
#me {
  width: 100%;
  display: flex;
    justify-content: center
}
#portrait {
  width: 40%;
  border-radius: 50%;
  // variable sass ne fonctionne pas
  border: 2px solid $color-dark;
}

</style>
