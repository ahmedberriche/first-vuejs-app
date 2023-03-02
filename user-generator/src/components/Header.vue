<template>
  <header class="header">
    <div class="container">
      <div class="main-content">
        <span>{{ title }}</span>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  name: "Header",
  props: ["title"],
};
</script>
<style scoped>
.header {
  background: #439cfa;
  height: 60px;
  width: 100%;
  color: #fff;
  font-size: 24px;
}
.container {
  /* max-width: 600px; */
  max-width: 80%;
  margin: 0 auto;
  height: 100%;
}
.main-content {
  height: 100%;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
</style>
