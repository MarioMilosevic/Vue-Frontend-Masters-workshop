<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    list: {
      type: Array,
      required: true
    }
  }
})
</script>

<template>
  <ul class="list">
    <li v-for="(person, index) in list" :key="index" class="item">
      <img :src="person.image" alt="image" class="picture" />
      <h2 class="fullName">{{ person.fullName }}</h2>
    </li>
  </ul>
</template>

<style scoped>
.list {
  list-style: none;
}

.item {
    border: 1px solid black;
    display: flex;
    align-items: center;
    gap: 1rem;
}

.picture {
    object-fit: cover;
  width: 50px;
  height: 50px;
  border-radius: 9999px;
}

.fullName {
    font-weight: 600;
    font-size: 1.5rem;
}
</style>
