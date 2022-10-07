<template>
  <div id="card">
    <div class="container_img">
      <img
        :src="require(`../assets/logos/${project.logo}`)"
        :alt="'Logo ' + project.name"
      />
    </div>
    <h3 id="title">{{ project.title }}</h3>
    <p id="developpement">{{ project.developpement }}</p>
    <div id="description">{{ project.description }}</div>
    <div id="technos">
      <div v-for="tech in project.techno" :key="tech.id">
        <p>{{ tech }}</p>
      </div>
    </div>
    <div id="buttons">
      <a v-if="project.demo" class="btn" :href="project.demo"> Démo </a>
      <a v-if="project.code" class="btn" :href="project.code"> Code </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: {
    project: Object,
  },
  computed: {},
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../main.scss";
#card {
  border: 2px solid $color-dark;
  border-radius: $br;
  background: $color-tertiary;
  overflow: hidden;
  padding: 0.5em;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  .container_img {
    height: 100px;
    display: flex;
    margin-left: auto;
    margin-right: auto;
    // justify-content: center;
  }
  img {
    display: block;
    // width: auto;
    // height: 40px;
    object-fit: cover;
    // display: flex;
    // margin-left: auto;
    // margin-right: auto;
    padding: 0.5em;

    max-width: 100%;
    max-height: 100%;
    // height: auto;
  }
  h3 {
    margin: 0;
    padding: 0;
    font-size: 1rem;
  }
  #developpement {
    font-size: 0.8rem;
  }
  #description {
    font-size: 0.9rem;
  }
  #technos {
    display: flex;
    justify-content: space-around;
    p {
      cursor: default;
      border-radius: $br;
      border: 2px outset $color-grey;
      padding: 0.5em;
      font-weight: 500;
      background: $color-primary;
      color: $color-dark;
      transition: 0.25s all ease-in-out;
      &:hover {
        font-weight: 600;
        border: 2px inset $color-dark;
        background: $color-primary;
        color: $color-dark;
      }
    }
  }
  #buttons {
    display: flex;
    justify-content: space-around;
    a {
      text-decoration: none;
      padding: 0.5em;
      border-radius: $br;
      font-weight: 600;
      border: 2px inset $color-black;
      background: $color-primary;
      color: $color-dark;
      transition: 0.3s all ease-in-out;
      &:hover {
        background: $color-dark;
        color: $color-primary;
        border: 2px outset $color-grey;
      }
    }
  }
}
</style>
