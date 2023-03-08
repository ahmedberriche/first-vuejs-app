<template>
  <div class="card">
    <div class="card-profile">
      <img :src="picture" alt="" />
    </div>
    <h2>{{ username }}</h2>
    <h3 v-if="email">email: {{ email }}</h3>
    <button v-on:click="actionButton">generate profile</button>
  </div>
</template>
<script>
export default {
  props: ["email", "picture", "actionButton", "username"],
};
</script>
<style scoped>
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
