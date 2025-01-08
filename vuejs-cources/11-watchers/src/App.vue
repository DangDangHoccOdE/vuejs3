<!-- eslint-disable vue/no-use-v-if-with-v-for -->
<script setup>
import { ref, watch } from 'vue';
const question = ref('');
const isLoading = ref(false);
const answer = ref('');
watch(question,async(newQuestion,oldQuestion)=>{
  if(newQuestion.includes('?')){
    isLoading.value = true;
    answer.value = 'Thinking...';
    try{
      const response = await fetch('https://yesno.wtf/api');
      answer.value = (await response.json()).answer;

    }catch(error){
      answer.value = 'Error: ' + error.message;
    }finally{
      isLoading.value = false;
    }
  }
})
</script>

<template>
  <div>
    <h1>Watchers</h1>
    <p>Hỏi 1 câu hỏi có thể trả lời bằng "yes" hoặc "no"</p>
    <input type="text" v-model="question" :disabled="isLoading"/>
    <p>{{ answer }}</p>
  </div>
</template>
