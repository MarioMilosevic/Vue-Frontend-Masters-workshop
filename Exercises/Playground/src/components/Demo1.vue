<template>
  <h1>{{ name }}</h1>
</template>

<script lang="ts">
import { ref } from "vue";
export default {
  name: "Demo1",
  setup() {
    const name = ref("Mario");

    setTimeout(() => {
      name.value = "Toni";
    }, 2000);
    return {
      name,
    };
  },
};
</script>

<style lang="scss" scoped></style>
