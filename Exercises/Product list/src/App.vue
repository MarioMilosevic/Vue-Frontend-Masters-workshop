<template>
  <List :list="desserts"/>
</template>

<script lang="ts">
import { dessertsData } from "./utilities/constants";
import List from "./components/List.vue";
export default {
  data() {
    return {
      desserts: dessertsData,
    };
  },
  components: {
    List,
  },
};
</script>
