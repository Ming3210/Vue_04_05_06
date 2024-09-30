<template>
  <div>
    <h1>B1</h1>
    <button @click="change">Hiện</button>
    <p v-if="isShow">Rikkei Educaton</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const change = () => {
  isShow.value = !isShow.value;
};
const isShow = ref(false);
</script>

<style></style>
