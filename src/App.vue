<template>
  <div id="app">
    <product-list :products="products" />
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import ProductList from './components/ProductList.vue';

interface Product {
  id: number;
  label: string;
  description: string;
  qte: number;
}

const products = ref<Product[]>([
  { id: 1, label: 'Dragon Ball', description: 'Vegeta', qte: 15 },
  { id: 2, label: 'Naruto Shippuden', description: 'Sasuke', qte: 0 },
  { id: 3, label: 'Solo Leveling', description: 'Sun Hue', qte: 3 },
]);
</script>
