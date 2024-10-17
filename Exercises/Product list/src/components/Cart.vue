<script>
import FilledCart from './FilledCart.vue';
export default {
  components: {
    FilledCart
  },
  props: ["cart"],
  emits:['remove-item', 'handle-modal'],
  computed: {
    totalCapacity() {
      return this.cart.reduce((total, dessert) => total + dessert.capacity, 0);
    },
  },
  methods: {
    onRemoveItem(dessert) {
      this.$emit('remove-item', dessert)
    },
    onHandleModal(state) {
      this.$emit('handle-modal', state)
    }
  }
};
</script>

<template>
  <div class="wrapper">
    <h1>Your Cart ({{ totalCapacity }})</h1>
  <span v-if="totalCapacity === 0">Your added items will appear here</span>
    <FilledCart v-else :cart="cart" @remove-item="onRemoveItem" @handle-modal="onHandleModal"/>
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
