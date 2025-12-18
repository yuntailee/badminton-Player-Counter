<template>
  <div class="counter">
    <button @click="decrement">-</button>
    <span class="count">{{ count }}</span>
    <button @click="increment">+</button>
  </div>
</template>

<script setup>
defineProps({
  count: {
    type: Number,
    default: 0,
  },
});
const emit = defineEmits(["update:count"]);

const increment = () => {
  emit("update:count", count + 1);
};

const decrement = () => {
  if (count > 0) {
    emit("update:count", count + -1);
  }
};
</script>

<style scoped>
.counter {
  display: flex;
  align-items: center;
  gap: 15px;
}
.counter button {
  width: 40px;
  height: 40px;
  font-size: 20px;
  cursor: pointer;
}
.count {
  font-size: 24px;
  min-width: 50px;
  text-align: center;
}
</style>
