<template>
  <header class="header">
    <img class="imagen-logo" src="..\assets\logo_pokemon.png" alt="">
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .imagen-logo {
    height: 100%;
    object-fit: cover;
    object-position: center center;
  }
</style>
