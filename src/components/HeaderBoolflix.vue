<template>
  <header>
      <h1>boolflix</h1>
      <div>
          <input type="text" placeholder="Digita qui" v-model='search'>
          <button @click="$emit('pass-movie', search)">Cerca</button>
      </div>
  </header>
</template>

<script>
export default {
  data () {
    return {
      search: ''
    }
  }
}

</script>

<style scoped lang="scss">
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: black;
    padding: 1rem;
}

h1{
    text-transform: uppercase;
    color: red;
}

input{
    padding: 0.5rem;
    width: 200px;
}
 button{
     padding: 0.5rem;
     background-color: red;
 }

</style>
