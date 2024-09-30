<template>
  <div class="exercise10">
    <h2>B10</h2>
    <button @click="addRandomNumber">Random number</button>
    <div class="number-list">
      <h3>Danh sách số ngẫu nhiên:</h3>
      [<span v-for="(number, index) in numbers" :key="index"
        >{{ number }}{{ index < numbers.length - 1 ? "," : "" }}</span
      >]
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const numbers = ref([]);

const addRandomNumber = () => {
  const randomNumber = Math.floor(Math.random() * 10) + 1; // Tạo số ngẫu nhiên từ 1 đến 10
  numbers.value.push(randomNumber);
};
</script>

<style></style>
