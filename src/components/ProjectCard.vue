<template>
    <div id="container">
        <div id="card" >
            <img :src="project.logo"/>
            <h3 id="title"> {{project.title}}</h3>
            <p id="developpement"> {{project.developpement}}</p>
            <div id="description"> {{project.description}}          
            </div>
            -------------------
            <div id="techno" > Technologies utilisées :
              <!-- {{ project.techno}} -->
              <div v-for="tech in project.techno" :key="tech.id">
                {{ tech }}  
              </div>
                     
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    project: Object,
  },
  computed: {
  },
  methods: {
  }
}
</script>

<style lang="scss" scoped>
@import "../main.scss";
#container {
  border: 2px solid $color-dark;
  border-radius: 1em;
  background:	$color-tertiary;
  overflow: hidden;
  padding: 0.5em
}

</style>