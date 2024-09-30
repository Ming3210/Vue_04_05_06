<template>
  <div class="exercises11">
    <h2>B11</h2>
    <div class="search-container">
      <input
        v-model="searchKeyword"
        type="text"
        placeholder="Nhập tên cần tìm..."
        @input="filterUsers"
      />
      <button @click="filterUsers">Tìm kiếm</button>
    </div>
    <div class="user-list">
      <h3>Danh sách người dùng:</h3>
      <ul>
        <li v-for="user in filteredUsers" :key="user.id">
          {{ user.name }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const users = [
  { id: 1, name: "Nguyen Van A" },
  { id: 2, name: "Tran Thi B" },
  { id: 3, name: "Le Van C" },
  { id: 4, name: "Pham Thi D" },
  { id: 5, name: "Hoang Van E" },
];

const searchKeyword = ref("");
const filteredUsers = ref(users);

const filterUsers = () => {
  filteredUsers.value = users.filter((user) =>
    user.name.toLowerCase().includes(searchKeyword.value.toLowerCase())
  );
};
</script>

<style></style>
