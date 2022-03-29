<template>
  <div id="app">
    <header-boolflix @search='searchInput'/>
    <main-boolflix :search-movie="movie"/>
  </div>
</template>

<script>
import HeaderBoolflix from './components/HeaderBoolflix.vue'
import MainBoolflix from './components/MainBoolflix.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderBoolflix,
    MainBoolflix
  },
  data () {
    return {
      movie: []
    }
  },
  created () {
    axios.get(
      'https://api.themoviedb.org/3/search/movie?api_key=58d440feb39fe720c632f6aaec3cb1f1&language=it&query=movie')
      .then((response) => {
        this.movie = response.data.results
      })
  },
  methods: {
    searchInput (event) {
      this.movie = event
      console.log(this.movie)
    }
  }
}
</script>

<style lang="scss">
@import './assets/stile.scss';

</style>
