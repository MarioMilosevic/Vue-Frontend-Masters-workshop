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
      this.isModalOpen = false;
    },
    handleModal(state) {
      this.isModalOpen = state;
    },
  },
};
</script>

<template>
  <List :list="desserts" :cart="cart" @remove-item="removeItem" />
  <Cart :cart="cart" @remove-item="removeItem" @handle-modal="handleModal" />
  <Modal :isModalOpen="isModalOpen" :cart="cart" @empty-cart="emptyCart" />
</template>
