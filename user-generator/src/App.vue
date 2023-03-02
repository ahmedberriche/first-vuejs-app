<template>
  <Header title="myFirstApp" />
  <div class="container">
    <Card />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Card from "./components/Card.vue";
export default {
  name: "App",
  components: {
    Header,
    Card,
  },
};
</script>
<style scoped>
.container {
  max-width: 80%;
  margin: 0 auto;
}
</style>
