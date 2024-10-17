<script>
import { CoMinus, CoPlus } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";
addIcons(CoMinus, CoPlus);

export default {
  props: ["dessert"],
  components: {
    "v-icon": OhVueIcon,
  },
  emits: ["increment-item", "decrement-item"],
};
</script>

<template>
  <button class="wrapper interaction-button">
    <v-icon name="co-minus" class="icon" @click="$emit('decrement-item')" />
    <h2>{{ dessert.capacity }}</h2>
    <v-icon name="co-plus" class="icon" @click="$emit('increment-item')" />
  </button>
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
