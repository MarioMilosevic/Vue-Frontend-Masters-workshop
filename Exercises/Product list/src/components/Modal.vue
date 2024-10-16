<template>
  <div v-if="open" class="modal">
    <h1>Order confirmed</h1>
    <h2>We hope you enjoy your food!</h2>
    <ul class="modalList">
      <li v-for="item in cart" :key="item.name">
        <CartItem :item :showButton="false" />
      </li>
    </ul>
    <button @click="$emit('start-new-order')">Start new order</button>
  </div>
</template>

<script>
import CartItem from "./CartItem.vue";
export default {
  name: "Modal",
    props: ["cart", "open"],
    emits: ['start-new-order'],
  components: {
    CartItem,
  },
};
</script>

<style scoped>
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
