<template>
  <div class="app">
    <h2>購物車數量</h2>
    <Counter v-model:count="quantity" />
    <p>目前數量：{{ quantity }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Counter from "./components/Counter.vue";

const quantity = ref(1);
</script>
