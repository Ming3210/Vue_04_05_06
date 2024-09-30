<template>
  <div>
    <h1>B2</h1>
    <button @click="change" v-if="isShow">Hiện</button>
    <button @click="change" v-else>Ẩn</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const change = () => {
  isShow.value = !isShow.value;
};
const isShow = ref(true);
</script>

<style></style>
