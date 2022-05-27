<template>
  <v-container class="container" id="education">
    <h2 class="title-h2">Education</h2>
      <v-timeline>
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
          title: 'Taman Kanak-Kanak (TK)',
          description: 'Saya menjalani pendidikan di TK Citra Dharma selama 2 tahun. Dari tahun 2009 sampai 2011'
        },
        {
          color: 'green',
          year: '2011 - 2017',
          title: 'Sekolah Dasar (SD)',
          description: 'Saya menjalani pendidikan di SD Negeri 6 Dalung selama 6 tahun. Dari tahun 2011 sampai 2017'
        },
        {
          color: 'pink',
          year: '2017 - 2020',
          title: 'Sekolah Menengah Pertama (SMP)',
          description: 'Saya menjalani pendidikan di SMP Negeri 2 Kuta Utara selama 3 tahun. Dari tahun 2017 sampai 2020'
        },
        {
          color: 'deep-orange',
          year: '2020 - Until Present',
          title: 'Sekolah Menengah Kejuruan (SMK)',
          description: 'Saya baru menjalani pendidikan di SMK Negeri 1 Denpasar selama 2 tahun. Dari tahun 2020 sampai sekarang'
        },
      ],
    }),
  }
</script>