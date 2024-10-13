<template>
  <div class="dessert_container">
    <img v-bind:src="dessert.image" v-bind:alt="dessert.image" />
    <div>
      <h2>{{ dessert.name }}</h2>
      <h3>{{ dessert.description }}</h3>
      <h4>{{ dessert.price }}</h4>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dessert: {
        name: "Waffle",
        description: "Waffle with Berries",
        price: 6.5,
        image: "../assets/image-cake-desktop.jpg",
      },
    };
  },
};
</script>

<style scoped>
.dessert_container {
  border: 1px solid black;
}
</style>
