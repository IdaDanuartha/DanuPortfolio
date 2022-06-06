<template>
  <v-footer
    color="blue darken-1"
    padless
    id="footer"
  >
    <v-row
      justify="center"
      no-gutters
    >
      <a class="social-link" href="https://www.instagram.com/dan.dev14/"><v-icon class="ma-4" color="white">mdi-instagram</v-icon></a>
      <a class="social-link" href="https://www.facebook.com/danuartha1421/"><v-icon class="ma-4" color="white">mdi-facebook</v-icon></a>
      <a class="social-link" href="mailto:danuart21@gmail.com"><v-icon class="ma-4" color="white">mdi-email</v-icon></a>
      <a class="social-link" href="https://www.youtube.com/channel/UCBffIZcqjFU0KkGWxkJ3rlw/featured"><v-icon class="ma-4" color="white">mdi-youtube</v-icon></a>
      <v-col
        class="blue lighten-1 py-5 text-center white--text"
        cols="12"
      >
        Copyright © {{ new Date().getFullYear() }} — <strong>DanuPortfolio</strong>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
  export default {

  }
</script>

<style scoped>
    #footer {
        margin-top: 150px;
    }

    .social-link {
      transition: all 0.2s;
    }

    .social-link:hover {
      background-color: rgb(19, 121, 246);
    }
</style>