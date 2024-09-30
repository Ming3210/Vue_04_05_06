<template>
  <div>
    <h1>B6</h1>
    <span :key="index" v-for="(number, index) in arr">
      <span v-if="number % 2 != 0">
        <span v-if="sumOfDigits(number) % 2 == 0">{{ `${number} ` }}</span>
      </span>
    </span>
  </div>
</template>

<script setup>
const arr = [5, 12, 15, 22, 9, 18, 25, 30, 7, 33];

function sumOfDigits(num) {
  return num
    .toString()
    .split("")
    .reduce((sum, digit) => sum + parseInt(digit), 0);
}
</script>

<style></style>
