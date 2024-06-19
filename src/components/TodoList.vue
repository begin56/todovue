<template>
    <div class="todo-list">
      <h1>To-Do List</h1>
      <input v-model="newTodo" placeholder="Enter todo" />
      <button @click="addTodo">+</button>
      <ul>
        <li v-for="(todo, index) in todos" :key="index">
          {{ todo.text }}
          <button @click="deleteTodo(index)" >X</button>
        </li>
      </ul>
    </div>
  </template>
  
<script setup>
import { ref } from 'vue';

const newTodo = ref('');
const todos = ref([]);
  
const addTodo = () => {
if (newTodo.value.trim()) {
    todos.value.push({text:newTodo.value});
    newTodo.value = '';
}
};
  
const deleteTodo = (index) => {
todos.value.splice(index, 1);
};

</script>
  
<style>

.todo-list {
max-width: 400px;
margin: auto;
}

input{
padding: 10px;
}
       
button{
padding: 10px;
margin-left: 5px;
}

ul{
list-style-type:none;
}

li{
padding: 10px;
margin-top: 10px;
border:2px solid black;
display: flex; 
justify-content:space-between;
}   
</style>
     
   
    
  
  