<script lang="ts">
import { dessertsData } from "./utilities/constants";
import List from "./components/List.vue";
import Cart from "./components/Cart.vue";

export default {
  components: {
    List,
    Cart,
  },
  data() {
    return {
      desserts: dessertsData,
      cart: [],
    };
  },
  methods: {
    add(dessert) {
      this.cart.push(dessert);
    },
  },
  provide() {
    return {
      add: this.add,
    };
  },
};
</script>

<template>
  <List :list="desserts" :cart="cart"/>
  <Cart :cart="cart" />
</template>