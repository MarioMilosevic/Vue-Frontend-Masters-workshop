<template>
  <div>
    <h2>{{ name }}</h2>
    <button @click="setName">Change Name</button>
    <h2>{{ firstName }} {{ lastName }}</h2>
    <button @click="changeHero">Change Hero</button>
  </div>
</template>

<script lang="ts">
import { ref, reactive, toRefs } from "vue";
export default {
  setup() {
    const name = ref("Mario");
    const state = reactive({
      firstName: "Bruce",
      lastName: "Wayne",
    });
    const setName = () => {
      name.value = "Toni";
        };

        function changeHero() {
            state.firstName = "Clark",
            state.lastName = "Kent"
        }

    return {
      name,
      setName,
        ...toRefs(state),
      changeHero
    };
  },
};
</script>
