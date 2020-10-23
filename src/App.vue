<template>
 <main>
    <film-list></film-list>
 </main>
</template>

<script>

import FilmList from '@/components/FilmList.vue'

export default {
  //! THE DATA SECTION OF THIS APP IS DECIDING WHAT THE DATA NAMES AND TYPES WILL BE THAT ARE USED THROUGHOUT THE APP - EG  A LIST OF FILMS
  data() {
    return {
      films: [],
      characters: []
    };
  },
  //! THE MOUNTED SECTION GRABS WHATEVER INFORMATION IS REQUIRED BEFORE THE APP LOADS - THIS IS DONE ASYNCHRONOUSLY
  mounted() {
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(data => this.films = data)
  
  fetch('https://ghibliapi.herokuapp.com/people')
    .then(res => res.json())
    .then(data => this.characters = data)
  },
  components: {
    FilmList,
  }
}
</script>

<style>

</style>