<script>
export default {
  props: {
    list: Array
  }
}
</script>

<template>
  <div class="heading">
    <h1>{{ list.length }}</h1>
    <p>Birthdays Today</p>
  </div>
</template>

<style scoped>
.heading {
    display: flex;
    align-items: center;
    gap: 1rem;
}
</style>
