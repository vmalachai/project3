<script setup>
import { ref } from 'vue';

const newTodo = ref(''); // Holds the value of the input
const todos = ref([]);   // Holds the list of todos

// Method to add a new todo item
const addTodo = () => {
  if (newTodo.value.trim()) { // Check if the input is not empty
    todos.value.push({ text: newTodo.value, completed: false }); // Add new todo
    newTodo.value = ''; // Clear the input field
  }
};

// Method to remove a todo item
const removeTodo = (index) => {
  todos.value.splice(index, 1); // Remove todo at the specified index
};
</script>

<template>
  <div>
   
    <h1>My To-Do List</h1>
    <input
      v-model="newTodo"
      @keyup.enter="addTodo"
      placeholder="Add a new task"
    />
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        <input type="checkbox" v-model="todo.completed" />
        <span :class="{ completed: todo.completed }">{{ todo.text }}</span>
        <button @click="removeTodo(index)">Remove</button>
      </li>
    </ul>
  </div>
</template>


