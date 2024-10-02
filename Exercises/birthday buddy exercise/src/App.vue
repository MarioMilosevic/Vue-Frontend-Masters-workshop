<script lang="ts">
import PersonList from './components/PersonList.vue'
import { data } from './utils/constants'

export default {
  data() {
    return {
      peopleList: data 
    }
  },
  components: {
    PersonList 
  }
}
</script>


<template>
  <div class="container">
    <PersonList :list="peopleList" /> 
  </div>
</template>

<style scoped>
.container {
  border: 1px solid black;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
