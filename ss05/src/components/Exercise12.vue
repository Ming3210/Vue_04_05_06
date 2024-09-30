<template>
  <div>
    <h1>B12</h1>
    <div>
      <button @click="showNotification">Show notification</button>
      <div>
        <div v-if="visible">
          <span>Hiển thị thông báo ở đây</span>
          <button @click="hideNotification">X</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const visible = ref(false);

const showNotification = () => {
  visible.value = true;

  setTimeout(hideNotification, 2000);
};

const hideNotification = () => {
  visible.value = false;
};
</script>

<style></style>
