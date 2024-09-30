<template>
  <div>
    <h1>B3</h1>
    <div v-if="role == 'admin'">Role Admin</div>
    <div v-else-if="role == 'user'">Role User</div>
    <div v-else>Role Guest</div>
  </div>
</template>

<script setup>
const role = "admin";
</script>

<style></style>
