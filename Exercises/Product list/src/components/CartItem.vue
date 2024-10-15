<script>
import { IoCloseCircleOutline } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";
addIcons(IoCloseCircleOutline);
export default {
  components: {
    "v-icon": OhVueIcon,
    },
    props: ['item'],
    mounted() {
    console.log(this.item)
  }
};
</script>
<template>
  <li>
    <h3>{{ item.description }}</h3>
    <div class="summary">
      <span>{{item.capacity}}x</span>
      <span>@ ${{ item.price.toFixed(2) }}</span>
      <span>@ ${{ (item.price * item.capacity).toFixed(2) }}</span>
    </div>
    <v-icon name="io-close-circle-outline" class="icon" scale="1.4"/>
  </li>
</template>

<style scoped>
li {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  position: relative;
  border-bottom: 1px solid black;
  padding-bottom: 8px;
}

.summary {
  display: flex;
  gap: 0.6rem;
}

.icon {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: -5%;
  cursor: pointer;
}
</style>
