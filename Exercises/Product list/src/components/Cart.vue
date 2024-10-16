<script>
import EmptyCart from './EmptyCart.vue';
import FilledCart from './FilledCart.vue';
export default {
  components: {
    EmptyCart,
    FilledCart
  },
  props: ["cart"],
  emits:['remove-item'],
  computed: {
    totalCapacity() {
      return this.cart.reduce((total, dessert) => total + dessert.capacity, 0);
    },
  },
  methods: {
    onRemoveItem(dessert) {
      this.$emit('remove-item', dessert)
    }
  }
};
</script>

<template>
  <div class="wrapper">
    <h1>Your Cart ({{ totalCapacity }})</h1>
    <EmptyCart v-if="totalCapacity === 0"/>
    <FilledCart v-else :cart="cart" @remove-item="onRemoveItem"/>
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
