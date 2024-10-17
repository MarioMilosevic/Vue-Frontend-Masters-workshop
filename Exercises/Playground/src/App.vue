<script>
import Card from "./components/Card.vue";
export default {
  name: "App",
  components: {
    Card,
  },
  data() {
    return {
      name: "",
    };
  },
};
</script>

<template>
  <Card></Card>
  <Card>Card content</Card>
  <Card><h2>Card content</h2></Card>
  <Card><img src="https://picsum.photos/200" alt="some picture" /></Card>

  <Card>
    <template v-slot:header> Header </template>
    <template v-slot:footer> Footer </template>
    <template v-slot:default>
      Default
    </template>
  </Card>
</template>

<style scoped></style>
