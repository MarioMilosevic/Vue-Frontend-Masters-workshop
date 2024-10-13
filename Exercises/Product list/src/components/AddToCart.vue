<template>
  <button>
    <v-icon name="co-cart" />
    Add to cart
  </button>
</template>

<script>
import { CoCart } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";

addIcons(CoCart);

export default {
  components: {
    "v-icon": OhVueIcon,
  },
};
</script>

<style scoped>
button {
  padding: 10px 20px;
  border-radius: 20px;
  border: none;
  cursor: pointer;
  position: absolute;
  bottom: -4%;
  transform: translateX(-50%);
  left: 50%;
}
button:hover {
  color: #ef4444;
}
</style>
