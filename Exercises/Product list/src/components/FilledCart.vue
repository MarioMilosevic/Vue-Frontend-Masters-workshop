<script>
import CartItem from "./CartItem.vue";
export default {
  data() {
    return {
      open: false,
    };
  },
  components: {
    CartItem,
  },
  props: ["cart"],
  emits: ["remove-item", "handle-modal"],
  methods: {
    startNewOrder() {
      this.emptyCart(), (this.open = false);
    },
    onRemoveItem(dessert) {
      this.$emit("remove-item", dessert);
    },
  },
  computed: {
    totalPrice() {
      return this.cart
        .reduce((total, dessert) => total + dessert.price * dessert.capacity, 0)
        .toFixed(2);
    },
  },
};
</script>

<template>
  <ul class="cartList">
    <li v-for="item in cart" :key="item.name">
      <CartItem :item="item" :showButton="true" @remove-item="onRemoveItem" />
    </li>
  </ul>
  <div class="total">
    <h3>Order Total:</h3>
    <h2>{{ `$${totalPrice}` }}</h2>
  </div>

  <button @click="$emit('handle-modal',true)">Confirm order</button>
</template>

<style scoped>
.cartList {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.total {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

button {
  background-color: #ef4444;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  cursor: pointer;
}

button:hover {
  background-color: red;
}
</style>
