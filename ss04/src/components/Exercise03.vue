<template>
  <div>
    <h2>B3</h2>
    <p>Width: {{ width }}</p>
    <p>Height: {{ height }}</p>
    <p>Area: {{ area }}</p>
    <button @click="increaseWidth">Increase width</button>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const width = ref(10);
const height = ref(20);

const area = computed(() => {
  return width.value * height.value;
});

const increaseWidth = () => {
  width.value += 10;
};
</script>
