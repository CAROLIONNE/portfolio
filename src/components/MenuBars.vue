<template>
  <div id="bloc-menu">
    <nav>
      <div id="navbar">
        <ul>
          <a href="#skills" class="link">Compétences</a>
          <a href="#portfolio" class="link">Portfolio</a>
          <a href="#contact" class="link">Contact</a>
        </ul>
      </div>
    </nav>
  </div>
  <div id="cv">
    <a href="./Soc_caroline.pdf" download>
      <p id="name" @hover="showCV">Caroline <strong>Soc</strong></p>
      <p id="cv-effect">Mon CV</p>
    </a>
  </div>
  <router-view />
</template>

<script>
export default {
  name: "MenuBars",
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../main.scss";
nav {
  #navbar {
    display: flex;
  }
  ul {
    display: flex;
    align-items: baseline;
    a {
      text-decoration: none;
      color: floralwhite;
      font-size: large;
    }
    .link {
      margin: 10px;
      border-bottom: 2px solid transparent;
      transition: all 0.2s ease-in-out;
    }
    .link:hover {
      border-bottom: 2px solid $color-primary;
      // padding: 6px 0;
    }
  }
}

#cv {
  cursor: default;
  position: absolute;
  top: 0;
  right: 0;
  padding-right: 1em;
  overflow: hidden;
  transition: all 0.5s ease-out;
  &:hover {
    transform: translateY(-2em);
  }
  a {
    text-decoration: none;
    color: $color-tertiary;
    position: relative;
    strong {
      color: lighten($color-secondary, 8%);
    }
  }
}
</style>
