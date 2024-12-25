<template>
  <h2>{{ firstName }} {{ lastName }}</h2>
</template>

<script lang="ts">
import { reactive, toRefs } from "vue";
export default {
  name: "Demo2",
  setup() {
    const state = reactive({
      firstName: "Bruce",
      lastName: "Wayne",
    });

    setTimeout(() => {
        state.firstName = "Clark",
        state.lastName = "Kent"
    }, 2000);

    return toRefs(state)

 
  },
};
</script>

<style scoped></style>
