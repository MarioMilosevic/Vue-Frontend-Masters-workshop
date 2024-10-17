<script>
export default {
  name: "Input",
  props: {
    modelValue: String,
  },
};
</script>

<template>
  <input
    type="text"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>

<style scoped>
input[type="text"] {
  padding: 6px 12px;
  color: #555;
  background-color: #fff;
  border-radius: 4px;
}
</style>
