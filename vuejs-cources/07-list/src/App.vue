<script setup>
import { ref } from 'vue';
const newTodo = ref('');
const todos = ref([{
  id: "1",
  text: 'Learn Vue 3',
},
{
  id: "2",
  text: 'Build a todo app',
},]
);

const addTodo = () => {
  if(newTodo.value.trim() === '') return;
  const todo = {
    id: todos.value.length + 1,
    text: newTodo.value,
  }
  todos.value.push(todo);
  newTodo.value = '';
}
</script>

<template>
  <div>
    <input type="text" v-model="newTodo" @keyup.enter="addTodo" />
    <button @click="addTodo">Add Todo</button>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>
