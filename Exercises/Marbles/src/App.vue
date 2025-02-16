<template>
  <!-- <div>
    <router-link :to="{path:'/user', query:{param1:'test1'}}">Home</router-link>
  </div> -->
  <div class="buttons">
    <button @click="startInterval">-</button>
    <h2>{{ count }}</h2>
    <button @click="startInterval" @mousedown="mouseDown" @mouseup="stopInterval">+</button>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue"

const count = ref(0)
let intervalId = null
const timeoutId = null

const increment = () => {
  count.value++
}

const startInterval = () => {
  if (!intervalId) {
    intervalId = setInterval(increment, 1000)
  }
}

const stopInterval = () => {
  clearInterval(intervalId)
  intervalId = null
}

const mouseDown = () => {
  if (!timeoutId) {
    setTimeout(() => {
      startInterval()
    }, 500)
  }
  console.log("mis dole")
}
</script>

<style scoped>
.buttons {
  display: flex;
  align-items: center;
  gap: 1rem;
}
</style>
