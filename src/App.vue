<script>
import { reactive } from "vue";
export default {
  async setup() {
    const state = reactive({
      userList: [],
    });
    async function fetchUsers() {
      const response = await fetch(
        "http://jsonplaceholder.typicode.com/users"
      ).then((response) => response.json());
      return response;
    }

    state.userList = await fetchUsers();

    return {
      state,
      fetchUsers,
    };
  },
  // data: () => ({
  //   userList: [],
  // }),
};
</script>

<template>
  <Suspense>
    {{ state.userList }}

    <template v-slot:fallback>Data is loading...</template>
  </Suspense>
</template>
