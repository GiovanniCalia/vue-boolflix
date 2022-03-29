<template>
  <header>
      <h1>boolflix</h1>
      <input type="text" placeholder="digita qui">
  </header>
</template>

<script>
export default {

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

</style>
