<template>
  <v-container class="container" id="portfolio">
    <h2 class="title-h2">Portfolio</h2>
    <v-row>
      <v-col v-for="portfolio in portfolioDatas" :key="portfolio.name">
        <v-card class="" max-width="300">
          <v-img
            :src="portfolio.image"
            height="200px"
          ></v-img>

          <v-card-title> {{ portfolio.name }} </v-card-title>

          <v-card-subtitle> {{ portfolio.technology }} </v-card-subtitle>

          <v-card-actions>
            <a :href="portfolio.link" color="blue accent-2" class="view-link"> View </a>

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
import mynotes from '@/assets/mynotes.png'
import skillful from '@/assets/skillful.png'
import simpleMovie from '@/assets/simple-movie-app.png'
import dbengkel from '@/assets/d-bengkel.png'
import aplikasiTabung from '@/assets/hitung-tabung.png'
import searchMovie from '@/assets/search-movie-api.png'

export default {
  data: () => ({
    show: false,
    portfolioDatas: [
        {
            name: 'MyNotes',
            technology: 'Laravel, Bootstrap',
            description: 'Sebuah website sederhana untuk menyimpan materi-materi yang ada disekolah. Website ini dibuat menggunakan framework Laravel 8 dan bootstrap untuk framework cssnya.',
            link: 'https://github.com/IdaDanuartha/MyNotes-laravel',
            image: mynotes
        },
        {
            name: 'Skillful',
            technology: 'HTML, CSS, Javascript, Bootstrap',
            description: 'Sebuah website blog statis yang dibuat bersama 6 orang untuk tugas sekolah. Website ini dibuat menggunakan HTML, CSS, Javascript dan bootstrap untuk framework cssnya.',
            link: 'https://github.com/IdaDanuartha/skillful',
            image: skillful
        }, 
        {
            name: 'Simple Movie App',
            technology: 'Vue Js, Tailwind',
            description: 'Sebuah website sederhana untuk melihat sinopsis-sinopsis film. Website ini dibuat menggunakan framework Vue Js, tailwind untuk framework cssnya dan API dari OMDb untuk data filmnya.',
            link: 'https://github.com/IdaDanuartha/Simple-Movie-App',
            image: simpleMovie
        },
        {
            name: 'DBengkel APP',
            technology: 'Laravel, Bootstrap, Tailwind',
            description: 'Sebuah website E-Commerce yang menjual kebutuhan bengkel. Website ini dibuat menggunakan framework Laravel 8, Bootstrap dan Tailwind untuk framework cssnya.',
            link: 'https://github.com/IdaDanuartha/DBengkel-web',
            image: dbengkel
        },
        {
            name: 'Aplikasi Tabung',
            technology: 'Java',
            description: 'Sebuah aplikasi sederhana untuk menghitung volume dan luas permukaan bangun ruang tabung. Aplikasi ini dibuat menggunakan bahasa Java untuk melengkapi tugas sekolah.',
            link: 'https://github.com/IdaDanuartha/Aplikasi-Menghitung-Tabung',
            image: aplikasiTabung
        },
        {
            name: 'Search Movie App',
            technology: 'HTML, CSS, Javascript',
            description: 'Sebuah website sederhana untuk mecari dan melihat sinopsis film. Website ini dibuat menggunakan HTML, CSS, Javascript dan API dari OMDb untuk data filmnya',
            link: 'https://github.com/IdaDanuartha/SearchMovie-API',
            image: searchMovie
        }
    ]
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