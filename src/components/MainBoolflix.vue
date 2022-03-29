<template>
  <main>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
  </main>
</template>

<script>
export default {

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
    width: 400px;
    height: 500px;
    background-color: red;
}
</style>
