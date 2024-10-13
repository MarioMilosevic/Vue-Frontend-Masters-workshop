<template>
  <ul>
    <li v-for="dessert in desserts" :key="dessert.name">
      <img v-bind:src="dessert.image" v-bind:alt="dessert.image" />
      <div>
        <h2>{{ dessert.name }}</h2>
        <h3>{{ dessert.description }}</h3>
        <h4>{{ dessert.price }}</h4>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">
import { dessertsData } from "./utilities/constants";
import SingleDesert from "./components/single-desert.vue";
console.log(dessertsData);
export default {
  data() {
    return {
      desserts: dessertsData,
    };
  },
  components: {
    SingleDesert,
  },
};
</script>
