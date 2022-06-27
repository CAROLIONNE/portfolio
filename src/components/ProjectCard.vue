<template>
    <div id="container">
        <div id="card" >
            <img :src="project.logo"/>
            <p id="title"> {{project.title}}</p>
            <p id="developpement"> {{project.developpement}}</p>
            <div id="description"> {{project.description}}          
            </div>
            <div id="techno"> {{ project.techno}}         
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    project: Object,
  }
}
</script>

<style lang="scss" scoped>
@import "../main.scss";
#container {
  border: 2px solid $color-dark;
  border-radius: 1em;
  width: 400px;
  background:	$color-tertiary;
  overflow: hidden;
  padding: 0.5em
}

</style>