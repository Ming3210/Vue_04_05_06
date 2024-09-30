<template>
  <div class="exercise08">
    <h2>B8</h2>
    <div class="buttons">
      <button @click="sortAscending">Tăng dần</button>
      <button @click="sortDescending">Giảm dần</button>
    </div>
    <div class="numbers">
      <button v-for="number in numbers" :key="number">{{ number }}</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const numbers = ref([5, 2, 8, 1, 9, 3, 7, 4, 6]);

const sortAscending = () => {
  numbers.value.sort((a, b) => a - b);
};

const sortDescending = () => {
  numbers.value.sort((a, b) => b - a);
};
</script>

<style></style>
