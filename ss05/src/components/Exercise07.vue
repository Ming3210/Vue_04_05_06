<template>
  <div>
    <h1>B7</h1>
    <button
      v-for="index in 3"
      :key="index"
      @click="activeIndex = index"
      :class="{ active: activeIndex === index }"
    >
      Button {{ index }}
    </button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const activeIndex = ref(1);
</script>

<style>
.active {
  background-color: rgb(255, 0, 0);
}
</style>
