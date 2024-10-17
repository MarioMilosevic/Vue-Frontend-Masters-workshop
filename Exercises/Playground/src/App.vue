<script>
import CustomInput from './components/CustomInput.vue';

export default {
  name: "App",
  components: {
    CustomInput
  },
  data() {
    return {
      name:""
    };
  },
};
</script>

<template>
  <CustomInput v-model="name"/>
</template>

<style scoped></style>
