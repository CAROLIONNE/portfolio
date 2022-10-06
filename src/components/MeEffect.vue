<template>
  <div class="wrapper">
    <h1 class="static-txt">Hello, I'm</h1>
    <ul class="dynamic-txts">
      <li><span>Soc Caroline</span></li>
      <li><span>Open to Work !</span></li>
      <li><span>Motivated !</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MeEffect",
  data() {
    return {};
  },
  computed: {},

  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../main.scss";
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-bottom: 1rem;
  background-color: $color-black;
  height: fit-content;
  width: fit-content;
  opacity: 0.6;
  // justify-content: center;
  // align-items: center;
  margin-left: auto;
  margin-right: auto;
}
li {
  list-style: none;
}
.mobile-txt {
  display: none;
}
.static-txt {
  color: $color-primary;
  margin-top: 0.5rem;
  margin-bottom: 0;
  font-size: 1.5rem;
}
.dynamic-txts {
  display: block;
  // margin-left: 15px;
  line-height: 90px;
  height: 90px;
  overflow: hidden;
}

.dynamic-txts li {
  color: $color-secondary;
  font-size: 60px;
  font-weight: 500;
  position: relative;
  top: 0;
  animation: slide 9s steps(3) infinite;
}

.dynamic-txts li {
  position: relative;
}

@keyframes slide {
  100% {
    top: -270px;
  }
}

.dynamic-txts li::after {
  content: "";
  position: absolute;
  left: 0;
  height: 100%;
  width: 100%;
  border-left: 2px solid $color-secondary;
  background-color: $color-black;
  animation: typing 3s steps(14) infinite;
}

@keyframes typing {
  40%,
  60% {
    left: calc(100% + 30px);
  }
  100% {
    left: 0;
  }
}
</style>
