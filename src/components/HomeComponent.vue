<template>
  <v-parallax
    dark
    src="@/assets/black.jpg"
    id="home"
  >
    <v-row
      align="center"
      justify="center"
    >
      <v-col
        class="text-center"
        cols="6"
      >
        <h1 class="text-h4 font-weight-medium mb-4">
          Ida Putu Sucita Danuartha
        </h1>
        <h4 class="subheading font-weight-regular">
          Software Engineering Student at SMK Negeri 1 Denpasar
        </h4>
      </v-col>
      <v-col
        cols="6"
      >
        <img width="500" :src="profileImg" alt="Profile Picture">
      </v-col>
    </v-row>
  </v-parallax>
</template>

<script>
import profile from '@/assets/removebg-profile-3.png'
export default {
  data() {
    return {
      profileImg: profile
    }
  }
}
</script>

<style scoped>
 #home {
   margin-bottom: 50px;
 }
</style>
