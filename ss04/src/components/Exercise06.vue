<template>
  <div>
    <h2>B6</h2>
    <input type="number" v-model="inputValue" />
    <button @click="addToCart">Add to cart</button>
    <p>Total in cart: {{ totalInCart }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const cartItems = ref([]);
const inputValue = ref(0);

const totalInCart = computed(() => {
  return cartItems.value.reduce((sum, item) => sum + item, 0);
});

const addToCart = () => {
  if (!isNaN(inputValue.value) && inputValue.value > 0) {
    cartItems.value.push(inputValue.value);
    inputValue.value = 0;
  }
};
</script>
