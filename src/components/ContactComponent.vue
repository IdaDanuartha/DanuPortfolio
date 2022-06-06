<template>
  <v-container class="container" id="contact">
      <h2 class="title-h2">Contact Me</h2>
    <form>
      <v-text-field
        v-model="name"
        :error-messages="nameErrors"
        label="Name"
        required
        @input="$v.name.$touch()"
        @blur="$v.name.$touch()"
      ></v-text-field>
      <v-text-field
        v-model="email"
        :error-messages="emailErrors"
        label="E-mail"
        required
        @input="$v.email.$touch()"
        @blur="$v.email.$touch()"
      ></v-text-field>
    <v-textarea v-model="bio" :error-messages="bioErrors" required @input="$v.name.$touch()"
        @blur="$v.name.$touch()">
        <template v-slot:label>
        <div>Message</div>
        </template>
    </v-textarea>

      <v-btn class="mt-3 mr-4 blue lighten-1" style="color: #fff;" @click="submit"> submit </v-btn>
      <v-btn class="mt-3 blue-grey lighten-3" @click="clear"> clear </v-btn>
    </form>
  </v-container>
</template>

<script>
import { validationMixin } from "vuelidate";
import { required, maxLength, email } from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],

  validations: {
    name: { required, maxLength: maxLength(10) },
    email: { required, email },
    bio: { required }
  },

  data: () => ({
    name: "",
    email: "",
    bio: "",
    select: null,
    items: ["Item 1", "Item 2", "Item 3", "Item 4"],
    checkbox: false,
  }),

  computed: {
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.required && errors.push("Name is required.");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("Must be valid e-mail");
      !this.$v.email.required && errors.push("E-mail is required");
      return errors;
    },
    bioErrors() {
      const errors = [];
      if (!this.$v.bio.$dirty) return errors;
      !this.$v.bio.required && errors.push("Message is required");
      return errors;
    },
  },

  methods: {
    submit() {
      this.$v.$touch();
    },
    clear() {
      this.$v.$reset();
      this.name = "";
      this.email = "";
      this.bio = "";
      this.checkbox = false;
    },
  },
};
</script>