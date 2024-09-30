<template>
  <div class="exercise09">
    <h2>B9</h2>
    <div class="gender-display">
      <p>
        Giới tính hiện tại: <strong>{{ currentGender }}</strong>
      </p>
    </div>
    <button @click="randomizeGender">Random gender</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const genders = ["Nam", "Nữ", "Khác"];
const currentGender = ref("Nam");

const randomizeGender = () => {
  const randomIndex = Math.floor(Math.random() * genders.length);
  currentGender.value = genders[randomIndex];
};
</script>

<style scoped></style>
