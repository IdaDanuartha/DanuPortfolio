<template>
  <v-container class="container" id="portfolio">
    <h2 class="title-h2">Portfolio</h2>
    <v-row class="mx-auto">
      <v-col
        cols="12"
        sm="6"
        md="4"
        lg="3"
        v-for="portfolio in portfolioDatas"
        :key="portfolio.name"
      >
        <v-card class="" max-width="300">
          <v-img :src="portfolio.image" height="200px"></v-img>

          <v-card-title> {{ portfolio.name }} </v-card-title>

          <v-card-subtitle> {{ portfolio.technology }} </v-card-subtitle>

          <v-card-actions>
            <a :href="portfolio.link" color="blue accent-2" class="view-link">
              View
            </a>

            <v-spacer></v-spacer>

            <v-btn icon @click="show = !show">
              <v-icon>{{
                show ? "mdi-chevron-up" : "mdi-chevron-down"
              }}</v-icon>
            </v-btn>
          </v-card-actions>

          <v-expand-transition>
            <div v-show="show">
              <v-divider></v-divider>

              <v-card-text>
                {{ portfolio.description }}
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import mynotes from "@/assets/mynotes.png";
import simpleMovie from "@/assets/simple-movie-app.png";
import dbengkel from "@/assets/d-bengkel.png";
import searchMovie from "@/assets/search-movie-api.png";
import blogApp from "@/assets/blogApp.jpg";
import bookshelfAPI from "@/assets/bookshelf-api.jpg";
import travelend from "@/assets/travelend.png";

export default {
  data: () => ({
    show: false,
    portfolioDatas: [
      {
        name: "MyNotes",
        technology: "Laravel, Bootstrap",
        description:
          "A basic website for educational materials storage. This site was built with the Laravel 8 framework and the Bootstrap CSS framework.",
        link: "https://github.com/IdaDanuartha/MyNotes-laravel",
        image: mynotes,
      },
      {
        name: "Simple Movie App",
        technology: "Vue Js, Tailwind",
        description:
          "A straightforward website for viewing movies synopses. The Vue Js framework was used to build this website, as well as Tailwind for the CSS framework and the OMDb API for the movie data.",
        link: "https://github.com/IdaDanuartha/Simple-Movie-App",
        image: simpleMovie,
      },
      {
        name: "DBengkel APP",
        technology: "Laravel, Jquery, Tailwind",
        description:
          "An E-Commerce site that offers workshop supplies and has a lot of features. The Laravel 8 framework, Jquery, and Tailwind for the CSS framework were used to create this website.",
        link: "https://github.com/IdaDanuartha/DBengkel-web",
        image: dbengkel,
      },
      {
        name: "Search Movie App",
        technology: "HTML, CSS, Javascript",
        description:
          "A basic website that allows you to search for and see movie synopses. This website was built with HTML, CSS, Javascript, and the OMDb API for movie data.",
        link: "https://github.com/IdaDanuartha/SearchMovie-API",
        image: searchMovie,
      },
      {
        name: "DanBlog App",
        technology: "Laravel, Tailwind",
        description:
          "a full-stack blog with a content management system built using the Laravel framework and Tailwindcss.",
        link: "https://github.com/IdaDanuartha/danblog-app",
        image: blogApp,
      },
      {
        name: "Bookshelf API",
        technology: "Nodejs (Hapi.js)",
        description:
          "A simple Rest API project with Nodejs and Hapijs framework. This project is an assignment from dicoding.",
        link: "https://github.com/IdaDanuartha/bookshelf-api",
        image: bookshelfAPI,
      },
      {
        name: "Travelend App",
        technology: "Laravel, Bootstrap",
        description:
          "A dynamic travel landing page created with the Laravel framework, Livewire for routing, and Bootstrap for styling.",
        link: "https://github.com/IdaDanuartha/travelend-revisi",
        image: travelend,
      },
    ],
  }),
};
</script>

<style scoped>
.view-link {
  transition: all 0.2s;
  padding: 5px 10px;
  border-radius: 5px;
}

.view-link:hover {
  background-color: rgba(19, 121, 246, 0.2);
}

.view-link:focus {
  outline: rgba(19, 121, 246, 0.6) solid 3px;
}
</style>