<template>
  <div class="buttons">
    <HoldButton
      @click-event="decrement"
      @mouse-down-event="startInterval(decrement)"
      @mouse-up-event="stopInterval"
      @mouse-leave-event="stopInterval"
      >-</HoldButton
    >
    <h2>{{ count }}</h2>
    <HoldButton
      @click-event="increment"
      @mouse-down-event="startInterval(increment)"
      @mouse-up-event="stopInterval"
      @mouse-leave-event="stopInterval"
      >+</HoldButton
    >
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import HoldButton from "./components/HoldButton.vue";

const count = ref(0);
let intervalId = null;
const timeoutId = null;

const increment = () => {
  console.log("increment");
  count.value++;
};

const decrement = () => {
  count.value--;
};

const startInterval = (cb) => {
  if (!intervalId) {
    intervalId = setInterval(cb, 1000);
  }
};

const stopInterval = () => {
  clearInterval(intervalId);
  intervalId = null;
};
</script>

<style scoped>
.buttons {
  display: flex;
  align-items: center;
  gap: 1rem;
}
</style>
