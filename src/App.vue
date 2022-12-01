<template>
  <div id="app">
    <HeadComp @emitSearch="searchFilms" />
    <MainComp :paramFilms="arrayFilms"  :paramSerieTv="serieTV"/>
  </div>
</template>

<script>
import HeadComp from './components/HeadComp.vue'
import MainComp from './components/MainComp.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeadComp,
    MainComp
  },
  data() {
    return {
      arrayFilms: [],
      serieTV: []
    }
  },
  methods: {
    searchFilms(valoreRicerca) {
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=9611be04af8d32f630d5c3fee8162eca&query=' + valoreRicerca)
        .then((response) => {
          this.arrayFilms = response.data.results
        })

      axios.get('https://api.themoviedb.org/3/search/tv?api_key=9611be04af8d32f630d5c3fee8162eca&query=' + valoreRicerca)
        .then((response) => {
          this.serieTV = response.data.results
        })
    }
  }
}
</script>

<style lang="scss">

</style>
