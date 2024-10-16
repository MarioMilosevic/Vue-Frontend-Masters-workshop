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
  inject: ["emptyCart"],
  methods: {
    startNewOrder() {
      this.emptyCart(), (this.open = false);
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
      <CartItem :item="item" :showButton="true" />
    </li>
  </ul>
  <div class="total">
    <h3>Order Total:</h3>
    <h2>{{ `$${totalPrice}` }}</h2>
  </div>

  <button @click="open = true">Confirm order</button>

  <Teleport to="body">
    <div v-if="open" class="modal">
      <h1>Order confirmed</h1>
      <h2>We hope you enjoy your food!</h2>
      <ul class="modalList">
        <li v-for="item in cart" :key="item.name">
          <CartItem :item :showButton="false" />
        </li>
      </ul>
      <button @click="startNewOrder()">Start new order</button>
      <!-- <button @click="open = false">Start new order</button> -->
    </div>
  </Teleport>
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

.modal {
  border: 1px solid black;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 500px;
  height: 500px;
  background-color: white;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.modalList {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
