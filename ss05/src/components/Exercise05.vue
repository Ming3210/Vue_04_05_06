<template>
  <div>
    <h1>B5</h1>
    <sppan :key="index" v-for="(number, index) in array">
      <span v-if="number % 2 == 0">
        {{ ` ${number} ` }}
      </span>
    </sppan>
  </div>
</template>

<script setup>
const array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11];
</script>

<style></style>
