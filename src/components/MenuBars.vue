<template>
  <div id="bloc-menu">
    <nav>
      <svg
        style="fill: #FEC5E9"
        @click="displayMenu = !displayMenu"
        id="menu-bars"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 448 512"
      >
        <path
          d="M0 96C0 78.33 14.33 64 32 64H416C433.7 64 448 78.33 448 96C448 113.7 433.7 128 416 128H32C14.33 128 0 113.7 0 96zM0 256C0 238.3 14.33 224 32 224H416C433.7 224 448 238.3 448 256C448 273.7 433.7 288 416 288H32C14.33 288 0 273.7 0 256zM416 448H32C14.33 448 0 433.7 0 416C0 398.3 14.33 384 32 384H416C433.7 384 448 398.3 448 416C448 433.7 433.7 448 416 448z"
        />
      </svg>
      <div
        class="overlay"
        @click="displayMenu = !displayMenu"
        v-if="displayMenu"
      >
        <ul>
          <a href="#skills" class="link">Compétences</a>
          <a href="#portfolio" class="link">Portfolio</a>
          <a href="#contact" class="link">Contact</a>
        </ul>
      </div>
    </nav>
  </div>
  <div id="cv">
    <!-- Lien a faire fonctionner -->
    <!-- <a href="../assets/CV_Soc_Caroline_dev-web.pdf" @click="uploadCV"> -->
    <a href="" @click="uploadCV">
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
    return {
      displayMenu: false,
    };
  },
  props: {
    visible: Boolean,
    showMenu: Function,
  },
};
</script>

<style lang="scss" scoped>
@import "../main.scss";
nav {
  position: fixed;
}
#menu-bars {
  width: 1.5em;
  display: flex;
  cursor: pointer;
  transition: 0.5s ease all;
  &:hover {
    transform: rotate(180deg);
  }
}

#cv {
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
      color: lighten($color-secondary, 8%)
    }
  }
}
.overlay {
  background: rgba(0, 0, 0, 0.9);
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
}
ul {
  display: flex;
  flex-direction: column;
  align-items: baseline;
  a {
    text-decoration: none;
    color: floralwhite;
    font-size: xxx-large;
  }
  .link {
    margin: 10px;
    transition: all 0.3s ease-out;
  }
  .link:hover {
    border-top: 4px solid $color-primary;
    border-bottom: 4px solid $color-primary;
    padding: 6px 0;
  }
}
</style>
