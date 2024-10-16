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
    removeItem(dessert) {
      dessert.capacity = 0;
      this.cart = this.cart.filter((item) => item.name !== dessert.name);
    },
    incrementItem(dessert) {
      const item = this.findCartItem(dessert);
      if (item) {
        item.capacity++;
      }
    },
    decrementItem(dessert) {
      const item = this.findCartItem(dessert);
      if (item) {
        if (item.capacity > 1) {
          item.capacity--;
        } else {
          this.removeItem(dessert);
        }
      }
    },
    emptyCart() {
      // forEach
      this.cart = [];
      this.desserts = this.desserts.map((prev) => {
        return { ...prev, capacity: 0 }; 
      });
    },
  },

  provide() {
    return {
      add: this.add,
      removeItem: this.removeItem,
      increment: this.incrementItem,
      decrement: this.decrementItem,
      emptyCart: this.emptyCart,
    };
  },
};
</script>

<template>
  <List :list="desserts" :cart="cart" />
  <Cart :cart="cart" />
</template>
