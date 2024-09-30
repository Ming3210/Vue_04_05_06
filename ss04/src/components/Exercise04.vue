<template>
  <div>
    <h2>B4</h2>
    <input v-model="inputValue" placeholder="Nhập giá trị" />
    <p>Giá trị hiện tại: {{ inputValue }}</p>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const inputValue = ref("");

watch(inputValue, (newValue, oldValue) => {
  console.log(`Giá trị đã thay đổi từ "${oldValue}" thành "${newValue}"`);
});
</script>
