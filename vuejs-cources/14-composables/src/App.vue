<!-- eslint-disable vue/no-use-v-if-with-v-for -->
<script setup>
import { useCounter } from './composables/useCounter';

const { increment, decrement, count } = useCounter();

</script>
<template>
  <div>
    <h1>Composables</h1>
    \<p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
    <button @click="decrement">Decrement</button>
  </div>
</template>
