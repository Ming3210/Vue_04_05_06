<template>
  <div>
    <h2>B5</h2>
    <ul>
      <li v-for="product in products" :key="product.id">
        {{ product.name }} - Số lượng: {{ product.quantity }}
        <button @click="increaseQuantity(product.id)">Tăng số lượng</button>
      </li>
    </ul>
    <p>Tổng số lượng sản phẩm trong giỏ hàng: {{ totalQuantity }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const products = ref([
  { id: 1, name: "Mèn mén loại 1", quantity: 3 },
  { id: 2, name: "Mèn mén loại 2", quantity: 5 },
  { id: 3, name: "Mèn mén loại 3", quantity: 1 },
]);

const increaseQuantity = (productId) => {
  const product = products.value.find((p) => p.id === productId);
  if (product) {
    product.quantity++;
  }
};

const totalQuantity = computed(() => {
  return products.value.reduce((total, product) => total + product.quantity, 0);
});
</script>
