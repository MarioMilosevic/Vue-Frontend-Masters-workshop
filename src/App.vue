<script>
// const url = "https://pokeapi.co/api/v2/pokemon?limit=151";
import BaseButton from "./components/BaseButton.vue";
import BaseLayout from "./components/BaseLayout.vue";

export default {
  components: {
    BaseButton,
    BaseLayout,
  },
  // setup() {
  // },
  // data: () => ({
  //   pokedex: [1, 2, 3],
  // }),
  // methods: {
  //   async fetchPokemon() {
  //     this.pokedex = await fetch(url).then((response) => response.json());
  //   },
  // },
  // beforeCreate() {
  //   console.log("Before create");
  // },
  // created() {
  //   console.log("Create");
  //   console.log(this.pokedex);
  // },
};
</script>

<template>
  <BaseLayout>
    <template v-slot:main>Main </template>
    <template v-slot:footer>Footer </template>
    <template v-slot:sidebar>Aside </template>
  </BaseLayout>

</template>
