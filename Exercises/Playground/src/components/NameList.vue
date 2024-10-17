<script>
export default {
  name: "NameList",
  data() {
    return {
      names: [
        {
          firstName: "Bruce",
          lastName: "Wayne",
        },
        {
          firstName: "Peter",
          lastName: "Parker",
        },
        {
          firstName: "Bruce",
          lastName: "Banner",
        },
      ],
    };
  },
};
</script>
<template>
  <ul>
    <li v-for="name in names" :key="name.firstName">
      <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
    </li>
  </ul>
</template>

<style scoped>
ul {
  list-style: none;
}
</style>
