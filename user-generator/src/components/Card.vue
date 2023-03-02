<template>
  <div class="main-content">
    <div class="card">
      <div class="card-profile">
        <img :src="picture" alt="" />
      </div>
      <h2>{{ username }}</h2>
      <h3>email: {{ email }}</h3>
      <button v-on:click="getUser">generate profile</button>
    </div>
  </div>
</template>
<script>
import defaultUserImg from "../assets/images/default-user.jpg";
const API_URL = "https://randomuser.me/api";
export default {
  data() {
    return {
      username: "username",
      email: "email",
      picture: API_URL,
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
      this.picture = results[0].picture.large || defaultUserImg;
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
.card {
  border: 1px solid #fff;
  padding: 15px 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  min-width: 250px;
  max-width: 350px;
  background-color: #fff;
  border-radius: 15px;
}
.card-profile img {
  height: 80px;
  width: 80px;
  border-radius: 50%;
}
.card button {
  background-color: #439cfa;
  padding: 10px;
  color: #fff;
  outline: none;
  border: none;
}
</style>
