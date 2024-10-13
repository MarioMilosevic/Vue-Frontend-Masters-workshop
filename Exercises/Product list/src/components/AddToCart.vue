<template>
  <button>
    <v-icon name="co-cart" class="icon"/>
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
  /* border: none; */
  border: 1px solid #6b7280;
  cursor: pointer;
  position: absolute;
  bottom: -4%;
  transform: translateX(-50%);
  left: 50%;
}
button:hover {
  color: #ef4444;
  border-color: #ef4444;
}

.icon {
    color: #ef4444;
}
</style>
