<template>
  <main>
        <div v-for='element in filterTitle' :key='element.id' class="p-relative">
            <div class="box">
                <div>Titolo: {{ element.title }}</div>
                <div>Titolo originale: {{ element.original_title }}</div>
                <div>Language: {{ element.original_language }}</div>
                <div>Voto: {{ element.vote_average }}</div>
            </div>
            <div class="box-img">
                <img :src="image(element.poster_path)" :alt="element.title">
            </div>
        </div>
  </main>
</template>

<script>
export default {
  data () {
    return {
      arrMovie: []
    }
  },
  props: {
    searchMovie: Array,
    foundMovie: String
  },
  methods: {
    image (result) {
      return 'https://image.tmdb.org/t/p/w500' + result
    }
  },
  computed: {
    filterTitle () {
      if (this.foundMovie === '') {
        return this.arrMovie === this.searchMovie
      } else {
        return this.searchMovie.filter(element => element.title.toLowerCase().includes(this.foundMovie.toLowerCase()))
      }
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

    div{
        margin-bottom: 0.5rem;
    }

    img{
        width: 100%;
    }
}

.p-relative{
    position: relative;
    margin: auto;
}

.box-img{
    margin: 1rem;
    width: 300px;
    height: 400px;
    background-color: blue;
    position: absolute;
    top: 0;

    &:hover{
        display: none;
    }

    img{
        width: 100%;
        height: 100%;
    }
}

</style>
