<template>
  <v-app id="inspire" style="font-family: 'Fira Code'">
    <v-navigation-drawer color="grey darken-4" v-model="drawer" app>
      <v-list-item>
        <v-list-item-content>
          <v-img
            height="100%"
            src="@/assets/coding.jpg"
          >
            <v-row align="end" class="fill-height">
              <v-col align-self="start" class="pa-0" cols="12">
                <v-avatar
                  class="profile d-block mx-auto mt-5"
                  color="grey"
                  size="75"
                >
                  <v-img src="@/assets/my-profile-3.jpeg"></v-img>
                </v-avatar>
              </v-col>
              <v-col class="py-0">
                <v-list-item color="rgba(0, 0, 0, .4)" dark>
                  <v-list-item-content class="text-center">
                    <v-list-item-title class="text-h6">
                      Danuartha
                    </v-list-item-title>
                    <v-list-item-subtitle
                      >Jr. Web Developer</v-list-item-subtitle
                    >
                  </v-list-item-content>
                </v-list-item>
              </v-col>
            </v-row>
          </v-img>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item :href="item.link" v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon class="white--text">{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title class="white--text">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar elevation="4" app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title class="font-weight-medium">DanuPortfolio</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <Home></Home>
      <About></About>
      <Skills></Skills>
      <Education></Education>
      <Portfolio></Portfolio>
      <Contact></Contact>
      <Footer></Footer>
    </v-main>
  </v-app>
</template>

<script>
import Home from "@/components/HomeComponent.vue";
import About from "@/components/AboutComponent.vue";
import Skills from "@/components/SkillsComponent.vue";
import Education from "@/components/EducationComponent.vue";
import Portfolio from "@/components/PortfolioComponent.vue";
import Contact from "@/components/ContactComponent.vue";
import Footer from "@/components/FooterComponent.vue";
export default {
  components: {
    Home,
    About,
    Skills,
    Education,
    Portfolio,
    Contact,
    Footer,
  },
  data() {
    return {
      drawer: null,
      items: [
        { title: "Home", icon: "mdi-home", link: '#home' },
        { title: "About Me", icon: "mdi-account", link: '#about' },
        { title: "Skills", icon: "mdi-sword", link: '#skills' },
        { title: "Education", icon: "mdi-school", link: '#education' },
        { title: "Portfolio", icon: "mdi-account-box-outline", link: '#portfolio' },
        { title: "Contact Me", icon: "mdi-phone", link: '#contact' },
      ],
    };
  },
};
</script>

<style>
html {
  scroll-behavior: smooth;
}

.container {
  padding-top: 100px;
  margin-top: 100px;
  width: 80%;
}

@media (max-width: 768px) {
  .container {
    width: 95%;
  }
}
.title-h2 {
  margin-bottom: 20px;
}

.title-h2::after {
  content: "";
  width: 70px;
  height: 3px;
  border-radius: 10px;
  background-color: rgb(46, 129, 237);
  display: block;
}

a {
  text-decoration: none;
}
</style>