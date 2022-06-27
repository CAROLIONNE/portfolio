<template>
  <Nav @click="showMenu = !showMenu" />
  <div class="home" v-if="showMenu">
    <!-- <img alt="logo" src=""> -->
    <div id="me">
      <img id="portrait" src="./assets/images/me.jpg" alt="Photo de moi" />
    </div>
    <div id="container-skills">
      <h2 id="skills">Compétences</h2>
      <!-- ajouter logo technos  -->
    </div>
    <div id="container-projects">
      <h2 id="portfolio">Portfolio</h2>
      <div id="projects" v-for="project in projects" :key="project.id">
        <ProjectCard :project="project" />
      </div>
    </div>
    <div id="container-contact">
      <h2 id="contact">Contactez-moi</h2>
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
      showMenu: true,
    };
  },
  components: {
    Nav,
    ProjectCard,
    ContactMe,
  },
};
</script>
<style lang="scss">
@import "main.scss";
// .home {
//   display: flex;
//   flex-wrap: wrap;
//   border-radius: 1em;
//   justify-content: space-around;
//   gap: 1em 1.5em;
// }
#me {
  width: 100%;
  display: flex;
  justify-content: center;
  height: 500px;
}
#portrait {
  //   margin-left: auto;
  // margin-right: auto;
  display: flex;
  max-width: 100%;
  max-height: 100%;
  border-radius: 25%;
  border: 2px solid $color-dark;
}
#container-skills {
  #skills {
    width: 100%;
    margin-left: 2em;
  }
}
#container-projects {
  width: 100%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 1em 1.5em;
  #portfolio {
    // a perso cursor
    cursor: pointer;
    width: 100%;
    margin-left: 2em;
    transition: all 1s;
    // effet a tester
    &:hover {
      border-bottom: 2px solid $color-primary;
    }
  }
}
#container-contact {
  #contact {
    width: 100%;
    margin-left: 2em;
  }
}
</style>
