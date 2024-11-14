<template>
  <div id="app" class="todo-container">
    <h1>Daftar Tugas Yang Harus Dikerjakan</h1>
    <input
      type="text"
      v-model="newTask"
      placeholder="Tambahkan tugas baru"
      @keyup.enter="addTask"
    />
    <button @click="addTask">Tambah Tugas</button>

    <ul class="task-list">
      <li
        v-for="(task, index) in tasks"
        :key="index"
        :class="{ completed: task.completed }"
      >
        <input type="checkbox" v-model="task.completed" />
        <span>{{ task.text }}</span>
        <button @click="removeTask(index)">Hapus</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
      tasks: [],
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim()) {
        this.tasks.push({ text: this.newTask, completed: false });
        this.newTask = "";
      }
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
.todo-container {
  max-width: 400px;
  margin: 50px auto;
  text-align: center;
}
input[type="text"] {
  padding: 10px;
  width: 70%;
  margin-bottom: 10px;
}
button {
  margin-left: 5px;
}
.task-list {
  list-style: none;
  padding: 0;
}
.task-list li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 5px;
}
.task-list li.completed span {
  text-decoration: line-through;
  color: rgb(245, 0, 0);
}
</style>

