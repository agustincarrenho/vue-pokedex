<template>
  <div id="app">
    <Nav/>
    <Pokemons />
  </div>
</template>

<script>
import Nav from './components/Nav.vue';
import Pokemons from './components/Pokemons.vue';
export default {
  name: 'App',
  components: {
    Pokemons,
    Nav
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
