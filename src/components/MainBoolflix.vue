<template>
  <main>
        <div v-for='element in filterTitle' :key='element.id' class="p-relative">
            <div class="box">
                <div>Titolo: {{ element.title }}</div>
                <div>Titolo originale: {{ element.original_title }}</div>
                <!--<div>Language: {{ element.original_language }}</div>-->
                <lang-flag :iso="element.original_language" :squared="false"/>
                <div>
                  <span> Voto: {{ element.vote_average }}</span>
                    <font-awesome-icon v-for='index in 5' :key='index' icon="fa-star starSolid"/>
                </div>
            </div>
            <div class="box-img">
                <img :src="image(element.poster_path)" :alt="element.title">
            </div>
        </div>
  </main>
</template>

<script>
import LangFlag from 'vue-lang-code-flags'

export default {
  components: {
    LangFlag
  },
  data () {
    return {
      arrMovie: [],
      arrTv: []
    }
  },
  props: {
    searchMovie: Array,
    scTv: Array,
    foundMovie: String,
    foundTv: String
  },
  methods: {
    image (result) {
      if (result === null) {
        return 'https://picsum.photos/id/2/300/400'
      } else {
        return 'https://image.tmdb.org/t/p/w500' + result
      }
    },
    rating (media) {
      return media * 0.5
    }
  },
  computed: {
    filterTitle () {
      if (this.foundMovie === '' && this.foundTv === '') {
        return this.arrMovie === this.searchMovie && this.arrTv === this.scTv
      } else {
        const result = this.searchMovie.filter(element => element.title.toLowerCase().includes(this.foundMovie.toLowerCase())).concat(this.scTv.filter(element => element.name.toLowerCase().includes(this.foundTv.toLowerCase())))
        console.log(result)
        return result
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
    margin-right: 0.5rem;
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
