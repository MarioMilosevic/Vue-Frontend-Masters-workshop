<script lang="ts">
export default {
  data() {
    return {
      name: 'Mario',
    };
  },
};
</script>

<template>
  <div class="container">{{ name }}</div>
</template>

<style scoped>


.container {
  /* background-color: red; */
  border: 1px solid black;
}
</style>
