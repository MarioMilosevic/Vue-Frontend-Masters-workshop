<script>
import CartItem from './CartItem.vue';
import EmptyCart from './EmptyCart.vue';
import FilledCart from './FilledCart.vue';
export default {
  components: {
    CartItem,
    EmptyCart
  },
  props: ["cart"],
  computed: {
    totalCapacity() {
      return this.cart.reduce((total, dessert) => total + dessert.capacity, 0);
    },
  },
};
</script>

<template>
  <div class="wrapper">
    <h1>Your Cart ({{ totalCapacity }})</h1>
    <EmptyCart v-if="totalCapacity === 0"/>
    <FilledCart v-else/>
    <CartItem/>

  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  background-color: #fafafa;
  padding: 1rem;
}
</style>
