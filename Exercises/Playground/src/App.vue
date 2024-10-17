<script>
import Card from "./components/Card.vue";
import NameList from "./components/NameList.vue";
export default {
  name: "App",
  components: {
    NameList,
  },
  data() {
    return {
      name: "",
    };
  },
};
</script>

<template>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.lastName }} {{ slotProps.firstName }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps"> {{ slotProps.firstName }} </template>
  </NameList>
</template>

<style scoped></style>
