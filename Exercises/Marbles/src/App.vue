<template>
  <div class="buttons">
    <HoldButton
      @click-event="decrement"
      @mouse-down-event="mouseDownHandler(decrement)"
      @mouse-up-event="stopInterval"
      @mouse-leave-event="stopInterval"
      >-</HoldButton
    >
    <h2>{{ count }}</h2>
    <HoldButton
      @click-event="increment"
      @mouse-down-event="mouseDownHandler(increment)"
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

const increment = () => {
  count.value++;
};

const decrement = () => {
  count.value--;
};

const stopInterval = () => {
  clearInterval(intervalId);
  intervalId = null;
};


const mouseDownHandler = (cb) => {
  cb()
  if (!intervalId) {
    setTimeout(() => {
      intervalId = setInterval((cb), 100);
    }, 500);
}
}

</script>

<style scoped>
.buttons {
  display: flex;
  align-items: center;
  gap: 1rem;
}
</style>
