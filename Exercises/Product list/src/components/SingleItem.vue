<template>
  <div class="image-container">
    <img
      :src="dessert.image"
      :alt="dessert.image"
      :class="{ selected: dessert.capacity > 0 }"
    />

    <AddToCart
      @add-to-cart="addDessert"
      :dessert="dessert"
      v-if="dessert.capacity === 0"
    />
    <ItemCount :dessert="dessert" v-else />
  </div>
  <div class="dessert-info">
    <h3>{{ dessert.name }}</h3>
    <h2>{{ dessert.description }}</h2>
    <h4>{{ `$${dessert.price.toFixed(2)}` }}</h4>
  </div>
</template>

<script>
import AddToCart from "./AddToCart.vue";
import ItemCount from "./ItemCount.vue";
export default {
  props: ["dessert", "cart"],
  components: {
    AddToCart,
    ItemCount,
  },
  inject: ["add"],
  methods: {
    addDessert() {
      this.add(this.dessert);
    },
  },
};
</script>

<style scoped>
.image-container {
  position: relative;
}

img {
  width: 100%;
}

.dessert-info {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

h3 {
  padding-top: 1rem;
  font-weight: 100;
}

h4 {
  color: #ef4444;
}

.selected {
  border: 3px solid #ef4444;
}
</style>
