<template>
  <div>
    <h2>B9</h2>

    <div v-for="article in articles" :key="article.id" class="article-item">
      <h3>Id: {{ article.id }}</h3>
      <h4>Title: {{ article.title }}</h4>
      <p>Content: {{ article.content }}</p>
      <p>Author: {{ article.author }}</p>
      <hr />
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const articles = ref([
  {
    id: 1,
    title: "Tại sao nên học ReactJS",
    content: "Học ReactJS để đi làm",
    author: "David",
  },
  {
    id: 2,
    title: "Props trong ReactJS",
    content: "Props giúp truyền dữ liệu từ component con xuống component cha",
    author: "Linda",
  },
  {
    id: 3,
    title: "State trong ReactJS là gì?",
    content: "State giúp lưu trạng thái dữ liệu bên trong một component",
    author: "David",
  },
]);
</script>

<style scoped></style>
