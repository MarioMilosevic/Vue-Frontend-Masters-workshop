<template>
  <h1>Desserts</h1>
  <ul class="list">
    <li v-for="dessert in list" :key="dessert.name">
      <SingleItem :dessert="dessert" />
    </li>
  </ul>
</template>

<script>
import SingleItem from "./SingleItem.vue";
export default {
  props: ["list"],
  components: {
    SingleItem,
  },
};
</script>

<style scoped>
.list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  list-style: none;
  max-width: 1200px;
}
</style>
