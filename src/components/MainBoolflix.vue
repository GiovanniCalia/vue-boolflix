<template>
  <main>

            <div v-for='element in searchMovie' :key='element.title' class="p-relative">
                <div class="box">
                    <img src="image + element.poster_path" alt="">
                  <div>Titolo: {{ element.title }}</div>
                  <div>Titolo originale: {{ element.original_title }}</div>
                  <div>Voto: {{ element.vote_average }}</div>
                  <div>Overview: {{ element.overview }}</div>
                </div>
                <!--<div class="box-img">
                    <img src="https://image.tmdb.org/t/p/w500/1k6iwC4KaPvTBt1JuaqXy3noZRY.jpg" alt="">
                </div>-->
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
      const result = 'https://image.tmdb.org/t/p/w500'
      return result
    }
  },
  computed: {
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

    img{
        width: 100%;
    }
}

.p-relative{
    position: relative;
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
