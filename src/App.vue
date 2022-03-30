<template>
  <div id="app">
    <header-boolflix @pass-movie='searchInput'/>
    <main-boolflix :search-movie="movie" :found-movie="scMovie"/>
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
      scMovie: ''
    }
  },
  created () {
    axios.get(
      'https://api.themoviedb.org/3/search/movie?api_key=58d440feb39fe720c632f6aaec3cb1f1&language=it&query=movie')
      .then((response) => {
        this.movie = response.data.results
        console.log(this.movie)
        console.log('https://api.themoviedb.org/3/search/movie?api_key=58d440feb39fe720c632f6aaec3cb1f1&language=it&query=movie')
        console.log('https://api.themoviedb.org')
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
    }
  }
}
</script>

<style lang="scss">
@import './assets/stile.scss';

</style>
