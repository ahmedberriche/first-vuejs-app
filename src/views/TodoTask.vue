<template>
  <div class="main-content">
    <div class="task-container">
      <div class="header">
        Task Tracker
        <span><Button text="Add Task" :handleClick="handleAddTask" /></span>
      </div>
      <div v-if="addTask" class="task-input">
        <Input label="Task" placeholder="add task" v-model="taskText" />
        <div class="task-action-btn">
          <Button
            text="save task"
            :customClass="customBtn"
            :handleClick="onAddTask"
          />
        </div>
      </div>

      <div v-for="(task, index) in tasks" class="task-list">
        <Task
          :onDelete="handleDelete"
          :createdAt="task.createdAt"
          :title="task.title"
          :index="index"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
import Task from "../components/Task.vue";
import Input from "../components/Input.vue";
export default {
  name: "TodoTask",
  components: {
    Button,
    Task,
    Input,
  },
  methods: {
    handleDelete(id) {
      let newTasks = [...this.tasks];

      console.log("deleting ...", newTasks.splice(id, 1));
      this.tasks = newTasks.splice(id, 1);
    },

    onAddTask() {
      if (!this.taskText) return;
      let newTask = { title: this.taskText, createdAt: "1" };
      this.tasks = [...this.tasks, newTask];
      this.taskText = "";
    },
    handleAddTask() {
      this.addTask = !this.addTask;
    },
  },
  data() {
    return {
      addTask: false,
      tasks: [],
      customBtn: "task-action-btn",
      taskText: "",
    };
  },
};
</script>
<style>
.task-container {
  border: 1px solid #fff;
  padding: 15px 10px;
  width: 350px;
  background-color: #fff;
  border-radius: 10px;
}
.task-container .header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  font-size: 20px;
}
.task-list:not(:last-child) {
  margin-bottom: 10px;
}
.task-action-btn button {
  width: 100%;
  background: #6e6060;
}
.task-action-btn {
  margin-bottom: 20px;
}
</style>
