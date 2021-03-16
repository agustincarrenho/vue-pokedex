<template>
    <div class="container">
      <div v-for="pokemon in pokemons" :key="pokemon" class="item">
        <Pokemon :name="pokemon.name" :image="`${imageUrl+pokemon.id}.png`" />
      </div>
    </div>
</template>

<script>
import Pokemon from "./Pokemon.vue";

export default {
  components: { Pokemon },
  name: "Pokemons",
  data() {
    return {
      pokemons: [],
      pokeImage: [],
      imageUrl : 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/'
    };
  },
  mounted: function () {
    fetch("https://pokeapi.co/api/v2/pokemon")
      .then((response) => response.json())
      .then((data) => {
        data.results.forEach((pokemon) => {
          pokemon.id = pokemon.url
            .split("/")
            .filter(function (part) {
              return !!part;
            })
            .pop();
          this.pokemons.push(pokemon);
        });
      });
  },
};
</script>


<style >
.container {
  display: grid;
  grid-template-columns: auto auto auto auto;
  padding: 10px;
}

.item {
  padding: 20px;
}
.nav {
  display: flex;
  background-color: red;
  height: 15vh;
  align-items: center;
  justify-content: center;
}
.nav ul {
  display: flex;
  width: 100%;
}

.nav li {
  list-style: none;
  margin: auto;
}
</style>