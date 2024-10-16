<script>
import { IoCloseCircleOutline } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";
addIcons(IoCloseCircleOutline);
export default {
  components: {
    "v-icon": OhVueIcon,
  },
  emits:['remove-item'],
  props: {
    item: {
      type: Object,
      required:true
    },
    showButton: {
      type: Boolean,
      required: true,
    },
  },
  computed: {
    itemPrice() {
      return this.item.price.toFixed(2)
    },
    totalPrice() {
      return (this.item.price * this.item.capacity).toFixed(2)
    }
  }
};
</script>
<template>
  <div class="wrapper">
    <img v-if="!showButton" :src="item.image" :alt="item.image" />
    <div class="content">
      <h3>{{ item.description }}</h3>
      <div class="summary">
        <span>{{ item.capacity }}x</span>
        <span>@ ${{ itemPrice }}</span>
        <span>@ ${{ totalPrice }}</span>
      </div>
      <v-icon
        v-if="showButton"
        name="io-close-circle-outline"
        class="icon"
        scale="1.4"
        @click="$emit('remove-item', item)"
      />
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  list-style: none;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  position: relative;
  border-bottom: 1px solid black;
  padding-bottom: 8px;
}

img {
  width: 35px;
}

.content {
  display: flex;
  flex-direction: column;
  gap: 0.2rem;
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

h3 {
  font-weight: 500;
}
</style>
