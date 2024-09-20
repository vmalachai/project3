<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
 <div>
  <h1>My To-Do List</h1>
  <input v-model="newTodo" @keyupenter="addTodo" placeholder="Add a new task" />
 <ul>
  <TodoItem
  v-for="(todo, index) in todos"
  :key="index"
  :todo="todo"
  @remove="removeTodo(index)"
  />
 </ul>
 </div>
</template>
<script>


</script>
<style scoped>

</style>
