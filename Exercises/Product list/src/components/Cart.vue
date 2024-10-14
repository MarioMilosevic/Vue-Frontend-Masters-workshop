<script>
export default {
  props: ["cart"],
};
</script>

<template>
  <div class="wrapper">
    <h1>Your Cart ({{ cart.length }})</h1>
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
