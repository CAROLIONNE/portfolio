<template>
  <div>
    <h3>Envie de me présenter un projet ou tout simplement de discuter ?</h3>
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
      <p v-if="send" >Je vous remerçie de votre intêret 😄, je vous recontacte rapidement </p>
      <div id="container-btn">
          <BtnContact
            name="Envoyer"
          />
          <BtnContact
          id="btn-icon"
            name="Réinitialiser"
            :action="onReset"
          />
      </div>
    </form>
  </div>
</template>

<script>
import emailjs from "emailjs-com";
import BtnContact from "../components/BtnContact.vue";
export default {
  name: "ContactMe",
  components: { BtnContact },
  data() {
    return {
      name: "",
      email: "",
      message: "",
      send: false,
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
          $event.target,
          "aXQKIS6B2tstkFrsM",
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
      this.onReset();
      this.send = true;
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
  h3 {
    font-style: italic;
    color: $color-grey;
    font-weight: 300;
    display: flex;
    justify-content: center;
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
  // border: 2px outset $color-dark;
  border: 2px outset $color-primary;
  border-radius: $br;
  .field {
    width: 80%;
    padding: 0.5em;
    margin: 0.5em;

    background: $color-black;
    color: floralwhite;
    font-weight: bold;
    font-style: italic;
    border-right: none;
    border-left: none;
    border-top: none;
    border-bottom: $color-secondary 1px solid;
  }
  #container-btn {
    display: flex;
    align-items: flex-end;
  }
}
</style>
