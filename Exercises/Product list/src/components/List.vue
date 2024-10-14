<template>
  <div class="wrapper">
    <h1>Desserts</h1>
    <ul class="list">
      <li v-for="dessert in list" :key="dessert.name">
        <SingleItem :dessert="dessert" :cart="cart"/>
      </li>
    </ul>
  </div>
</template>

<script>
import SingleItem from "./SingleItem.vue";
export default {
  props: ["list", 'cart'],
  components: {
    SingleItem,
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  gap:1rem;
  max-width: 900px;
}

.list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  list-style: none;
}
</style>
