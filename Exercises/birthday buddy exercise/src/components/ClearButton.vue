<script>
export default {
  props: {
    list: {
      type: Array,
      required: true
    }
  },
  emits: ['clear-all']
}
</script>

<template>
  <button class="button" @click="$emit('clear-all')">Clear All</button>
</template>


