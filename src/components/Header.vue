<template>
  <header class="header">
    <div class="container">
      <div class="main-content">
        <span>{{ title }}</span>
        <article>
          <a href="#/">Card Profile</a> <a href="#/task">Task tracker</a>
        </article>
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
  justify-content: space-between;
  align-items: center;
}
.main-content a {
  text-decoration: none;
  color: #fff;
}
.main-content a:not(:last-child) {
  margin-right: 10px;
}
</style>
