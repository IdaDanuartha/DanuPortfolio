<template>
  <v-container class="container" id="skills">
      <h2 class="title-h2">Skills</h2>
    <v-row no-gutters>
      <v-col
        v-for="skill in skills"
        :key="skill"
        cols="12"
        sm="2"
        class="ma-1"
      >
        <v-card
          class="pa-3"
          outlined
        >
        <img :src="skill.img" width="100%" class="d-block" alt="">
        <h6 class="text-center mt-2">{{ skill.name }}</h6>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import html from '@/assets/skills-img/html.png'
import css from '@/assets/skills-img/css-3.png'
import js from '@/assets/skills-img/js.png'
import php from '@/assets/skills-img/php.png'
import mysql from '@/assets/skills-img/mysql.png'
import bootstrap from '@/assets/skills-img/bootstrap.png'
import tailwind from '@/assets/skills-img/tailwind.png'
import laravel from '@/assets/skills-img/laravel.png'
import vuejs from '@/assets/skills-img/vue js.png'
import nodejs from '@/assets/skills-img/nodejs.png'
import mongodb from '@/assets/skills-img/mongodb.png'

export default {
    data() {
        return {
            skills: [
                {
                    name: "HTML",
                    img: html
                },
                {
                    name: "CSS",
                    img: css
                },
                {
                    name: "Javascript",
                    img: js
                },
                {
                    name: "PHP",
                    img: php
                },
                {
                    name: "MySQL",
                    img: mysql
                },
                {
                    name: "Bootstrap",
                    img: bootstrap
                },
                {
                    name: "Tailwind",
                    img: tailwind
                },
                {
                    name: "Laravel",
                    img: laravel
                },
                {
                    name: "Vue Js",
                    img: vuejs
                },
                {
                    name: "Node Js",
                    img: nodejs
                },
                {
                    name: "MongoDB",
                    img: mongodb
                },
            ]
        }
    }
}
</script>
