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
    findCartItem(dessert) {
      return this.cart.find((item) => item.name === dessert.name);
    },
    add(dessert) {
      const item = this.findCartItem(dessert);
      if (item) {
        item.capacity++;
      } else {
        dessert.capacity = 1;
        this.cart.push(dessert);
      }
    },
    incrementItem(dessert) {
      const item = this.findCartItem(dessert);
      if (item) {
        item.capacity++;
      }
    },
    decrementItem(dessert) {
      const item = this.findCartItem(dessert);
      if (item && item.capacity > 1) {
        item.capacity--;
      }
    },
  },

  provide() {
    return {
      add: this.add,
      increment: this.incrementItem,
      decrement: this.decrementItem,
    };
  },
};
</script>

<template>
  <List :list="desserts" :cart="cart" />
  <Cart :cart="cart" />
</template>
