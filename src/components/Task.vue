<template>
  <div class="task" :key="index">
    <div class="task-title">
      {{ title }}
      <button @click="onDelete(index)">remove</button>
    </div>
    <p style="font-weight: 400">{{ createdAt }}</p>
  </div>
</template>
<script>
export default {
  name: "Task",
  props: ["onDelete", "createdAt", "title", "index"],
};
</script>
<style scoped>
.task {
  padding: 15px;
  background: #cfd4d0;
  border-left: 5px solid #05a32c;
}
.task-title {
  font-size: 16px;
  font-weight: 700;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.task button {
  background: #f75757;
  padding: 5px 10px;
  color: #fff;
  border: none;
  font-size: 15px;
  border-radius: 10px;
  margin-left: 15px;
  float: right;
}
</style>
