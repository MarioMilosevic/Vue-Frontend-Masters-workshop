<script>
const url = "https://pokeapi.co/api/v2/pokemon?limit=151";
export default {
  data: () => ({
    pokedex: [1, 2, 3],
  }),
  methods: {
    async fetchPokemon() {
      this.pokedex = await fetch(url).then((response) => response.json());
    },
  },
  beforeCreate() {
    console.log("Before create");
    console.log(this.pokedex);
  },
  created() {
    console.log("Create");
    console.log(this.pokedex);
    this.fetchPokemon()
  },
};
</script>

<template>
  <pre>
    {{ pokedex }}
  </pre>
  <button @click="fetchPokemon">fetch</button>
</template>
