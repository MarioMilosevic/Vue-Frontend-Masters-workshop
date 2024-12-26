<template>
  <div>
    <input type="text" placeholder="First Name" v-model="fName" />
    <input type="text" placeholder="Last Name" v-model="lName" />
    <h2>Options Fullname is {{ fullName }}</h2>

    <input type="text" placeholder="First Name" v-model="refFirstName" />
    <input type="text" placeholder="Last Name" v-model="refLastName" />
    <h2>Computed Fullname is {{ refFullName }}</h2>
    <input type="text" placeholder="First Name" v-model="reactiveFirstName" />
    <input type="text" placeholder="Last Name" v-model="reactiveLastName" />
    <h2>Reactive Fullname is {{ reactiveFullName }}</h2>
  </div>
</template>
<script lang="ts">
import { ref, reactive, computed, toRefs } from "vue";
export default {
  setup() {
    const refFirstName = ref("");
    const refLastName = ref("");
    const state = reactive({
      reactiveFirstName: "",
      reactiveLastName: "",
    });

    const reactiveFullName = computed(function () {
      return `${state.reactiveFirstName} ${state.reactiveLastName}`;
    });

    const refFullName = computed(function () {
      return `${refFirstName.value} ${refLastName.value}`;
    });

    return {
      refFirstName,
      refLastName,
      refFullName,
      ...toRefs(state),
      reactiveFullName,
    };
  },
  data() {
    return {
      fName: "",
      lName: "",
    };
  },
  computed: {
    fullName() {
      return `${this.fName} ${this.lName}`;
    },
  },
};
</script>
