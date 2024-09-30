<template>
  <div>
    <h1>B4</h1>
    <button @click="display">Hiển thị</button>
    <button @click="hide">Ẩn</button>
    <p v-show="show">Thông báo : <b>Welcon to Rikkei Education</b></p>
  </div>
</template>

<script setup>
import { ref } from "vue";

const show = ref(false);
const display = () => {
  show.value = true;
};
const hide = () => {
  show.value = false;
};
</script>

<style></style>
