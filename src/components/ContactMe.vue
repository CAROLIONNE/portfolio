<template>
  <div>
    <h3>Envie de me presenter un projet ou tout simplement discuter ?</h3>
    <form @submit.prevent="sendEmail($event)" @reset="onReset">
      <input
        class="field"
        id="name"
        v-model.trim="name"
        type="text"
        name="name"
        placeholder="Nom"
      />
      <input
        class="field"
        id="email"
        v-model.trim="email"
        type="email"
        name="email"
        placeholder="Email"
      />
      <textarea
        class="field"
        id="message"
        v-model.trim="message"
        type="text"
        name="message"
        placeholder="Message"
      >
      </textarea>
      <input type="submit" value="Envoyer" />
      <button type="reset">Reset</button>
    </form>
  </div>
</template>

<script>
import emailjs from "emailjs-com";
// emailjs.init('aXQKIS6B2tstkFrsM');
export default {
  name: "ContactMe",
  data() {
    return {
      name: "",
      email: "",
      message: "",
    };
  },
  computed: {
    formValid() {
      const { name, email, message } = this;
      return (
        name.length > 0 &&
        /(.+)@(.+){2,}.(.+){2,}/.test(email) &&
        message.length > 0
      );
    },
  },

  methods: {
    sendEmail($event) {
       if (!this.formValid) {
        return;
      }
      try {
        emailjs.sendForm(
          "service_kp63xtu",
          "template_376fs8r",
          $event.target, "aXQKIS6B2tstkFrsM",
          {
            name: this.name,
            email: this.email,
            message: this.message,
          }
        );
      } catch (error) {
        console.log({ error });
      }
      // Reset form field
      this.name = "";
      this.email = "";
      this.message = "";
    },
    onReset() {
      this.name = "";
      this.email = "";
      this.message = "";
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../main.scss";
div {
  padding-left: 4.5em;
  h3 {
    color: $color-grey;
  }
}
form {
  padding: 0.4em;
  width: 80%;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  align-items: center;
  flex-direction: column;
  border: 2px outset $color-dark;
  border-radius: 1em;
  .field {
    width: 80%;
    padding: 0.5em;
    margin: 0.5em;
  }
}
</style>
