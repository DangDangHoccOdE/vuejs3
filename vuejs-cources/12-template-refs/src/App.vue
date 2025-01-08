<!-- eslint-disable vue/no-use-v-if-with-v-for -->
<script setup>
import { onMounted, ref } from 'vue';
const inputRef = ref(null);
const list = ['Item 1','Item 2','Item 3'];
const itemRefs = ref([]);

onMounted(()=>{
  inputRef.value.focus();
  itemRefs.value.forEach((itemRef)=>{
    itemRef.style.transition = 'opacity 1s';
    itemRef.style.opacity = 1;
  })
})
</script>

<template>
  <div>
    <h1>Template refs</h1>
    <input ref="inputRef" type="text" v-model="question" :disabled="isLoading"/>

    <ul>
      <li v-for="(item,index) in list" :key="index" ref="itemRefs" style="opacity: 0;">{{ item }}</li>
    </ul>
  </div>
</template>
