<template>
  <div class="main-content">
    <Card
      :username="username"
      :email="email"
      :actionButton="getUser"
      :picture="picture"
    />
  </div>
</template>

<script>
import defaultUserImg from "../assets/images/default-user.jpg";
import Card from "../components/Card.vue";
const API_URL = "https://randomuser.me/api";
export default {
  name: "CardProfile",
  components: {
    Card,
  },
  data() {
    return {
      username: "",
      email: "",
      picture: defaultUserImg,
    };
  },
  created() {
    // fetch on init
    this.getUser();
  },
  methods: {
    async getUser() {
      const url = `${API_URL}`;
      const { results } = await (await fetch(url)).json();
      this.username = results[0].name.first + " " + results[0].name.last;
      this.email = results[0].email;
      this.picture = results[0].picture.large;
    },
  },
};
</script>
<style scoped>
.main-content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  background: rgba(192, 192, 192, 0.4);
}
</style>
