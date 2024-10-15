<script>
import CartItem from "./CartItem.vue";
export default {
  components: {
    CartItem,
    },
  props:['cart']
};
</script>

<template>
   <ul class="list">
      <li v-for="item in cart" :key="item.name">
        <CartItem :item="item" />
      </li>
    </ul>
</template>

<style scoped>
ul{
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
}
</style>
