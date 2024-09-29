<script>
export default {
  props: {
    user: {
      name: {
        typeof: Object,
        required: true,
      },
      favoriteFood: {
        typeof: String,
        required: true,
      },
    },
    // name: {
    //     typeof: String,
    //     default:"John Doe"
    // },
    // favoriteFood: {
    //     typeof: String,
    //     default:"Steak"
    // },
  },
  emits: ["change-name"],
};
</script>

<template>
  <h1>User: {{ user.name }}</h1>
  <p>Favorite Food: {{ user.favoriteFood }}</p>
  <button @click="$emit('change-name')">Change name</button>
</template>
