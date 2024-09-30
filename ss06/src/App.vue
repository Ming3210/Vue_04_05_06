<template>
  <div class="todo-app">
    <h1>Todo List</h1>

    <div class="input-section">
      <input v-model="newTask" type="text" placeholder="Enter your job" />
      <button @click="addTask">Add Job</button>
    </div>

    <ul>
      <li
        v-for="(task, index) in tasks"
        :key="task.id"
        :class="{ completed: task.status }"
      >
        <input
          type="checkbox"
          v-model="task.status"
          @change="saveTasksToLocalStorage"
        />
        <span>{{ task.name }}</span>
        <button @click="deleteTask(index)">Delete</button>
      </li>
    </ul>

    <p>
      Số công việc hoàn thành: {{ completedTasks }} / {{ tasks.length }} công
      việc
    </p>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from "vue";

const newTask = ref("");
const tasks = ref([]);

const onMounted = () => {
  const savedTasks = localStorage.getItem("tasks");
  if (savedTasks) {
    tasks.value = JSON.parse(savedTasks);
  }
};

onMounted();

const saveTasksToLocalStorage = () => {
  localStorage.setItem("tasks", JSON.stringify(tasks.value));
};

const addTask = () => {
  if (!newTask.value.trim()) {
    alert("Tên công việc không được để trống");
    return;
  }

  const isDuplicate = tasks.value.some((task) => task.name === newTask.value);
  if (isDuplicate) {
    alert("Tên công việc đã tồn tại");
    return;
  }

  tasks.value.push({
    id: Date.now(),
    name: newTask.value,
    status: false,
  });

  newTask.value = "";
  saveTasksToLocalStorage();
};

const deleteTask = (index) => {
  if (confirm("Bạn có chắc chắn muốn xóa công việc này không?")) {
    tasks.value.splice(index, 1);
    saveTasksToLocalStorage();
  }
};

const completedTasks = computed(
  () => tasks.value.filter((task) => task.status).length
);
</script>

<style>
.todo-app {
  max-width: 500px;
  margin: 0 auto;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  background-color: #fff;
}

.input-section {
  display: flex;
  margin-bottom: 20px;
}

input[type="text"] {
  flex: 1;
  padding: 10px;
  border: 2px solid #ddd;
  border-radius: 5px;
  margin-right: 10px;
}

button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

li span {
  flex: 1;
}

li.completed span {
  text-decoration: line-through;
}

button {
  background-color: #ff4d4d;
  margin-left: 10px;
}

button:hover {
  background-color: #d93636;
}
</style>
