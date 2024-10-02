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
      <img :src="person.image" :alt="person.image" class="picture" />
      <div class="information_container">
        <h2 class="fullName">{{ person.fullName }}</h2>
        <h3 class="age">{{ person.age }} years</h3>
      </div>
    </li>
  </ul>
</template>

<style scoped>
.list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.item {
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
  font-weight: 500;
  font-size: 1.5rem;
}

.age {
    font-weight: 300;
    font-size: 1rem;
}
</style>
