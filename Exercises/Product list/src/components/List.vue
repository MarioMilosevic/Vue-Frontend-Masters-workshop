<script>
import SingleItem from "./SingleItem.vue";
export default {
  props: ["list", "cart"],
  emits: ["remove-item"],
  components: {
    SingleItem,
  },
  methods: {
    findCartItem(dessert) {
      return this.cart.find((item) => item.name === dessert.name);
    },
    addItem(dessert) {
      const item = this.findCartItem(dessert);
      if (item) {
        item.capacity++;
      } else {
        dessert.capacity = 1;
        this.cart.push(dessert);
      }
    },
    removeItemEmit(dessert) {
      this.$emit("remove-item", dessert);
    },
    incrementItem(dessert) {
      const item = this.findCartItem(dessert);
      if (item) {
        item.capacity++;
      }
    },
    decrementItem(dessert) {
      const item = this.findCartItem(dessert);
      if (item) {
        if (item.capacity > 1) {
          item.capacity--;
        } else {
          this.removeItemEmit(dessert);
        }
      }
    },
  },
};
</script>

<template>
  <div class="wrapper">
    <h1>Desserts</h1>
    <ul class="list">
      <li v-for="dessert in list" :key="dessert.name">
        <SingleItem
          :dessert="dessert"
          :cart="cart"
          @addItem="addItem"
          @removeItem="removeItemEmit"
          @incrementItem="incrementItem"
          @decrementItem="decrementItem"
        />
      </li>
    </ul>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 900px;
}

.list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  list-style: none;
}
</style>
