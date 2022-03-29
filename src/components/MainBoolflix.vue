<template>
  <main>
      <div class="box" v-for='element in searchMovie' :key='element'>
          <div>{{ element.title }}</div>
      </div>
  </main>
</template>

<script>
export default {
  props: {
    searchMovie: String
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
    width: 300px;
    height: 400px;
    background-color: red;
}
</style>
