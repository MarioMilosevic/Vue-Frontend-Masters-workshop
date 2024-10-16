<script lang="ts">
import { dessertsData } from "./utilities/constants";
import List from "./components/List.vue";
import Cart from "./components/Cart.vue";
import Modal from "./components/Modal.vue";

export default {
  components: {
    List,
    Cart,
    Modal,
  },
  data() {
    return {
      desserts: dessertsData,
      cart: [],
      isModalOpen: false,
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
      this.desserts.forEach((dessert) => (dessert.capacity = 0));
      this.cart = [];
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
  <Modal :isModalOpen="isModalOpen" :cart="cart" @start-new-order="emptyCart" />
</template>
