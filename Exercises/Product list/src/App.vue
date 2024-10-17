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
    removeItem(dessert) {
      dessert.capacity = 0;
      this.cart = this.cart.filter((item) => item.name !== dessert.name);
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
