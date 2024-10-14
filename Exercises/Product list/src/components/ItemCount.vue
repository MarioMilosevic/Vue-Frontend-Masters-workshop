<script>
import { CoMinus, CoPlus } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";
addIcons(CoMinus, CoPlus);

export default {
  data() {
    return {
      count: 0, // Fixed syntax error: Changed semicolon to comma
    };
  },
  components: {
    "v-icon": OhVueIcon,
  },
  methods: {
    incrementCount() {
      this.count++;
    },
    decrementCount() {
      this.count--;
    },
  },
};
</script>

<template>
  <div class="wrapper interaction-button">
    <v-icon name="co-minus" class="icon" />
    <h2>{{ count }}</h2>
    <!-- Removed the extra < and > -->
    <v-icon name="co-plus" class="icon" />
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
</style>
