<template>
  <div id="app">
    <header-boolflix />
    <main-boolflix />
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
  created () {
    axios.get(
      'https://api.themoviedb.org/3/movie/550?api_key=58d440feb39fe720c632f6aaec3cb1f1')
      .then()
  }
}
</script>

<style lang="scss">
@import './assets/stile.scss';

</style>
