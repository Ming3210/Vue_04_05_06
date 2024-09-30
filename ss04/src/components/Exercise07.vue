<template>
  <div>
    <h2>B7</h2>
    <input type="number" v-model="number" placeholder="" />
    <p>Số: {{ number }}</p>
    <p>Bình phương: {{ squaredNumber }}</p>
  </div>
</template>

<script setup>
import { ref, computed, watch } from "vue";

const number = ref(0);

const squaredNumber = computed(() => {
  return number.value * number.value;
});

watch(number, (newValue, oldValue) => {
  console.log(`Number changed from ${oldValue} to ${newValue}`);
});
</script>
