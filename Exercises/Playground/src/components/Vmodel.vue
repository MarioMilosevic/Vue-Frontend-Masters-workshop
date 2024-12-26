<template>
  <div>
    <!-- Options API -->
    <input type="text" placeholder="First Name" v-model="fName" />
    <input type="text" placeholder="Last Name" v-model="lName" />

    <input type="text" placeholder="Hero Name" v-model="heroName" />
    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />
  </div>
</template>
<script lang="ts">
import { ref, reactive, toRefs } from "vue";
export default {
  setup() {
    const heroName = ref("");
    const state = reactive({
      firstName: "",
      lastName: "",
    });

    return {
      heroName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      fName: "",
      lName: "",
    };
  },
};
</script>
<style></style>
