<script>
import CartItem from "./CartItem.vue";
export default {
  components: {
    CartItem,
    },
  props: ['cart'],
  computed: {
    totalPrice() {
      return this.cart.reduce((total, dessert) => total + dessert.price, 0).toFixed(2)
    }
  },

};
</script>

<template>
   <ul class="list">
      <li v-for="item in cart" :key="item.name">
        <CartItem :item="item" />
      </li>
    </ul>
    <div class="total">
      <h3>Order Total</h3>
      <h2>{{`$${totalPrice}`}}</h2>
    </div>

    <button>Confirm order</button>
</template>

<style scoped>
ul{
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
}
.total {
  border: 1px solid black;
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
