<template>
  <button
    @click="emits('click-event')"
    @mousedown="emits('mouse-down-event')"
    @mouseup="emits('mouse-up-event')"
    @mouseleave="emits('mouse-leave-event')"
  >
    <slot />
  </button>
</template>

<script setup lang="ts">
const emits = defineEmits([
  "click-event",
  "mouse-down-event",
  "mouse-up-event",
  "mouse-leave-event",
]);
</script>

<style scoped></style>
