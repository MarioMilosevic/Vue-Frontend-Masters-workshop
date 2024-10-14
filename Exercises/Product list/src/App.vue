<template>
  <List :list="desserts" />
  <Cart :cart="cart" />
</template>

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
      console.log('add')
      this.cart.push(dessert)
      console.log(this.cart)
    }
  },
  provide() {
    return {
      add:this.add
    }
  }
};
</script>
