<template>
  <button :class="customClass" @click="handleClick">{{ text }}</button>
</template>
<script>
export default {
  name: "Button",
  props: ["text", "customClass", "handleClick"],
};
</script>
<style scoped>
button {
  background: #05a32c;
  padding: 10px 15px;
  color: #fff;
  border: none;
  font-size: 16px;
  border-radius: 10px;
}
</style>
