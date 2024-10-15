<script>
import { IoCloseCircleOutline } from "oh-vue-icons/icons";
import { OhVueIcon, addIcons } from "oh-vue-icons";
addIcons(IoCloseCircleOutline);
export default {
  components: {
    "v-icon": OhVueIcon,
  },
  props: {
    item: {
      name: {
        type: String,
        required: true,
      },
      description: {
        type: String,
        required: true,
      },
      capacity: {
        type: Number,
        required: true,
      },
      image: {
        type: String,
        required: false,
      },
      price: {
        type: Number,
        required: true,
      },
    },
    showButton: {
      type: Boolean,
      required: true,
    },
  },
  inject: ["removeItem"],
  methods: {
    deleteItem() {
      this.removeItem(this.item);
    },
  },
};
</script>
<template>
  <div class="wrapper">
    <img v-if="!showButton" :src="item.image" :alt="item.image" />
    <div class="content">
      <h3>{{ item.description }}</h3>
      <div class="summary">
        <span>{{ item.capacity }}x</span>
        <span>@ ${{ item.price.toFixed(2) }}</span>
        <span>@ ${{ (item.price * item.capacity).toFixed(2) }}</span>
      </div>
      <v-icon
        v-if="showButton"
        name="io-close-circle-outline"
        class="icon"
        scale="1.4"
        @click="deleteItem"
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
