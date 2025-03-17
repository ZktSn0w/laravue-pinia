<script setup>
import { useCounterStore } from '../stores/counter';
import { storeToRefs } from 'pinia';

const counterStore = useCounterStore();
const { count, doubleCount } = storeToRefs(counterStore);

const increment = () => counterStore.increment();
const decrement = () => counterStore.decrement();
</script>

<template>
  <div class="bg-red-500">
    <h2>Counter: {{ count }}</h2>
    <h3>Double: {{ doubleCount }}</h3>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
  </div>
</template>
