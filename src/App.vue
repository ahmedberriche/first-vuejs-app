<template>
  <Header title="myFirstApp" />
  <div class="container">
    <CardProfile />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import CardProfile from "./views/CardProfile.vue";
import TodoTask from "./views/TodoTask.vue";

// const routes = {
//   "/": CardProfile,
//   "/task": TodoTask,
// };
export default {
  name: "App",
  components: {
    Header,
    CardProfile,
  },
};
</script>
<style scoped>
.container {
  max-width: 80%;
  margin: 0 auto;
}
</style>
