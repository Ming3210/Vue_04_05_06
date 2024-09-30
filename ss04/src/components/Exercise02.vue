<template>
  <div>
    <h2>B2</h2>
    <p>Company: {{ info.company }}</p>
    <p>Age: {{ info.age }}</p>
    <button @click="updateInfo">Update Info</button>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const info = reactive({
  company: "Rikkei",
  age: 1,
});

const updateInfo = () => {
  info.company = "Rekkii";
  info.age = 2;
};
</script>
