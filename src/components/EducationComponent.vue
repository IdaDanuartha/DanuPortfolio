<template>
  <v-container class="container" id="education">
    <h2 class="title-h2">Education</h2>
      <!-- <v-timeline>
    <v-timeline-item
      v-for="(year, i) in years"
      :key="i"
      :color="year.color"
      small
    >
      <template v-slot:opposite>
        <span
          :class="`headline font-weight-bold ${year.color}--text`"
          v-text="year.year"
        ></span>
      </template>
      <div class="py-4">
        <h2 :class="`headline font-weight-light mb-4 ${year.color}--text`">
         {{ year.title}}
        </h2>
        <div>
          {{ year.description }}
        </div>
      </div>
    </v-timeline-item>
  </v-timeline> -->
  <v-timeline>
    <v-timeline-item
      v-for="(year, i) in years"
      :key="i"
      :color="year.color"
      medium
    >
      <template v-slot:opposite>
        <span>{{ year.year }}</span>
      </template>
      <v-card class="elevation-3 white--text" :class="year.color">
        <v-card-title class="text-sm-h6 text-h5 font-weight-bold ">
          {{ year.title }}
        </v-card-title>
        <v-card-text class="font-weight-medium">
          {{ year.description }}
        </v-card-text>
      </v-card>
    </v-timeline-item>
  </v-timeline>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      years: [
        {
          color: 'cyan',
          year: '2009 - 2011',
          title: 'Kindergarten',
          description: 'Citra Dharma Kindergarten was where I spent two years of my life learning. In the years 2009-2011'
        },
        {
          color: 'green',
          year: '2011 - 2017',
          title: 'Elementary School',
          description: 'SD Negeri 6 Dalung was where I spent six years of my education. In the years 2011-2017'
        },
        {
          color: 'pink',
          year: '2017 - 2020',
          title: 'Junior High School',
          description: 'SMP Negeri 2 Kuta Utara was where I spent three years of my education. In the years 2017-2020'
        },
        {
          color: 'deep-orange',
          year: '2020 - Until Present',
          title: 'Vocational High School',
          description: 'For the past two years, I have been a student at SMK Negeri 1 Denpasar. From 2020 to the present'
        },
      ],
    }),
  }
</script>