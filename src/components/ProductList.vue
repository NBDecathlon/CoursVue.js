<template>
  <table border="1">
    <thead>
      <tr>
        <th>ID</th>
        <th>Label</th>
        <th>Description</th>
        <th>Statut</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="product in products" :key="product.id">
        <td>{{ product.id }}</td>
        <td>{{ product.label }}</td>
        <td>{{ product.description }}</td>
        <td>{{ product.qte > 0 ? 'Disponible' : 'Indisponible' }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

interface Product {
  id: number;
  label: string;
  description: string;
  qte: number;
}

export default defineComponent({
  name: 'ProductList',
  props: {
    products: {
      type: Array as PropType<Product[]>,
      required: true,
    },
  },
});
</script>

<style>
table {
  width: 100%;
  border-collapse: collapse;
}

th,
td {
  padding: 8px;
  text-align: left;
}
</style>
