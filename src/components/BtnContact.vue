<template>
  <div>
    <button class="btn" @click="action">{{ name }}</button>
  </div>
</template>

<script>
export default {
  name: "BtnContact",
  props: {
    name: String,
    action: Function,
  },
};
</script>

<style lang="scss" scoped>
@import "../main.scss";

.btn {
  margin: 1em;
  display: inline-block;
  text-align: center;
  vertical-align: middle;
  padding: 12px 24px;
  border: 1px solid #b38ba4;
  border-radius: 8px;
  background: #ffc7ea;
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    from(#ffc7ea),
    to(#b38ba4)
  );
  background: -moz-linear-gradient(top, #ffc7ea, #b38ba4);
  background: linear-gradient(to bottom, #ffc7ea, #b38ba4);
  color: $color-black;
  text-decoration: none;
}
.btn:hover,
.btn:focus {
  border: 1px solid #ffc7ea;
  background: #ffefff;
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    from(#ffefff),
    to(#d7a7c5)
  );
  background: -moz-linear-gradient(top, #ffefff, #d7a7c5);
  background: linear-gradient(to bottom, #ffefff, #d7a7c5);
  color: #111111;
}
.btn:active {
  background: #b38ba4;
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    from(#b38ba4),
    to(#b38ba4)
  );
  background: -moz-linear-gradient(top, #b38ba4, #b38ba4);
  background: linear-gradient(to bottom, #b38ba4, #b38ba4);
}
.btn-icon:before {
  content: "\0000a0";
  display: inline-block;
  height: 24px;
  width: 24px;
  line-height: 24px;
  margin: 0 4px -6px -4px;
  position: relative;
  top: 0px;
  left: 0px;
  background: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAACXBIWXMAAA7EAAAOxAGVKw4bAAABdUlEQVRIic3Vv0pcURAG8J9BtkixWIpICgkWIvsAy4IWPoHpEhGSSshTpLbwUdRKFgQbESxkUdwmpExCSLMhpFOJxYzxev13r7qSD4Z7zz0z8525c2aGIWOkot4kWhjP9Q8c4etjyEexjH2c4G9JTnJvOXVrYRY9nKGLJUyhkTKV37ZSp5c28DJ1bsU8BuijU+Ew7dQdpO0hVu86+QA7aFZwfoFm2gxS1m5SGhWh9ms6L5L0RX7+ERST81bclDn8ruG4hTf5/hkzxc0iwUdsY7eGc5jGSmH9E3/KSpPi2i3VdH4vXuSzJaLZGxbBRYU+qjKfCw1xkz5wGcFT4lU+vw+LoI1THJc3PuFbSRYfQNAVTRBX66CJCWyIioYvNZ13sID3N22uieQ8tFWMpW1P4eDlHPwSUWzWJBnDetq+Ezm4hlXRauddtut2BecdV9v1rWiIYUE0rLsGzmsxybqpc6DU5KrgSUZmnaE/K/4xUUTH/ofWcg7xP1l2e+46fwAAAABJRU5ErkJggg==")
    no-repeat left center transparent;
  background-size: 100% 100%;
}
</style>
