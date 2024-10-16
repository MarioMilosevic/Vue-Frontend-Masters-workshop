<script>
import CartItem from "./CartItem.vue";
export default {
  name: "Modal",
  props: ["cart", "isModalOpen"],
  emits: ["empty-cart"],
  components: {
    CartItem,
  },
};
</script>

<template>
  <div v-if="isModalOpen" class="overlay">
    <div class="modal">
      <h1>Order confirmed</h1>
      <h2>We hope you enjoy your food!</h2>
      <ul class="modalList">
        <li v-for="item in cart" :key="item.name">
          <CartItem :item :showButton="false" />
        </li>
      </ul>
      <button @click="$emit('empty-cart')">Start New Order</button>
    </div>
  </div>
</template>

<style scoped>
.overlay {
  z-index: 10;
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
  backdrop-filter: blur(3px);
  opacity: 1;
}

.modal {
  z-index: 20;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 500px;
  height: 500px;
  background-color: white;
  padding: 1rem 1.2rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 1rem;
}

.modalList {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

h2 {
  font-weight: 300;
}

button {
  background-color: #ef4444;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  cursor: pointer;
  color: white;
  font-size: 1rem;
}

button:hover {
  background-color: red;
}
</style>
