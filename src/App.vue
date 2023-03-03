<template>
  <Header title="myFirstApp" />
  <div class="container">
    <div class="main-content">
      <component :is="currentView" />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import CardProfile from "./views/CardProfile.vue";
import TodoTask from "./views/TodoTask.vue";

const routes = {
  "/": CardProfile,
  "/task": TodoTask,
};
export default {
  name: "App",
  components: {
    Header,
    CardProfile,
  },
  data() {
    return {
      currentPath: window.location.hash,
    };
  },
  computed: {
    currentView() {
      console.log("test", this.currentPath.slice(1));
      return routes[this.currentPath.slice(1) || "/"];
    },
  },
  mounted() {
    window.addEventListener("hashchange", () => {
      this.currentPath = window.location.hash;
    });
  },
};
</script>
<style scoped>
.container {
  max-width: 80%;
  margin: 0 auto;
}
.main-content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  background: rgba(192, 192, 192, 0.4);
}
</style>
