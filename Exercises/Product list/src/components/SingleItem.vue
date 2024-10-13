<template>
  <div class="image-container">
    <img :src="dessert.image" :alt="dessert.image" />
    <AddToCart />
  </div>
  <div class="dessert-info">
    <h3>{{ dessert.name }}</h3>
    <h2>{{ dessert.description }}</h2>
    <h4>{{ dessert.price }}</h4>
  </div>
</template>

<script>
export default {
  props: ['dessert'],
};
</script>

<style scoped>
.image-container {
  position: relative;
  background-color: red;
  width: 300px;
}

img {
  width: 100%;
}

.dessert-info {
  border: 1px solid black;
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}
</style>
