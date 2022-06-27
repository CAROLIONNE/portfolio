<template>
  <div>
    <h3>Envie de me presenter un projet ou tout simplement discuter ?</h3>
    <form @submit.prevent="submit">
      <input
        id="name"
        v-model="name"
        type="text"
        name="name"
        placeholder="Nom"
      />
      <input
        id="mail"
        v-model="mail"
        type="email"
        name="mail"
        placeholder="Email"
      />
      <input
        id="message"
        v-model="message"
        type="text"
        name="message"
        placeholder="Message"
      />
      <input type="submit" value="Envoyer" />
    </form>
  </div>
</template>

<script>
export default {
  name: "ContactMe",
  methods: {
    submit() {},
  },
};
</script>

<style lang="scss" scoped>
@import "../main.scss";
div {
  margin-left: 3em;
}
form {
  width: 80%;
    margin-left: auto;
  margin-right: auto;
  display: flex;
  align-items: center;
  flex-direction: column;
  border: 2px solid $color-dark;
  border-radius: 1em;
  input {
    width: 80%;
    padding: 0.5em;
    margin: 0.5em;
  }
}
</style>
