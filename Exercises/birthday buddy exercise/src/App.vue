<script lang="ts">
import PersonList from './components/PersonList.vue'
import HeadingTitle from './components/HeadingTitle.vue'
import { data } from './utils/constants'

export default {
  data() {
    return {
      peopleList: data
    }
  },
  components: {
    PersonList,
    HeadingTitle
  }
}
</script>

<template>
  <div class="container">
    <HeadingTitle :list="peopleList" />
    <PersonList :list="peopleList" />
  </div>
</template>

<style scoped>
.container {
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
</style>
