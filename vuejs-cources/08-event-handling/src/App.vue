<script setup>
import { ref } from 'vue';

const count = ref(0);
const sayHi1 = () => {
  alert('Hi 1');
}

const sayHi2 = () => {
  alert('Hi 2');
}
</script>

<template>
  <div>
    <h1>Event handling</h1>
    <button @click="sayHi1">
      <button @click.stop="sayHi2">Say Hi 2</button>
      Say Hi 1
    </button>
  </div>
</template>
