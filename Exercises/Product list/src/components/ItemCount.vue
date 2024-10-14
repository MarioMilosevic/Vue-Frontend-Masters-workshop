<script>
import { CoMinus, CoPlus } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";
addIcons(CoMinus, CoPlus);

export default {
  props: ["dessert"],
  components: {
    "v-icon": OhVueIcon,
  },
  inject: ["increment", "decrement"],
  methods: {
    incrementDessert() {
      this.increment(this.dessert);
    },
    decrementDessert() {
      this.decrement(this.dessert);
    },
  },
};
</script>

<template>
  <div class="wrapper interaction-button">
    <v-icon name="co-minus" class="icon" @click="decrementDessert" />
    <h2>{{ dessert.capacity }}</h2>
    <v-icon name="co-plus" class="icon" @click="incrementDessert" />
  </div>
</template>

<style scoped>
.wrapper {
  background-color: #ef4444;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 50%;
}

.icon {
  cursor: pointer;
  border-radius: 9999px;
}
.icon:active {
  background-color: white;
}
</style>
