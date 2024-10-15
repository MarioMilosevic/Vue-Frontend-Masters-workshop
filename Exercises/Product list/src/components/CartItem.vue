<script>
import { IoCloseCircleOutline } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";
addIcons(IoCloseCircleOutline);
export default {
  components: {
    "v-icon": OhVueIcon,
  },
};
</script>
<template>
  <li>
    <h2>Waffle with Berries</h2>
    <div class="summary">
      <span>2x</span>
      <span>@ $7.00</span>
      <span>@ $14.00</span>
    </div>
    <v-icon name="io-close-circle-outline" class="icon"  />
  </li>
</template>

<style scoped>
li {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  position: relative;
  /* border: 1px solid black; */
 padding: 0;
}

.summary {
    display: flex;
    gap: 0.6rem;
}

.icon {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    right: -10%;
    cursor: pointer;
}
</style>
