<template>
    <div id="container">
        <div id="card" >
            <img :src="skill.logo"/>
        </div>
    </div>
</template>

<script>
export default {
  name: 'SkillCard',
  props: {
    skill: Object,
  }
}
</script>

<style lang="scss" scoped>
@import "../main.scss";
// #container {
//   border: 2px solid $color-dark;
//   border-radius: 1em;
//   width: 400px;
//   background:	$color-tertiary;
//   overflow: hidden;
//   padding: 0.5em
// }

</style>