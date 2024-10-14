<script>
import { CoCart } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";

addIcons(CoCart);

export default {
  components: {
    "v-icon": OhVueIcon,
  },
  emits: ["add-to-cart"],
};
</script>

<template>
  <button @click="$emit('add-to-cart')" class="interaction-button">
    <v-icon name="co-cart" class="icon" />
    Add to cart
  </button>
</template>

<style scoped>
button:hover {
  color: #ef4444;
  border-color: #ef4444;
}

.icon {
  color: #ef4444;
}
</style>
