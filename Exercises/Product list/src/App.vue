<template>
  <List :list="desserts"/>
  <Cart :cart="cart"/>
</template>

<script lang="ts">
import { dessertsData } from "./utilities/constants";
import List from "./components/List.vue";
import Cart from "./components/Cart.vue";
export default {
  data() {
    return {
      desserts: dessertsData,
      cart:[]
    };
  },
  components: {
    List,
    Cart
  },
};
</script>
