<script>
export default {
  props: ["cart"],
  computed: {
    totalCapacity() {
      return this.cart.reduce((total, dessert) => total + dessert.capacity, 0);
    },
  },
};
</script>

<template>
  <div class="wrapper">
    <h1>Your Cart ({{ totalCapacity }})</h1>
    <span>Your added items will appear here</span>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
