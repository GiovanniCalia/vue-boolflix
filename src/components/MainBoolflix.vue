<template>
  <main>
      <div class="box" v-for='element in searchMovie' :key='element.title'>
          <img src="" alt="">
          <div>Titolo: {{ element.title }}</div>
          <div>Titolo originale: {{ element.original_title }}</div>
          <div>Voto: {{ element.vote_average }}</div>
          <div>Overview: {{ element.overview }}</div>
      </div>
  </main>
</template>

<script>
export default {
  props: {
    searchMovie: Array
  },
  methods: {
    image () {
      return 'https://image.tmdb.org/t/p/w500) + this.searchMovie.poster_path'
    }
  }
}
</script>

<style scoped lang="scss">
main{
    padding: 2rem;
    height: calc(100vh - 69px);
    background-color: grey;
    overflow-y: auto;
    display: flex;
    flex-wrap: wrap;
}

.box{
    margin: 1rem;
    padding: 1rem;
    width: 300px;
    height: 400px;
    background-color: red;
    overflow-y: auto;

    div{
        margin-bottom: 0.5rem;
    }
}
</style>
