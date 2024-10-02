<script lang="ts">
import PersonList from './components/PersonList.vue'
import HeadingTitle from './components/HeadingTitle.vue'
import ClearButton from './components/ClearButton.vue'
import { data } from './utils/constants'

export default {
  data() {
    return {
      peopleList: data
    }
  },
  components: {
    PersonList,
    HeadingTitle,
    ClearButton
  },
  methods: {
    clearAll() {
      this.peopleList = []
    },
    filterPeople(fullName:string) {
      this.peopleList = this.peopleList.filter((people) => people.fullName !== fullName)
    }
  }
}
</script>

<template>
  <div class="container">
    <HeadingTitle :list="peopleList" />
    <PersonList :list="peopleList" @filter-people="filterPeople"/>
    <ClearButton :list="peopleList" @clear-all="clearAll" />
  </div>
</template>

<style scoped>
.container {
  width: 400px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
</style>
