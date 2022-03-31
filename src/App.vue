<template>
  <div id="app">
    <header-boolflix @pass-movie='searchInput'/>
    <main-boolflix :search-movie="movie" :sc-tv='tv' :found-movie="scMovie" :found-tv='scrTv'/>
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
      movie: [],
      tv: [],
      scMovie: '',
      scrTv: ''
    }
  },
  created () {
    axios.get(
      'https://api.themoviedb.org/3/search/movie?api_key=58d440feb39fe720c632f6aaec3cb1f1&language=it&query=movie')
      .then((response) => {
        this.movie = response.data.results
        console.log(this.movie)
      })
    axios.get(
      'https://api.themoviedb.org/3/search/tv?api_key=58d440feb39fe720c632f6aaec3cb1f1&language=it&query=tv')
      .then((response) => {
        this.tv = response.data.results
        console.log(this.tv)
      })
  },
  methods: {
    searchInput (search) {
      axios.get(
        'https://api.themoviedb.org/3/search/movie?api_key=58d440feb39fe720c632f6aaec3cb1f1&language=it&query=' + search)
        .then(() => {
          this.scMovie = search
          console.log(search)
        })
      axios.get(
        'https://api.themoviedb.org/3/search/tv?api_key=58d440feb39fe720c632f6aaec3cb1f1&language=it&query=' + search)
        .then(() => {
          this.scrTV = search
        })
    }
  }
}
</script>

<style lang="scss">
@import './assets/stile.scss';
</style>
