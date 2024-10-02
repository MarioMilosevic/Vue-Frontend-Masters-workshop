<script>
export default {
  props: {
    list: {
      type: Array,
      required: true
    }
  },
  methods: {
    clearAll() {}
  }
}
</script>

<template>
  <button class="button">Clear All</button>
</template>

<style scoped>
.button {
  background-color: darkmagenta;
  color: aliceblue;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  cursor: pointer;
}
</style>
