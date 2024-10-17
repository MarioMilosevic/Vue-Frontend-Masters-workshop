<script>
import AddToCart from "./AddToCart.vue";
import ItemCount from "./ItemCount.vue";
export default {
  props: ["dessert", "cart"],
  emits: ["addItem", "removeItem", "incrementItem", "decrementItem"],
  components: {
    AddToCart,
    ItemCount,
  },
};
</script>

<template>
  <li class="image-container">
    <img
      :src="dessert.image"
      :alt="dessert.image"
      :class="{ selected: dessert.capacity > 0 }"
    />

    <AddToCart
      v-if="dessert.capacity === 0"
      @add-to-cart="$emit('addItem', dessert)"
      :dessert="dessert"
    />
    <ItemCount
      v-else
      :dessert="dessert"
      @increment-item="$emit('incrementItem', dessert)"
      @decrement-item="$emit('decrementItem', dessert)"
    />
  </li>
  <div class="dessert-info">
    <h3>{{ dessert.name }}</h3>
    <h2>{{ dessert.description }}</h2>
    <h4>{{ `$${dessert.price.toFixed(2)}` }}</h4>
  </div>
</template>
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
  outline: 3px solid #ef4444;
}
</style>
