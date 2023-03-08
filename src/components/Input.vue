<template>
  <label>{{ label }}</label>
  <input
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
    :placeholder="placeholder"
  />
</template>
<script>
export default {
  name: "Input",
  props: ["label", "placeholder", "modelValue"],
  emits: ["update:modelValue"],
};
</script>
<style scoped>
input {
  width: 100%;
  height: 30px;
  margin-bottom: 20px;
}
label {
  font-size: 16px;
  font-weight: 700;
}
</style>
